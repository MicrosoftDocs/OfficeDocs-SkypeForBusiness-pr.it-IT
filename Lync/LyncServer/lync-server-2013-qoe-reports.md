---
title: 'Lync Server 2013: report QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04960c43dc8e29c6e5af44a1d3109e40dd578479
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Report QoE in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>Riepilogo QoE/report di tendenza

I report di riepilogo/tendenze QoE sono utili per trovare i tempi di utilizzo del giorno e per esaminare la qualità dei contenuti multimediali in questi periodi per assicurare che le risorse di rete dell'organizzazione siano sufficienti. L'organizzazione può anche usare i numerosi filtri disponibili nel report per isolare i numeri di prestazioni per determinati percorsi, tipi di client e dispositivi e server.

I report di riepilogo/tendenza QoE sono costituiti da:

  - Riepilogo/report di riassunto UC-to-UC

  - Riepilogo PSTN/rapporto tendenza

  - Riepilogo delle conferenze/rapporto sulle tendenze

</div>

<div>

## <a name="qoe-performance-reports"></a>Report prestazioni QoE

I report sulle prestazioni QoE includono dettagli sui tre report che si concentrano sulle prestazioni QoE di Mediation Server, A/V Conferencing Servers e location endpoint.

</div>

<div>

## <a name="mediation-server-performance-report"></a>Report prestazioni Mediation Server

Il report prestazioni Mediation Server elenca le metriche conseguite da una o più mediazioni durante il periodo di tempo specificato. Le metriche per la gamba del server comunicazioni unificate (UC)-mediazione e il segmento Mediation Server-to-gateway di ogni chiamata vengono segnalate separatamente. Usare questo report per confrontare il volume e le prestazioni dei vari server di mediazione dell'organizzazione.

Per ogni Mediation Server (e per ogni gamba di chiamata), nel report vengono visualizzati i seguenti elementi:

  - Numero di chiamate

  - Perdita pacchetti

  - Tempo di andata e ritorno

  - Jitter

  - Punteggio di opinione media conversazione (MOS)

  - Invio di MOS

  - MOS in ascolto

  - MOS di rete

  - Degradazione MOS Network

  - Ritorno Echo

  - Livello di segnale

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>Report prestazioni di un/V Conferencing Server

Il report prestazioni A/V Conferencing Server fornisce elenchi di metriche conseguiti da uno o più server di conferenza A/V durante il periodo di tempo specificato. Questo report può essere usato per confrontare il volume e le prestazioni dei vari server di conferenza A/V dell'organizzazione. L'organizzazione può anche isolare il report in modo da mostrare solo l'esperienza per specifici tipi di client, ad esempio client Lync o client PSTN.

Per ogni server A/V Conferencing, il report Visualizza le operazioni seguenti:

  - Numero di conferenze

  - Perdita pacchetti

  - Tempo di andata e ritorno

  - Jitter

  - Punteggio di opinione media conversazione (MOS)

  - Invio di MOS

  - MOS in ascolto

  - MOS di rete

  - Degradazione MOS Network

  - Ritorno Echo

  - Livello di segnale

</div>

<div>

## <a name="location-based-performance-report"></a>Report prestazioni basato sulla posizione

Il report prestazioni basato sulla posizione fornisce un elenco di percorsi di rete e per ogni posizione viene visualizzato il numero di chiamate in ogni intervallo di qualità predeterminato. L'obiettivo di questo report è quello di comprendere la qualità dei contenuti multimediali della maggior parte delle chiamate telefoniche dell'organizzazione per varie posizioni, in modo da poter identificare le posizioni poco performanti e vedere i diversi gradi di qualità dei contenuti multimediali nell'organizzazione posizioni diverse.

Quando si Visualizza il report, vengono visualizzate diverse tabelle di metriche, ovvero una tabella per ogni metrica a cui l'organizzazione decide di segnalare. Per questo report è possibile scegliere tra le metriche seguenti:

  - Punteggio di opinione media conversazione (MOS)

  - MOS di rete

  - Degradazione MOS Network

  - Invio di MOS

  - MOS in ascolto

  - Perdita pacchetti

  - Jitter

  - Latenza

</div>

</div>

<span> </span>

</div>

</div>

</div>

