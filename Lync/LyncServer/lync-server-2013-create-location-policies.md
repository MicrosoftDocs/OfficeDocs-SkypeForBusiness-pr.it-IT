---
title: 'Lync Server 2013: creare criteri per la posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f420d3b634df79411bbc72cd4c029f9b5d97e19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a>Creare criteri di posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-11_

Lync Server usa un criterio di posizione per abilitare i client Lync per il E9-1-1 durante la registrazione client. Un criterio di posizione contiene le impostazioni che definiscono il modo in cui verrà implementato E9-1-1.

È possibile modificare i criteri di posizione globale e creare nuovi criteri di posizione contrassegnati. Un client ottiene un criterio globale quando non si trova all'interno di una subnet con un criterio di posizione associato o quando al client non è stato assegnato direttamente un criterio di posizione. I criteri contrassegnati vengono assegnati a subnet o utenti.

Per creare un criterio di posizione, è necessario usare un account che sia membro del gruppo RTCUniversalServerAdmins oppure sia un membro del ruolo amministrativo di CsVoiceAdministrator o disponga di autorizzazioni e diritti di amministratore equivalenti.

Per una descrizione completa dei criteri di posizione, vedere [definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md). I cmdlet in questa procedura usano i criteri di posizione definiti con i valori seguenti:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>Dichiarazione di non responsabilità</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>I criteri aziendali richiedono l'impostazione di una posizione. Se non si imposta una posizione, i servizi di emergenza non saranno in grado di individuare l'utente in caso di emergenza. Impostare una posizione.</p></td>
</tr>
<tr class="even">
<td><p>UseLocationForE911Only</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>TwoWay</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


Per informazioni dettagliate sull'uso dei criteri di posizione, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>Per creare criteri di posizione

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.
    
    <div>
    

    > [!NOTE]  
    > CsLocationPolicy non riesce se l'impostazione per <STRONG>PstnUsage</STRONG> non è già presente nell'elenco globale di PstnUsages.

    
    </div>

2.  Facoltativamente, eseguire il cmdlet seguente per modificare il criterio della posizione globale:
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Eseguire la procedura seguente per creare criteri di posizione contrassegnati.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Eseguire il cmdlet seguente per applicare il criterio di posizione con tag creato nel passaggio 3 a un criterio utente.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

