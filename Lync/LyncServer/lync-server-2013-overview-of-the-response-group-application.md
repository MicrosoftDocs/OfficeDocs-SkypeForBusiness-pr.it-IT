---
title: "Lync Server 2013: Panoramica dell'applicazione Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Panoramica dell'applicazione Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-11_

Quando un chiamante chiama un gruppo di risposte, la chiamata viene instradata a un agente in base a un gruppo di risposta o alle domande del chiamante per rispondere alla risposta vocale interattiva (IVR). L'applicazione Response Group USA i metodi di routing dei gruppi di risposta standard per instradare la chiamata al successivo agente disponibile. I metodi di routing delle chiamate includono il routing seriale, più lungo-inattivo, parallelo, rotondo Robin e supervisore (ovvero tutti gli agenti vengono chiamati contemporaneamente per ogni chiamata in arrivo, indipendentemente dalla presenza corrente). Se non sono disponibili agenti, la chiamata viene mantenuta in una coda finché non è disponibile un agente. Mentre si è in coda, il chiamante sente la musica finché un agente disponibile non accetta la chiamata. Se la coda è piena o se la chiamata viene interrotta durante la coda, il chiamante potrebbe udire un messaggio e quindi essere disconnesso o trasferito in una destinazione diversa. Quando un agente accetta la chiamata, il chiamante potrebbe non essere in grado di visualizzare l'identità dell'agente, a seconda del modo in cui l'amministratore configura il gruppo di risposte. Gli agenti possono essere formali, quindi devono accedere al gruppo prima di poter accettare le chiamate instradate al gruppo o informale, il che significa che non accedono al gruppo per accettare le chiamate.

<div>


> [!NOTE]  
> Solo gli utenti locali possono essere agenti. Se un agente viene spostato da locale a online, le chiamate di Response Group non verranno indirizzate a tale agente.



</div>

<div>


> [!NOTE]  
> L'applicazione Response Group usa un servizio interno, denominato match making, per accodare le chiamate e trovare gli agenti disponibili. Ogni computer che esegue l'applicazione Response Group esegue il servizio di creazione delle corrispondenze, ma solo un servizio per il pool di Lync Server è attivo alla volta, mentre gli altri sono passivi. Se il servizio di corrispondenza attiva diventa non disponibile durante un'interruzione non pianificata, uno dei servizi di corrispondenza passiva diventa attivo. L'applicazione Response Group fa del suo meglio per assicurarsi che il routing delle chiamate e l'accodamento continuino senza interruzioni. Tuttavia, quando si verifica una transizione del servizio di corrispondenza, le chiamate in fase di trasferimento vengono perse. Ad esempio, se la transizione è dovuta al fatto che il server front-end si abbassa, vengono perse anche le chiamate attualmente gestite dal servizio Active match making del server front-end.



</div>

In Lync Server 2013 sono disponibili due ruoli di gestione per la gestione dei gruppi di risposta: Response Group Manager e Response Group Administrator. Gli amministratori del gruppo di risposte possono gestire qualsiasi aspetto di un gruppo di risposte. I responsabili dei gruppi di risposte possono gestire solo determinati aspetti e solo per i gruppi di risposta di cui sono proprietari. Il nuovo ruolo di gestione può contribuire a ridurre i costi amministrativi, perché è possibile delegare responsabilità limitate per gruppi di risposta specifici a qualsiasi utente abilitato per VoIP aziendale.

Per supportare il nuovo ruolo di Manager, l'applicazione di Response Group di Lync Server 2013 introduce un **tipo di flusso di lavoro** gestito o non gestito. La tabella seguente descrive i gruppi di risposta gestiti e non Managed.

### <a name="managed-and-unmanaged-response-groups"></a>Gruppi di risposte gestite e non gestiti

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di gruppo di risposta</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Non gestite</p></td>
<td><ul>
<li><p>I gruppi di risposte non gestiti non hanno gestori assegnati. Solo l'amministratore del gruppo di risposte può configurare questi gruppi di risposta.</p></li>
<li><p>Più gruppi di risposte non gestiti possono condividere una coda o un gruppo di agenti.</p></li>
<li><p>Quando si esegue la migrazione dei gruppi di risposte da una versione precedente a Lync Server 2013, il tipo viene impostato su non gestito.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Gestito</p></td>
<td><ul>
<li><p>Gli amministratori del gruppo di risposte possono configurare qualsiasi aspetto dei gruppi di risposta gestiti.</p></li>
<li><p>I responsabili del gruppo di risposte non possono visualizzare o modificare i gruppi di risposta che non sono assegnati esplicitamente.</p></li>
<li><p>I responsabili del gruppo di risposte possono configurare solo alcune impostazioni per i gruppi di risposta assegnati esplicitamente.</p></li>
<li><p>I gruppi di risposta gestiti non possono condividere le code o i gruppi di agenti con qualsiasi altro gruppo di risposte, gestito o non gestito.</p></li>
</ul></td>
</tr>
</tbody>
</table>


La tabella seguente descrive le azioni che i responsabili dei gruppi di risposta possono e non possono eseguire per i gruppi di risposte assegnati.

### <a name="response-group-manager-capabilities"></a>Funzionalità di gestione gruppi di risposte

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Può configurare:</th>
<th>Può creare, eliminare o configurare:</th>
<th>Non</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agenti</p></li>
<li><p>Messaggio di benvenuto</p></li>
<li><p>Nome del gruppo di risposte</p></li>
<li><p>Descrizione</p></li>
<li><p>Numero di visualizzazione</p></li>
<li><p>Orari di ufficio</p></li>
<li><p>Musica in attesa</p></li>
<li><p>Stato (attivo/inattivo)</p></li>
<li><p>Cercare flussi di lavoro di gruppo o flussi di lavoro IVR (Interactive Voice Response)</p></li>
</ul></td>
<td><ul>
<li><p>Gruppi di agenti</p></li>
<li><p>Code</p></li>
<li><p>Set di festività</p></li>
</ul></td>
<td><ul>
<li><p>Creare o eliminare qualsiasi tipo di flusso di lavoro</p></li>
<li><p>Modificare le impostazioni del gruppo di risposte di base, ad esempio: <strong>URI SIP</strong>, <strong>numero di telefono</strong>o <strong>tipo di flusso di lavoro</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


I responsabili del gruppo di risposte possono usare gli strumenti seguenti per gestire i gruppi di risposta designati.

  - Pannello di controllo di Lync Server
    
    <div>
    

    > [!NOTE]  
    > I responsabili dei gruppi di risposte possono gestire solo le impostazioni di Response Group con questo strumento. Le altre impostazioni di Lync Server non sono disponibili per i responsabili.

    
    </div>

  - Strumento di configurazione di Response Group

  - Lync Server Management Shell

Il gruppo di risposte si adatta bene agli ambienti dipartimentali o gruppi di lavoro (per informazioni dettagliate, vedere [pianificazione della capacità per il gruppo di risposte in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e può essere distribuito in installazioni di telefonia completamente nuove. Supporta le chiamate in arrivo dalla distribuzione VoIP aziendale e dalla rete di vettori locali. Gli agenti possono usare Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition per eseguire le chiamate instradate.

L'applicazione Response Group è un componente di Enterprise Voice. Quando si distribuisce VoIP aziendale, l'applicazione Response Group viene installata e attivata automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

