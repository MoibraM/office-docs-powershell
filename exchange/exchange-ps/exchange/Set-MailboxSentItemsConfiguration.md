---
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
online version: https://docs.microsoft.com/powershell/module/exchange/set-mailboxsentitemsconfiguration
applicable: Exchange Server 2010
title: Set-MailboxSentItemsConfiguration
schema: 2.0.0
author: chrisda
ms.author: chrisda
ms.reviewer:
---

# Set-MailboxSentItemsConfiguration

## SYNOPSIS
This cmdlet is available only in Exchange Server 2010.

Use the Set-MailboxSentItemsConfiguration cmdlet to modify the Sent Items settings for mailboxes in your organization.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://docs.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-MailboxSentItemsConfiguration [-Confirm]
 [-DomainController <Fqdn>]
 [-Identity <MailboxIdParameter>]
 [-SendAsItemsCopiedTo <SentItemsCopiedTo>]
 [-SendOnBehalfOfItemsCopiedTo <SentItemsCopiedTo>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
By default, when you use Send As or Send On Behalf Of to send a message from another mailbox, the message is saved in your Sent Items folder (not in the Sent Items folder of the source mailbox). In Microsoft Exchange Server 2010 Service Pack 3 (SP3), you can save copies messages in the Sent Items folder of the sender and the source mailbox. For example, consider a shared mailbox that receives customer feedback and is monitored by multiple users. When someone responds to a message in the shared mailbox, you can save the message in the Sent Items folder of the shared mailbox and the sender's mailbox.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-MailboxSentItemsConfiguration -Identity "Customer Support Feedback" -SendAsItemsCopiedTo SenderAndFrom
```

This example configures the shared mailbox named "Customer Support Feedback" so that sent messages are saved both to the Sent Items folder of the "Customer Support Feedback" mailbox, and the Sent Items folder of the user that sent the message.

## PARAMETERS

### -Confirm
The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Exchange Server 2010

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController
The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
The Identity parameter specifies the mailbox whose Sent Items configuration you want to modify. You can use any value that uniquely identifies the mailbox. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Domain\\Username
- Email address
- GUID
- LegacyExchangeDN
- SamAccountName
- User ID or user principal name (UPN)

```yaml
Type: MailboxIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SendAsItemsCopiedTo
The SendAsItemsCopiedTo parameter specifies where messages that are sent from the mailbox using Send As permission are saved. Valid values are:

- Sender: Messages sent from the mailbox are saved in the Sent Items folder of the user who sent the message. This is the default value.
- SenderAndFrom: Messages sent from the mailbox are saved in the Sent Items folder of the user who sent the message, and in the Sent Items folder of the mailbox.

```yaml
Type: SentItemsCopiedTo
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SendOnBehalfOfItemsCopiedTo
The SendOnBehalfOfItemsCopiedTo parameter specifies where messages that are sent from the mailbox using Send On Behalf Of permission are saved. Valid values are:

- Sender: Messages sent from the mailbox are saved in the Sent Items folder of the user who sent the message. This is the default value.
- SenderAndFrom: Messages sent from the mailbox are saved in the Sent Items folder of the user who sent the message, and in the Sent Items folder of the mailbox.

```yaml
Type: SentItemsCopiedTo
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Exchange Server 2010

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
