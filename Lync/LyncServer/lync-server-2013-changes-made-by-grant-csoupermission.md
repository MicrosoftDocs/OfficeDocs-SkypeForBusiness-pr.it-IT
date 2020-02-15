---
title: 'Lync Server 2013: modifiche apportate da Grant-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Modifiche apportate da Grant-CsOUPermission in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-20_

Per delegare l'amministrazione di Lync Server 2013, è possibile aggiungere autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.

Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata, come indicato nelle tabelle seguenti.

<div>

## <a name="granting-permission-for-user-objects"></a>Concessione di autorizzazioni per gli oggetti utente

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente di un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.

### <a name="permissions-granted-for-user-objects"></a>Autorizzazioni concesse per gli oggetti utente

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo</th>
<th>Autorizzazione</th>
<th>Si applica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replica modifiche directory</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leggere RTCUserSearchPropertySet</p>
<p>Leggere RTCUserProvisioningPropertySet</p>
<p>Leggere RTCPropertySet</p>
<p>Leggere le informazioni pubbliche</p>
<p>Leggere informazioni generali</p>
<p>Leggere le restrizioni degli account utente</p></td>
<td><p>Oggetti utente discendente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Scrittura RTCUserSearchPropertySet</p>
<p>Scrittura msExchUCVoiceMailSettings</p>
<p>Scrittura RTCUserProvisioningPropertySet</p>
<p>Scrittura RTCPropertySet</p>
<p>Scrittura proxyAddresses</p></td>
<td><p>Oggetti utente discendente</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Concessione di autorizzazioni per gli oggetti computer

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.

### <a name="permissions-granted-for-computer-objects"></a>Autorizzazioni concesse per gli oggetti computer

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo</th>
<th>Autorizzazione</th>
<th>Si applica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replica modifiche directory</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leggere le informazioni pubbliche</p>
<p>Lettura convalidata-DNS-host-name</p></td>
<td><p>Oggetti Computer discendenti</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Leggere le informazioni pubbliche</p>
<p>Lettura convalidata-DNS-host-name</p></td>
<td><p>Oggetti Computer discendenti</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concessione di autorizzazioni per gli oggetti Contact o AppContact

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti contatto o gli oggetti AppContact su un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Autorizzazioni concesse per gli oggetti Contact o AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo</th>
<th>Autorizzazione</th>
<th>Si applica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replica modifiche directory</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leggere RTCUserSearchPropertySet</p>
<p>Leggere RTCUserProvisioningPropertySet</p>
<p>Leggere RTCPropertySet</p>
<p>Leggere le informazioni pubbliche</p>
<p>Leggere informazioni generali</p>
<p>Leggere le informazioni personali</p>
<p>Leggere le restrizioni degli account utente</p></td>
<td><p>Oggetti contatto discendenti</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Scrittura RTCUserSearchPropertySet</p>
<p>Scrittura otherIpPhone</p>
<p>Scrittura di displayName</p>
<p>Descrizione di scrittura</p>
<p>Scrittura telephoneNumber</p>
<p>Scrittura msExchUCVoiceMailSettings</p>
<p>Scrittura RTCUserProvisioningPropertySet</p>
<p>Scrittura RTCPropertySet</p>
<p>Scrittura proxyAddresses</p></td>
<td><p>Oggetti contatto discendenti</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Concessione di autorizzazioni per gli oggetti Device

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.

### <a name="permissions-granted-for-device-objects"></a>Autorizzazioni concesse per gli oggetti Device

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo</th>
<th>Autorizzazione</th>
<th>Si applica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replica modifiche directory</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leggere RTCUserSearchPropertySet</p>
<p>Leggere RTCUserProvisioningPropertySet</p>
<p>Leggere RTCPropertySet</p>
<p>Leggere le informazioni pubbliche</p>
<p>Leggere le informazioni personali</p>
<p>Leggere informazioni generali</p>
<p>Leggere le restrizioni degli account utente</p></td>
<td><p>Oggetti contatto discendenti</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Crea elemento figlio</p>
<p>Elimina elemento figlio</p>
<p>Elimina albero</p></td>
<td><p>Contatto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Scrittura di displayName</p>
<p>Descrizione di scrittura</p>
<p>Scrittura telephoneNumber</p></td>
<td><p>Oggetti utente discendente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Scrittura RTCUserSearchPropertySet</p>
<p>Scrittura otherIpPhone</p>
<p>Scrittura di displayName</p>
<p>Descrizione di scrittura</p>
<p>Scrittura telephoneNumber</p>
<p>Scrittura msExchUCVoiceMailSettings</p>
<p>Scrittura RTCUserProvisioningPropertySet</p>
<p>Scrittura RTCPropertySet</p>
<p>Scrittura proxyAddresses</p></td>
<td><p>Oggetti contatto discendenti</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Concessione di autorizzazioni per gli oggetti InetOrgPerson

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Autorizzazioni concesse per gli oggetti InetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo</th>
<th>Autorizzazione</th>
<th>Si applica a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replica modifiche directory</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Elenca contenuto</p>
<p>Leggere tutte le proprietà</p>
<p>Autorizzazioni di lettura</p></td>
<td><p>Solo questo oggetto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Leggere RTCUserSearchPropertySet</p>
<p>Leggere RTCUserProvisioningPropertySet</p>
<p>Leggere RTCPropertySet</p>
<p>Leggere le informazioni personali</p>
<p>Leggere le informazioni pubbliche</p>
<p>Leggere informazioni generali</p>
<p>Leggere le restrizioni degli account utente</p></td>
<td><p>Oggetti inetOrgPerson discendenti</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Scrittura RTCUserSearchPropertySet</p>
<p>Scrittura RTCUserProvisioningPropertySet</p>
<p>Scrittura RTCPropertySet</p>
<p>Scrittura proxyAddresses</p></td>
<td><p>Oggetti inetOrgPerson discendenti</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

