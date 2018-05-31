---
Description: In initializing a VSS restore operation, a requester needs to retrieve the Backup Component Document and each relevant Writer Metadata Document created and saved during the backup operation.
ms.assetid: 0a087125-c9d4-460a-8153-3e2e26633ac2
title: Overview of Restore Initialization
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Overview of Restore Initialization

In initializing a VSS restore operation, a requester needs to retrieve the Backup Component Document and each relevant Writer Metadata Document created and saved during the backup operation. The writer will have its current state queried in handling the [*Identify event*](vssgloss-i.md#base-vssgloss-identify-event) that the requester generates. For more information, see [Overview of Processing a Restore Under VSS](overview-of-processing-a-restore-under-vss.md).

The following table shows the sequence of actions and events that are required to initialize a restore operation.



| Requester action                                                                                                                                                                                                                                                                                                       | Event                                                     | Writer action                                                                                                                                                                                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Create an [**IVssBackupComponents**](/windows/win32/VsBackup/nl-vsbackup-ivssbackupcomponents?branch=master) interface, initialize it to manage a restore, and load stored requester metadata (see [**CreateVssBackupComponents**](/windows/win32/VsBackup/nf-vsbackup-createvssbackupcomponents?branch=master), [**IVssBackupComponents::InitializeForRestore**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-initializeforrestore?branch=master)). | None                                                      | None                                                                                                                                                                                                                                                                                                                      |
| Call [**CreateVssExamineWriterMetadata**](/windows/win32/VsBackup/nf-vsbackup-createvssexaminewritermetadata?branch=master) to create [**IVssExamineWriterMetadata**](/windows/win32/VsBackup/nl-vsbackup-ivssexaminewritermetadata?branch=master) interfaces and load them with stored writer metadata.                                                                                                           | None                                                      | None                                                                                                                                                                                                                                                                                                                      |
| Initiate asynchronous contact with writers (see [**IVssBackupComponents::GatherWriterMetadata**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-gatherwritermetadata?branch=master).)                                                                                                                                                                      | [*Identify*](vssgloss-i.md#base-vssgloss-identify-event) | The writer begins event handling in support of the restore. Creates the Writer Metadata Document (see [Working with the Writer Metadata Document](working-with-the-writer-metadata-document.md), [**CVssWriter::OnIdentify**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onidentify?branch=master), [**IVssCreateWriterMetadata**](/windows/win32/VsWriter/nl-vswriter-ivsscreatewritermetadata?branch=master)). |
| The requester waits for writers to initialize by calling [**IVssAsync**](/windows/win32/Vss/nn-vss-ivssasync?branch=master).                                                                                                                                                                                                                               | None                                                      | None                                                                                                                                                                                                                                                                                                                      |



 

## Requester Actions during Restore Initialization

During the initialization phase of a restore, the requester needs to have access to the stored Backup Components Document and all the Writer Metadata Documents.

Depending on the implementation, this will mean either that the requester will require that backup media be mounted and readable, or that some other mechanism for accessing the stored metadata be available.

The requester uses the stored XML document containing the Backup Components Document of the requester that performed the backup to initialize its Backup Components Document using [**IVssBackupComponents::InitializeForRestore**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-initializeforrestore?branch=master) can access the information.

As was the case during the backup, the Backup Components Document has insufficient information to support a restore; therefore, the requester needs access to those Writer Metadata Documents stored during backup (see [Use of Components by the Requester](use-of-components-by-the-requestor.md)).

The requester retrieves the stored writer metadata by calling [**CreateVssExamineWriterMetadata**](/windows/win32/VsBackup/nf-vsbackup-createvssexaminewritermetadata?branch=master) for each writer whose data was backed up and now is to be restored. This function creates an [**IVssExamineWriterMetadata**](/windows/win32/VsBackup/nl-vsbackup-ivssexaminewritermetadata?branch=master) object for each writer and loads the writer's Writer Metadata Document into the object.

As was the case during the backup, to initiate cooperation between itself and the system's writers, a requester must generate an [*Identify*](vssgloss-i.md#base-vssgloss-identify-event) event by calling [**IVssBackupComponents::GatherWriterMetadata**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-gatherwritermetadata?branch=master). It is not necessary to call [**IVssBackupComponents::GatherWriterStatus**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-gatherwriterstatus?branch=master) following the completion of [**GatherWriterMetadata**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-gatherwritermetadata?branch=master). Writers that fail to process the [*Identify*](vssgloss-i.md#base-vssgloss-identify-event) event will not be included in the list of writers providing the metadata to be returned by [**IVssBackupComponents::GetWriterMetadataCount**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-getwritermetadatacount?branch=master) and [**IVssBackupComponents::GetWriterMetadata**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-getwritermetadata?branch=master) (see [Determining Writer Status](determining-writer-status.md)).

As with the backup operation, a requester will need to query and parse the information in the Backup Components Document and compare it to data in the Writer Metadata Documents to determine which components were backed up and to choose those to be restored (see [Overview of Preparing for Restore](overview-of-preparing-for-restore.md)). In addition, the requester will need to generate a detailed list containing information about the files on the backup media selected for restore, as well as how and where they are to be restored. (See [Generating a Restore Set](generating-a-restore-set.md).)

Therefore, some backup applications may find it useful to have stored on the backup media their own list (in their own optimized format) of the files and their associated writer, component, restore procedure, and location information. This list can be used to minimize the amount of parsing and comparing of Writer Metadata Documents and the Backup Component Documents required to support a restore.

## Writer Actions during Restore Initialization

Just as is done during a restore operation, in response to the Identify event, VSS calls each writer's virtual handler method [**CVssWriter::OnIdentify**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onidentify?branch=master).

Note that applications other than the current requester (for instance, system applications) can generate Identify events, which must be handled by the writer. In addition, there is no way for a writer to determine from within [**CVssWriter::OnIdentify**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onidentify?branch=master) which application has generated the Identify event.

Given that a writer may receive several Identify events while processing a restore operation, writers should never set state information in the [**CVssWriter::OnIdentify**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onidentify?branch=master) handler. Instead, they must use the same algorithm for creating their Writer Metadata Document as was done during backup operations (see [Writer Actions during Backup Initialization](overview-of-backup-initialization.md#writer-actions-during-backup-initialization) for more information).

 

 


