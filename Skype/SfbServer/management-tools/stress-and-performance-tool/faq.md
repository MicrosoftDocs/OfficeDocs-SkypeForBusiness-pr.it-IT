---
title: Domande frequenti sullo strumento di stress e prestazioni di Skype for Business Server 2015
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
description: Skype for business 2015 stress and Performance Tool Frequently Asked Questions (domande frequenti), utili per scoprire quali configurazioni di strumenti sono supportate, per la risoluzione dei problemi relativi agli strumenti e per chiarire comportamenti che possono essere visualizzati durante l'esecuzione degli strumenti di stress e prestazioni.
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814966"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Domande frequenti sullo strumento di stress e prestazioni di Skype for Business Server 2015
 
Skype for business 2015 stress and Performance Tool Frequently Asked Questions (domande frequenti), utili per scoprire quali configurazioni di strumenti sono supportate, per la risoluzione dei problemi relativi agli strumenti e per chiarire comportamenti che possono essere visualizzati durante l'esecuzione degli strumenti di stress e prestazioni.
  
 In questa sezione sono incluse alcune delle domande più frequenti sullo strumento per lo stress e le prestazioni di Skype for Business Server 2015 e possono essere utili per la risoluzione dei problemi e per le scelte di configurazione degli strumenti.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>È possibile eseguire LyncPerfTool.exe in produzione?

Questo **non** è consigliato. Lo strumento potrebbe influire sulle prestazioni del server di produzione, sulla sicurezza e sull'esperienza dell'utente finale.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Si sta registrando gli utenti per la prima volta. Perché i server che eseguono un carico elevato?

La prima volta che gli utenti accedono, si verificano ulteriori operazioni in background. Di conseguenza, le prestazioni sul server back-end di Microsoft SQL Server possono essere degradate. Si consiglia di eseguire un test breve che accede a tutti gli utenti e quindi riavviare i client prima di iniziare a misurare i risultati con lo strumento. Skype for Business Server non supporta più di 12 sessioni di accesso utente simultanee al secondo, ma tenere presente che il numero effettivo che può essere gestito dai server dipende dalla configurazione hardware e potrebbe essere inferiore al valore supportato.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>I client sono in esaurimento memoria. Cosa si può fare?

Se i client esauriscono la memoria, è consigliabile ridurre il numero di utenti connessi al pool Front End di Skype for Business Server. È inoltre possibile scegliere di eseguire la scalabilità orizzontale dei pool Front end se il problema persiste.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>È possibile eseguire questo strumento su un server Skype for business?

Non è possibile farlo. Questo scenario non è supportato perché potrebbe avere esito negativo a causa di una mancata corrispondenza binaria e anche perché l'obiettivo è quello di misurare il consumo di risorse sul server. Effettivamente l'esecuzione dello strumento potrebbe influire sulle prestazioni del server e invalidare i dati e le misure.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>È possibile eseguire LyncPerfTool.exe su un server virtuale o su Microsoft Hyper-V Server 2008/2012?

Sì, è possibile.
  
## <a name="what-does-mpop-mean"></a>Cosa significa MPOP?

MPOP è un metodo ridotto per dire "più punti di presenza". MPOP ha lo scopo di simulare gli scenari in cui gli utenti accedono a client Skype for business 2015 da più computer o dispositivi. Tenere presente che, in LyncPerfTool.exe, ogni endpoint utilizza il profilo predefinito. In altre parole, il profilo non è suddiviso tra due punti di presenza.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ho cominciato LyncPerfTool.exe ma non succede nulla. Per quale motivo?

Controllare il contatore totale degli endpoint attivi nei server per verificare se gli utenti si connettono. Se gli utenti non si connettono, verificare la configurazione di Skype for Business Server 2015. Il problema visualizzato in genere si verifica perché uno dei nomi del server, il prefisso utente o la password non è corretto. Tenere presente che i client esterni devono specificare il proxy di accesso e i valori di TargetServer. Verificare il numero di porta nel file di configurazione.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>In che modo è possibile verificare che venga misurato qualcosa?

Esistono contatori delle prestazioni di LyncPerfTool che indicano se gli utenti si connettono e eseguono azioni, ma il modo più semplice per verificare che le azioni vengano misurate consiste nell'accedere a uno degli account con un client Skype for business 2015 e fare queste azioni personalmente. Controllare i risultati per confermare che sono state eseguite misure.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Sono stati installati gli strumenti di pianificazione della capacità di Lync Server 2010 e/o gli strumenti di pianificazione della capacità di Lync Server 2013. È tutto a posto?

 Questi strumenti presentano problemi di interoperabilità. È necessario disinstallare tutte le versioni precedenti di questi strumenti per ottenere dati validi dallo strumento di ricerca di stress e prestazioni di Skype for Business Server 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Gli strumenti di stress e prestazioni configurano la topologia del server delle informazioni di chiamata CAA?

No, gli strumenti non lo faranno. Gli strumenti creano solo utenti, contatti e liste di distribuzione per simulare il carico dell'utente.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual è il numero massimo di utenti supportati dagli strumenti?

Durante il testing, è stato creato un totale di 80.000 utenti ed è stato eseguito il test per un totale di 30.000 utenti che eseguono questi strumenti. Si consiglia un massimo di 120.000 utenti, anche se le limitazioni tecniche consentono valori superiori. Tenere presente che questi valori dipendono dal server e dall'hardware nell'ambiente.
  

