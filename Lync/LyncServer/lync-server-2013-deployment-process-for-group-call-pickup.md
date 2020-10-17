---
title: 'Lync Server 2013: processo di distribuzione per il ritiro delle chiamate di gruppo'
description: 'Lync Server 2013: processo di distribuzione per il prelievo delle chiamate di gruppo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a01409b257c685ae71dfdb13074f2d8ea590cd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552492"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Processo di distribuzione per il ritiro delle chiamate di gruppo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione del prelievo delle chiamate di gruppo. Prima di configurare il prelievo delle chiamate di gruppo, è necessario distribuire Enterprise Edition o Standard Edition con VoIP aziendale. I componenti richiesti dal ritiro delle chiamate di gruppo vengono installati e abilitati quando si distribuisce VoIP aziendale.

### <a name="group-call-pickup-deployment-process"></a>Processo di distribuzione del prelievo delle chiamate di gruppo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Gruppi e ruoli obbligatori</th>
<th>Documentazione sulla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Abilitare lo strumento Resource Kit di SEFAUtil nella topologia</p></td>
<td><ol>
<li><p>Utilizzare il cmdlet <strong>New-CsTrustedApplicationPool</strong> per creare un nuovo pool di applicazioni attendibili.</p></li>
<li><p>Utilizzare il cmdlet <strong>New-CsTrustedApplication</strong> per specificare lo strumento SEFAUtil come applicazione attendibile.</p></li>
<li><p>Eseguire il cmdlet <strong>Enable-CsTopology</strong> per abilitare la topologia.</p></li>
<li><p>Installare gli strumenti del Resource Kit in un front end server nel pool di applicazioni attendibili creato nel passaggio 1.</p></li>
<li><p>Verificare che SEFAUtil sia in esecuzione correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Distribuire lo strumento SEFAUtil in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare gli intervalli di numeri di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata</p></td>
<td><p>Utilizzare il cmdlet <strong>New-CsCallParkOrbit</strong> per creare intervalli di numeri di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata e assegnare gli intervalli di prelievo delle chiamate di tipo GroupPickup.</p>
<div>

> [!NOTE]  
> È necessario utilizzare Lync Server Management Shell per creare, modificare, rimuovere e visualizzare gli intervalli di numeri di prelievo delle chiamate di gruppo nella tabella orbit del parcheggio di chiamata. Gli intervalli di numeri di prelievo delle chiamate di gruppo non sono disponibili nel pannello di controllo di Lync Server.


</div>
<div>

> [!NOTE]  
> Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri vengono in genere configurati come blocco di estensioni virtuali. L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di intervallo nella tabella orbit del parcheggio di chiamata non è supportata.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Assegnare un numero di prelievo delle chiamate agli utenti e abilitare il prelievo delle chiamate di gruppo per gli utenti</p></td>
<td><p>Utilizzare il parametro/enablegrouppickup nello strumento Resource Kit di SEFAUtil per abilitare il prelievo delle chiamate di gruppo e assegnare un numero di prelievo di chiamata per gli utenti.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Abilitazione del prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnazione di un numero di gruppo</a></p></td>
</tr>
<tr class="even">
<td><p>Notificare agli utenti il numero di prelievo di chiamata assegnato e qualsiasi altro numero di interesse</p></td>
<td><p>Poiché qualsiasi utente può recuperare una chiamata effettuata a un utente di prelievo delle chiamate di gruppo, gli utenti possono eseguire il monitoraggio di più di un gruppo.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicare le assegnazioni di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare la distribuzione del prelievo delle chiamate di gruppo</p></td>
<td><p>Provare a inserire e recuperare le chiamate per assicurarsi che la configurazione funzioni come previsto.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional Verificare la distribuzione del prelievo delle chiamate di gruppo in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

