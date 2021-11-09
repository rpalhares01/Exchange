# Exchange
MSS Legacy Template (GPO)
To add ADMX templates to Group Policy, Windows Server 2008 and above uses a Central Store to store Administrative Template files. In Windows 7, the ADM folder is not created in a GPO as in earlier versions of Windows. Therefore, domain controllers do not store or replicate redundant copies of .adm files. To take advantage of the benefits of .admx files, you must create a Central Store in the SYSVOL folder on a domain controller. The Central Store is a file location that is checked by the Group Policy tools. The Group Policy tools use any .admx files that are in the Central Store. The files that are in the Central Store are later replicated to all domain controllers in the domain.

The Central Store for .admx and .adml files are located at the following locations:

.ADMX Files
\\<your domain>\SYSVOL\<FDQN>\policies\PolicyDefinitions\

.ADML Files
\\<your domain>\SYSVOL\<FDQN>\policies\PolicyDefinitions\en-us

Ex. \\contoso\SYSVOL\contoso.microsoft.com\policies\PolicyDefinitions\

Whenever you want to add a new template to the central store, you must find or download the new .ADMX and the .ADML files and copy them to the central store. For example, if your company is upgrading from IE9 to IE11, you will need to update the group policy templates so that any new policies related to IE11 become available for domain administrators. You can search the Internet and download these ADMX/ADML files or you can install IE11 on your PC which will update the ADMX and ADML files on your PC during the IE11 installation. In order to update the Central Store, all you need to do is copy those ADMX and ADML files from your PC to the appropriate SYSVOL locations. For Windows 7 comptuers, the local .ADMX and .ADML files are located at the following locations:

.ADMX Files
C:\Windows\PolicyDefinitions

.ADML Files
C:\Windows\PolicyDefinitions\en-US
