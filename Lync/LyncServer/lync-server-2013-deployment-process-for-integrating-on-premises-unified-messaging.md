---
title: Processo di distribuzione per l'integrazione della messaggistica unificata locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Processo di distribuzione per l'integrazione della messaggistica unificata locale con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-17_

Se si vuole integrare la messaggistica UNIFICAta di Exchange con Lync Server 2013, è necessario eseguire le attività descritte in questo argomento. Verificare inoltre le procedure consigliate per la pianificazione e la distribuzione descritte in [linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). Questo argomento presuppone che sia stato distribuito Lync Server 2013 con un Mediation Server collocato e che siano stati abilitati gli utenti per Lync Server 2013, ma non necessariamente che siano stati eseguiti tutti i passaggi per la distribuzione e la configurazione per abilitare VoIP aziendale, come descritto in [distribuzione di VoIP aziendale in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.

<div>

## <a name="unified-messaging-integration-process"></a>Processo di integrazione della messaggistica unificata

<div>


> [!IMPORTANT]
> È importante coordinarsi con gli amministratori di Exchange dell'organizzazione per confermare le attività che ognuno di voi eseguirà per garantire una corretta integrazione.



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
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Distribuire una delle operazioni seguenti:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) o Service Pack più recente</p></li>
<li><p>Microsoft Exchange Server 2010 o Service Pack più recente</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Se si usa Microsoft Exchange Server 2013, installare i ruoli di Exchange Server seguenti nella stessa foresta o in un'altra foresta come Lync Server 2013:</p>
<ul>
<li><p>Accesso client</p></li>
<li><p>Cassetta postale</p></li>
</ul>
<p>Se Microsoft Exchange Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta di Lync Server 2013.</p>
<p>Se si usa Exchange 2010, installare i ruoli di Exchange Server seguenti nella stessa foresta o in un'altra foresta come Lync Server 2013:</p>
<ul>
<li><p>Messaggistica unificata</p></li>
<li><p>Trasporto Hub</p></li>
<li><p>Accesso client</p></li>
<li><p>Cassetta postale</p></li>
</ul>
<p>Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta di Lync Server 2013.</p></td>
<td><p>Amministratori organizzazione (se si tratta del primo server di Exchange nell'organizzazione)</p>
<p>O</p>
<p>Amministratore dell'organizzazione di Exchange (se non si tratta del primo server di Exchange nell'organizzazione)</p></td>
<td><p>Vedere la documentazione appropriata per la versione di Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentazione di distribuzione di <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>Exchange Server 2007.</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 o la documentazione di distribuzione del <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Service Pack più recente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Pianificazione e distribuzione di <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>Microsoft Exchange Server 2013.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installare i certificati.</p></td>
<td><p>Scaricare e installare certificati per ogni server Messaggistica unificata di Exchange da un'autorità di certificazione radice attendibile (CA). I certificati sono necessari per la sicurezza MTLS (Mutual Transport Level Security) tra i server che usano Exchange UM e Lync Server 2013.</p></td>
<td><p>Gli amministratori</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Creare e configurare un nuovo dial plan di messaggistica unificata di Exchange.</p></td>
<td><p>Nel server Messaggistica unificata di Exchange creare un dial plan SIP basato sui requisiti di distribuzione specifici dell'organizzazione.</p></td>
<td><p>Amministratore dell'organizzazione di Exchange</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come creare un dial plan&quot; URI SIP di messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere creare un dial plan&quot; di <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>messaggistica unificata.</p>
<p>Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurare le impostazioni di sicurezza per il dial plan di messaggistica unificata di Exchange.</p></td>
<td><p>Per crittografare il traffico VoIP aziendale, configurare le impostazioni di sicurezza nel dial plan di messaggistica unificata di Exchange come <strong>protetto tramite SIP</strong> o <strong>protetto</strong>. Si tratta di un passaggio particolarmente importante se si è distribuito o si prevede di distribuire i dispositivi Lync Phone Edition nell'ambiente. Per i dispositivi Lync Phone Edition per funzionare in un ambiente con integrazione di messaggistica unificata di Exchange, le impostazioni di crittografia di Lync Server devono essere allineate alle impostazioni di sicurezza del dial plan di Exchange UM. Per informazioni dettagliate, vedere la documentazione relativa alla distribuzione.</p></td>
<td><p>Amministratore dell'organizzazione di Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></p>
<p>Per Exchange 2007 SP1 o Service Pack più recente, vedere anche:</p>
<p>&quot;Come configurare la sicurezza in un dial plan&quot; di <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>messaggistica unificata.</p>
<p>Per Exchange 2010 o Service Pack più recente, vedere anche:</p>
<p>&quot;Configurare la sicurezza VoIP in un dial plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>di messaggistica unificata.</p>
<p>Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Aggiungere server di messaggistica unificata al dial plan di messaggistica unificata di Exchange.</p></td>
<td><p>Per abilitare un server di messaggistica unificata appena installato per rispondere ed elaborare le chiamate in arrivo, è necessario aggiungere il server Messaggistica unificata a un dial plan di messaggistica unificata. In questo caso, aggiungere il server al dial plan di messaggistica unificata di Exchange.</p></td>
<td><p>Gli amministratori</p>
<p>Amministratori di Exchange Server</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere un server di messaggistica unificata a un&quot; Dial <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>Plan.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere visualizzare o configurare le proprietà di un server&quot; messaggistica <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>unificata.</p>
<p>Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurare le cassette postali con indirizzi SIP.</p></td>
<td><p>Assegna indirizzi SIP alle cassette postali degli utenti di VoIP aziendale che utilizzeranno le funzionalità di messaggistica unificata di Exchange.</p></td>
<td><p>Amministratore di Lync Server 2013</p>
<p>Amministratore del destinatario di Exchange</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere, rimuovere o modificare un indirizzo SIP per un utente&quot; abilitato alla <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>messaggistica unificata.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere Modificare un indirizzo SIP per un utente&quot; abilitato alla <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>messaggistica unificata.</p>
<p>Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Eseguire lo script exchucutil. ps1.</p></td>
<td><p>Nel server che esegue i servizi di messaggistica unificata di Exchange aprire Exchange Management Shell ed eseguire lo script exchucutil. ps1, che esegue le operazioni seguenti:</p>
<ul>
<li><p>Concede l'autorizzazione Lync Server 2013 per la lettura degli oggetti servizi di dominio Active Directory UM di Exchange, in particolare i dial plan SIP creati nell'attività precedente.</p></li>
<li><p>Crea un oggetto gateway IP di messaggistica unificata in Active Directory per ogni pool di Lync Server 2013 Enterprise Edition o un server Standard Edition che ospita gli utenti abilitati per VoIP aziendale.</p></li>
<li><p>Crea un gruppo di ricerca di messaggistica unificata di Exchange per ogni gateway. L'identificatore pilota del gruppo cerca sarà il nome del dial plan associato al gateway corrispondente. Questi devono essere mappati a 1:1 se sono presenti più dial plan.</p></li>
</ul></td>
<td><p>Amministratore dell'organizzazione di Exchange</p>
<p>Amministratore del destinatario di Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare i dial plan di Lync Server 2013.</p></td>
<td><p>Se si esegue l'integrazione con Exchange 2007 SP1 o un Service Pack più recente o Exchange 2010, creare un nuovo piano VoIP aziendale con un nome che corrisponda al nome di dominio completo (FQDN) di Exchange UM dial plan.</p>



> [!NOTE]
> Sarà necessario eseguire questa operazione per ogni dial plan di messaggistica unificata.


<p>Se si esegue l'integrazione con Exchange 2010 SP1, verificare che siano stati configurati piani di dial-up aziendali a livello globale/sito o a livello di pool.</p>



> [!NOTE]
> Se si esegue l'integrazione con Exchange 2010 SP1, non è necessario che il dial plan di Lync Server e i nomi di dial plan di messaggistica unificata di Exchange non corrispondano.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configurazione dei dial plan in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Eseguire lo strumento di integrazione della messaggistica unificata di Exchange.</p></td>
<td><p>In Lync Server 2013 eseguire <strong>OcsUmUtil. exe</strong>, che:</p>
<ul>
<li><p>Crea gli oggetti contatto accesso sottoscrittore e operatore automatico.</p></li>
<li><p>Verifica che sia presente un piano di chiamata VoIP aziendale con un nome corrispondente all'FQDN di Exchange dial plan di messaggistica unificata. Se si esegue Exchange 2010 SP1 o versione successiva, non è necessario che i nomi dei dial plan corrispondano e si possa ignorare l'avviso dello strumento.</p></li>
</ul>
<p>Questo strumento analizza le impostazioni della messaggistica unificata di Exchange in Active Directory e consente all'amministratore di Lync Server 2013 di visualizzare, creare e modificare oggetti contatto.</p></td>
<td><p>RTCUniversalServerAdmins <em>e</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Per eseguire correttamente OcsUmUtil. exe, l'utente deve appartenere a entrambi questi gruppi.





> [!NOTE]
> Per creare oggetti contatto, l'utente che esegue OcsUmUtil. exe deve avere l'autorizzazione corretta per l'unità organizzativa Active Directory in cui sono archiviati i nuovi oggetti contatto. Questa autorizzazione può essere concessa eseguendo il cmdlet <STRONG>Grant-CsOUPermission</STRONG> . Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Se necessario, eseguire altre operazioni di configurazione VoIP aziendale.</p></td>
<td><p>Se non sono già state configurate le impostazioni vocali aziendali nei server o negli utenti, eseguire una o più delle operazioni seguenti:</p>
<ul>
<li><p>Distribuire e configurare</p>
<p>Gateway PSTN (Public Switched Telephone Network) e Mediation Server</p></li>
<li><p>Definire i criteri vocali, i record di utilizzo PSTN e le route di chiamata in uscita.</p></li>
<li><p>Consentire agli utenti di VoIP aziendale.</p></li>
<li><p>Facoltativamente, configurare utenti specifici con dial plan.</p></li>
</ul>
<p>Altre operazioni di configurazione possono essere necessarie in base alle funzionalità vocali aziendali abilitate.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Vedere gli argomenti nelle sezioni seguenti:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Abilitare gli utenti di VoIP aziendale per la messaggistica unificata di Exchange.</p></td>
<td><p>Nel server Messaggistica unificata di Exchange verificare che sia stato creato un criterio cassetta postale di messaggistica unificata e che ogni utente disponga di un'assegnazione di numero di interno univoco e quindi abilitare l'utente per la messaggistica unificata.</p></td>
<td><p>Amministratore del destinatario di Exchange</p></td>
<td><p>Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come abilitare un utente per la messaggistica&quot; unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Per Exchange 2010 o Service Pack più recente, &quot;vedere Abilitare un utente per la messaggistica&quot; unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</p>
<p>Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

