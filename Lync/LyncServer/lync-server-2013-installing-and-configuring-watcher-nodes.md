---
title: 'Lync Server 2013: installazione e configurazione di nodi Watcher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89465227e351da3c69116201efe5ee4eab89eca4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Installazione e configurazione di nodi Watcher in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

I *nodi Watcher* sono computer che eseguono periodicamente transazioni sintetiche di Lync Server. *Le transazioni sintetiche* sono cmdlet di Windows PowerShell che verificano che gli scenari degli utenti finali chiave, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei, funzionino come previsto. Per Lync Server 2013, System Center Operations Manager può eseguire le transazioni sintetiche mostrate nella tabella seguente. Nella tabella sono visualizzati tre tipi di transazione sintetici diversi:

  - **Impostazione predefinita**. Queste sono le transazioni sintetiche che verrà eseguito da un nodo Watcher per impostazione predefinita. Quando si crea un nuovo nodo Watcher, è possibile specificare le transazioni sintetiche che verranno eseguite da node. Questo è lo scopo del parametro tests usato dal cmdlet **New-CsWatcherNodeConfiguration** . Se non si usa il parametro tests quando viene creato il nodo Watcher, verranno eseguite automaticamente tutte le transazioni sintetiche predefinite e non verranno eseguite le transazioni sintetiche non predefinite. Questo significa, ad esempio, che il nodo Watcher sarà configurato per eseguire il Test CsAddressBookService, ma non sarà configurato per eseguire il test di test-CsExumConnectivity.

  - **Non predefinito**. Come suggerisce il nome, le transazioni sintetiche non predefinite sono test che i nodi di Watcher non vengono eseguiti per impostazione predefinita. Tuttavia, il nodo Watcher può essere abilitato per eseguire tutte le transazioni sintetiche non predefinite. Questa operazione può essere eseguita quando si crea il nodo Watcher (usando il cmdlet **New-CsWatcherNodeConfiguration** ) o in qualsiasi momento. Molte delle transazioni sintetiche non predefinite richiedono passaggi di configurazione aggiuntivi. Per informazioni dettagliate, vedere [istruzioni per la configurazione speciale per le transazioni sintetiche in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Extended**. I test estesi sono un tipo speciale di transazione sintetica non predefinita. A differenza di altre transazioni sintetiche, i test estesi possono essere eseguiti più volte durante ogni passaggio. Questa funzionalità può essere utile quando si verifica un comportamento, ad esempio più route vocali PSTN (Public Switched Telephone Network) per un pool. Questa operazione può essere configurata semplicemente aggiungendo più istanze di un test esteso a un nodo Watcher.

Per informazioni dettagliate sul processo di aggiunta di altre transazioni sintetiche a un nodo Watcher, vedere [gestione dei nodi Watcher in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md). È possibile usare Lync Server Management Shell per rimuovere le transazioni sintetiche da un nodo Watcher.

Le transazioni sintetiche disponibili per i nodi Watcher includono le seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome cmdlet (nome test)</th>
<th>Descrizione</th>
<th>Tipo di transazione sintetica</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Conferma che gli utenti possono cercare gli utenti non presenti nell'elenco contatti.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Conferma che gli utenti possono cercare utenti non presenti nell'elenco contatti tramite HTTP.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>Conferma che gli utenti possono inviare messaggi istantanei peer-to-peer.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Conferma che gli utenti possono inserire chiamate audio peer-to-peer (solo segnalazione).</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (presenza)</p></td>
<td><p>Conferma che gli utenti possono visualizzare la presenza di altri utenti.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (registrazione)</p></td>
<td><p>Conferma che gli utenti possono accedere a Lync.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Non usato con la versione locale di Lync Server 2013</p></td>
<td><p>Esteso</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Conferma che gli utenti possono effettuare e ricevere chiamate con persone esterne all'organizzazione (numeri PSTN).</p></td>
<td><p>Non predefinito, esteso</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Conferma che gli utenti possono creare e partecipare a una conferenza audio/video.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Conferma che l'A/V Edge Server è in grado di accettare connessioni per chiamate peer-to-peer e conferenze telefoniche.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (dataconference)</p></td>
<td><p>Conferma che gli utenti possono partecipare a una conferenza di collaborazione dati, una riunione online che include attività come lavagne e sondaggi.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Conferma che un utente può connettersi alla messaggistica UNIFICAta di Exchange.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Conferma che gli utenti possono inviare messaggi istantanei in conferenze e partecipare a conversazioni di messaggistica istantanea con tre o più persone.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Conferma che gli utenti possono creare e partecipare a riunioni pianificate tramite un collegamento a un indirizzo Web.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Conferma che gli utenti di dispositivi mobili sono in grado di registrare e inviare messaggi istantanei.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Conferma che gli utenti possono scambiare messaggi usando il servizio di chat persistente.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Conferma che è possibile accedere ai contatti di un utente tramite l'archivio contatti unificato. L'archivio contatti unificato consente agli utenti di gestire un singolo set di contatti a cui è possibile accedere tramite Lync 2013, Outlook e/o Outlook Web Access.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Conferma che un messaggio istantaneo può essere inviato attraverso il gateway XMPP (Extensible Messaging and Presence Protocol).</p></td>
<td><p>Non predefinito</p></td>
</tr>
</tbody>
</table>


Non è necessario installare i nodi Watcher per usare System Center Operations Manager. Se non si installano questi nodi, è comunque possibile ottenere avvisi in tempo reale dai componenti di Lync Server 2013 quando si verifica un problema. Il Management Pack per i componenti e gli utenti non usa i nodi Watcher. Tuttavia, i nodi Watcher sono obbligatori se vuoi monitorare gli scenari end-to-end usando il Management Pack di monitoraggio attivo.

<div>


> [!NOTE]  
> Gli amministratori possono anche eseguire manualmente le transazioni sintetiche, senza bisogno di usare o installare Operations Manager. Per informazioni dettagliate sui vari cmdlet test-CS, vedere l' <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Indice cmdlet di Lync Server 2013</A>.



</div>

A seconda delle dimensioni della distribuzione, le transazioni sintetiche possono usare una grande quantità di memoria computer e tempo processore. Per questo motivo, ti consigliamo di usare un computer dedicato come nodo Watcher. Ad esempio, non devi configurare un front end server per fungere da nodo Watcher. I nodi Watcher devono soddisfare le specifiche hardware seguenti:

<div>


> [!NOTE]  
> Un nodo di Watcher di Microsoft Lync Server 2010 legacy non può essere collocato nello stesso computer con un nodo di Watcher di Lync Server 2013. Il motivo è che i file di sistema principali per Lync Server 2010 e Lync Server 2013 non possono essere installati nello stesso computer.<BR>Tuttavia, i nodi di Watcher di Lync Server 2013 possono monitorare simultaneamente sia Lync Server 2013 che Lync Server 2010. Le transazioni sintetiche predefinite sono supportate in entrambe le versioni di prodotto.



</div>

I nodi di Watcher di Lync Server 2013 possono essere distribuiti all'interno o all'esterno di un'organizzazione per verificare:

  - <span></span>  
    Connettività ai pool per gli utenti all'interno dell'organizzazione.

  - <span></span>  
    Connettività tramite reti perimetrali per gli utenti remoti che lavorano all'esterno dell'organizzazione.

  - <span></span>  
    Connettività agli elettrodomestici di filiale.

  - <span></span>  
    Connettività a Lync Server 2010 all'interno dell'organizzazione e tramite reti perimetrali.

Sono disponibili diverse opzioni di autenticazione per l'interno e l'esterno dell'organizzazione per semplificare l'amministrazione. Per informazioni dettagliate, vedere [configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Per configurare un computer come nodo Watcher, è necessario eseguire i passaggi seguenti dopo aver installato System Center Operations Manager e aver importato i Management Pack di Lync Server 2013.

Prima di installare i file di base di Lync Server 2013 e i file dell'agente del centro di sistema, è anche necessario verificare che il computer del nodo Watcher soddisfi tutti i prerequisiti per l'installazione di Lync Server 2013. Inoltre, il computer del nodo Watcher dovrebbe avere gli elementi seguenti installati:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Requisito minimo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Una delle operazioni seguenti:</p>
<ul>
<li><p>processore a 64 bit, quad-core, 2,33 GHz o superiore</p></li>
<li><p>processore 2-vie a 64 bit, Dual-Core, 2,33 GHz o superiore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Sistema operativo di rete</p></td>
<td><ul>
<li><p>1 adattatore di rete 1 Gbps</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 o</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - Versione completa di .NET Framework 4,5.

  - Windows Identity Foundation.

  - Windows PowerShell 3,0.

Non appena sono stati soddisfatti tutti questi prerequisiti, è possibile configurare il nodo Watcher per:

  - Installazione dei file di base di Lync Server 2013 nel computer del nodo Watcher.

  - Installazione dell'agente di System Center Operations Manager nel computer del nodo Watcher.

  - Eseguire il file eseguibile di WatcherNode. msi.

  - Uso dei cmdlet **CsWatcherNodeConfiguration** per configurare gli utenti di test per l'utilizzo da parte del nodo Watcher.

</div>

<span> </span>

</div>

</div>

</div>

