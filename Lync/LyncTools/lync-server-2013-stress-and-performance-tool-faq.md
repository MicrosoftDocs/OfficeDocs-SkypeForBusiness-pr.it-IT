---
title: Domande frequenti sugli strumenti di stress e prestazioni di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Domande frequenti sugli strumenti di stress e prestazioni di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Domande frequenti

Ecco alcune domande frequenti sullo strumento per lo stress e le prestazioni di Lync Server 2013.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>È possibile eseguire LyncPerfTool. exe in produzione?

Non è consigliabile. Questo strumento avrà un impatto sulle prestazioni del server, sulla sicurezza e sull'esperienza utente.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Accedo agli utenti per la prima volta. Perché i server sono in funzione a un carico elevato?

La prima volta che si esegue l'accesso agli utenti, esistono altre operazioni che si verificano. Di conseguenza, le prestazioni del server back-end di Microsoft SQL Server verranno degradate. È consigliabile eseguire un breve test che registri tutti gli utenti e quindi riavviare i client prima di misurare i risultati. Non sono supportate più di 12 sessioni di accesso simultanee degli utenti al secondo, ma questo dipende dalla configurazione hardware.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>I miei clienti stanno esaurendo la memoria. Cosa dovrei fare?

Se i client esauriscono la memoria, è necessario ridurre il numero di utenti per computer.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>I miei clienti sono sempre al 100 per cento della CPU. Cosa dovrei fare?

Se i client sono in uso con CPU molto alta dopo che tutti gli utenti hanno eseguito l'accesso, è necessario ridurre il numero di utenti per computer. I picchi di CPU elevati sono accettabili, ma, se sostenuti, è necessario ridurre il carico.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>È possibile eseguire lo strumento nel server?

Non. Questo scenario non è supportato e potrebbe non riuscire a causa di una mancata corrispondenza binaria. Inoltre, poiché il punto consiste nel misurare il consumo di risorse sul server, l'uso dello strumento renderebbe le misurazioni senza significato.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>È possibile eseguire LyncPerfTool. exe in un server virtuale o in Microsoft Hyper-V Server 2008/2012?

Sì.

</div>

<div>

## <a name="what-does-mpop-mean"></a>Cosa significa MPOP?

MPOP è sinonimo di più punti di presenza. È concepito per simulare lo scenario in cui gli utenti hanno effettuato l'accesso a Lync 2013 da più computer. Tieni presente che in LyncPerfTool. exe ogni endpoint usa il profilo predefinito, ovvero il profilo non è diviso tra i due punti di presenza.

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>È stato avviato LyncPerfTool. exe, ma non succede nulla. Cosa sta succedendo?

Controlla il contatore degli endpoint attivi totali nei client per vedere se gli utenti si connettono. Se gli utenti non si connettono, verificare la configurazione di Lync Server 2013. Questo problema si verifica in genere perché il nome del server, il prefisso dell'utente o la password non sono corretti. Tieni presente che i client esterni devono specificare il proxy di accesso come valore TargetServer. Verificare la porta nel file di configurazione.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Come si fa a sapere che sta succedendo qualcosa?

I vari contatori delle prestazioni di LyncPerfTool indicano se gli utenti si connettono o eseguono azioni. Tuttavia, un modo semplice per verificare è eseguire l'accesso a uno degli account usando Lync 2013 ed eseguire l'azione desiderata.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Sono installati gli strumenti di pianificazione della capacità di Live Communications Server 2007 R2 e/o Lync Server 2010. È OK?

Non. Esistono problemi di interoperabilità ed è necessario disinstallare tutte le versioni precedenti di questo prodotto.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Gli strumenti di stress e prestazioni configurano la topologia del server delle informazioni sulle chiamate CAA?

Non. Gli strumenti creano solo utenti, contatti e liste di distribuzione e simulano il caricamento dell'utente.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual è il numero massimo di utenti supportati dagli strumenti?

L'uso di questi strumenti è stato creato fino a un totale di 80.000 utenti e test eseguiti per un totale di 30.000 utenti. Suggeriamo un numero massimo di utenti di 120.000, anche se le limitazioni tecniche consentiranno un valore superiore, a seconda dell'hardware del client e del server disponibile.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

