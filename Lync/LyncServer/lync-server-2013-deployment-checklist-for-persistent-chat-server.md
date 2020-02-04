---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per il server Chat persistente'
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
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

Distribuzione di Lync Server 2013, il server di chat persistente richiede di distribuirlo nella sequenza corretta e di completare tutti i passaggi necessari per la distribuzione.

<div>

## <a name="deployment-sequence"></a>Sequenza di distribuzione

È possibile distribuire il server di chat persistente dopo la distribuzione della topologia iniziale, incluso almeno un Lync Server 2013, un pool Front end o un Lync Server 2013, un server Standard Edition. Questo argomento descrive come distribuire il server di chat persistente aggiungendolo a una distribuzione esistente.

</div>

<div>

## <a name="deployment-process"></a>Processo di distribuzione

La tabella seguente elenca i passaggi di base per distribuire il server di chat persistente e fornisce collegamenti per ulteriori dettagli.

### <a name="persistent-chat-server-deployment-process"></a>Processo di distribuzione del server di chat persistente

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
<th>Ruoli obbligatori e appartenenze ai gruppi</th>
<th>Argomenti correlati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installare hardware e software prerequisiti</strong></p></td>
<td><p>Sull'hardware che soddisfa i requisiti di sistema, installare le operazioni seguenti:</p>
<ul>
<li><p>Nei server front end del server di chat persistente:</p></li>
</ul>
<ul>
<li><p>Sistema operativo che soddisfa i requisiti di sistema</p></li>
<li><p>Prerequisiti software per i computer che eseguono Lync Server 2013</p></li>
<li><p>SQL Server nel server che ospiterà il database del server di chat persistente</p></li>
</ul>
<p>Se è necessaria la conformità del server di chat persistente:</p>
<ul>
<li><p>SQL Server nel server che ospita il database di conformità del server di chat persistente</p></li>
</ul></td>
<td><p>Qualsiasi utente membro del gruppo Administrators locale.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella documentazione relativa al supporto tecnico</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisiti tecnici per il server di chat persistente in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Creare la topologia interna appropriata per supportare il server di chat persistente e, facoltativamente, la conformità della chat persistente</strong></p></td>
<td><p>Eseguire Generatore di topologie per aggiungere un pool di server di chat persistente alla topologia:</p>
<ul>
<li><p>Aggiungere componenti del server di chat persistenti alla topologia</p></li>
<li><p>Creare un database di SQL Server per l'archivio di Chat Server persistente (e un backup di SQL Server per il ripristino di emergenza)</p></li>
<li><p>Definire un nuovo archivio di file di Lync o usare un archivio file di Lync esistente per i file del server di chat persistente</p></li>
<li><p>Associare il pool di Lync Server 2013 che può instradare le richieste a questo pool di server di chat persistente</p></li>
</ul>
<p>Se è necessaria la conformità della chat persistente:</p>
<ul>
<li><p>Aggiungere lo Store di conformità della chat persistente</p></li>
<li><p>Fare clic sulla casella di controllo della definizione del pool di Persistent Chat Server per abilitare la conformità</p></li>
<li><p>Pubblicare la topologia</p></li>
</ul>
<p>Se si installa il server di chat persistente in Standard Edition, il nome di dominio completo (FQDN) del pool del server di chat persistente deve corrispondere al server Standard Edition e i database di SQL Server sono collocati nell'istanza di SQL Server Express nello standard Server Edition</p></td>
<td><p>Per definire una topologia, un account membro del gruppo utenti locali.</p>
<p>Per pubblicare la topologia, un account che sia un membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che l'utente disponga anche delle autorizzazioni di controllo completo (lettura/scrittura/modifica) nell'archivio di file di Lync per i file del server di chat permanenti, in modo che il generatore di topologia possa configurare gli elenchi DACL necessari.</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p><strong>Distribuire il server Chat persistente</strong></p></td>
<td><p>Eseguire la configurazione di Lync Server in tutti i computer che eseguono il server di chat persistente. La configurazione del server di chat persistente è integrata nella distribuzione guidata di Lync Server 2013 che fornisce le istruzioni seguenti:</p>
<ul>
<li><p>Distribuire l'archivio di gestione locale</p></li>
<li><p>Installare i servizi server di chat persistenti</p></li>
<li><p>Richiedere e assegnare certificati</p></li>
<li><p>Eseguire e avviare i servizi</p></li>
</ul></td>
<td><p>Qualsiasi utente membro del gruppo Administrators locale.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Distribuzione di un server di chat persistente in Lync server 2013</a> nella documentazione di distribuzione</p></td>
</tr>
<tr class="even">
<td><p><strong>Creare un amministratore di Chat persistente</strong></p></td>
<td><p>Aggiungere utenti al gruppo di sicurezza CsPersistentChatAdministrator.</p></td>
<td><p>Qualsiasi utente membro di Domain Administrators.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Aggiunta di un amministratore di chat persistente in Lync Server 2013</a> nella documentazione di distribuzione</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare il server Chat persistente</strong></p></td>
<td><p>Configurare gli utenti:</p>
<ul>
<li><p>L'utente deve essere abilitato tramite criteri per accedere al server di chat persistente. Per impostazione predefinita, il criterio è disattivato per tutti gli utenti e può essere definito in ambito globale/sito/pool/User.</p></li>
<li><p>Configurare le impostazioni</p></li>
</ul></td>
<td><p>L'utente deve essere un membro di CsPersistentChatAdministrator. Per modificare i criteri, l'utente deve essere in CsUserAdministrator, almeno.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configurazione del server di chat persistente in Lync server 2013</a> nella documentazione di distribuzione</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> È possibile distribuire uno o più pool di server di chat permanenti. Supportiamo più pool di server di chat persistenti per motivi normativi per cui i dati generati in una determinata area geografica devono rimanere in quell'area geografica. Ad esempio, se si distribuisce un pool di server di chat persistente a Chicago e un altro a Zurigo per conformarsi alle normative per i dati in Svizzera, gli utenti possono connettersi alle camere in entrambi i pool di server della chat persistente, purché abbiano accesso.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

