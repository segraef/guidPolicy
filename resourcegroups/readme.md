# Add a tag to resource groups (GUID)

Add a tag to resource groups (GUID)

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsegraef%2FguidPolicy%2Fmaster%2Fresourcegroups%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "add-guid-tag" -DisplayName "Add a tag to resource groups (GUID)" -description "Add a tag to resource groups (GUID)" -Policy 'https://raw.githubusercontent.com/segraef/guidPolicy/master/resourcegroups/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/segraef/guidPolicy/master/resourcegroups/azurepolicy.parameters.json' -Mode Indexed
$definition
$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -tagName 'guid' -PolicyDefinition $definition
$assignment 
````



## Try with CLI

````cli

az policy definition create --name 'add-guid-tag' --display-name 'Add a guid tag to resource groups (GUID)' --description 'Add a guid tag to resource groups (GUID)' --rules 'https://raw.githubusercontent.com/segraef/guidPolicy/master/resourcegroups/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/segraef/guidPolicy/master/resourcegroups/azurepolicy.parameters.json' --mode Indexed

az policy assignment create --name <assignmentname> --scope <scope> --policy "add-guid-tag" --params "{'tagName':{'value': 'guid'}}"

````