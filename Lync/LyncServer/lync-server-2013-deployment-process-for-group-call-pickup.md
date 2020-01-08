---
title: 'Lync Server 2013: processo di distribuzione per il ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Processo di distribuzione per il ritiro delle chiamate di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione della raccolta di chiamate di gruppo. È necessario distribuire Enterprise Edition o Standard Edition con Enterprise Voice prima di configurare il ritiro delle chiamate di gruppo. I componenti necessari per il ritiro delle chiamate di gruppo sono installati e abilitati quando si distribuisce VoIP aziendale.

### <a name="group-call-pickup-deployment-process"></a>Processo di distribuzione del pickup della chiamata di gruppo

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
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Abilitare lo strumento SEFAUtil Resource Kit nella topologia</p></td>
<td><ol>
<li><p>Usa il cmdlet <strong>New-CsTrustedApplicationPool</strong> per creare un nuovo pool di applicazioni attendibili.</p></li>
<li><p>Usa il cmdlet <strong>New-CsTrustedApplication</strong> per specificare lo strumento SEFAUtil come applicazione attendibile.</p></li>
<li><p>Eseguire il cmdlet <strong>Enable-CsTopology</strong> per abilitare la topologia.</p></li>
<li><p>Installare gli strumenti del Resource Kit in un server front-end che si trova nel pool di applicazioni attendibile creato nel passaggio 1.</p></li>
<li><p>Verificare che SEFAUtil sia in corso correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Distribuire lo strumento SEFAUtil in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare intervalli di numeri di raccolta chiamate nella tabella Orbit di Call Park</p></td>
<td><p>Usa il cmdlet <strong>New-CsCallParkOrbit</strong> per creare intervalli di numeri di prelievo delle chiamate nella tabella Orbit di Call Park e assegnare gli intervalli di prelievo delle chiamate per il tipo GroupPickup.</p>
<div>

> [!NOTE]  
> È necessario usare Lync Server Management Shell per creare, modificare, rimuovere e visualizzare intervalli di numeri di prelievo delle chiamate di gruppo nella tabella Orbit di Call Park. Gli intervalli di numeri di raccolta delle chiamate di gruppo non sono disponibili nel pannello di controllo di Lync Server.


</div>
<div>

> [!NOTE]  
> Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri sono in genere configurati come blocco di estensioni virtuali. L'assegnazione di numeri DID (Direct inwarding Dialing) come numeri di intervallo nella tabella Orbit di parcheggio delle chiamate non è supportata.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Assegnare un numero di prelievo delle chiamate agli utenti e abilitare il ritiro delle chiamate di gruppo per gli utenti</p></td>
<td><p>Usa il parametro/enablegrouppickup nello strumento Resource Kit di SEFAUtil per abilitare il ritiro delle chiamate di gruppo e assegnare un numero di prelievo chiamate per gli utenti.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnare un numero di gruppo</a></p></td>
</tr>
<tr class="even">
<td><p>Informare gli utenti del numero di prelievo delle chiamate assegnate e di qualsiasi altro numero di interesse</p></td>
<td><p>Poiché qualsiasi utente può recuperare una chiamata effettuata a un utente di un pick-up di chiamata di gruppo, gli utenti potrebbero voler monitorare più di un gruppo.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicare le assegnazioni di ritiro delle chiamate di gruppo agli utenti in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare la distribuzione del ritiro delle chiamate di gruppo</p></td>
<td><p>Testare il posizionamento e il recupero delle chiamate per verificare che la configurazione funzioni come previsto.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Opzionale Verificare la distribuzione del ritiro delle chiamate di gruppo in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

