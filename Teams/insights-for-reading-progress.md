---
title: Informazioni approfondite per i suggerimenti di Valutazione della lettura
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Informazioni su come vengono usati i dati di Insights in Valutazione della lettura per migliorare le competenze di lettura degli studenti.
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157884"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>Informazioni approfondite per i suggerimenti di Valutazione della lettura

Questo articolo è rivolto agli amministratori IT dell'istruzione che vogliono capire come vengono usati i dati di Insights per i suggerimenti di Valutazione della lettura.

Insights consente ai docenti di tenere traccia della fluidità di lettura degli studenti usando Valutazione della lettura, uno strumento che registra gli studenti che leggono ad alta voce e rileva automaticamente gli errori.

Valutazione della lettura fornisce i seguenti tipi di esercizi di test di lettura:

- **Parole contestuali**: esercita le parole consigliate in base alle parole pronunciate erroneamente dagli studenti nelle attività precedenti di Valutazione della lettura.
- **Parole correlate**: esercita le parole consigliate in base agli errori comuni agli studenti con lo stesso tipo di difficoltà di lettura.

Per indicazioni sui docenti sull'uso di Insights per valutazione della lettura, vedi [Creare attività di verifica della valutazione della lettura con Approfondimenti](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe).

## <a name="how-does-microsoft-recommend-correlated-words"></a>In che modo Microsoft consiglia parole correlate?

Le parole correlate sono parole personalizzate consigliate che Insights per l'istruzione identifica come difficili per altri studenti che condividono schemi di lettura simili.

Le parole correlate si basano su una tecnica di apprendimento automatico chiamata **Filtro collaborativo**.

- Insights analizza i dati di lettura degli studenti nelle varie classi che condividono la tua area geografica e la tua lingua per identificare gruppi di parole difficili per gli studenti.

- Data una serie di parole difficili, Insights identifica anche cluster simili e li usa per consigliare altre parole agli studenti per l'esercitazione mirata.

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>Microsoft mantiene i dati degli studenti privati e sicuri?

Microsoft si impegna a usare i dati in modo responsabile ed etico.

Ecco alcune delle misure adottate per creare questa funzionalità:

- Le analisi dei dati degli studenti sono create in modo approfondito, il che significa che Microsoft non ha accesso ai dati di lettura degli studenti, ma solo ai risultati dell'analisi.

- Gli amministratori tenant possono rifiutare esplicitamente il processo di analisi dei dati disattivando [l'interruttore Inferenze avanzate](class-insights.md#turn-on-and-off-advanced-inferences-in-insights).

- Le parole non appropriate vengono filtrate dagli elenchi di suggerimenti **Parole correlate** . Questa operazione viene eseguita attraverso una combinazione di tecniche di data science e il blocco di parole problematiche note. Tuttavia, questo processo non è una prova di errore. I docenti devono esaminare le raccomandazioni.

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>Quali sono le limitazioni dei suggerimenti sulle parole di Insights?

- I suggerimenti di Word per Valutazione della lettura sono attualmente supportati in [queste lingue](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages).

- Le parole correlate vengono presentate solo nelle classi con almeno cinque studenti che hanno inviato attività di Valutazione della lettura.

- Insights potrebbe non consigliare nuove parole nei casi in cui non esistono studenti con schemi di errore simili, ma non identici.
