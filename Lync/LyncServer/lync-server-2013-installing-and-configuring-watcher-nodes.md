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
ms.openlocfilehash: 19a4fad29b29dbec895a2c327ce2ddc054b8202b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Installazione e configurazione di nodi Watcher in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

I *nodi Watcher* sono computer che eseguono periodicamente transazioni sintetiche di Lync Server. *Le transazioni sintetiche* sono cmdlet di Windows PowerShell che verificano che gli scenari fondamentali degli utenti finali, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei, funzionino come previsto. Per Lync Server 2013, System Center Operations Manager è in grado di eseguire le transazioni sintetiche illustrate nella tabella seguente. Esistono tre tipi diversi di transazioni sintetiche:

  - **Valore predefinito**. Queste sono le transazioni sintetiche eseguite per impostazione predefinita da un nodo Watcher. Quando si crea un nuovo nodo Watcher esiste la possibilità di specificare quali transazioni sintetiche verranno eseguite dal nodo. (Questo è lo scopo del parametro tests utilizzato dal cmdlet **New-CsWatcherNodeConfiguration** ). Se non si utilizza il parametro tests quando viene creato il nodo Watcher, verranno eseguite automaticamente tutte le transazioni sintetiche predefinite e non verranno eseguite le transazioni sintetiche non predefinite. Ciò significa,ad esempio, che il nodo Watcher verrà configurato per eseguire il test Test-CsAddressBookService, ma non il test Test-CsExumConnectivity.

  - **Non predefinito**. Come indica il nome, le transazioni sintetiche non predefinite sono i test che non vengono eseguiti per impostazione predefinita dai nodi Watcher. Il nodo Watcher può essere tuttavia abilitato all'esecuzione di qualsiasi transazione sintetica non predefinita. È possibile specificare questa impostazione durante la creazione del nodo Watcher (tramite il cmdlet **New-CsWatcherNodeConfiguration**) o in qualsiasi momento in seguito. Per molte delle transazioni sintetiche non predefinite sono necessari passaggi aggiuntivi di configurazione. Per informazioni dettagliate, vedere [istruzioni di installazione speciali per le transazioni sintetiche in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Extended**. I test estesi sono un tipo speciale di transazione sintetica non predefinita. Diversamente da altre transazioni sintetiche, i test estesi possono essere eseguiti più volte durante ogni passaggio. Si tratta di un'opzione utile durante la verifica di comportamenti come più route vocali PSTN (Public Switched Telephone Network) per un pool. Per ottenere questa configurazione è sufficiente aggiungere più istanze di un test esteso a un nodo Watcher.

Per informazioni dettagliate sul processo di aggiunta di altre transazioni sintetiche a un nodo Watcher, vedere [Managing Watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md). È possibile utilizzare Lync Server Management Shell per rimuovere le transazioni sintetiche da un nodo Watcher.

Le transazioni sintetiche disponibili per i nodi Watcher includono le seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome del cmdlet (nome test)</th>
<th>Descrizione</th>
<th>Tipo di transazione sintetica</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Conferma che gli utenti siano in grado di cercare utenti non presenti nel loro elenco contatti.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Conferma che gli utenti siano in grado di cercare utenti non presenti nel loro elenco contatti tramite HTTP.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>Conferma che gli utenti siano in grado di inviare messaggi istantanei peer-to-peer.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Conferma che gli utenti siano in grado di effettuare chiamate audio peer-to-peer (solo segnalazione).</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>Conferma che gli utenti siano in grado visualizzare la presenza di altri utenti.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>Conferma che gli utenti siano in grado di accedere a Lync.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Non utilizzata con la versione locale di Lync Server 2013</p></td>
<td><p>Estesa</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Conferma che gli utenti siano in grado di effettuare e ricevere chiamate con persone esterne all'organizzazione (numeri PSTN).</p></td>
<td><p>Non predefinita, estesa</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Conferma che gli utenti siano in grado di creare conferenze audio/video e di parteciparvi.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Conferma che gli A/V Edge Server siano in grado di accettare connessioni da chiamate e conferenze telefoniche peer-to-peer.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (dataconference)</p></td>
<td><p>Conferma che gli utenti possano partecipare a conferenze con collaborazione dati, ovvero una riunione online che include attività come lavagne e sondaggi.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Conferma che un utente può connettersi alla messaggistica unificata di Exchange.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Conferma che gli utenti siano in grado di inviare messaggi istantanei in conferenze e partecipare a conversazioni istantanee con tre o più persone.</p></td>
<td><p>Predefinita</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Conferma che gli utenti siano in grado di creare riunioni pianificate e parteciparvi tramite un collegamento a un indirizzo Web.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Conferma che gli utenti di dispositivi mobili siano in grado di registrarsi e inviare messaggi istantanei.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Conferma che gli utenti possono scambiare messaggi tramite il servizio chat persistente.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Conferma che è possibile accedere ai contatti di un utente tramite l'archivio contatti unificato. L'archivio contatti unificato consente agli utenti di gestire un singolo gruppo di contatti a cui è possibile accedere utilizzando Lync 2013, Outlook e/o Outlook Web Access.</p></td>
<td><p>Non predefinito</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Conferma che sia possibile inviare un messaggio istantaneo attraverso il gateway XMPP (Extensible Messaging and Presence Protocol).</p></td>
<td><p>Non predefinito</p></td>
</tr>
</tbody>
</table>


Non è necessario installare i nodi Watcher per poter utilizzare System Center Operations Manager. Se non si installano questi nodi, è comunque possibile ottenere avvisi in tempo reale dai componenti di Lync Server 2013 quando si verifica un problema. (Il componente e il Management Pack degli utenti non utilizzano i nodi Watcher). Tuttavia, i nodi Watcher sono obbligatori se si desidera monitorare gli scenari end-to-end tramite Active Monitoring Management Pack.

<div>


> [!NOTE]  
> Gli amministratori possono inoltre eseguire transazioni sintetiche manualmente, senza dover utilizzare o installare Operations Manager. Per informazioni dettagliate sui vari cmdlet test-CS, vedere l' <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Indice dei cmdlet di Lync Server 2013</A>.



</div>

A seconda delle dimensioni della distribuzione, le transazioni sintetiche potrebbero utilizzare una grande quantità di memoria e tempo del processore del computer. Per questo motivo, è consigliabile utilizzare un computer dedicato come nodo Watcher. Ad esempio, non è necessario configurare un front end server come nodo Watcher. I nodi Watcher devono rispondere alle specifiche hardware seguenti:

<div>


> [!NOTE]  
> Un nodo Microsoft Lync Server 2010 Watcher legacy non può essere collocato nello stesso computer con un nodo di monitoraggio di Lync Server 2013. Ciò è dovuto al fatto che i file di sistema di base per Lync Server 2010 e Lync Server 2013 non possono essere installati nello stesso computer.<BR>Tuttavia, i nodi di monitoraggio di Lync Server 2013 possono monitorare contemporaneamente sia Lync Server 2013 che Lync Server 2010. Le transazioni sintetiche predefinite sono supportate in entrambe le versioni.



</div>

I nodi di Watcher di Lync Server 2013 possono essere distribuiti all'interno o all'esterno di un'organizzazione per consentirne la verifica:

  - <span></span>  
    Connettività ai pool per gli utenti all'interno dell'organizzazione.

  - <span></span>  
    Connettività tramite reti perimetrali per gli utenti remoti che lavorano all'esterno dell'organizzazione.

  - <span></span>  
    Connettività a Survivable Branch Appliance.

  - <span></span>  
    Connettività a Lync Server 2010 all'interno dell'organizzazione e tramite reti perimetrali.

Sono disponibili opzioni di autenticazione diverse per le connessioni dall'interno e dall'esterno per semplificare l'amministrazione. Per ulteriori informazioni, vedere [configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Per configurare un computer come nodo Watcher, è necessario eseguire i passaggi seguenti dopo aver installato System Center Operations Manager e aver importato Lync Server 2013 Management Pack.

Prima di installare i file di base di Lync Server 2013 e i file dell'agente centro di sistema, è inoltre necessario verificare che il computer del nodo Watcher soddisfi tutti i prerequisiti per l'installazione di Lync Server 2013. Nel computer del nodo Watcher, inoltre, dovrebbero essere installati gli elementi seguenti:


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
<td><p>Una delle opzioni seguenti:</p>
<ul>
<li><p>processore a 64 bit, quad-core, 2,33 GHz o superiore</p></li>
<li><p>processore 2-Way a 64 bit, Dual Core, 2,33 GHz o superiore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Sistema operativo di rete</p></td>
<td><ul>
<li><p>1 scheda di rete 1 Gbps</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 o</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - Versione completa di .NET Framework 4.5.

  - Windows Identity Foundation.

  - Windows PowerShell 3.0.

Quando tutti questi prerequisiti sono soddisfatti è possibile procedere alla configurazione del nodo Watcher con i passaggi seguenti:

  - Installazione dei file di base di Lync Server 2013 nel computer del nodo Watcher.

  - Installazione dell'agente System Center Operations Manager nel computer del nodo Watcher.

  - Esecuzione del file eseguibile Watchernode.msi.

  - Utilizzo dei cmdlet **CsWatcherNodeConfiguration** per configurare gli utenti di prova utilizzati dal nodo Watcher.

</div>

<span> </span>

</div>

</div>

</div>

