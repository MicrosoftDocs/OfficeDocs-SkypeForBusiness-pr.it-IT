---
title: Processo di distribuzione per l'integrazione della messaggistica unificata locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d60b120db57ad73c33e682fa8150e99f5606e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Processo di distribuzione per l'integrazione della messaggistica unificata locale e di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-17_

Se si desidera integrare la messaggistica unificata di Exchange con Lync Server 2013, è necessario eseguire le attività descritte in questo argomento. È inoltre necessario esaminare le procedure consigliate per la pianificazione e la distribuzione descritte in [linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). In questo argomento si presuppone che sia stato distribuito Lync Server 2013 con un Mediation Server collocato e che siano stati abilitati gli utenti per Lync Server 2013, ma non necessariamente che siano stati eseguiti tutti i passaggi di distribuzione e configurazione per abilitare VoIP aziendale, come descritto in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.

<div>

## <a name="unified-messaging-integration-process"></a>Processo di integrazione di messaggistica unificata

<div>


> [!IMPORTANT]
> È importante coordinarsi con gli amministratori di Exchange dell'organizzazione per confermare le attività che ognuno di voi eseguirà per garantire un'integrazione agevole e corretta.



</div>


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
<td><p>Distribuire uno dei prodotti seguenti:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) o Service Pack più recente</p></li>
<li><p>Microsoft Exchange Server 2010 o Service Pack più recente</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Se si utilizza Microsoft Exchange Server 2013, installare i seguenti ruoli del server Exchange nella stessa foresta o in una foresta diversa come Lync Server 2013:</p>
<ul>
<li><p>Accesso client</p></li>
<li><p>Cassetta postale</p></li>
</ul>
<p>Se Microsoft Exchange Server 2013 e la messaggistica unificata di Exchange vengono installati in foreste diverse, configurare ogni foresta di Exchange in modo che consideri attendibile la foresta di Lync Server 2013.</p>
<p>Se si utilizza Exchange 2010, installare i seguenti ruoli del server Exchange nella stessa foresta o in una foresta diversa come Lync Server 2013:</p>
<ul>
<li><p>Messaggistica unificata</p></li>
<li><p>Trasporto Hub</p></li>
<li><p>Accesso client</p></li>
<li><p>Cassetta postale</p></li>
</ul>
<p>Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange in modo che consideri attendibile la foresta di Lync Server 2013.</p></td>
<td><p>Amministratori dell'organizzazione (se è il primo Exchange Server dell'organizzazione)</p>
<p>-O-</p>
<p>Amministratore dell'organizzazione di Exchange (se non è il primo Exchange Server dell'organizzazione)</p></td>
<td><p>Per informazioni sulla versione di Exchange di cui si dispone, vedere la documentazione appropriata:</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentazione relativa alla distribuzione di Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>Server 2007 all'indirizzo.</p>
</dd>
<dt><span></span></dt>
<dd><p>Documentazione relativa alla distribuzione del Service Pack di <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>Exchange Server 2010 o versione più recente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 pianificazione e distribuzione in <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installare i certificati.</p></td>
<td><p>Scaricare e installare i certificati per ogni server Messaggistica unificata di Exchange da un'autorità di certificazione (CA) radice attendibile. I certificati sono necessari per la sicurezza MTLS (Mutual Transport Level Security) tra i server che eseguono la messaggistica unificata di Exchange e Lync Server 2013.</p></td>
<td><p>Amministratori</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Creare e configurare un nuovo dial plan SIP di messaggistica unificata di Exchange.</p></td>
<td><p>Nel server Messaggistica unificata di Exchange, creare un dial plan SIP in base ai requisiti di distribuzione specifici dell'organizzazione.</p></td>
<td><p>Amministratore dell'organizzazione di Exchange</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come creare un dial plan&quot; URI SIP di messaggistica unificata <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>in.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere creare un dial plan&quot; di <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>messaggistica unificata in.</p>
<p>Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurare le impostazioni di protezione per il dial plan SIP di messaggistica unificata di Exchange.</p></td>
<td><p>Per crittografare il traffico VoIP aziendale, configurare le impostazioni di sicurezza nel dial plan SIP di messaggistica unificata di Exchange come <strong>SIP</strong> con protezione o <strong>protetto</strong>. Questo è un passaggio particolarmente importante se è stato distribuito o si intende distribuire i dispositivi Lync Phone Edition nell'ambiente in uso. Affinché i dispositivi Lync Phone Edition funzionino in un ambiente con integrazione di messaggistica unificata di Exchange, le impostazioni di crittografia di Lync Server devono essere allineate alle impostazioni di protezione di messaggistica unificata di Exchange. Per informazioni dettagliate, vedere la documentazione relativa alla distribuzione.</p></td>
<td><p>Amministratore dell'organizzazione di Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></p>
<p>Per Exchange 2007 SP1 o Service Pack più recente, vedere anche:</p>
<p>&quot;Informazioni su come configurare la sicurezza in un dial plan&quot; di messaggistica <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>unificata in.</p>
<p>Per Exchange 2010 o Service Pack più recente, vedere anche:</p>
<p>&quot;Configurare la sicurezza VoIP su un dial plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>di messaggistica unificata.</p>
<p>Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Aggiungere i server Messaggistica unificata al dial plan SIP di messaggistica unificata di Exchange.</p></td>
<td><p>Per consentire a un server di Messaggistica unificata appena installato di rispondere alle chiamate in arrivo e di elaborarle, è necessario aggiungere il server di Messaggistica unificata a un dial plan di Messaggistica unificata. In questo caso, aggiungere il server al dial plan SIP di messaggistica unificata di Exchange.</p></td>
<td><p>Amministratori</p>
<p>Amministratori di Exchange Server</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere il server Messaggistica unificata a un dial&quot; Plan <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>all'indirizzo.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere Visualizzazione o configurazione delle proprietà di un server&quot; di <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>messaggistica unificata in.</p>
<p>Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurare cassette postali con indirizzi SIP</p></td>
<td><p>Assegnare gli indirizzi SIP alle cassette postali degli utenti di VoIP aziendale che utilizzeranno le funzionalità di messaggistica unificata di Exchange.</p></td>
<td><p>Amministratore di Lync Server 2013</p>
<p>Amministratore destinatari di Exchange</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere, rimuovere o modificare un indirizzo SIP per un utente&quot; abilitato alla messaggistica unificata <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>in.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere Modificare un indirizzo SIP per un utente&quot; abilitato alla messaggistica <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>unificata in.</p>
<p>Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Eseguire lo script exchucutil.ps1.</p></td>
<td><p>Nel server che esegue i servizi di messaggistica unificata di Exchange, aprire Exchange Management Shell ed eseguire lo script exchucutil. ps1, che esegue le operazioni seguenti:</p>
<ul>
<li><p>Concede l'autorizzazione di Lync Server 2013 per la lettura degli oggetti di servizi di dominio Active Directory di messaggistica unificata di Exchange, in particolare i dial plan SIP creati nell'attività precedente.</p></li>
<li><p>Crea un oggetto gateway IP di messaggistica unificata in Active Directory per ogni pool di Lync Server 2013 Enterprise Edition o un server Standard Edition che ospita gli utenti abilitati per VoIP aziendale.</p></li>
<li><p>Crea un gruppo di risposta di messaggistica unificata di Exchange per ogni gateway. L'identificatore pilota del gruppo di risposta sarà il nome del dial plan associato al gateway corrispondente. Deve esistere un mapping uno a uno in caso di più dial plan.</p></li>
</ul></td>
<td><p>Amministratore dell'organizzazione di Exchange</p>
<p>Amministratore destinatari di Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare i dial plan di Lync Server 2013.</p></td>
<td><p>Se si esegue l'integrazione con Exchange 2007 SP1 o Service Pack più recente o Exchange 2010, creare un nuovo dial plan VoIP aziendale con un nome che corrisponda al nome di dominio completo (FQDN) del dial plan di messaggistica unificata di Exchange.</p>



> [!NOTE]
> Sarà necessario eseguire questa operazione per ogni dial plan di messaggistica unificata.


<p>Se si esegue l'integrazione con Exchange 2010 SP1, assicurarsi che siano stati configurati piani di chiamata VoIP Enterprise a livello globale o a livello di sito o di pool.</p>



> [!NOTE]
> Se si esegue l'integrazione con Exchange 2010 SP1, il dial plan di Lync Server e i nomi dei dial plan SIP di messaggistica unificata di Exchange non devono corrispondere.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configurazione di dial plan in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Eseguire lo strumento di integrazione della messaggistica unificata di Exchange.</p></td>
<td><p>In Lync Server 2013 eseguire <strong>OcsUmUtil. exe</strong>, che:</p>
<ul>
<li><p>Crea oggetti contatto Accesso sottoscrittore e Operatore automatico.</p></li>
<li><p>Verifica la presenza di un dial plan VoIP aziendale con un nome che corrisponde all'FQDN del dial plan di messaggistica unificata di Exchange. Se si esegue Exchange 2010 SP1 o versione successiva, i nomi dei dial plan non devono corrispondere ed è possibile ignorare l'avviso dello strumento.</p></li>
</ul>
<p>Questo strumento funziona analizzando Active Directory per le impostazioni di messaggistica unificata di Exchange e consentendo all'amministratore di Lync Server 2013 di visualizzare, creare e modificare gli oggetti contatto.</p></td>
<td><p>RTCUniversalServerAdmins <em>e</em> TCUniversalUserAdmins</p>



> [!IMPORTANT]
> Per eseguire correttamente ocsumutil.exe, l'utente deve appartenere a entrambi i gruppi.





> [!NOTE]
> Per creare oggetti contatto, l'utente che esegue ocsumutil.exe deve disporre dell'autorizzazione appropriata per l'unità organizzativa di Active Directory in cui sono archiviati i nuovi oggetti contatto. Questa autorizzazione può essere concessa eseguendo il cmdlet <STRONG>Grant-CsOUPermission</STRONG> . Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Se necessario, eseguire altre operazioni di configurazione di VoIP aziendale.</p></td>
<td><p>Se le impostazioni di VoIP aziendale non sono state già configurate nei server o negli utenti, eseguire una o più delle operazioni seguenti:</p>
<ul>
<li><p>Distribuire e configurare</p>
<p>Gateway PSTN (Public Switched Telephone Network) e Mediation Server</p></li>
<li><p>Definire criteri vocali, record di utilizzo PSTN e route di chiamate in uscita.</p></li>
<li><p>Abilitare gli utenti per VoIP aziendale.</p></li>
<li><p>Facoltativamente, configurare utenti specifici con i dial plan.</p></li>
</ul>
<p>È possibile che siano necessarie altre operazioni di configurazione a seconda delle funzionalità di VoIP aziendale abilitate.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Vedere gli argomenti nelle sezioni seguenti:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Abilitare gli utenti di VoIP aziendale per la messaggistica unificata di Exchange.</p></td>
<td><p>Sul server Messaggistica unificata di Exchange, verificare che sia stato creato un criterio cassetta postale di messaggistica unificata e che ogni utente disponga di un'assegnazione univoca del numero di interno e quindi abilitare l'utente alla messaggistica unificata.</p></td>
<td><p>Amministratore destinatari di Exchange</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere How to Enable a user for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere Abilitare un utente per la messaggistica&quot; unificata in <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</p>
<p>Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

