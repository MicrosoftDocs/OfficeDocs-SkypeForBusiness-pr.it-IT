---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per il monitoraggio'
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
ms.openlocfilehash: 71b7d69054df266139f3f13ca0ca53e1803f44b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Elenco di controllo di distribuzione per il monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-05_

Anche se il monitoraggio è già installato e attivato in ogni server front-end, è necessario intraprendere diversi passaggi prima di poter effettivamente raccogliere dati di monitoraggio per Microsoft Lync Server 2013. Questi passaggi sono descritti nell'elenco di controllo seguente:


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
<td><p>Appartenenza a ruoli e gruppi</p></td>
<td><p>Documentazione</p></td>
</tr>
<tr class="even">
<td><p><strong>Installare hardware e software prerequisiti</strong></p></td>
<td><p>Installare una versione supportata di Microsoft SQL Server nel computer che fungerà da archivio dati back-end per il monitoraggio.</p></td>
<td><p>Utente del dominio che è anche membro del gruppo Administrators locale.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella Guida alla supportabilità</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella Guida alla supportabilità</p></td>
</tr>
<tr class="odd">
<td><p><strong>Creare la topologia interna appropriata per supportare il monitoraggio</strong></p></td>
<td><p>Usare il generatore di topologia di Lync Server 2013 per aggiungere database di monitoraggio alla topologia, quindi pubblicato la topologia aggiornata.</p></td>
<td><p>Per definire una topologia, un utente membro del gruppo utenti locali.</p>
<p>Per pubblicare la topologia, un utente membro se il gruppo Domain Administrators e il gruppo RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associazione di un archivio di monitoraggio con un pool Front-end in Lync Server 2013</a> nella Guida alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p><strong>Abilitare le impostazioni di monitoraggio appropriate</strong></p></td>
<td><p>Abilitare il monitoraggio della registrazione dei dettagli delle chiamate (CDR) e/o la qualità dell'esperienza (QoE) negli ambiti globali e/o del sito.</p></td>
<td><p>Un utente membro del gruppo RTCUniversalServerAdmins o a cui è stato assegnato un ruolo RBAC che consente di accedere ai cmdlet CsCdrConfiguration e CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza in Lync Server 2013</a> nella Guida alle operazioni</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

