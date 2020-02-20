---
title: Domande frequenti su Lync Server 2013 stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6c4a9909bfecd8157fe3afe9f653a684fe1053b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Domande frequenti su Lync Server 2013 stress and Performance Tool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Domande frequenti

Di seguito sono riportate alcune domande frequenti sullo strumento Lync Server 2013 stress and performance.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>È possibile eseguire LyncPerfTool. exe in produzione?

Non è consigliabile. Questo strumento avrà un impatto sulle prestazioni del server, sulla sicurezza e sull'esperienza utente.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>La prima volta che si accede ai miei utenti. Perché i server sono in esecuzione a un carico così elevato?

La prima volta che si esegue l'accesso agli utenti, sono presenti operazioni aggiuntive. Di conseguenza, le prestazioni sul server back-end di Microsoft SQL Server verranno danneggiate. È consigliabile eseguire un test breve che accede a tutti gli utenti e quindi riavviare i client prima di misurare i risultati. Non sono supportate più di 12 sessioni di accesso utente simultanee al secondo, ma ciò dipende dalla configurazione hardware.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>I client esauriscono la memoria. Cosa si può fare?

Se i client esauriscono la memoria, è necessario ridurre il numero di utenti per computer.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>I client sono al 100 percento della CPU per tutto il tempo. Cosa si può fare?

Se i client sono in esecuzione con CPU molto alta dopo che tutti gli utenti hanno effettuato l'accesso, è necessario ridurre il numero di utenti per computer. Gli alti picchi di CPU sono accettabili, ma se sono sostenuti, è necessario ridurre il carico.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>È possibile eseguire lo strumento nel server stesso?

No. Questo scenario non è supportato e potrebbe avere esito negativo a causa di una mancata corrispondenza binaria. Inoltre, poiché il punto è misurare il consumo di risorse sul server, l'esecuzione dello strumento consentirebbe di eseguire il rendering delle misurazioni insignificanti.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>È possibile eseguire LyncPerfTool. exe su un server virtuale o su Microsoft Hyper-V Server 2008/2012?

Sì.

</div>

<div>

## <a name="what-does-mpop-mean"></a>Cosa significa MPOP?

MPOP è sinonimo di più punti di presenza. Si intende simulare lo scenario in cui gli utenti accedono a Lync 2013 da più computer. Si noti che in LyncPerfTool. exe ogni endpoint utilizza il profilo predefinito, ovvero che il profilo non è suddiviso tra i due punti di presenza.

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Sono stati avviati LyncPerfTool. exe ma non è stato avviato alcun evento. Per quale motivo?

Controllare il contatore totale degli endpoint attivi sui client per verificare se gli utenti si connettono. Se gli utenti non si connettono, verificare la configurazione di Lync Server 2013. Questo problema si verifica in genere perché il nome del server, il prefisso dell'utente o la password non è corretta. Si noti che i client esterni devono specificare il proxy di accesso come valore TargetServer. Verificare la porta nel file di configurazione.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Come si fa a sapere che sta accadendo qualcosa?

I vari contatori delle prestazioni di LyncPerfTool indicano se gli utenti si connettono e eseguono azioni. Tuttavia, un modo semplice per effettuare la verifica consiste nell'accedere a uno degli account utilizzando Lync 2013 ed eseguire l'azione desiderata.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Sono stati installati gli strumenti di pianificazione della capacità di Live Communications Server 2007 R2 e/o Lync Server 2010. È tutto OK?

No. Sono presenti problemi di interoperabilità ed è necessario disinstallare tutte le versioni precedenti del prodotto.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Gli strumenti di stress e prestazioni configurano la topologia del server delle informazioni di chiamata CAA?

No. Gli strumenti creano solo gli utenti, i contatti e le liste di distribuzione e simulano il carico dell'utente.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual è il numero massimo di utenti supportati dagli strumenti?

È stato creato un totale di 80.000 utenti e sono stati eseguiti test per un totale di 30.000 utenti, utilizzando questi strumenti. È consigliabile disporre di un massimo di 120.000 utenti, anche se le limitazioni tecniche consentono un valore superiore, a seconda dell'hardware del server e del client.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

