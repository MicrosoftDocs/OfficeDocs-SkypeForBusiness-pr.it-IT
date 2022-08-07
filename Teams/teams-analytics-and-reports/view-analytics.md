---
title: Visualizzare i dati analitici in Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: rahulmi
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sull'analisi tra team, l'analisi per team e l'analisi per canale in Teams, che consentono agli utenti di visualizzare i dati di utilizzo per i team o i canali di cui fanno parte.
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 9755eca1c6f6f1afb57b615dfa7e96fd0cbefe64
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267391"
---
# <a name="view-analytics-in-teams"></a>Visualizzare i dati analitici in Teams

In Microsoft Teams, gli utenti possono visualizzare i dati analitici per i team e i canali di cui fanno parte. Queste informazioni consentono agli utenti di conoscere i modelli di utilizzo e le attività dei propri team. Gli utenti possono visualizzare dati come il numero di utenti attivi, post, risposte e altro in tre livelli.

- **L'analisi tra team** offre agli utenti un'ampia panoramica dei dati di utilizzo per tutti i team di cui sono membri o proprietari in un'unica visualizzazione elenco.
- **L'analisi per team** offre agli utenti una visualizzazione più granulare, che mostra i dati di utilizzo per un team specifico.
- **L'analisi per canale** offre agli utenti una visualizzazione ancora più granulare, che mostra i dati di utilizzo per un canale specifico.

Gli utenti possono filtrare una qualsiasi di queste visualizzazioni per visualizzare i dati per un periodo di tempo specificato.

## <a name="view-cross-team-analytics"></a>Visualizzare l'analisi tra team

1. In Teams, in fondo all'elenco dei team, accanto a **Partecipa o crea un team**, fai clic su **Gestisci team**.
2. Fare clic sulla scheda **Analisi** .
3. Selezionare un intervallo di date per visualizzare i dati di utilizzo per tutti i team di cui si è membri o proprietari.

    ![Screenshot della visualizzazione di analisi tra team.](../media/view-analytics-cross-team.png)

    |Elemento |Descrizione  |
    |--------|-------------|
    |**Nome**   |Nome del team. |
    |**Utenti attivi**   |Numero di utenti attivi nel team e linea di tendenza dell'attività del team durante il periodo di tempo specificato.
    |**Persone**   |Numero totale di persone nel team nel periodo di tempo specificato. Sono inclusi proprietari del team, membri del team e guest.|
    |**Utenti guest**   |Numero di guest nel team durante il periodo di tempo specificato. |
    |**Messaggi**   |Numero di nuovi messaggi pubblicati nella chat del team durante il periodo di tempo specificato. |
    |**Risposte**   |Numero di risposte nella chat del team durante il periodo di tempo specificato. |
    |**Tipo**   |Che si tratti di un team privato o pubblico.|

## <a name="view-per-team-analytics"></a>Visualizzare l'analisi per team

1. In Teams passare al team desiderato, fare clic su **Altre opzioni (...)** e quindi su **Gestisci team**.
2. Fare clic sulla scheda **Analisi** .
4. Selezionare un intervallo di date per visualizzare i dati di utilizzo per il team.  

    ![Screenshot della visualizzazione di analisi per team.](../media/view-analytics-per-team.png)

    |Elemento |Descrizione  |
    |--------|-------------|
    |**Riepilogo**   |Riepilogo dell'attività del team, tra cui:<ul><li>**Utenti**: numero totale di utenti nel periodo di tempo specificato. Sono inclusi proprietari del team, membri del team e guest.</li> <li>**Post**: numero di nuovi messaggi pubblicati nella chat del team durante il periodo di tempo specificato.</li><li>**Risposte**: numero di risposte nella chat del team durante il periodo di tempo specificato.</li> <li>**App**: numero di app aggiunte al team.</li><li>**Riunioni**: numero di riunioni di Teams organizzate a livello di team.</li> </ul> |
    |**Utenti attivi**   |Numero di utenti attivi e inattivi.|
    |**Ruolo**   |Numero di utenti per ruolo, inclusi proprietari del team, membri del team e guest.|
    |**Grafico Utenti attivi**  |Numero di attività giornaliere. Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di utenti attivi in tale data.|
    |**Grafico messaggi**  |Numero totale di messaggi pubblicati nella chat del team per data. Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di nuovi post e risposte pubblicati in tale data.|

> [!TIP]
> È anche possibile visualizzare l'analisi per team facendo clic su un team nell'elenco nella [visualizzazione analisi tra team](#view-cross-team-analytics).

## <a name="view-per-channel-analytics"></a>Visualizzare l'analisi per canale

1. In Teams passare al canale desiderato, fare clic su **Altre opzioni (...)** e quindi su **Gestisci canale**.
2. Fare clic sulla scheda **Analisi** .
3. Selezionare un intervallo di date per visualizzare i dati di utilizzo per il canale.  

    ![Screenshot della visualizzazione di analisi per canale.](../media/view-analytics-per-channel.png)

    |Elemento |Descrizione  |
    |--------|-------------|
    |**Riepilogo**   |Riepilogo delle attività del canale, tra cui:<ul><li>**Utenti**: numero totale di utenti nel periodo di tempo specificato. Sono inclusi proprietari del team, membri del team e guest.</li> <li>**Post**: numero di nuovi messaggi pubblicati nel canale durante il periodo di tempo specificato.</li><li>**Risposte**: numero di risposte nel canale durante il periodo di tempo specificato.</li> <li>**App**: numero di app aggiunte al canale.</li> </ul> |
    |**Grafico messaggi**  |Numero totale di messaggi pubblicati nella chat del canale per data. Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di nuovi post e risposte pubblicati in tale data.|

> [!TIP]
> È anche possibile visualizzare l'analisi per canale selezionando un canale nella casella di riepilogo a discesa nella [visualizzazione di analisi per team](#view-per-team-analytics).
    
> [!NOTE]
> Gli utenti attivi vengono definiti come utenti che eseguono un'azione intenzionale nel client desktop, nel client per dispositivi mobili e nel client Web. Esempi di azione intenzionale includono l'avvio di una chat, l'inserimento di una chiamata, la condivisione di un file, la modifica di un documento all'interno dei team, la partecipazione a una riunione e così via. Eliminiamo azioni passive come l'avvio automatico, la riduzione a icona di uno schermo o la chiusura dell'app. De-duplica anche tutte le azioni in un singolo ID utente.

## <a name="related-topics"></a>Argomenti correlati

- [Visualizzare i dati analitici per i team](https://support.office.com/article/view-analytics-for-your-teams-5b8ad4b1-af34-4217-aff4-cd11a820b56b)
- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).