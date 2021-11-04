---
title: Domande frequenti per lo Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business domande frequenti su Stress and Performance Tool 2015, utili per individuare le configurazioni degli strumenti supportate, risolvere i problemi relativi agli strumenti e chiarire i comportamenti che possono verificarsi durante l'esecuzione degli strumenti Stress and Performance.
ms.openlocfilehash: 7a922293b4e8b938d6ed9c1d3f763a47b70a5c6c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771942"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Domande frequenti per lo Skype for Business Server 2015 Stress and Performance Tool
 
Skype for Business domande frequenti su Stress and Performance Tool 2015, utili per individuare le configurazioni degli strumenti supportate, risolvere i problemi relativi agli strumenti e chiarire i comportamenti che possono verificarsi durante l'esecuzione degli strumenti Stress and Performance.
  
 Queste domande frequenti riguardano alcune delle domande più frequenti sullo strumento stress e prestazioni di Skype for Business Server 2015 e possono essere utili per la risoluzione dei problemi e le scelte di configurazione degli strumenti.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>È possibile eseguire LyncPerfTool.exe in produzione?

Questa operazione **non è** consigliata. Lo strumento influisce sulle prestazioni, sulla sicurezza e sull'esperienza utente finale del server di produzione.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Sto accedendo agli utenti per la prima volta. Perché i server eseguono un carico elevato?

Al primo accesso degli utenti, vengono eseguite operazioni aggiuntive in background. Di conseguenza, le prestazioni nel server Microsoft SQL Server back-end possono essere ridotte. È consigliabile eseguire un breve test che consente di accedere a tutti gli utenti e quindi riavviare i client prima di iniziare a misurare i risultati con lo strumento. Skype for Business Server non supporta più di 12 sessioni di accesso utente simultanee al secondo, ma tenere presente che il numero effettivo che può essere gestito dai server dipende dalla configurazione hardware e può essere inferiore al valore supportato.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Memoria insufficiente per i client. Cosa devo fare?

Se la memoria dei client è insufficiente, è consigliabile ridurre il numero di utenti connessi per Skype for Business Server pool Front End. È inoltre possibile scegliere di scalare orizzontalmente i pool Front End se il problema è persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>È possibile eseguire questo strumento in un server Skype for Business, se stesso?

Non dovresti farlo. Questo scenario non è supportato perché potrebbe non riuscire a causa di una mancata corrispondenza binaria e anche perché l'obiettivo è misurare l'utilizzo delle risorse nel server. L'esecuzione dello strumento in realtà influisce sulle prestazioni del server e invalida i dati e le misurazioni.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>È possibile eseguire LyncPerfTool.exe in un server virtuale o Microsoft Hyper-V Server 2008/2012?

Sì, è possibile.
  
## <a name="what-does-mpop-mean"></a>Cosa significa MPOP?

MPOP è un modo abbreviato di dire "più punti di presenza". MPOP ha lo scopo di simulare scenari in cui gli utenti sono connessi Skype for Business client 2015 da più computer o dispositivi. Tenere presente che, in LyncPerfTool.exe, ogni endpoint usa il profilo predefinito. In altre parole, il profilo non viene diviso tra due punti di presenza.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ho iniziato LyncPerfTool.exe ma non succede nulla. Per quale motivo?

Controllare il contatore Totale endpoint attivi nei server per verificare se gli utenti si connettono. Se gli utenti non si connettono, verificare la configurazione Skype for Business Server 2015. Il problema che si verifica in genere si verifica perché il nome del server, il prefisso utente o la password non è corretto. Tenere presente che i client esterni devono specificare i valori proxy di accesso e TargetServer. Verificare il numero di porta nel file di configurazione.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Come posso essere sicuro che venga misurato qualcosa?

Esistono contatori delle prestazioni di LyncPerfTool che indicano se gli utenti si connettono ed eseguono azioni, ma il modo più semplice per verificare che le azioni vengano misurate è accedere a uno degli account con un client Skype for Business 2015 ed eseguire tali azioni manualmente. Controllare i risultati per verificare che le misurazioni sono state prese.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Sono installati gli strumenti di pianificazione della capacità di Lync Server 2010 e/o Lync Server 2013. È tutto a posto?

 Questi strumenti hanno problemi di interoperabilità. È necessario disinstallare tutte le versioni precedenti di questi strumenti per ottenere dati validi dallo strumento Skype for Business Server 2015 Stress and Performance.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Gli strumenti stress e prestazioni configurano la topologia del server informazioni sulle chiamate CAA?

No, gli strumenti non consentono di eseguire questa operazione. Gli strumenti consentono di creare solo utenti, contatti e liste di distribuzione per simulare il carico degli utenti.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual è il numero massimo di utenti supportati dagli strumenti?

Durante i test, abbiamo creato fino a un totale di 80.000 utenti ed eseguito test per un totale di 30.000 utenti che eseguono questi strumenti. Consigliamo un massimo di 120.000 utenti, anche se le limitazioni tecniche consentono valori più elevati. Tenere presente che questi valori dipendono dal server e dall'hardware dell'ambiente.
  

