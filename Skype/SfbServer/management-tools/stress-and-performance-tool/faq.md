---
title: Domande frequenti per lo strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Domande frequenti sugli strumenti di stress e prestazioni di Skype for business 2015 (FAQ), utili per scoprire quali configurazioni di strumenti sono supportate, risolvere i problemi relativi agli strumenti e chiarire i comportamenti che potrebbero essere visualizzati quando si esegue lo strumento stress e prestazioni .
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816185"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Domande frequenti per lo strumento di stress e prestazioni di Skype for Business Server 2015
 
Domande frequenti sugli strumenti di stress e prestazioni di Skype for business 2015 (FAQ), utili per scoprire quali configurazioni di strumenti sono supportate, risolvere i problemi relativi agli strumenti e chiarire i comportamenti che potrebbero essere visualizzati quando si esegue lo strumento stress e prestazioni .
  
 In questa pagina sono elencate alcune delle domande più frequenti sullo strumento di stress e prestazioni di Skype for Business Server 2015 e possono essere utili per la risoluzione dei problemi e le opzioni di configurazione degli strumenti.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>È possibile eseguire LyncPerfTool. exe in produzione?

Questa operazione **non** è consigliata. Lo strumento influisce sulle prestazioni del server di produzione, sulla sicurezza e sull'esperienza utente finale.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Sto registrando i miei utenti per la prima volta. Perché i server che gestiscono un carico elevato?

La prima volta che si effettua l'accesso agli utenti, le operazioni aggiuntive si verificano in background. Di conseguenza, le prestazioni del server back-end di Microsoft SQL Server possono essere degradate. È consigliabile eseguire un breve test che registri tutti gli utenti e quindi riavviare i client prima di iniziare a misurare i risultati con lo strumento. Skype for Business Server non supporta più di 12 sessioni di accesso simultanee degli utenti al secondo, ma tieni presente che il numero effettivo che può essere gestito dai server dipende dalla configurazione hardware e può essere inferiore al valore supportato.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>I miei clienti stanno esaurendo la memoria. Cosa dovrei fare?

Se i client esauriscono la memoria, è consigliabile ridurre il numero di utenti connessi al pool Front-End di Skype for Business Server. Se il problema persiste, è anche possibile scegliere di scalare i pool Front-end.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>È possibile eseguire questo strumento in un server Skype for business?

Non dovresti farlo. Questo scenario non è supportato perché potrebbe non riuscire a causa di una mancata corrispondenza binaria e anche perché l'obiettivo è misurare il consumo delle risorse nel server. In realtà l'esecuzione dello strumento potrebbe influire sulle prestazioni del server e invalidare i dati e le misure.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>È possibile eseguire LyncPerfTool. exe in un server virtuale o in Microsoft Hyper-V Server 2008/2012?

Sì, è possibile.
  
## <a name="what-does-mpop-mean"></a>Cosa significa MPOP?

MPOP è un modo ridotto per dire "più punti di presenza". MPOP è concepito per simulare scenari in cui gli utenti accedono al client Skype for business 2015 da più computer o dispositivi. Tieni presente che in LyncPerfTool. exe ogni endpoint usa il profilo predefinito. In altre parole, il profilo non è diviso tra due punti di presenza.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>È stato avviato LyncPerfTool. exe, ma non succede nulla. Cosa sta succedendo?

Controllare il contatore degli endpoint attivi totali nei server per verificare se gli utenti si connettono. Se gli utenti non si connettono, verificare la configurazione di Skype for Business Server 2015. Il problema che si sta vedendo in genere si verifica perché uno di nome server, un prefisso utente o una password non è corretto. Tieni presente che i client esterni devono specificare i valori proxy e TargetServer di Access. Verificare il numero di porta nel file di configurazione.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Come si può verificare che qualcosa venga misurato?

Esistono contatori delle prestazioni di LyncPerfTool che indicano se gli utenti si connettono o eseguono azioni, ma il modo più semplice per verificare che le azioni vengano misurate consiste nell'accedere a uno degli account con un client di Skype for business 2015 azioni personali. Verificare i risultati per confermare le misurazioni.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Sono installati gli strumenti di pianificazione della capacità di Lync Server 2010 e/o gli strumenti di pianificazione della capacità di Lync Server 2013. Va bene?

 Questi strumenti hanno problemi di interoperabilità. Devi disinstallare tutte le versioni precedenti di questi strumenti per ottenere dati validi dallo strumento di stress e prestazioni di Skype for Business Server 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Gli strumenti di stress e prestazioni configurano la topologia del server delle informazioni sulle chiamate CAA?

No, gli strumenti non lo faranno. Gli strumenti creano solo utenti, contatti e liste di distribuzione per simulare il caricamento degli utenti.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual è il numero massimo di utenti supportati dagli strumenti?

Durante i test, abbiamo creato fino a un totale di 80.000 utenti e test eseguiti per un totale di 30.000 utenti che hanno eseguito questi strumenti. Suggeriamo un numero massimo di utenti di 120.000, anche se le limitazioni tecniche consentono valori più alti. Tieni presente che questi valori dipendono dal server e dall'hardware nell'ambiente.
  

