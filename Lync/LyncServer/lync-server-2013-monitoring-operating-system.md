---
title: 'Lync Server 2013: monitoraggio del sistema operativo'
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
ms.openlocfilehash: 42ac03f61fca5717d279d39e703a8ffa97e8c2cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Monitoraggio del sistema operativo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-01-26_

È necessario monitorare le prestazioni di tutti i server e i componenti di Lync Server 2013. Uno dei componenti più importanti, naturalmente, è il sistema operativo stesso. Lync Server 2013 supporta le edizioni x64 di:

  - Windows Server 2008 R2

  - Windows Server 2012 e Windows Server 2012 R2

Il modo più trasparente per monitorare un sistema operativo consiste nell'usare il Management Pack del sistema operativo Windows Server. Fornisce le nozioni fondamentali per il monitoraggio, ad esempio prestazioni, integrità e disponibilità per i computer che eseguono Windows Server 2012, Windows Server 2012 R2 e Windows Server 2008 R2.

Individuando, avvisando e rispondendo automaticamente agli eventi importanti e agli indicatori di prestazioni, questi Management Pack riducono i tempi di risoluzione per i problemi e aumentano la disponibilità complessiva e le prestazioni dei sistemi che esegue Windows Server sistemi operativi.

Oltre a rilevanti Windows Server Management Pack per System Center Operations Manager, è possibile usare gli strumenti e le risorse di sistema seguenti per monitorare l'integrità del sistema operativo (a seconda della versione del sistema operativo).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 include le caratteristiche e gli strumenti aggiuntivi seguenti per aiutare gli amministratori con il monitoraggio e la gestione dei sistemi operativi di base:

  - **Monitoraggio risorse** è uno strumento avanzato che consente di comprendere in modo approfondito l'utilizzo delle risorse di sistema da parte dei processi e dei servizi. Oltre a effettuare il monitoraggio dell'utilizzo delle risorse in tempo reale, Monitoraggio risorse consente di analizzare i processi che non rispondono, identificare le applicazioni che utilizzano file e controllare processi e servizi.

  - **Componente di analisi dell'affidabilità** è un agente incorporato che fornisce informazioni dettagliate sull'esperienza relative all'utilizzo del sistema e all'affidabilità. Queste informazioni vengono esposte tramite un'interfaccia di Strumentazione gestione Windows (WMI), rendendole disponibili per l'utilizzo da parte di sistemi per lettori portatili. L'esposizione del Componente di analisi dell'affidabilità tramite un'interfaccia WMI consente agli sviluppatori di monitorare e analizzare le applicazioni, aumentando affidabilità e prestazioni.

  - **Windows Server 2008 R2** usa il componente di analisi di affidabilità predefinito per calcolare un indice di affidabilità, che fornisce informazioni sull'uso e la stabilità complessive del sistema nel tempo. The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Monitoraggio affidabilità e prestazioni di Windows Server 2008

Le funzionalità Monitoraggio affidabilità e Monitoraggio prestazioni di Windows costituiscono uno snap-in MMC (Microsoft Management Console) nel quale sono combinate le funzionalità di strumenti autonomi precedenti, tra cui Avvisi e registri di prestazioni, Server Performance Advisor (SPA) e Monitor di sistema. Lo snap-in è provvisto di un'interfaccia grafica per la personalizzazione di insiemi di dati sulle prestazioni e di sessioni di traccia degli eventi.

È inoltre incluso Monitoraggio affidabilità, uno snap-in MMC che consente di tenere traccia delle modifiche apportate al sistema e di confrontarle con le variazioni in termini di stabilità del sistema in una visualizzazione grafica delle relative relazioni.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Monitoraggio affidabilità e Monitoraggio prestazioni di Windows

L'affidabilità e il monitoraggio delle prestazioni di Windows combinano le funzionalità di alcuni ex strumenti autonomi come i registri delle prestazioni e gli avvisi, oltre a un monitor di sistema e a un Server Performance Advisor, ma offre anche alcune nuove caratteristiche di Windows Server 2008 e Windows Server 2008 R2, ad esempio il seguente:

  - Insiemi agenti di raccolta dati

  - Visualizzazione risorse

  - Monitoraggio affidabilità

  - Creazioni guidate e modelli per la creazione di registri

**Insieme agenti di raccolta dati** raggruppa gli agenti di raccolta dati in elementi riutilizzabili per l'utilizzo in scenari diversi di monitoraggio delle prestazioni. Dopo l'archiviazione di un gruppo di agenti di raccolta dati come Insieme agenti di raccolta dati, è possibile eseguire operazioni come ad esempio la pianificazione sull'intero insieme modificando una sola proprietà. Sono inclusi anche modelli di insieme agenti di raccolta dati che consentono agli amministratori di sistema di cominciare a raccogliere immediatamente i dati delle prestazioni specifici di un ruolo di server o di uno scenario di monitoraggio.

La pagina iniziale di Monitoraggio affidabilità e Monitoraggio prestazioni di Windows è la nuova schermata di ** Visualizzazione risorse** che offre una panoramica grafica in tempo reale dell'utilizzo della CPU, del disco, della rete e della memoria. Espandendo ognuno di questi elementi monitorati, gli amministratori di sistema possono identificare quali processi vengono utilizzati dalle singole risorse. Nelle versioni precedenti di Windows, i dati in tempo reale specifici di un processo sono disponibili soltanto in modo limitato in Gestione attività.

In **Monitoraggio affidabilità** viene calcolato un indice di stabilità del sistema che indica se eventuali problemi imprevisti hanno ridotto l'affidabilità del sistema. In un grafico dell'indice di stabilità del sistema nel tempo vengono identificate rapidamente le date in cui i problemi hanno iniziato a verificarsi. Nel relativo Rapporto stabilità sistema vengono riportati i dettagli per risolvere la causa principale della riduzione dell'affidabilità. La visualizzazione delle modifiche del sistema, ad esempio l'installazione o la rimozione delle applicazioni, gli aggiornamenti al sistema operativo oppure l'aggiunta o la modifica di driver, affiancata agli errori, ad esempio gli errori delle applicazioni, gli arresti anomali del sistema operativo o gli errori hardware, consente di sviluppare rapidamente una strategia per risolvere i problemi.

È possibile ora aggiungere contatori ai file di registro e pianificarne l'avvio, l'interruzione e la durata tramite un'**interfaccia della creazione guidata**. È inoltre possibile salvare questa configurazione come modello per la raccolta dello stesso registro su computer successivi senza ripetere la selezione dell'agente di raccolta dati e pianificare i processi. In Monitoraggio affidabilità e Monitoraggio prestazioni di Windows sono state incorporate le funzionalità Avvisi e registri di prestazioni per l'utilizzo con qualsiasi insieme agenti di raccolta dati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

