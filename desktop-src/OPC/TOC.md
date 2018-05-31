# [Packaging](packaging.md)
## [Packaging API Programming Guide](packaging-programming-guide.md)
### [Getting Started with the Packaging API](packaging-api-overview.md)
### [Open Packaging Conventions Fundamentals](open-packaging-conventions-overview.md)
### [Packages Fundamentals](packages.md)
#### [Packages Overview](packages-overview.md)
#### [Packages How-To Topics](packages-how-to-topics.md)
##### [How to Load a Package for Reading](loading-a-package.md)
##### [How to Save a Package](saving-a-package.md)
##### [How to Write a Package](writing-a-package.md)
### [Parts Fundamentals](parts.md)
#### [Parts Overview](parts-overview.md)
#### [Parts How-To Topics](parts-how-to-topics.md)
##### [Finding the Core Properties Part](finding-the-core-properties-part.md)
##### [Modifying Part Content](modifying-part-content.md)
##### [Resolving a Part Name from a Target URI](resolving-a-part-name-from-a-relationship-s-target-uri.md)
### [Relationships Fundamentals](relationships.md)
#### [Relationships Overview](relationships-overview.md)
### [Digital Signatures Fundamentals](digital-signatures.md)
#### [Digital Signatures Overview](digital-signatures-overview.md)
#### [Digital Signatures How-To Topics](digital-signatures-how-to-topics.md)
##### [Validating a Package Signature](validating-a-package-signature.md)
### [Differences between the Native and Managed APIs](differences-between-the-native-and-managed-apis.md)
## [Packaging API Reference](packaging-programming-reference.md)
### [Packaging Interfaces](packaging-interfaces.md)
#### [Core Packaging Interfaces](core-packaging-interfaces.md)
##### [IOpcFactory](/windows/previous-versions/msopc/nn-msopc-iopcfactory?branch=master)
###### [CreateDigitalSignatureManager](/windows/previous-versions/msopc/nf-msopc-iopcfactory-createdigitalsignaturemanager?branch=master)
###### [CreatePackage](/windows/previous-versions/msopc/nf-msopc-iopcfactory-createpackage?branch=master)
###### [CreatePackageRootUri](/windows/previous-versions/msopc/nf-msopc-iopcfactory-createpackagerooturi?branch=master)
###### [CreatePartUri](/windows/previous-versions/msopc/nf-msopc-iopcfactory-createparturi?branch=master)
###### [CreateStreamOnFile](/windows/previous-versions/msopc/nf-msopc-iopcfactory-createstreamonfile?branch=master)
###### [ReadPackageFromStream](/windows/previous-versions/msopc/nf-msopc-iopcfactory-readpackagefromstream?branch=master)
###### [WritePackageToStream](/windows/previous-versions/msopc/nf-msopc-iopcfactory-writepackagetostream?branch=master)
##### [IOpcPackage](/windows/previous-versions/msopc/nn-msopc-iopcpackage?branch=master)
###### [GetPartSet](/windows/previous-versions/msopc/nf-msopc-iopcpackage-getpartset?branch=master)
###### [GetRelationshipSet](/windows/previous-versions/msopc/nf-msopc-iopcpackage-getrelationshipset?branch=master)
##### [IOpcPart](/windows/previous-versions/msopc/nn-msopc-iopcpart?branch=master)
###### [GetCompressionOptions](/windows/previous-versions/msopc/nf-msopc-iopcpart-getcompressionoptions?branch=master)
###### [GetContentStream](/windows/previous-versions/msopc/nf-msopc-iopcpart-getcontentstream?branch=master)
###### [GetContentType](/windows/previous-versions/msopc/nf-msopc-iopcpart-getcontenttype?branch=master)
###### [GetName](/windows/previous-versions/msopc/nf-msopc-iopcpart-getname?branch=master)
###### [GetRelationshipSet](/windows/previous-versions/msopc/nf-msopc-iopcpart-getrelationshipset?branch=master)
##### [IOpcPartEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcpartenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcpartenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcpartenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcpartenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcpartenumerator-moveprevious?branch=master)
##### [IOpcPartSet](/windows/previous-versions/msopc/nn-msopc-iopcpartset?branch=master)
###### [CreatePart](/windows/previous-versions/msopc/nf-msopc-iopcpartset-createpart?branch=master)
###### [DeletePart](/windows/previous-versions/msopc/nf-msopc-iopcpartset-deletepart?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcpartset-getenumerator?branch=master)
###### [GetPart](/windows/previous-versions/msopc/nf-msopc-iopcpartset-getpart?branch=master)
###### [PartExists](/windows/previous-versions/msopc/nf-msopc-iopcpartset-partexists?branch=master)
##### [IOpcPartUri](/windows/previous-versions/msopc/nn-msopc-iopcparturi?branch=master)
###### [ComparePartUri](/windows/previous-versions/msopc/nf-msopc-iopcparturi-compareparturi?branch=master)
###### [GetSourceUri](/windows/previous-versions/msopc/nf-msopc-iopcparturi-getsourceuri?branch=master)
###### [IsRelationshipsPartUri](/windows/previous-versions/msopc/nf-msopc-iopcparturi-isrelationshipsparturi?branch=master)
##### [IOpcRelationshipEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcrelationshipenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipenumerator-moveprevious?branch=master)
##### [IOpcRelationship](/windows/previous-versions/msopc/nn-msopc-iopcrelationship?branch=master)
###### [GetId](/windows/previous-versions/msopc/nf-msopc-iopcrelationship-getid?branch=master)
###### [GetRelationshipType](/windows/previous-versions/msopc/nf-msopc-iopcrelationship-getrelationshiptype?branch=master)
###### [GetSourceUri](/windows/previous-versions/msopc/nf-msopc-iopcrelationship-getsourceuri?branch=master)
###### [GetTargetMode](/windows/previous-versions/msopc/nf-msopc-iopcrelationship-gettargetmode?branch=master)
###### [GetTargetUri](/windows/previous-versions/msopc/nf-msopc-iopcrelationship-gettargeturi?branch=master)
##### [IOpcRelationshipSet](/windows/previous-versions/msopc/nn-msopc-iopcrelationshipset?branch=master)
###### [CreateRelationship](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipset-createrelationship?branch=master)
###### [DeleteRelationship](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipset-deleterelationship?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipset-getenumerator?branch=master)
###### [GetEnumeratorForType](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipset-getenumeratorfortype?branch=master)
###### [GetRelationship](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipset-getrelationship?branch=master)
###### [GetRelationshipsContentStream](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipset-getrelationshipscontentstream?branch=master)
###### [RelationshipExists](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipset-relationshipexists?branch=master)
##### [IOpcUri](/windows/previous-versions/msopc/nn-msopc-iopcuri?branch=master)
###### [CombinePartUri](/windows/previous-versions/msopc/nf-msopc-iopcuri-combineparturi?branch=master)
###### [GetRelationshipsPartUri](/windows/previous-versions/msopc/nf-msopc-iopcuri-getrelationshipsparturi?branch=master)
###### [GetRelativeUri](/windows/previous-versions/msopc/nf-msopc-iopcuri-getrelativeuri?branch=master)
#### [Packaging Digital Signature Interfaces](packaging-digital-signature-interfaces.md)
##### [IOpcCertificateEnumerator Interface](/windows/previous-versions/msopc/nn-msopc-iopccertificateenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopccertificateenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopccertificateenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopccertificateenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopccertificateenumerator-moveprevious?branch=master)
##### [IOpcCertificateSet](/windows/previous-versions/msopc/nn-msopc-iopccertificateset?branch=master)
###### [Add](/windows/previous-versions/msopc/nf-msopc-iopccertificateset-add?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopccertificateset-getenumerator?branch=master)
###### [Remove](/windows/previous-versions/msopc/nf-msopc-iopccertificateset-remove?branch=master)
##### [IOpcDigitalSignature](/windows/previous-versions/msopc/nn-msopc-iopcdigitalsignature?branch=master)
###### [GetCanonicalizationMethod](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getcanonicalizationmethod?branch=master)
###### [GetCertificateEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getcertificateenumerator?branch=master)
###### [GetCustomObjectEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getcustomobjectenumerator?branch=master)
###### [GetCustomReferenceEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getcustomreferenceenumerator?branch=master)
###### [GetNamespaces](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getnamespaces?branch=master)
###### [GetPackageObjectReference](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getpackageobjectreference?branch=master)
###### [GetSignatureId](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsignatureid?branch=master)
###### [GetSignatureMethod](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsignaturemethod?branch=master)
###### [GetSignaturePartName](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsignaturepartname?branch=master)
###### [GetSignaturePartReferenceEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsignaturepartreferenceenumerator?branch=master)
###### [GetSignatureRelationshipReferenceEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsignaturerelationshipreferenceenumerator?branch=master)
###### [GetSignatureValue](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsignaturevalue?branch=master)
###### [GetSignatureXml](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsignaturexml?branch=master)
###### [GetSigningTime](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-getsigningtime?branch=master)
###### [GetTimeFormat](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignature-gettimeformat?branch=master)
##### [IOpcDigitalSignatureEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcdigitalsignatureenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignatureenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignatureenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignatureenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignatureenumerator-moveprevious?branch=master)
##### [IOpcDigitalSignatureManager](/windows/previous-versions/msopc/nn-msopc-iopcdigitalsignaturemanager?branch=master)
###### [CreateSigningOptions](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-createsigningoptions?branch=master)
###### [GetSignatureEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-getsignatureenumerator?branch=master)
###### [GetSignatureOriginPartName](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-getsignatureoriginpartname?branch=master)
###### [RemoveSignature](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-removesignature?branch=master)
###### [ReplaceSignatureXml](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-replacesignaturexml?branch=master)
###### [SetSignatureOriginPartName](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-setsignatureoriginpartname?branch=master)
###### [Sign](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-sign?branch=master)
###### [Validate](/windows/previous-versions/msopc/nf-msopc-iopcdigitalsignaturemanager-validate?branch=master)
##### [IOpcRelationshipSelector](/windows/previous-versions/msopc/nn-msopc-iopcrelationshipselector?branch=master)
###### [GetSelectionCriterion](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselector-getselectioncriterion?branch=master)
###### [GetSelectorType](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselector-getselectortype?branch=master)
##### [IOpcRelationshipSelectorEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcrelationshipselectorenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselectorenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselectorenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselectorenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselectorenumerator-moveprevious?branch=master)
##### [IOpcRelationshipSelectorSet](/windows/previous-versions/msopc/nn-msopc-iopcrelationshipselectorset?branch=master)
###### [Create](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselectorset-create?branch=master)
###### [Delete](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselectorset-delete?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcrelationshipselectorset-getenumerator?branch=master)
##### [IOpcSignatureCustomObject](/windows/previous-versions/msopc/nn-msopc-iopcsignaturecustomobject?branch=master)
###### [GetXml](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobject-getxml?branch=master)
##### [IOpcSignatureCustomObjectEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcsignaturecustomobjectenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobjectenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobjectenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobjectenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobjectenumerator-moveprevious?branch=master)
##### [IOpcSignatureCustomObjectSet](/windows/previous-versions/msopc/nn-msopc-iopcsignaturecustomobjectset?branch=master)
###### [Create](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobjectset-create?branch=master)
###### [Delete](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobjectset-delete?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcsignaturecustomobjectset-getenumerator?branch=master)
##### [IOpcSignaturePartReference](/windows/previous-versions/msopc/nn-msopc-iopcsignaturepartreference?branch=master)
###### [GetContentType](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreference-getcontenttype?branch=master)
###### [GetDigestMethod](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreference-getdigestmethod?branch=master)
###### [GetDigestValue](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreference-getdigestvalue?branch=master)
###### [GetPartName](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreference-getpartname?branch=master)
###### [GetTransformMethod](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreference-gettransformmethod?branch=master)
##### [IOpcSignaturePartReferenceEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcsignaturepartreferenceenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreferenceenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreferenceenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreferenceenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreferenceenumerator-moveprevious?branch=master)
##### [IOpcSignaturePartReferenceSet](/windows/previous-versions/msopc/nn-msopc-iopcsignaturepartreferenceset?branch=master)
###### [Create](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreferenceset-create?branch=master)
###### [Delete](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreferenceset-delete?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcsignaturepartreferenceset-getenumerator?branch=master)
##### [IOpcSignatureReference](/windows/previous-versions/msopc/nn-msopc-iopcsignaturereference?branch=master)
###### [GetDigestMethod](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereference-getdigestmethod?branch=master)
###### [GetDigestValue](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereference-getdigestvalue?branch=master)
###### [GetId](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereference-getid?branch=master)
###### [GetTransformMethod](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereference-gettransformmethod?branch=master)
###### [GetType](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereference-gettype?branch=master)
###### [GetUri](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereference-geturi?branch=master)
##### [IOpcSignatureReferenceEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcsignaturereferenceenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereferenceenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereferenceenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereferenceenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereferenceenumerator-moveprevious?branch=master)
##### [IOpcSignatureReferenceSet](/windows/previous-versions/msopc/nn-msopc-iopcsignaturereferenceset?branch=master)
###### [Create](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereferenceset-create?branch=master)
###### [Delete](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereferenceset-delete?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcsignaturereferenceset-getenumerator?branch=master)
##### [IOpcSignatureRelationshipReference](/windows/previous-versions/msopc/nn-msopc-iopcsignaturerelationshipreference?branch=master)
###### [GetDigestMethod](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreference-getdigestmethod?branch=master)
###### [GetDigestValue](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreference-getdigestvalue?branch=master)
###### [GetRelationshipSelectorEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreference-getrelationshipselectorenumerator?branch=master)
###### [GetRelationshipSigningOption](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreference-getrelationshipsigningoption?branch=master)
###### [GetSourceUri](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreference-getsourceuri?branch=master)
###### [GetTransformMethod](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreference-gettransformmethod?branch=master)
##### [IOpcSignatureRelationshipReferenceEnumerator](/windows/previous-versions/msopc/nn-msopc-iopcsignaturerelationshipreferenceenumerator?branch=master)
###### [Clone](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceenumerator-clone?branch=master)
###### [GetCurrent](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceenumerator-getcurrent?branch=master)
###### [MoveNext](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceenumerator-movenext?branch=master)
###### [MovePrevious](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceenumerator-moveprevious?branch=master)
##### [IOpcSignatureRelationshipReferenceSet](/windows/previous-versions/msopc/nn-msopc-iopcsignaturerelationshipreferenceset?branch=master)
###### [Create](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceset-create?branch=master)
###### [CreateRelationshipSelectorSet](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceset-createrelationshipselectorset?branch=master)
###### [Delete](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceset-delete?branch=master)
###### [GetEnumerator](/windows/previous-versions/msopc/nf-msopc-iopcsignaturerelationshipreferenceset-getenumerator?branch=master)
##### [IOpcSigningOptions](/windows/previous-versions/msopc/nn-msopc-iopcsigningoptions?branch=master)
###### [GetCertificateEmbeddingOption](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getcertificateembeddingoption?branch=master)
###### [GetCertificateSet](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getcertificateset?branch=master)
###### [GetCustomObjectSet](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getcustomobjectset?branch=master)
###### [GetCustomReferenceSet](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getcustomreferenceset?branch=master)
###### [GetDefaultDigestMethod](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getdefaultdigestmethod?branch=master)
###### [GetSignatureId](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getsignatureid?branch=master)
###### [GetSignatureMethod](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getsignaturemethod?branch=master)
###### [GetSignaturePartName](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getsignaturepartname?branch=master)
###### [GetSignaturePartReferenceSet](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getsignaturepartreferenceset?branch=master)
###### [GetSignatureRelationshipReferenceSet](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-getsignaturerelationshipreferenceset?branch=master)
###### [GetTimeFormat](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-gettimeformat?branch=master)
###### [SetCertificateEmbeddingOption](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-setcertificateembeddingoption?branch=master)
###### [SetDefaultDigestMethod](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-setdefaultdigestmethod?branch=master)
###### [SetSignatureId](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-setsignatureid?branch=master)
###### [SetSignatureMethod](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-setsignaturemethod?branch=master)
###### [SetSignaturePartName](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-setsignaturepartname?branch=master)
###### [SetTimeFormat](/windows/previous-versions/msopc/nf-msopc-iopcsigningoptions-settimeformat?branch=master)
### [Packaging Enumerations](packaging-enumerations.md)
#### [OPC_CANONICALIZATION_METHOD](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0001_0076_0001?branch=master)
#### [OPC_CERTIFICATE_EMBEDDING_OPTION](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0001_0076_0004?branch=master)
#### [OPC_COMPRESSION_OPTIONS](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0000_0002_0002?branch=master)
#### [OPC_READ_FLAGS](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0000_0002_0004?branch=master)
#### [OPC_RELATIONSHIP_SELECTOR](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0001_0076_0002?branch=master)
#### [OPC_RELATIONSHIPS_SIGNING_OPTION](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0001_0076_0003?branch=master)
#### [OPC_SIGNATURE_TIME_FORMAT](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0001_0076_0005?branch=master)
#### [OPC_SIGNATURE_VALIDATION_RESULT](/windows/previous-versions/msopc/ne-msopc-opc_signature_validation_result?branch=master)
#### [OPC_STREAM_IO_MODE](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0000_0002_0003?branch=master)
#### [OPC_URI_TARGET_MODE](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0000_0002_0001?branch=master)
#### [OPC_WRITE_FLAGS](/windows/previous-versions/msopc/ne-msopc-__midl___midl_itf_msopc_0000_0002_0005?branch=master)
### [Packaging Errors](packaging-errors.md)
#### [Package Consumption Error Group](package-consumption-error-group.md)
#### [Part URI Error Group](part-uri-error-group.md)
## [Packaging API Samples](packaging-programming-samples.md)
### [Set Author Sample](set-author-sample.md)
#### [setauthor.cpp](setauthor-cpp.md)
#### [wordlib.h](wordlib-h.md)
#### [wordlib.cpp](wordlib-cpp.md)
#### [opclib.h](opclib-h.md)
#### [opclib.cpp](opclib-cpp.md)
#### [util.h](setauthor-util-h.md)
### [Music Bundle Sample](music-bundle-sample.md)
#### [musicbundle.h](musicbundle-h.md)
#### [musicbundle.cpp](musicbundle-cpp.md)
#### [MusicBundleProduction.cpp](musicbundleproduction-cpp.md)
#### [MusicBundleConsumption.cpp](musicbundleconsumption-cpp.md)
#### [util.h](musicbundle-util-h.md)
#### [util.cpp](musicbundle-util-cpp.md)
### [Music Bundle Signature Sample](music-bundle-signature-sample.md)
#### [sign.h](sign-h.md)
#### [sign.cpp](sign-cpp.md)
#### [validate.h](validate-h.md)
#### [validate.cpp](validate-cpp.md)
#### [util.h](musicbundlesignature-util-h.md)
#### [util.cpp](musicbundlesignature-util-cpp.md)
## [Packaging API Glossary](packaging-glossary.md)
