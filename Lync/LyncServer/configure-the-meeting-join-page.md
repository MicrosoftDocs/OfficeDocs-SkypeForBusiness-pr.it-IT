---
title: Configurare la pagina di partecipazione alle riunioni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c6622eb6820857b117c16bfa9ea2065678d3b88
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alle riunioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-14_

Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Lync 2013 è già installato nel computer dell'utente. Se un client è già installato, tale client si apre e si unisce alla riunione. Se un client non è installato, per impostazione predefinita viene aperta la versione 2013 di Lync Web App.

È possibile modificare il comportamento della pagina di partecipazione alla riunione se si vuole consentire agli utenti di partecipare a riunioni con Office Communicator 2007 R2 o Lync 2010 Attendant. Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Lync Server 2013, ma le configuri usando il cmdlet CsWebServiceConfiguration.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>Parametri di CsWebServiceConfiguration pagina di join della riunione

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro CsWebServiceConfiguration</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Se impostato su true, gli utenti che partecipano a una riunione usando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione usando Office Communicator 2007 R2. Il valore predefinito è False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Se impostato su true, le opzioni alternative per partecipare a una conferenza online (ad esempio Office Communicator 2007 R2) verranno espanse e visualizzate automaticamente agli utenti. Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Per configurare la pagina di partecipazione alla riunione tramite Lync Server 2013 Management Shell

1.  Avviare Lync Server 2013 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet seguente:
    
        Get-CsWebServiceConfiguration
    
    Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.

3.  Eseguire il comando seguente, con i parametri impostati su true o false, a seconda delle preferenze (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server 2013 Management Shell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

