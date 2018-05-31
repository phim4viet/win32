# [Active Directory Rights Management Services Scripting API](adrms-script-portal.md)
## [About the Active Directory Rights Management Services Scripting API](about-the-active-directory-rights-management-services-scripting-api.md)
### [Administration Overview](administration-overview.md)
### [Administration Architecture](administration-architecture.md)
### [AD RMS Scripting API Architecture](ad-rms-scripting-api-architecture.md)
#### [ConfigurationManager Architectural Illustration](configurationmanager-architectural-illustration.md)
#### [Enterprise Architectural Illustration](enterprise-architectural-illustration.md)
### [Installing the AD RMS Scripting API](installing-the-ad-rms-scripting-api.md)
## [Active Directory Rights Management Services Scripting API Reference](active-directory-rights-management-services-scripting-api-reference.md)
### [ADFederationService](adfederationservice-object.md)
#### [ADFederationService.Enabled](adfederationservice-enabled-property.md)
#### [ADFederationService.IsProxyEmailAddressesAllowed](adfederationservice-isproxyemailaddressesallowed-property.md)
#### [ADFederationService.IsSupported](adfederationservice-issupported-property.md)
#### [ADFederationService.RightsAccountCertificateRequestUrl](adfederationservice-rightsaccountcertificaterequesturl-property.md)
#### [ADFederationService.ValidityPeriodInDays](adfederationservice-validityperiodindays-property.md)
### [ApplicationSpecificDataItem](applicationspecificdataitem-object.md)
#### [ApplicationSpecificDataItem.Name](applicationspecificdataitem-name-property.md)
#### [ApplicationSpecificDataItem.Value](applicationspecificdataitem-value-property.md)
### [ApplicationSpecificDataItemCollection](applicationspecificdataitemcollection-object.md)
### [AuditReport](auditreport-object.md)
#### [AuditReport.CertifiedDomainUserAccountCount](auditreport-certifieddomainuseraccountcount-property.md)
#### [AuditReport.CertifiedFederatedIdentityCount](auditreport-certifiedfederatedidentitycount-property.md)
#### [AuditReport.Enabled](auditreport-enabled-property.md)
#### [AuditReport.ExportReportDefinitionLang](auditreport-exportreportdefinitionlang-method.md)
#### [AuditReport.ExportRequestTypeAverageDuration](auditreport-exportrequesttypeaverageduration-method.md)
#### [AuditReport.ExportRequestTypeDomainSummary](auditreport-exportrequesttypedomainsummary-method.md)
#### [AuditReport.ExportRequestTypeDomainUserSummary](auditreport-exportrequesttypedomainusersummary-method.md)
#### [AuditReport.ExportRequestTypeSummary](auditreport-exportrequesttypesummary-method.md)
#### [AuditReport.ExportUserRequestSummary](auditreport-exportuserrequestsummary-method.md)
#### [AuditReport.ExportUserRequestTypeList](auditreport-exportuserrequesttypelist-method.md)
#### [AuditReport.LoggingSystemInformation](auditreport-loggingsysteminformation-property.md)
### [ClusterInformation](clusterinformation-object.md)
#### [ClusterInformation.AdminContactEmail](clusterinformation-admincontactemail-property.md)
#### [ClusterInformation.ClusterType](clusterinformation-clustertype-property.md)
#### [ClusterInformation.IsDecommissioned](clusterinformation-isdecommissioned-property.md)
#### [ClusterInformation.Servers](clusterinformation-servers-property.md)
#### [ClusterInformation.Urls](clusterinformation-urls-property.md)
### [ConfigurationManager](configurationmanager-object.md)
#### [ConfigurationManager.AuditReport](configurationmanager-auditreport-property.md)
#### [ConfigurationManager.ClusterInformation](configurationmanager-clusterinformation-property.md)
#### [ConfigurationManager.Constants](configurationmanager-constants-property.md)
#### [ConfigurationManager.Enterprise](configurationmanager-enterprise-property.md)
#### [ConfigurationManager.Initialize](configurationmanager-initialize-method.md)
#### [ConfigurationManager.IsInRoles](configurationmanager-isinroles-method.md)
#### [ConfigurationManager.IsServerOnLocalMachine](configurationmanager-isserveronlocalmachine-property.md)
#### [ConfigurationManager.RightsTemplatePolicy](configurationmanager-rightstemplatepolicy-property.md)
#### [ConfigurationManager.Roles](configurationmanager-roles-property.md)
#### [ConfigurationManager.ServiceIdentity](configurationmanager-serviceidentity-property.md)
### [Constants](constants-object.md)
#### [Constants.ClusterTypeCertification](constants-clustertypecertification-property.md)
#### [Constants.ClusterTypeLicensing](constants-clustertypelicensing-property.md)
#### [Constants.ExcludedDomainUserType](constants-excludeddomainusertype-property.md)
#### [Constants.ExcludedExternalUserType](constants-excludedexternalusertype-property.md)
#### [Constants.ExcludedFederationUserType](constants-excludedfederationusertype-property.md)
#### [Constants.KeyHierarchyOther](constants-keyhierarchyother-property.md)
#### [Constants.KeyHierarchyPreproduction](constants-keyhierarchypreproduction-property.md)
#### [Constants.KeyHierarchyProduction](constants-keyhierarchyproduction-property.md)
#### [Constants.ProxySchemeBasic](constants-proxyschemebasic-property.md)
#### [Constants.ProxySchemeDigest](constants-proxyschemedigest-property.md)
#### [Constants.ProxySchemeWindowsIntegrated](constants-proxyschemewindowsintegrated-property.md)
#### [Constants.RoleAdministrator](constants-roleadministrator-property.md)
#### [Constants.RoleAuditor](constants-roleauditor-property.md)
#### [Constants.RoleTemplateEditor](constants-roletemplateeditor-property.md)
#### [Constants.TemplateExpirationTypeNever](constants-templateexpirationtypenever-property.md)
#### [Constants.TemplateExpirationTypeOnDate](constants-templateexpirationtypeondate-property.md)
#### [Constants.TemplateExpirationTypeUntilDays](constants-templateexpirationtypeuntildays-property.md)
#### [Constants.TemplateRightAllowMacros](constants-templaterightallowmacros-property.md)
#### [Constants.TemplateRightEdit](constants-templaterightedit-property.md)
#### [Constants.TemplateRightExport](constants-templaterightexport-property.md)
#### [Constants.TemplateRightExtract](constants-templaterightextract-property.md)
#### [Constants.TemplateRightForward](constants-templaterightforward-property.md)
#### [Constants.TemplateRightFullControl](constants-templaterightfullcontrol-property.md)
#### [Constants.TemplateRightPrint](constants-templaterightprint-property.md)
#### [Constants.TemplateRightReply](constants-templaterightreply-property.md)
#### [Constants.TemplateRightReplyAll](constants-templaterightreplyall-property.md)
#### [Constants.TemplateRightSave](constants-templaterightsave-property.md)
#### [Constants.TemplateRightView](constants-templaterightview-property.md)
#### [Constants.TemplateRightViewRights](constants-templaterightviewrights-property.md)
### [DatabaseInformation](databaseinformation-object.md)
#### [DatabaseInformation.DBName](databaseinformation-dbname-property.md)
#### [DatabaseInformation.Server](databaseinformation-server-property.md)
### [Enterprise](enterprise-object.md)
#### [Enterprise.EnterpriseDatabase](enterprise-enterprisedatabase-property.md)
#### [Enterprise.ExclusionPolicy](enterprise-exclusionpolicy-property.md)
#### [Enterprise.IssuancePolicy](enterprise-issuancepolicy-property.md)
#### [Enterprise.ProxySettings](enterprise-proxysettings-property.md)
#### [Enterprise.ResetServiceKeyPassword](enterprise-resetservicekeypassword-method.md)
#### [Enterprise.SecurityPolicy](enterprise-securitypolicy-property.md)
#### [Enterprise.ServerLicensorCertificate](enterprise-serverlicensorcertificate-property.md)
#### [Enterprise.ServiceConnectionPoint](enterprise-serviceconnectionpoint-property.md)
#### [Enterprise.ServicePrivateKeyProtectionInformation](enterprise-serviceprivatekeyprotectioninformation-property.md)
#### [Enterprise.TrustPolicy](enterprise-trustpolicy-property.md)
#### [Enterprise.UpdateAdminContactEmail](enterprise-updateadmincontactemail-method.md)
#### [Enterprise.UpdateExtranetCertificationClusterUrl](enterprise-updateextranetcertificationclusterurl-method.md)
#### [Enterprise.UpdateExtranetLicensingClusterUrl](enterprise-updateextranetlicensingclusterurl-method.md)
#### [Enterprise.UpdateIntranetLicensingClusterUrl](enterprise-updateintranetlicensingclusterurl-method.md)
### [EnterpriseDatabase](enterprisedatabase-object.md)
#### [EnterpriseDatabase.Configuration](enterprisedatabase-configuration-property.md)
#### [EnterpriseDatabase.DirectoryServices](enterprisedatabase-directoryservices-property.md)
### [EnterpriseUrls](enterpriseurls-object.md)
#### [EnterpriseUrls.Certification](enterpriseurls-certification-property.md)
#### [EnterpriseUrls.Licensing](enterpriseurls-licensing-property.md)
### [ExcludedApplication](excludedapplication-object.md)
#### [ExcludedApplication.AppName](excludedapplication-appname-property.md)
#### [ExcludedApplication.MaximumVersion](excludedapplication-maximumversion-property.md)
#### [ExcludedApplication.MinimumVersion](excludedapplication-minimumversion-property.md)
### [ExcludedApplicationCollection](excludedapplicationcollection-object.md)
#### [ExcludedApplicationCollection.Enabled](excludedapplicationcollection-enabled-property.md)
#### [ExcludedApplicationCollection.Refresh](excludedapplicationcollection-refresh-method.md)
### [ExcludedLockbox](excludedlockbox-object.md)
#### [ExcludedLockbox.Enabled](excludedlockbox-enabled-property.md)
#### [ExcludedLockbox.LockboxMinimumVersion](excludedlockbox-lockboxminimumversion-property.md)
### [ExcludedUserAccount](excludeduseraccount-object.md)
#### [ExcludedUserAccount.Date](excludeduseraccount-date-property.md)
#### [ExcludedUserAccount.PublicKey](excludeduseraccount-publickey-property.md)
#### [ExcludedUserAccount.UserId](excludeduseraccount-userid-property.md)
#### [ExcludedUserAccount.UserType](excludeduseraccount-usertype-property.md)
### [ExcludedUserAccountCollection](excludeduseraccountcollection-object.md)
#### [ExcludedUserAccountCollection.Enabled](excludeduseraccountcollection-enabled-property.md)
#### [ExcludedUserAccountCollection.Refresh](excludeduseraccountcollection-refresh-method.md)
### [ExclusionPolicy](exclusionpolicy-object.md)
#### [ExclusionPolicy.Applications](exclusionpolicy-applications-property.md)
#### [ExclusionPolicy.DisableLegacyWindowsVersions](exclusionpolicy-disablelegacywindowsversions-property.md)
#### [ExclusionPolicy.Lockbox](exclusionpolicy-lockbox-property.md)
#### [ExclusionPolicy.UserAccounts](exclusionpolicy-useraccounts-property.md)
### [ExpirationCondition](expirationcondition-object.md)
#### [ExpirationCondition.ExpirationData](expirationcondition-expirationdata-property.md)
#### [ExpirationCondition.RenewalDays](expirationcondition-renewaldays-property.md)
### [ExpirationData](expirationdata-object.md)
#### [ExpirationData.ExpirationType](expirationdata-expirationtype-property.md)
#### [ExpirationData.Value](expirationdata-value-property.md)
### [ExtendedCondition](extendedcondition-object.md)
#### [ExtendedCondition.EnableOnetimeLicense](extendedcondition-enableonetimelicense-property.md)
#### [ExtendedCondition.EnableViewInTrustedBrowser](extendedcondition-enableviewintrustedbrowser-property.md)
### [IssuancePolicy](issuancepolicy-object.md)
#### [IssuancePolicy.StandardCertificateValidityPeriodInDays](issuancepolicy-standardcertificatevalidityperiodindays-property.md)
#### [IssuancePolicy.TemporaryCertificateValidityPeriodInMinutes](issuancepolicy-temporarycertificatevalidityperiodinminutes-property.md)
### [LoggingSystemInformation](loggingsysteminformation-object.md)
#### [LoggingSystemInformation.DatabaseInformation](loggingsysteminformation-databaseinformation-property.md)
#### [LoggingSystemInformation.LoggingQueueName](loggingsysteminformation-loggingqueuename-property.md)
#### [LoggingSystemInformation.LoggingServiceName](loggingsysteminformation-loggingservicename-property.md)
### [OnlineTrustedServiceUserDomain](onlinetrustedserviceuserdomain-object.md)
#### [OnlineTrustedServiceUserDomain.CertificateExpirationTime](onlinetrustedserviceuserdomain-certificateexpirationtime-property.md)
#### [OnlineTrustedServiceUserDomain.CertificateName](onlinetrustedserviceuserdomain-certificatename-property.md)
#### [OnlineTrustedServiceUserDomain.Enabled](onlinetrustedserviceuserdomain-enabled-property.md)
#### [OnlineTrustedServiceUserDomain.ExcludedUsers](onlinetrustedserviceuserdomain-excludedusers-property.md)
#### [OnlineTrustedServiceUserDomain.Id](onlinetrustedserviceuserdomain-id-property.md)
### [OnlineTrustedServiceExcludedUserCollection](onlinetrustedserviceexcludedusercollection-object.md)
#### [OnlineTrustedServiceExcludedUserCollection.Update](onlinetrustedserviceexcludedusercollection-update-method.md)
### [ProxyAuthentication](proxyauthentication-object.md)
#### [ProxyAuthentication.Required](proxyauthentication-required-property.md)
#### [ProxyAuthentication.Scheme](proxyauthentication-scheme-property.md)
#### [ProxyAuthentication.UserAccount](proxyauthentication-useraccount-property.md)
### [ProxySettings](proxysettings-object.md)
#### [ProxySettings.Authentication](proxysettings-authentication-property.md)
#### [ProxySettings.Bypass](proxysettings-bypass-property.md)
#### [ProxySettings.BypassFilter](proxysettings-bypassfilter-property.md)
#### [ProxySettings.Port](proxysettings-port-property.md)
#### [ProxySettings.Refresh](proxysettings-refresh-method.md)
#### [ProxySettings.Required](proxysettings-required-property.md)
#### [ProxySettings.Server](proxysettings-server-property.md)
#### [ProxySettings.Update](proxysettings-update-method.md)
### [RevocationCondition](revocationcondition-object.md)
#### [RevocationCondition.PublicKeyFile](revocationcondition-publickeyfile-property.md)
#### [RevocationCondition.RefreshPerDays](revocationcondition-refreshperdays-property.md)
#### [RevocationCondition.Url](revocationcondition-url-property.md)
### [RightsTemplate](rightstemplate-object.md)
#### [RightsTemplate.ApplicationSpecificDataItems](rightstemplate-applicationspecificdataitems-property.md)
#### [RightsTemplate.Author](rightstemplate-author-property.md)
#### [RightsTemplate.CreatedTime](rightstemplate-createdtime-property.md)
#### [RightsTemplate.ExpirationCondition](rightstemplate-expirationcondition-property.md)
#### [RightsTemplate.ExtendedCondition](rightstemplate-extendedcondition-property.md)
#### [RightsTemplate.Id](rightstemplate-id-property.md)
#### [RightsTemplate.IsPublished](rightstemplate-ispublished-property.md)
#### [RightsTemplate.RevocationCondition](rightstemplate-revocationcondition-property.md)
#### [RightsTemplate.RightsRequestUrl](rightstemplate-rightsrequesturl-property.md)
#### [RightsTemplate.Summaries](rightstemplate-summaries-property.md)
#### [RightsTemplate.UpdatedTime](rightstemplate-updatedtime-property.md)
#### [RightsTemplate.UserRightsItems](rightstemplate-userrightsitems-property.md)
### [RightsTemplateCollection](rightstemplatecollection-object.md)
#### [RightsTemplateCollection.Copy](rightstemplatecollection-copy-method.md)
#### [RightsTemplateCollection.Publish](rightstemplatecollection-publish-method.md)
#### [RightsTemplateCollection.Refresh](rightstemplatecollection-refresh-method.md)
#### [RightsTemplateCollection.Update](rightstemplatecollection-update-method.md)
### [RightsTemplatePolicy](rightstemplatepolicy-object.md)
#### [RightsTemplatePolicy.PublishingFilePath](rightstemplatepolicy-publishingfilepath-property.md)
#### [RightsTemplatePolicy.RightsTemplateCollection](rightstemplatepolicy-rightstemplatecollection-property.md)
### [SecurityPolicy](securitypolicy-object.md)
#### [SecurityPolicy.DecommissionNow](securitypolicy-decommissionnow-method.md)
#### [SecurityPolicy.EnableDecommission](securitypolicy-enabledecommission-method.md)
#### [SecurityPolicy.EnableSuperUserGroup](securitypolicy-enablesuperusergroup-property.md)
#### [SecurityPolicy.SuperUserGroup](securitypolicy-superusergroup-property.md)
### [ServerLicensorCertificate](serverlicensorcertificate-object.md)
#### [ServerLicensorCertificate.Export](serverlicensorcertificate-export.md)
#### [ServerLicensorCertificate.FriendlyName](serverlicensorcertificate-friendlyname-property.md)
#### [ServerLicensorCertificate.KeyHierarchy](serverlicensorcertificate-keyhierarchy-property.md)
### [ServiceConnectionPoint](serviceconnectionpoint-object.md)
#### [ServiceConnectionPoint.Clear](serviceconnectionpoint-clear-method.md)
#### [ServiceConnectionPoint.MachineDomainName](serviceconnectionpoint-machinedomainname-property.md)
#### [ServiceConnectionPoint.Url](serviceconnectionpoint-url-property.md)
### [ServiceIdentity](serviceidentity-object.md)
#### [ServiceIdentity.CurrentServiceAccount](serviceidentity-currentserviceaccount-property.md)
#### [ServiceIdentity.NewServiceAccount](serviceidentity-newserviceaccount-property.md)
#### [ServiceIdentity.Update](serviceidentity-update-method.md)
### [ServicePrivateKeyProtectionInformation](serviceprivatekeyprotectioninformation-object.md)
#### [ServicePrivateKeyProtectionInformation.CryptographicServiceProviderName](serviceprivatekeyprotectioninformation-cryptographicserviceprovidername-property.md)
#### [ServicePrivateKeyProtectionInformation.IsServicePrivateKeySoftwareBased](serviceprivatekeyprotectioninformation-isserviceprivatekeysoftwarebased-property.md)
#### [ServicePrivateKeyProtectionInformation.KeyContainer](serviceprivatekeyprotectioninformation-keycontainer-property.md)
### [StringCollection](stringcollection-object.md)
### [TemplateLocaleName](templatelocalename-object.md)
#### [TemplateLocaleName.LanguageId](templatelocalename-languageid-property.md)
#### [TemplateLocaleName.Name](templatelocalename-name-property.md)
### [TemplateLocaleNameCollection](templatelocalenamecollection-object.md)
### [TemplateSummary](templatesummary-object.md)
#### [TemplateSummary.Description](templatesummary-description-property.md)
#### [TemplateSummary.LanguageId](templatesummary-languageid-property.md)
#### [TemplateSummary.Name](templatesummary-name-property.md)
### [TemplateSummaryCollection](templatesummarycollection-object.md)
### [TrustedDomainNameCollection](trusteddomainnamecollection-object.md)
#### [TrustedDomainNameCollection.Update](trusteddomainnamecollection-update-method.md)
### [TrustedPublishingDomain](trustedpublishingdomain-object.md)
#### [TrustedPublishingDomain.CryptoSvcProvider](trustedpublishingdomain-cryptosvcprovider-property.md)
#### [TrustedPublishingDomain.DisplayName](trustedpublishingdomain-displayname-property.md)
#### [TrustedPublishingDomain.Id](trustedpublishingdomain-id-property.md)
#### [TrustedPublishingDomain.IsImported](trustedpublishingdomain-isimported-property.md)
#### [TrustedPublishingDomain.KeyContainer](trustedpublishingdomain-keycontainer-property.md)
### [TrustedPublishingDomainCollection](trustedpublishingdomaincollection-object.md)
#### [TrustedPublishingDomainCollection.Export](trustedpublishingdomaincollection-export-method.md)
#### [TrustedPublishingDomainCollection.Import](trustedpublishingdomaincollection-import-method.md)
#### [TrustedPublishingDomainCollection.Refresh](trustedpublishingdomaincollection-refresh-method.md)
### [TrustedUserDomain](trusteduserdomain-object.md)
#### [TrustedUserDomain.CertificateExpirationTime](trusteduserdomain-certificateexpirationtime-property.md)
#### [TrustedUserDomain.DisplayName](trusteduserdomain-displayname-property.md)
#### [TrustedUserDomain.DomainNames](trusteduserdomain-domainnames-property.md)
#### [TrustedUserDomain.Id](trusteduserdomain-id-property.md)
#### [TrustedUserDomain.IsADFederationSvcTrusted](trusteduserdomain-isadfederationsvctrusted-property.md)
#### [TrustedUserDomain.IsImported](trusteduserdomain-isimported-property.md)
#### [TrustedUserDomain.IsSecurityIdentifiersAllowed](trusteduserdomain-issecurityidentifiersallowed-property.md)
### [TrustedUserDomainCollection](trusteduserdomaincollection-object.md)
#### [TrustedUserDomainCollection.Import](trusteduserdomaincollection-import-method.md)
#### [TrustedUserDomainCollection.Refresh](trusteduserdomaincollection-refresh-method.md)
### [TrustPolicy](trustpolicy-object.md)
#### [TrustPolicy.ADFederationService](trustpolicy-adfederationservice-property.md)
#### [TrustPolicy.OnlineTrustedServiceUserDomain](trustpolicy-onlinetrustedserviceuserdomain-property.md)
#### [TrustPolicy.TrustedPublishingDomains](trustpolicy-trustedpublishingdomains-property.md)
#### [TrustPolicy.TrustedUserDomains](trustpolicy-trusteduserdomains-property.md)
### [Urls](urls-object.md)
#### [Urls.Extranets](urls-extranets-property.md)
#### [Urls.Intranets](urls-intranets-property.md)
### [UserDomainAccount](userdomainaccount-object.md)
#### [UserDomainAccount.Domain](userdomainaccount-domain-property.md)
#### [UserDomainAccount.Password](userdomainaccount-password-property.md)
#### [UserDomainAccount.UserId](userdomainaccount-userid-property.md)
### [UserRightsItem](userrightsitem-object.md)
#### [UserRightsItem.CustomRights](userrightsitem-customrights-property.md)
#### [UserRightsItem.UserId](userrightsitem-userid-property.md)
#### [UserRightsItem.WellKnownRights](userrightsitem-wellknownrights-property.md)
### [UserRightsItemCollection](userrightsitemcollection-object.md)
#### [UserRightsItemCollection.GrantOwnerFullRights](userrightsitemcollection-grantownerfullrights-method.md)
### [VariantObjectCollection](variantobjectcollection-object.md)
### [Version](version-object.md)
#### [Version.Build](version-build-property.md)
#### [Version.Major](version-major-property.md)
#### [Version.Minor](version-minor-property.md)
#### [Version.Revision](version-revision-property.md)
