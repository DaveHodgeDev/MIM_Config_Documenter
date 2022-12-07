# MIM_Config_Documenter - this project provides helper scripts to generate the MIM Configuration Documenter report. 

## Script descriptions
The following scripts have been provided to assist the automation of the report:
- Export_MIM_Policy script will create the folder for storing the MIM Service Policy file and export the policy settings
- Export_MIM_Policy script will create the folders for storing the MIM Service Schema file and export the schema settings
- Invoke documenter will compare the recently exported settings against the template values to generate the MIM Config Documenter report.


## Report generation process

The following process is used to generate the report:

1. Download the latest version of the [MIM Config Documenter](https://github.com/Microsoft/MIMConfigDocumenter)
1. Extract the files to C:\Code\MIM_Config_Documenter
1. Run PowerShell as an Administator
1. Run the schema script: Export_MIM_Schema.ps1
1. Run the policy script: Export_MIM_Policy.ps1
1. Export the MIM Synchronization Engine Configuration files to the folder created by the export MIM Service settings scripts. 
  Using either of the following methods:
  - Export settings from the Synchronization Console to the folder
  - Generate from a command line
    1. Run PowerShell as an Administrator
    1. Change directory to the MIM Synchronization Engine's Bin folder
    1. .\svrexport "Sync Folder created by the script"
    - e.g. .\svrexport "C:\Code\MIM_Config_Documenter\Data\$Company\Pilot\SyncConfig"
7. Run the InvokeDocumenter.ps1 script to generate the report
8. Open the generated report at C:\Code\MIM_Config_Documenter\Reports
