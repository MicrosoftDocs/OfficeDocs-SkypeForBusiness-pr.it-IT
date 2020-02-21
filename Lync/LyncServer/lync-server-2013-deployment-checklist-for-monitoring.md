---
title: 'Lync Server 2013: elenco di controllo di distribuzione per il monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca72cf23ea3cb761dd652efae63ef086cae2e198
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Elenco di controllo di distribuzione per il monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-05_

Anche se il monitoraggio è già installato e attivato in ogni Front End Server, è necessario intraprendere alcuni passaggi prima di poter effettivamente raccogliere dati di monitoraggio per Microsoft Lync Server 2013. Questi passaggi sono descritti nell'elenco di controllo seguente:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Fase</p></td>
<td><p>Passaggi</p></td>
<td><p>Appartenenza a gruppi e ruoli </p></td>
<td><p>Documentazione</p></td>
</tr>
<tr class="even">
<td><p><strong>Installare l'hardware e il software prerequisiti</strong></p></td>
<td><p>Installare una versione supportata di Microsoft SQL Server nel computer che fungerà da archivio dati back-end per il monitoraggio.</p></td>
<td><p>Utente di dominio che è anche membro del gruppo Administrators locale.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella Guida alla supportabilità</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella Guida relativa alla supportabilità</p></td>
</tr>
<tr class="odd">
<td><p><strong>Creare la topologia interna appropriata per supportare il monitoraggio</strong></p></td>
<td><p>Utilizzare il generatore di topologie di Lync Server 2013 per aggiungere database di monitoraggio alla topologia e quindi pubblicare la topologia aggiornata.</p></td>
<td><p>Per definire una topologia, un utente membro del gruppo utenti locali.</p>
<p>Per pubblicare la topologia, un utente membro del gruppo Domain Administrators e del gruppo RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associazione di un archivio di monitoraggio a un pool Front end in Lync Server 2013</a> nella Guida alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p><strong>Abilitare le impostazioni di monitoraggio appropriate</strong></p></td>
<td><p>Abilitare il monitoraggio di registrazione dettagli chiamata (CDR) e/o la qualità di esperienza (QoE) negli ambiti globali e/o del sito.</p></td>
<td><p>Un utente membro del gruppo RTCUniversalServerAdmins o a cui è stato assegnato un ruolo RBAC che fornisce l'accesso ai cmdlet CsCdrConfiguration e CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurazione delle impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Lync Server 2013</a> nella Guida alle operazioni</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

