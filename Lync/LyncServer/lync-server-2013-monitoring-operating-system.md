---
title: 'Lync Server 2013: monitoraggio del sistema operativo'
description: 'Lync Server 2013: monitoraggio del sistema operativo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9454b91a5f55467f93b41752686b4b0d727d935
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548062"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a>Monitoraggio del sistema operativo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-01-26_

È necessario monitorare le prestazioni di tutti i server e i componenti del Lync Server 2013. Ovviamente, uno dei componenti più importanti è il sistema operativo stesso. Lync Server 2013 supporta le edizioni x64 di:

  - Windows Server 2008 R2

  - Windows Server 2012 e Windows Server 2012 R2

Il modo più trasparente per monitorare un sistema operativo consiste nell'utilizzare il Management Pack del sistema operativo Windows Server. Sono disponibili le nozioni fondamentali di monitoraggio, quali prestazioni, integrità e disponibilità per i computer che eseguono Windows Server 2012, Windows Server 2012 R2 e Windows Server 2008 R2.

Rilevando, avvertendo e rispondendo automaticamente a eventi importanti e indicatori di prestazioni, questi Management Pack riducono i tempi di risoluzione dei problemi e aumentano la disponibilità complessiva e le prestazioni di sistemi che eseguono i sistemi operativi Windows Server.

Oltre ai Management Pack di Windows Server rilevanti per System Center Operations Manager, è possibile utilizzare le risorse e gli strumenti di sistema seguenti per monitorare l'integrità del sistema operativo, a seconda della versione del sistema operativo.

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 include le funzionalità e gli strumenti aggiuntivi seguenti che consentono agli amministratori di eseguire il monitoraggio e la gestione di base del sistema operativo:

  - **Monitor risorse di Windows** è uno strumento potente per comprendere le modalità di utilizzo delle risorse di sistema da parte dei processi e dei servizi. Oltre a monitorare l'utilizzo delle risorse in tempo reale, un monitor delle risorse consente di analizzare i processi non rispondenti, identificare le applicazioni che utilizzano i file e controllare i processi e i servizi.

  - Il **componente di analisi dell'affidabilità** è un agente in-box che fornisce informazioni dettagliate sull'utilizzo e l'affidabilità del sistema. Queste informazioni vengono esposte tramite un'interfaccia WMI per renderlo disponibile per il consumo da parte dei sistemi di lettori portatili. Esponendo il componente di analisi dell'affidabilità tramite un'interfaccia WMI, gli sviluppatori possono monitorare e analizzare le applicazioni, aumentando l'affidabilità e le prestazioni.

  - **Windows Server 2008 R2** utilizza il componente di analisi dell'affidabilità incorporato per calcolare un indice di affidabilità, in cui vengono fornite informazioni sull'utilizzo e sulla stabilità generali del sistema nel tempo. Il componente di analisi dell'affidabilità tiene anche conto di eventuali modifiche importanti al sistema che potrebbero influire sulla stabilità, ad esempio gli aggiornamenti di Windows e le installazioni di applicazioni.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Monitoraggio affidabilità e prestazioni di Windows Server 2008

Monitoraggio affidabilità e prestazioni di Windows è uno snap-in MMC che combina la funzionalità dei precedenti strumenti autonomi, tra cui registri delle prestazioni e avvisi, Server Performance Advisor e monitor di sistema. Offre un'interfaccia grafica per la personalizzazione della raccolta di dati di prestazioni e delle sessioni di traccia degli eventi.

Include inoltre il monitoraggio dell'affidabilità, uno snap-in MMC che consente di tenere traccia delle modifiche apportate al sistema e le confronta con le modifiche apportate alla stabilità del sistema e fornisce una visualizzazione grafica della relazione.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Monitoraggio affidabilità e prestazioni di Windows

Sebbene l'affidabilità e il monitoraggio delle prestazioni di Windows combinino funzionalità di alcuni strumenti precedenti, ad esempio registri di prestazioni e avvisi, nonché System Monitor and Server Performance Advisor, vengono fornite anche alcune nuove funzionalità di Windows Server 2008 e Windows Server 2008 R2, ad esempio:

  - Insiemi di agenti di raccolta dati

  - Visualizzazione risorse

  - Monitoraggio affidabilità

  - Procedure guidate e modelli per la creazione di registri

Set di agenti di **raccolta dati** raggruppa i collezionisti di dati in elementi riutilizzabili per l'utilizzo con diversi scenari di monitoraggio delle prestazioni. Dopo che un gruppo di collezionisti di dati è archiviato come set di agenti di raccolta dati, le operazioni come la pianificazione possono essere applicate a tutto il set tramite una singola modifica della proprietà. Monitoraggio affidabilità e prestazioni di Windows include modelli set di agenti di raccolta dati predefiniti che consentono agli amministratori di sistema di raccogliere immediatamente dati sulle prestazioni specifici di un ruolo del server o di uno scenario di monitoraggio.

La Home page di monitoraggio affidabilità e prestazioni di Windows è la nuova schermata di **visualizzazione delle risorse** , che fornisce una panoramica grafica in tempo reale di utilizzo della CPU, del disco, della rete e della memoria. Espandendo ognuno di questi elementi monitorati, gli amministratori di sistema possono identificare i processi che utilizzano le risorse. Nelle versioni precedenti di Windows, in tempo reale, i dati specifici dei processi erano disponibili solo in formato limitato in Task Manager.

**Monitor di affidabilità** calcola un indice di stabilità del sistema che indica se i problemi imprevisti riducono l'affidabilità del sistema. Un grafico dell'indice di stabilità nel tempo identifica rapidamente le date in cui si sono verificati problemi. Il rapporto di stabilità del sistema associato fornisce informazioni dettagliate per la risoluzione dei problemi relativi alla causa di un'affidabilità ridotta. Visualizzando le modifiche apportate al sistema (installazione o rimozione di applicazioni, aggiornamenti al sistema operativo o aggiunta o modifica dei driver) affiancati da errori (errori di applicazioni, arresti anomali dei sistemi operativi o errori hardware), una strategia per risolvere i problemi può essere sviluppata rapidamente.

L'aggiunta di contatori ai file di registro e la pianificazione dell'avvio, dell'interruzione e della durata possono ora essere eseguite tramite un' **interfaccia della procedura guidata**. Inoltre, il salvataggio di questa configurazione come modello consente agli amministratori di sistema di raccogliere lo stesso registro su altri computer senza ripetere la selezione e i processi di pianificazione dell'agente di raccolta dati. Le funzionalità di avvisi e registri delle prestazioni sono state integrate in Monitoraggio affidabilità e prestazioni di Windows per l'utilizzo con qualsiasi insieme agenti di raccolta dati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

