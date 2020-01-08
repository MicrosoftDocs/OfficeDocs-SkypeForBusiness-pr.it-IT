---
title: 'Lync Server 2013: processo di distribuzione per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Processo di distribuzione per il gruppo di risposte in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-27_

Questa sezione offre una panoramica delle fasi e dei passaggi necessari per la distribuzione dell'applicazione Response Group.

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
<th>Documentazione di distribuzione</th>
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
<td><p>Installare componenti per il gruppo di risposte</p></td>
<td><p>I cmdlet di Lync Server, il pannello di controllo di Lync Server, lo strumento di configurazione dei gruppi di risposta, la console di accesso e di disconnessione degli agenti e il servizio Web client di Response Group vengono installati come parte dei servizi Web. I servizi Web vengono installati quando si distribuisce un pool di Enterprise Edition o un server Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Abilitare gli utenti per Lync 2013 e per Enterprise Voice</p></td>
<td><p>Abilitare gli utenti che saranno agenti per Lync Server e Enterprise Voice. Gli utenti devono essere abilitati prima di poterli aggiungere ai gruppi di agenti. In genere gli utenti sono abilitati per Lync Server durante la distribuzione di Enterprise Edition o Standard Edition Server. Gli utenti sono abilitati per VoIP aziendale durante la distribuzione di VoIP aziendale.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disabilitare o riattivare l'account utente per Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Consentire agli utenti di VoIP aziendale in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Creare e configurare Response Groups, costituiti da gruppi di agenti, code e flussi di lavoro</p></td>
<td><ol>
<li><p>Usare il pannello di controllo di Lync Server o Lync Server Management Shell per eseguire le operazioni seguenti:</p>
<ol>
<li><p>Creare e configurare gruppi di agenti.</p></li>
<li><p>Creare e configurare le code.</p></li>
</ol></li>
<li><p>Facoltativamente, è possibile usare Lync Server Management Shell per creare orari e festività di un gruppo di risposte predefinito.</p></li>
<li><p>Usare lo strumento di configurazione del gruppo di risposte o Lync Server Management Shell per creare flussi di lavoro (gruppi di risposta o flussi di chiamate IVR), inclusi gli orari di lavoro e le festività di Response Group personalizzati.</p>
<div>

> [!NOTE]  
> È possibile accedere allo strumento di configurazione del Response Group tramite il pannello di controllo di Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Creare gruppi di agenti per Response Group in Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Creare code di Response Group in Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Opzionale Definire le ore lavorative per il gruppo di risposte in Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Opzionale Definire set di festività di Response Group in Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Creare o modificare un flusso di lavoro in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Opzionale Personalizzare le impostazioni a livello di applicazione</p></td>
<td><p>Usare Lync Server Management Shell per personalizzare la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in attesa, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Opzionale Gestione dei delegati di Response Groups</p></td>
<td><p>Assegna agli utenti il ruolo CsResponseGroupManager per delegare la configurazione dei gruppi di risposta. I responsabili del gruppo di risposte possono quindi configurare i gruppi di risposte assegnati.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare la distribuzione di Response Group</p></td>
<td><p>Provare a rispondere alle chiamate al gruppo di ricerca e ai flussi di lavoro di risposta vocale interattivi per verificare che la configurazione funzioni come previsto.</p></td>
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

