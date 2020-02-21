---
title: 'Lync Server 2013: rapporti QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 353e0941f443e2cb971f8ebd037413232e21b827
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Report QoE in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>Riepilogo QoE/rapporti di tendenza

I report di riepilogo/tendenze QoE sono utili per individuare i tempi di utilizzo massimi del giorno ed esaminare la qualità multimediale in quei periodi per garantire che le risorse di rete dell'organizzazione siano sufficienti. L'organizzazione può anche utilizzare i numerosi filtri disponibili nel report per isolare i numeri di prestazioni per determinati percorsi, tipi di client e dispositivi e server.

I rapporti di riepilogo/trend QoE sono costituiti da:

  - Report di riepilogo/trend da UC a UC

  - Riepilogo PSTN/rapporto trend

  - Riepilogo conferenze/Rapporto tendenze

</div>

<div>

## <a name="qoe-performance-reports"></a>Rapporti sulle prestazioni QoE

I report sulle prestazioni QoE forniscono informazioni dettagliate sui tre rapporti che si concentrano sulle prestazioni QoE di Mediation Server, A/V Conferencing Server e endpoint locations.

</div>

<div>

## <a name="mediation-server-performance-report"></a>Rapporto prestazioni Mediation Server

Il rapporto prestazioni Mediation Server elenca le metriche ottenute da una o più mediazione durante il periodo di tempo specificato. Le metriche per la gamba del server Unified Communications (UC)-to-Mediation e la gamba Mediation Server-to-gateway di ogni chiamata vengono segnalate separatamente. Utilizzare questo report per confrontare il volume e le prestazioni dei diversi Mediation Server dell'organizzazione.

Per ogni Mediation Server (e per ogni gamba di chiamata), il report Visualizza gli elementi seguenti:

  - Numero di chiamate

  - Perdita di pacchetti

  - Tempo di andata e ritorno

  - Instabilità

  - Punteggio di opinione medio di conversazione (MOS)

  - Invio di MOS

  - MOS di attesa

  - MOS di rete

  - Degradazione MOS di rete

  - Return Echo

  - Livello di segnale

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>Report sulle prestazioni di A/V Conferencing Server

Il rapporto prestazioni A/V Conferencing Server fornisce gli elenchi di metriche ottenute da uno o più server A/V Conferencing durante il periodo di tempo specificato. Questo report può essere utilizzato per confrontare il volume e le prestazioni dei diversi server A/V Conferencing dell'organizzazione. L'organizzazione può anche isolare il report in modo da mostrare solo l'esperienza per specifici tipi di client, ad esempio client di Lync o client PSTN.

Per ogni server A/V Conferencing, il report Visualizza gli elementi seguenti:

  - Numero di conferenze

  - Perdita di pacchetti

  - Tempo di andata e ritorno

  - Instabilità

  - Punteggio di opinione medio di conversazione (MOS)

  - Invio di MOS

  - MOS di attesa

  - MOS di rete

  - Degradazione MOS di rete

  - Return Echo

  - Livello di segnale

</div>

<div>

## <a name="location-based-performance-report"></a>Report sulle prestazioni basato sulla posizione

Il report sulle prestazioni basato sulla posizione fornisce un elenco di percorsi di rete e per ogni percorso viene visualizzato il numero di chiamate in ogni intervallo di qualità predeterminato. L'obiettivo di questo report è quello di fornire informazioni sulla qualità multimediale della maggior parte delle chiamate telefoniche dell'organizzazione per diverse posizioni in modo da poter identificare le posizioni poco performative e vedere i diversi gradi di qualità multimediale nell'organizzazione. posizioni diverse.

Quando si Visualizza il report, vengono visualizzate diverse tabelle di metriche, ovvero una tabella per ogni metrica a cui l'organizzazione decide di riferire. Per questo report è possibile scegliere tra le metriche seguenti:

  - Punteggio di opinione medio di conversazione (MOS)

  - MOS di rete

  - Degradazione MOS di rete

  - Invio di MOS

  - MOS di attesa

  - Perdita di pacchetti

  - Instabilità

  - Latenza

</div>

</div>

<span> </span>

</div>

</div>

</div>

