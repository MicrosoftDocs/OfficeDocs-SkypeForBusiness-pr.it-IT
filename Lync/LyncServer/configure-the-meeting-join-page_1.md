---
title: Configurare la pagina di partecipazione alle riunioni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464b690709444c540d9a1b06809a751b5b15d82a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503313"
---
# <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alle riunioni

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-14_

Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Lync 2013 è già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se non è installato un client, per impostazione predefinita verrà aperta la versione 2013 di Microsoft Lync Web App.

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
<td><p>Se si imposta questo parametro su True, verranno espanse e visualizzate automaticamente agli utenti opzioni alternative per partecipare a una conferenza online, ad esempio Office Communicator 2007 R2. Se invece si imposta il parametro su False (valore predefinito), queste opzioni saranno comunque disponibili, ma l'utente dovrà visualizzare manualmente l'elenco.</p></td>
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

