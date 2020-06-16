---
title: Configurare la pagina di partecipazione alle riunioni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 10700dc8a75d5c067870b53c0e0e74b7a469504a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alle riunioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-14_

Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Lync 2013 è già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se non è installato un client, per impostazione predefinita verrà aperta la versione 2013 di Lync Web App.

È possibile modificare il comportamento della pagina di partecipazione alle riunioni se si desidera consentire agli utenti di partecipare alle riunioni con Office Communicator 2007 R2 o Lync 2010 Attendant. Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Lync Server 2013, ma è possibile configurarle utilizzando il cmdlet CsWebServiceConfiguration.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>Parametri di CsWebServiceConfiguration per la pagina di partecipazione alla riunione

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro di CsWebServiceConfiguration</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Se il valore è impostato su true, gli utenti che partecipano a una riunione utilizzando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione utilizzando Office Communicator 2007 R2. Il valore predefinito è False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Per configurare la pagina di partecipazione alle riunioni utilizzando Lync Server 2013 Management Shell

1.  Avviare Lync Server 2013 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet seguente:
    
        Get-CsWebServiceConfiguration
    
    Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.

3.  Eseguire il comando riportato di seguito, con i parametri impostati su true o false, a seconda della preferenza (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server 2013 Management Shell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

