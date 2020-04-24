# FHIR Server with Service Client application

This repositories contains scripts to deploy a FHIR server, together with e Service Client application that can be used for Server to Server communication

# Prerequisites

Before deploying the samples scenario make sure that you have `Az` and `AzureAd` powershell modules installed:

```PowerShell
Install-Module Az
Install-Module AzureAd
```

# Deployment

To deploy the sample scenario, first clone this git repo and find the deployment scripts folder:

```PowerShell
git clone https://github.com/Microsoft/fhir-server-samples
cd fhir-server-samples/deploy/scripts
```

Log into your Azure subscription:

```PowerShell
Login-AzAccount
```

Connect to Azure AD with:

```PowerShell
Connect-AzureAd -TenantDomain <AAD TenantDomain>
```

**NOTE** The connection to Azure AD can be made using a different tenant domain than the one tied to your Azure subscription. If you don't have privileges to create app registrations, users, etc. in your Azure AD tenant, you can [create a new one](https://docs.microsoft.com/azure/active-directory/develop/quickstart-create-new-tenant), which will just be used for demo identities, etc.

Then deploy the scenario with the Open Source FHIR Server for Azure:

```PowerShell
.\Create-FhirServerSamplesEnvironment.ps1 -EnvironmentName <ENVIRONMENTNAME> -UsePaaS $false
```

or the managed Azure API for FHIR:

```PowerShell
.\Create-FhirServerSamplesEnvironment.ps1 -EnvironmentName <ENVIRONMENTNAME> -UsePaaS $true
```

To delete the senario:

```PowerShell
.\Delete-FhirServerSamplesEnvironment.ps1 -EnvironmentName <ENVIRONMENTNAME>
```

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
