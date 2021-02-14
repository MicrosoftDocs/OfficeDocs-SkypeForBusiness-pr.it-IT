---
title: Domande frequenti su Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Domande frequenti su Skype for Business 2015 Stress and Performance Tool, utili per scoprire quali configurazioni degli strumenti sono supportate, risolvere i problemi relativi agli strumenti e chiarire i comportamenti che possono essere visualizzati quando si eseguono gli strumenti Stress and Performance.
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814966"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Domande frequenti su Skype for Business Server 2015 Stress and Performance Tool
 
Domande frequenti su Skype for Business 2015 Stress and Performance Tool, utili per scoprire quali configurazioni degli strumenti sono supportate, risolvere i problemi relativi agli strumenti e chiarire i comportamenti che possono essere visualizzati quando si eseguono gli strumenti Stress and Performance.
  
 Queste domande frequenti riguardano alcune delle domande più frequenti sullo strumento Stress and Performance di Skype for Business Server 2015 e possono essere utili per la risoluzione dei problemi e le scelte di configurazione degli strumenti.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>È possibile eseguire LyncPerfTool.exe in produzione?

Questa opzione **non è** consigliata. Lo strumento inciderebbe sulle prestazioni del server di produzione, sulla sicurezza e sull'esperienza dell'utente finale.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>I'm logging my users on for the first time. Perché i server eseguono un carico elevato?

Al primo accesso degli utenti, vengono eseguite operazioni aggiuntive in background. Di conseguenza, le prestazioni nel server Microsoft SQL Server back-end possono essere ridotte. È consigliabile eseguire un breve test che consente di accedere a tutti gli utenti e quindi riavviare i client prima di iniziare a misurare i risultati con lo strumento. Skype for Business Server non supporta più di 12 sessioni di accesso utente simultanee al secondo, ma tieni presente che il numero effettivo che può essere gestito dai server dipende dalla configurazione hardware e può essere inferiore al valore supportato.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Memoria insufficiente per i client. Cosa si può fare?

Se la memoria dei client è insufficiente, è consigliabile ridurre il numero di utenti connessi per ogni pool Front End di Skype for Business Server. È inoltre possibile scegliere di scalare orizzontalmente i pool Front End se il problema persiste.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Posso eseguire questo strumento su un server Skype for Business?

Non è consigliabile eseguire questa operazione. Questo scenario non è supportato perché potrebbe non riuscire a causa di una mancata corrispondenza binaria e anche perché l'obiettivo è misurare il consumo di risorse nel server. L'esecuzione dello strumento in realtà inciderebbe sulle prestazioni del server e invaliderebbe i dati e le misurazioni.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>È possibile eseguire LyncPerfTool.exe in un server virtuale o in Microsoft Hyper-V Server 2008/2012?

Sì.
  
## <a name="what-does-mpop-mean"></a>Cosa significa MPOP?

MPOP è un modo abbreviato di dire "più punti di presenza". MPOP ha lo scopo di simulare scenari in cui gli utenti sono connessi al client Skype for Business 2015 da più computer o dispositivi. Tenere presente che, in LyncPerfTool.exe, ogni endpoint usa il profilo predefinito. In altre parole, il profilo non viene suddiviso tra due punti di presenza.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>I started LyncPerfTool.exe but nothing is happening. Per quale motivo?

Controllare il contatore Totale endpoint attivi nei server per verificare se gli utenti si connettono. Se gli utenti non si connettono, verificare la configurazione di Skype for Business Server 2015. Il problema che si verifica in genere si verifica perché il nome del server, il prefisso utente o la password non è corretto. Tenere presente che i client esterni devono specificare i valori proxy di accesso e TargetServer. Verificare il numero di porta nel file di configurazione.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Come posso essere sicuro che venga misurato qualcosa?

Esistono contatori delle prestazioni di LyncPerfTool che indicano se gli utenti si connettono ed eseguono azioni, ma il modo più semplice per assicurarsi che vengano misurate le azioni è accedere a uno degli account con un client Skype for Business 2015 ed eseguire tali azioni manualmente. Controllare i risultati per verificare che le misurazioni sono state intraprese.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Sono installati gli strumenti di pianificazione della capacità di Lync Server 2010 e/o Lync Server 2013. Va bene?

 Questi strumenti hanno problemi di interoperabilità. È necessario disinstallare tutte le versioni precedenti di questi strumenti per ottenere dati validi dallo strumento Skype for Business Server 2015 Stress and Performance.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Gli strumenti stress e prestazioni configurano la topologia del server informazioni sulle chiamate CAA?

No, gli strumenti non lo fanno. Gli strumenti consentono di creare solo utenti, contatti e liste di distribuzione per simulare il carico degli utenti.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual è il numero massimo di utenti supportati dagli strumenti?

Durante i test, abbiamo creato fino a un totale di 80.000 utenti ed eseguito test per un totale di 30.000 utenti che eseguono questi strumenti. È consigliabile un massimo di 120.000 utenti, anche se le limitazioni tecniche consentono valori più elevati. Tenere presente che questi valori dipendono dal server e dall'hardware dell'ambiente.
  

