﻿---
title: New-CsRoutingConfiguration
TOCTitle: New-CsRoutingConfiguration
ms:assetid: ead67e35-b145-4041-ba3e-4b26c47cce1d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399056(v=OCS.15)
ms:contentKeyID: 49299215
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRoutingConfiguration

 

_**Dernière rubrique modifiée :** 2015-03-09_

This cmdlet returns an object containing the default settings for a routing configuration object. Cette applet de commande est une nouveauté de Lync Server 2010.

## Syntaxe

    New-CsRoutingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableLocationBasedRouting <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Route <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command creates an object containing the default routing configuration values and assigns that object to the variable $x. Any other use of this cmdlet will return an error.

    $x = New-CsRoutingConfiguration -Identity global -InMemory

## Detailed Description

A routing configuration is a container for all voice routes defined within a Lync Server deployment. To create a new voice route, use the **New-CsVoiceRoute** cmdlet.

A routing configuration can be defined only at the global level. In addition, you cannot have individually named routing configurations; there is only one voice route list for the entire Lync Server deployment. In the Lync Server implementation of Windows PowerShell, if you try to create an object that already exists by calling a cmdlet beginning with the New verb, you’ll receive an error message. Every implementation of Lync Server includes a default routing configuration object with a Global Identity. What this means is that the only voice route list that could be created already exists. So a call to the **New-CsRoutingConfiguration** cmdlet will always return an error message and will not create a new routing configuration.

The only exception to this is if you specify the InMemory parameter in the call to this cmdlet. This command will create an object only in memory that contains a default list of voice routes.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRoutingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRoutingConfiguration"}

## Paramètres


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The scope of the routing configuration. This value must be Global.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableLocationBasedRouting</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, voice routing will be managed by taking into account the location of both the user placing the call and the user receiving the call. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Crée une référence d’objet sans valider l’objet comme une modification définitive. Si vous affectez à une variable la sortie de cette cmdlet appelée avec ce paramètre, vous pouvez apporter des modifications aux propriétés de la référence d’objet, puis les valider en appelant la cmdlet Set- correspondante.</p></td>
</tr>
<tr class="even">
<td><p><em>Route</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>A list of all voice routes (Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route objects) defined for the Lync Server deployment.</p>
<p>You can create voice route objects by using the <strong>New-CsVoiceRoute</strong> cmdlet. That is the recommended way of adding voice routes to this list.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Décrit ce qui se passe si vous exécutez la commande sans l’exécuter réellement.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Can create an in-memory object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnRoutingSettings.

## Voir aussi

#### Autres ressources

[Remove-CsRoutingConfiguration](remove-csroutingconfiguration.md)  
[Set-CsRoutingConfiguration](set-csroutingconfiguration.md)  
[Get-CsRoutingConfiguration](get-csroutingconfiguration.md)  
[New-CsVoiceRoute](new-csvoiceroute.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

