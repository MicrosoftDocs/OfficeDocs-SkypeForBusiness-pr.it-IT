---
title: 'Lync Server 2013: elenco di controllo di distribuzione per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a67d8a755a5647424a00aa7e534f736a4c0b5aa3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-16_

Distribuzione di Lync Server 2013, il server Chat persistente richiede che venga distribuito nella sequenza corretta e che vengano completati tutti i passaggi necessari per la distribuzione.

<div>

## <a name="deployment-sequence"></a>Sequenza di distribuzione

È possibile distribuire il server Chat persistente dopo la distribuzione della topologia iniziale, tra cui almeno un Lync Server 2013, un pool Front end o un server Lync Server 2013, Standard Edition. In questo argomento viene descritto come distribuire il server Chat persistente aggiungendolo a una distribuzione esistente.

</div>

<div>

## <a name="deployment-process"></a>Processo di distribuzione

Nella tabella seguente sono elencati i passaggi di base per la distribuzione del server Chat persistente e vengono forniti collegamenti per ulteriori dettagli.

### <a name="persistent-chat-server-deployment-process"></a>Processo di distribuzione del server Chat persistente

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Attività</th>
<th>Passaggi</th>
<th>Appartenenze a gruppi e ruoli richiesti</th>
<th>Argomenti correlati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installare l'hardware e il software prerequisiti</strong></p></td>
<td><p>Nell'hardware che soddisfa i requisiti di sistema installare gli elementi seguenti:</p>
<ul>
<li><p>Nei front end server di Persistent Chat:</p></li>
</ul>
<ul>
<li><p>Sistema operativo che soddisfa i requisiti di sistema seguenti</p></li>
<li><p>Prerequisiti software per i computer in cui è in esecuzione Lync Server 2013</p></li>
<li><p>SQL Server nel server che ospiterà il database del server Chat persistente</p></li>
</ul>
<p>Se è necessaria la conformità del server Chat persistente:</p>
<ul>
<li><p>SQL Server nel server che ospiterà il database di conformità del server Chat persistente</p></li>
</ul></td>
<td><p>Tutti gli utenti membri del gruppo Administrators locale.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella documentazione relativa alla supportabilità</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisiti tecnici per il server Chat persistente in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Creare la topologia interna appropriata per supportare il server Chat persistente (e, facoltativamente, la conformità chat persistente)</strong></p></td>
<td><p>Eseguire Generatore di topologie per aggiungere un pool di server Chat persistente alla topologia:</p>
<ul>
<li><p>Aggiungere componenti del server Chat persistente alla topologia</p></li>
<li><p>Creare un database di SQL Server per l'archivio del server Chat persistente (e un backup di SQL Server per il ripristino di emergenza)</p></li>
<li><p>Definire un nuovo archivio file di Lync o utilizzare un archivio file di Lync esistente per i file del server Chat persistente</p></li>
<li><p>Associare il pool di Lync Server 2013 in grado di instradare le richieste al pool di server Chat persistente</p></li>
</ul>
<p>Se è necessaria la conformità della chat persistente:</p>
<ul>
<li><p>Aggiungere l'archivio di conformità di chat persistente</p></li>
<li><p>Fare clic sulla casella di controllo definizione pool di server Chat persistente per abilitare la conformità</p></li>
<li><p>Pubblicare la topologia</p></li>
</ul>
<p>Se si installa il server Chat persistente in Standard Edition, il nome di dominio completo (FQDN) del pool del server di chat persistente deve corrispondere al server Standard Edition e i database di SQL Server sono collocati nell'istanza di SQL Server Express nello standard Server Edition</p></td>
<td><p>Per definire una topologia, un account membro del gruppo Users locale.</p>
<p>Per pubblicare la topologia, un account membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e l'utente deve disporre anche di autorizzazioni di controllo completo (lettura/scrittura/modifica) nell'archivio file di Lync per i file del server Chat persistente, in modo che il generatore di topologie possa configurare gli elenchi DACL necessari.</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Aggiunta del server Chat persistente alla distribuzione in Lync server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p><strong>Distribuire il server Chat persistente</strong></p></td>
<td><p>Eseguire il programma di installazione di Lync Server in tutti i computer che eseguono il server Chat persistente. La configurazione del server Chat persistente è integrata nella distribuzione guidata di Lync Server 2013 che fornisce le istruzioni seguenti:</p>
<ul>
<li><p>Distribuire l'archivio di gestione locale</p></li>
<li><p>Installare i servizi del server Chat persistente</p></li>
<li><p>Richiedere e assegnare i certificati</p></li>
<li><p>Eseguire e avviare i servizi</p></li>
</ul></td>
<td><p>Tutti gli utenti membri del gruppo Administrators locale.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Distribuzione del server Chat persistente in Lync server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p><strong>Creare un amministratore di chat persistente</strong></p></td>
<td><p>Aggiungere gli utenti al gruppo di sicurezza CsPersistentChatAdministrator.</p></td>
<td><p>Tutti gli utenti membri del gruppo degli amministratori di dominio.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Aggiunta di un amministratore di chat persistente in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare il server chat persistente</strong></p></td>
<td><p>Configurare gli utenti:</p>
<ul>
<li><p>L'utente deve essere abilitato dai criteri per accedere al server Chat persistente. Per impostazione predefinita, i criteri sono disattivati per tutti gli utenti e possono essere definiti nell'ambito globale, del sito, del pool e dell'utente</p></li>
<li><p>Configurare le impostazioni</p></li>
</ul></td>
<td><p>L'utente deve essere membro di CsPersistentChatAdministrator. Per modificare i criteri, l'utente deve essere almeno membro di CsUserAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configurazione del server Chat persistente in Lync server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> È possibile distribuire uno o più pool di server Chat persistente. Sono supportati più pool di server Chat persistente per motivi normativi per i quali è necessario che i dati generati in un'area geografica siano presenti in tale area. Ad esempio, se si distribuisce un pool di server Chat persistente a Chicago e un altro a Zurigo per conformarsi alle normative per i dati svizzeri, gli utenti possono connettersi alle chat room in entrambi i pool di server con persistent, a condizione che dispongano dell'accesso.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

