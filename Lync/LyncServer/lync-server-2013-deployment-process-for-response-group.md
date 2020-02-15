---
title: 'Lync Server 2013: processo di distribuzione per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Processo di distribuzione per Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-27_

In questa sezione viene fornita una panoramica delle fasi e dei passaggi necessari per la distribuzione dell'applicazione Response Group.

### <a name="response-group-deployment-process"></a>Processo di distribuzione di Response Group

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
<th>Autorizzazioni</th>
<th>Documentazione relativa alla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Installare l'applicazione Response Group</p></td>
<td><p>L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Installare i componenti per Response Group</p></td>
<td><p>I cmdlet di Lync Server, il pannello di controllo di Lync Server, lo strumento di configurazione di Response Group, la console di accesso e disconnessione degli agenti e il servizio Web client Response Group vengono installati come parte dei servizi Web. I servizi Web vengono installati quando si distribuisce un pool Enterprise Edition o un server Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Abilitare gli utenti per Lync 2013 e per VoIP aziendale</p></td>
<td><p>Abilitare gli utenti che saranno agenti per Lync Server e VoIP aziendale. Gli utenti devono essere abilitati per poter essere aggiunti a gruppi di agenti. In genere, gli utenti sono abilitati per Lync Server durante la distribuzione di Enterprise Edition o del server Standard Edition. Gli utenti sono abilitati per VoIP aziendale durante la distribuzione di VoIP aziendale.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disabilitare o riabilitare l'account utente per Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Abilitare gli utenti per VoIP aziendale in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Creazione e configurazione di Response Group, costituiti da gruppi di agenti, code e flussi di lavoro</p></td>
<td><ol>
<li><p>Utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per eseguire le operazioni seguenti:</p>
<ol>
<li><p>Creare e configurare gruppi di agenti.</p></li>
<li><p>Creare e configurare code.</p></li>
</ol></li>
<li><p>Facoltativamente, utilizzare Lync Server Management Shell per creare l'orario di ufficio e le festività di Response Group predefiniti.</p></li>
<li><p>Utilizzare lo strumento di configurazione di Response Group o Lync Server Management Shell per creare flussi di lavoro (gruppi di risposta o flussi di chiamate IVR), compresi gli orari di ufficio e le festività di Response Group personalizzati.</p>
<div>

> [!NOTE]  
> È possibile accedere allo strumento di configurazione di Response Group tramite il pannello di controllo di Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Creare gruppi di agenti di Response Group Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Creare code di Response Group in Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Optional Definire l'orario di ufficio di Response Group in Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Optional Definire i set di festività di Response Group in Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Creare o modificare un flusso di lavoro in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Facoltativo) Personalizzazione delle impostazioni a livello di applicazione</p></td>
<td><p>Utilizzo di Lync Server Management Shell per personalizzare la configurazione predefinita per la musica di attesa, il file audio predefinito per la musica in attesa, il periodo di richiamata dell'agente e la configurazione del contesto delle chiamate.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestione delle impostazioni dei Response Group a livello di applicazione in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Facoltativo) Delega della gestione dei Response Group</p></td>
<td><p>Assegnare agli utenti il ruolo CsResponseGroupManager per delegare la configurazione dei Response Group. I responsabili dei Response Group possono quindi configurare i Response Group a loro assegnati.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare la distribuzione di Response Group</p></td>
<td><p>Testare la risposta alle chiamate nei flussi di lavoro del gruppo di risposta e del sistema IVR per assicurare che la configurazione funzioni come previsto.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

