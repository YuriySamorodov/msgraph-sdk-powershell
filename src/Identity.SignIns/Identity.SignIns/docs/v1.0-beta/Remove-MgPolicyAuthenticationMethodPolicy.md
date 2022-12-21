---
external help file:
Module Name: Microsoft.Graph.Identity.SignIns
online version: https://docs.microsoft.com/en-us/powershell/module/microsoft.graph.identity.signins/remove-mgpolicyauthenticationmethodpolicy
schema: 2.0.0
---

# Remove-MgPolicyAuthenticationMethodPolicy

## SYNOPSIS
Delete navigation property authenticationMethodsPolicy for policies

## SYNTAX

```
Remove-MgPolicyAuthenticationMethodPolicy [-IfMatch <String>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Delete navigation property authenticationMethodsPolicy for policies

## EXAMPLES

### Example 1: Code snippet
```powershell
Import-Module Microsoft.Graph.Identity.SignIns

$params = @{
	"@odata.context" = "https://graph.microsoft.com/v1.0/$metadata#authenticationMethodsPolicy"
	RegistrationEnforcement = @{
		AuthenticationMethodsRegistrationCampaign = @{
			SnoozeDurationInDays = 1
			State = "enabled"
			ExcludeTargets = @(
			)
			IncludeTargets = @(
				@{
					Id = "3ee3a9de-0a86-4e12-a287-9769accf1ba2"
					TargetType = "group"
					TargetedAuthenticationMethod = "microsoftAuthenticator"
				}
			)
		}
	}
	AuthenticationMethodConfigurations = @(
		@{
			"@odata.type" = "#microsoft.graph.fido2AuthenticationMethodConfiguration"
			Id = "Fido2"
			State = "disabled"
			IsSelfServiceRegistrationAllowed = $false
			IsAttestationEnforced = $false
		}
	)
}

Update-MgPolicyAuthenticationMethodPolicy -BodyParameter $params
```

This example shows how to use the Remove-MgPolicyAuthenticationMethodPolicy Cmdlet.

To learn about permissions for this resource, see the [permissions reference](/graph/permissions-reference).

## PARAMETERS

### -IfMatch
ETag

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns true when the command succeeds

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean

## NOTES

ALIASES

## RELATED LINKS

