---
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
online version: https://docs.microsoft.com/powershell/module/exchange/new-dlpcompliancepolicy
applicable: Security & Compliance
title: New-DlpCompliancePolicy
schema: 2.0.0
author: chrisda
ms.author: chrisda
ms.reviewer:
---

# New-DlpCompliancePolicy

## SYNOPSIS
This cmdlet is available only in Security & Compliance PowerShell. For more information, see [Security & Compliance PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).

Use the New-DlpCompliancePolicy cmdlet to create data loss prevention (DLP) policies in the Microsoft Purview compliance portal. DLP policies contain DLP rules that identify, monitor, and protect sensitive information.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://docs.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-DlpCompliancePolicy [-Name] <String>
 [-Comment <String>]
 [-Confirm]
 [-EndpointDlpLocation <MultiValuedProperty>]
 [-EndpointDlpLocationException <MultiValuedProperty>]
 [-ExceptIfOneDriveSharedBy <RecipientIdParameter[]>]
 [-ExceptIfOneDriveSharedByMemberOf <RecipientIdParameter[]>]
 [-ExchangeLocation <MultiValuedProperty>]
 [-ExchangeSenderMemberOf <RecipientIdParameter[]>]
 [-ExchangeSenderMemberOfException <RecipientIdParameter[]>]
 [-Force]
 [-Mode <PolicyMode>]
 [-OneDriveLocation <MultiValuedProperty>]
 [-OneDriveLocationException <MultiValuedProperty>]
 [-OneDriveSharedBy <RecipientIdParameter[]>]
 [-OneDriveSharedByMemberOf <RecipientIdParameter[]>]
 [-OnPremisesScannerDlpLocation <MultiValuedProperty>]
 [-OnPremisesScannerDlpLocationException <MultiValuedProperty>]
 [-PolicyTemplateInfo <PswsHashtable>]
 [-PowerBIDlpLocation <MultiValuedProperty>]
 [-PowerBIDlpLocationException <MultiValuedProperty>]
 [-Priority <Int32>]
 [-SharePointLocation <MultiValuedProperty>]
 [-SharePointLocationException <MultiValuedProperty>]
 [-TeamsLocation <MultiValuedProperty>]
 [-TeamsLocationException <MultiValuedProperty>]
 [-ThirdPartyAppDlpLocation <MultiValuedProperty>]
 [-ThirdPartyAppDlpLocationException <MultiValuedProperty>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
To use this cmdlet in Security & Compliance PowerShell, you need to be assigned permissions. For more information, see [Permissions in the Microsoft Purview compliance portal](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center-permissions).

## EXAMPLES

### Example 1
```powershell
New-DlpCompliancePolicy -Name "GlobalPolicy" -SharePointLocation All
```

This example creates a DLP policy named GlobalPolicy that will be enforced across all SharePoint Online locations.

### Example 2
```powershell
New-DlpCompliancePolicy -Name "GlobalPolicy" -Comment "Primary policy" -SharePointLocation "https://my.url","https://my.url2" -OneDriveLocation "https://my.url3","https://my.url4" -Mode Enable
```

This example creates a DLP policy named GlobalPolicy for the specified SharePoint Online and OneDrive for Business locations. The new policy has a descriptive comment and will be enabled on creation.

### Example 3

```powershell
New-DlpCompliancePolicy -Name "PowerBIPolicy" -Comment "Primary policy" -PowerBIDlpLocation "All" -PowerBIDlpLocationException "workspaceID1","workspaceID2","workspaceID3" -Mode Enable
```

This example creates a DLP policy named PowerBIPolicy for all qualifying Power BI workspaces (that is, those hosted on Premium Gen2 capacities) except for the specified workspaces. The new policy has a descriptive comment and will be enabled on creation.

## PARAMETERS

### -Name
The Name parameter specifies the unique name of the DLP policy. If the value contains spaces, enclose the value in quotation marks.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Comment
The Comment parameter specifies an optional comment. If you specify a value that contains spaces, enclose the value in quotation marks ("), for example: "This is an admin note".

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointDlpLocation
**Note**: This parameter requires membership in the Compliance administrator or Compliance data administrator roles in Azure Active Directory.

The EndpointDLPLocation parameter specifies the user accounts to include in the DLP policy for Endpoint DLP when they are logged on to an onboarded device. You identify the account by name or email address. You can use the value All to include all user accounts.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

For more information about Endpoint DLP, see [Learn about Endpoint data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointDlpLocationException
**Note**: This parameter requires membership in the Compliance administrator or Compliance data administrator roles in Azure Active Directory.

The EndpointDlpLocationException parameter specifies the user accounts to exclude from Endpoint DLP when you use the value All for the EndpointDlpLocation parameter. You identify the account by name or email address.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

For more information about Endpoint DLP, see [Learn about Endpoint data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExceptIfOneDriveSharedBy
The ExceptIfOneDriveSharedBy parameter specifies the OneDrive accounts to exclude from the DLP policy when you use the value All for the OneDriveSharedBy parameter. You identify the user by its email address.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: RecipientIdParameter[]
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExceptIfOneDriveSharedByMemberOf
The ExceptIfOneDriveSharedByMemberOf parameter specifies the distribution groups, mail-enabled security groups, or Microsoft 365 Groups to exclude from the DLP policy when you use the value All for the OneDriveSharedBy parameter. You identify the group by its email address.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: RecipientIdParameter[]
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeLocation
The ExchangeLocation parameter specifies whether to include email messages in the policy. The only valid value for this parameter is All. If you don't want to include email messages in the policy, don't use this parameter.

If you use `-ExchangeLocation All` by itself, the policy applies to email for all users.

To include only email of specific group members in the policy, use `-ExchangeLocation All` with the ExchangeSenderMemberOf parameter in the same command. Only members of groups specified by the ExchangeSenderMemberOf parameter are included in the policy.

To exclude only email of specific group members from the policy, use `-ExchangeLocation All` with the ExchangeSenderMemberOfException parameter in the same command. Only members of groups specified by the ExchangeSenderMemberOfException parameter are excluded from the policy.

The default value of this parameter is blank ($null).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeSenderMemberOf
The ExchangeSenderMemberOf parameter specifies the email addresses of distribution groups or mail-enabled security groups to include in the policy (the group members are included in the policy). You must use this parameter with the ExchangeLocation parameter.

You can specify multiple email addresses separated by commas.

You can't use this parameter with the ExchangeSenderMemberOfException parameter.

You can't use this parameter to specify Microsoft 365 Groups.

```yaml
Type: RecipientIdParameter[]
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeSenderMemberOfException
The ExchangeSenderMemberOfException parameter specifies the email addresses of distribution groups or mail-enabled security groups to exclude from the policy (the group members are excluded from the policy). You must use this parameter with the ExchangeLocation parameter.

You can specify multiple email addresses separated by commas.

You can't use this parameter with the ExchangeSenderMemberOf parameter.

You can't use this parameter to specify Microsoft 365 Groups.

```yaml
Type: RecipientIdParameter[]
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
The Mode parameter specifies the action and notification level of the DLP policy. Valid values are:

- Enable: The policy is enabled for actions and notifications. This is the default value.
- Disable: The policy is disabled.
- TestWithNotifications: No actions are taken, but notifications are sent.
- TestWithoutNotifications: An audit mode where no actions are taken, and no notifications are sent.

```yaml
Type: PolicyMode
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OneDriveLocation
Don't use this parameter. Use the OneDriveSharedBy and OneDriveSharedByMemberOf parameters instead.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OneDriveLocationException
Don't use this parameter. Use the ExceptIfOneDriveSharedBy and ExceptIfOneDriveSharedByMemberOf parameters instead.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OneDriveSharedBy
The OneDriveSharedBy parameter specifies the OneDrive accounts to include in the DLP policy. You identify the account in UPN format (laura@contoso.onmicrosoft.com). You can use the value All to include all OneDrive accounts.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: RecipientIdParameter[]
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OneDriveSharedByMemberOf
The OneDriveSharedByMemberOf parameter specifies the distribution groups, mail-enabled security groups, or Microsoft 365 Groups to include in the DLP policy when you aren't using the value All for the OneDriveSharedBy parameter. You identify the group by its email address.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: RecipientIdParameter[]
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnPremisesScannerDlpLocation
The OnPremisesScannerDlpLocation parameter specifies the on-premises file shares and SharePoint document libraries and folders to include in the DLP policy. You can use the value All to include all on-premises file shares and SharePoint document libraries and folders.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

For more information about the DLP on-premises scanner, see [Learn about the data loss prevention on-premises scanner](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-learn).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnPremisesScannerDlpLocationException
The OnPremisesScannerDlpLocationException parameter specifies the on-premises file shares and SharePoint document libraries and folders to exclude from the DLP policy if you use the value All for the OnPremisesScannerDlpLocation parameter.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

For more information about the DLP on-premises scanner, see [Learn about the data loss prevention on-premises scanner](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-learn).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyTemplateInfo
The PolicyTemplateInfo specifies the built-in or custom DLP policy templates to use in the DLP policy.

For more information about DLP policy templates, see [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include).

```yaml
Type: PswsHashtable
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerBIDlpLocation
The PowerBIDlpLocation parameter specifies the Power BI workspace IDs to include in the DLP policy. Only workspaces hosted in Premium Gen2 capacities are permitted. You can use the value All to include all supported workspaces.

You can find the workspace ID using any of the following procedures:

- In the Admin portal, choose **Workspaces**, then select a workspace and choose **\> More options (...) \> Details**.
- Look in the URL of a selected workspace.
- In PowerShell, use the **Get-PowerBIWorkspace** cmdlet.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

**Note**: You can't use this parameter if the DLP policy applies to other locations.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerBIDlpLocationException
The PowerBIDlpLocationException parameter specifies the Power BI workspace IDs to exclude from the DLP policy when you use the value All for the PowerBIDlpLocation parameter. Only workspaces hosted in Premium Gen2 capacities are permitted.

You can find the workspace ID using any of the following procedures:

- In the Admin portal, choose **Workspaces**, then select a workspace and choose **\> More options (...) \> Details**.
- Look in the URL of a selected workspace.
- In PowerShell, use the **Get-PowerBIWorkspace** cmdlet.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
The Priority parameter specifies a priority value for the policy that determines the order of policy processing. A lower integer value indicates a higher priority, the value 0 is the highest priority, and policies can't have the same priority value.

Valid values and the default value depend on the number of existing policies. For example, if there are 5 existing policies:

- Valid priority values for the existing 5 policies are from 0 through 4.
- Valid priority values for a new 6th policy are from 0 through 5.
- The default value for a new 6th policy is 5.

If you modify the priority value of a policy, the position of the policy in the list changes to match the priority value you specify. In other words, if you set the priority value of a policy to the same value as an existing policy, the priority value of the existing policy and all other lower priority policies after it is increased by 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePointLocation
The SharePointLocation parameter specifies the SharePoint Online sites to include in the DLP police. You identify the site by its URL value, or you can use the value All to include all sites.

You can't add SharePoint Online sites to the policy until they have been indexed.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePointLocationException
This parameter specifies the SharePoint Online sites to exclude when you use the value All for the SharePointLocation parameter. You identify the site by its URL value.

You can't add SharePoint Online sites to the policy until they have been indexed.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamsLocation
The TeamsLocation parameter specifies the Teams chat and channel messages to include in the DLP policy. You identify the entries by the email address or name of the account, distribution group, or mail-enabled security group. You can use the value All to include all accounts, distribution groups, and mail-enabled security groups.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamsLocationException
The TeamsLocation parameter specifies the Teams chat and channel messages to exclude from the DLP policy when you use the value All for the TeamsLocation parameter. You identify the entries by the email address or name of the account, distribution group, or mail-enabled security group.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThirdPartyAppDlpLocation
**Note**: This parameter requires membership in the Compliance administrator or Compliance data administrator roles in Azure Active Directory.

The ThirdPartyAppDlpLocation parameter specifies the non-Microsoft cloud apps to include in the DLP policy. You can use the value All to include all connected apps.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

For more information about DLP for non-Microsoft cloud apps, see [Use data loss prevention policies for non-Microsoft cloud apps](https://docs.microsoft.com/microsoft-365/compliance/dlp-use-policies-non-microsoft-cloud-apps).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThirdPartyAppDlpLocationException
**Note**: This parameter requires membership in the Compliance administrator or Compliance data administrator roles in Azure Active Directory.

The ThirdPartyAppDlpLocationException parameter specifies the non-Microsoft cloud apps to exclude from the DLP policy when you use the value All for the ThirdPartyAppDlpLocation parameter.

To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"<value1>","<value2>",..."<valueX>"`.

For more information about DLP for non-Microsoft cloud apps, see [Use data loss prevention policies for non-Microsoft cloud apps](https://docs.microsoft.com/microsoft-365/compliance/dlp-use-policies-non-microsoft-cloud-apps).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
The WhatIf switch doesn't work in Security & Compliance PowerShell.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
