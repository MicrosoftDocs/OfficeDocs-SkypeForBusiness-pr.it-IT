---
title: "Lync Server 2013: Panoramica dell'applicazione Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3bb7b9260e85326718bf388da977833c6e87ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Panoramica dell'applicazione Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-11_

Quando un chiamante chiama un Response Group, viene eseguito il routing della chiamata a un agente in base a un gruppo di risposta o alle risposte del chiamante alle domande di un sistema IVR (Interactive Voice Response). L'applicazione Response Group utilizza metodi di routing di Response Group standard per instradare la chiamata al successivo agente disponibile. I metodi di routing delle chiamate includono routing seriale, verso l'agente inattivo più a lungo, round robin e il nuovo routing operatore, in cui vengono chiamati tutti gli agenti contemporaneamente per ogni chiamata in arrivo, indipendentemente dalla loro effettiva presenza. Se non è disponibile alcun agente, la chiamata viene mantenuta in una coda fino a quando non è disponibile un agente. Mentre la chiamata è nella coda, il chiamante ascolta un brano musicale fino a quando un agente disponibile non accetta la chiamata. Se la coda è piena o si verifica il timeout della chiamata mentre questa è in coda, il chiamante potrebbe ascoltare un messaggio e quindi venire disconnesso o trasferito a una destinazione diversa. Quando un agente accetta la chiamata, il chiamante può o meno visualizzare l'identità dell'agente, a seconda del modo in cui l'amministratore ha configurato Response Group. Gli agenti possono essere agenti formali, ovvero devono accedere al gruppo prima di poter accettare le chiamate di cui viene eseguito il routing al gruppo, oppure agenti informali, ovvero non accedono al gruppo né si disconnettono per accettare le chiamate.

<div>


> [!NOTE]  
> Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.



</div>

<div>


> [!NOTE]  
> L'applicazione Response Group utilizza un servizio interno, denominato match making, per accodare le chiamate e trovare gli agenti disponibili. Ogni computer che esegue l'applicazione Response Group esegue il servizio di corrispondenza, ma è attivo un solo servizio di corrispondenza per ogni pool di Lync Server alla volta: le altre sono passive. Se il servizio di ricerca corrispondenze diventa non disponibile durante un guasto non pianificato, viene attivato uno dei servizi di ricerca corrispondenze passivi. L'applicazione Response Group consente di fare in modo che il routing delle chiamate e l'accodamento continuino senza interruzioni. Quando si verifica una transizione a un servizio di ricerca corrispondenze, tutte le chiamate in trasferimento durante la transizione vengono perdute. Ad esempio, se la transizione è dovuta alla fine del server front-end, vengono perse anche tutte le chiamate attualmente gestite dal servizio di corrispondenza attivo in quel front end server.



</div>

In Lync Server 2013, sono disponibili due ruoli di gestione per la gestione dei Response Group, ovvero il responsabile del gruppo di risposta e l'amministratore di Response Group. Gli amministratori di Response Group possono gestire qualsiasi aspetto di qualsiasi Response Group. I responsabili dei Response Group possono gestire solo alcuni aspetti e solo per i Response Group di cui sono proprietari. Il nuovo ruolo di gestione può contribuire a ridurre i costi amministrativi, in quanto è possibile delegare responsabilità limitate per gruppi di risposta specifici a qualsiasi utente abilitato per VoIP aziendale.

Per ospitare il nuovo ruolo di gestione, Lync Server 2013 Response Group Application introduce un **tipo di flusso di lavoro** gestito o non gestito. Nella tabella riportata di seguito vengono descritti i Response Group gestiti e non gestiti.

### <a name="managed-and-unmanaged-response-groups"></a>Response Group gestiti e non gestiti

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di Response Group</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Gestito</p></td>
<td><ul>
<li><p>Ai Response Group non gestiti non è assegnato alcun Gestore. Solo l'amministratore del gruppo di risposta può configurare questi Response Group.</p></li>
<li><p>Response group multipli non gestiti possono condividere una coda o gruppo di agenti.</p></li>
<li><p>Quando si esegue la migrazione dei Response Group da una versione precedente a Lync Server 2013, il tipo è impostato su non gestito.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Gestiti</p></td>
<td><ul>
<li><p>Gli amministratori di Response Group possono configurare qualsiasi aspetto dei gruppi di risposta gestiti.</p></li>
<li><p>I responsabili dei Response Group non sono in grado di visualizzare o modificare gruppi di risposta non assegnati in modo esplicito.</p></li>
<li><p>I responsabili dei Response Group possono configurare solo alcune impostazioni per i Response Group a loro assegnati in modo esplicito.</p></li>
<li><p>I Response group gestiti non possono condividere code o gruppi di agenti con altri Response group gestiti o non gestiti.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Nella tabella seguente vengono descritte le azioni che possono essere eseguite dai responsabili dei Response Group e che non è possibile eseguire per i Response Group a loro assegnati.

### <a name="response-group-manager-capabilities"></a>Capacità del manager del Response group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Possono configurare:</th>
<th>Possono creare, eliminare o configurare:</th>
<th>Possibile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agenti</p></li>
<li><p>Messaggio di benvenuto</p></li>
<li><p>Nome del gruppo di risposta</p></li>
<li><p>Descrizione</p></li>
<li><p>Numero visualizzato</p></li>
<li><p>Ore lavorative</p></li>
<li><p>Musica di attesa</p></li>
<li><p>Stato (attivo/inattivo)</p></li>
<li><p>Workflow del gruppo di risposta o Interactive voice response (IVR)</p></li>
</ul></td>
<td><ul>
<li><p>Gestione di gruppi di agenti</p></li>
<li><p>Code</p></li>
<li><p>Insiemi di festività</p></li>
</ul></td>
<td><ul>
<li><p>Creare o eliminare qualsiasi tipo di workflow</p></li>
<li><p>Modificare le impostazioni fondamentali dei Response Group, quali: <strong>URI SIP</strong>, <strong>Numero di telefono</strong> o <strong>Tipo di workflow</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


I responsabili dei Response Group possono utilizzare gli strumenti seguenti per gestire i Response Group designati.

  - Pannello di controllo di Lync Server
    
    <div>
    

    > [!NOTE]  
    > I responsabili dei Response Group possono gestire solo le impostazioni di Response Group con questo strumento. Altre impostazioni di Lync Server non sono disponibili per i responsabili.

    
    </div>

  - Strumento di configurazione di Response Group

  - Lync Server Management Shell

La scala dei Response Group è adatta agli ambienti dipartimentali o gruppi di lavoro (per informazioni dettagliate, vedere [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e può essere distribuita in installazioni di telefonia completamente nuove. Supporta le chiamate in arrivo dalla distribuzione di VoIP aziendale e dalla rete di vettori locali. Gli agenti possono utilizzare Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition per eseguire le chiamate instradate a tali operatori.

L'applicazione Response Group è un componente di VoIP aziendale. Quando si distribuisce VoIP aziendale, l'applicazione Response Group viene installata e attivata automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

