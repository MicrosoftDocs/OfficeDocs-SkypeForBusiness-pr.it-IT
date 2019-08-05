---
title: Usare Network Planner per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: Informazioni su come usare Network Planner per determinare i requisiti di rete per Microsoft teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea6a4a5989df0a780f75220ec314439f7dafcbe
ms.sourcegitcommit: 384e123f3b5cf1600ebd5ddd69bd022f9b8ba0f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "36185071"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usare Network Planner per Microsoft Teams

Network Planner è un nuovo strumento disponibile nell'interfaccia di amministrazione di teams. È possibile trovarlo accedendo a **Impostazioni** > di**rete**a livello di organizzazione. In pochi passaggi, la pianificazione della rete può aiutare a determinare e organizzare i requisiti di rete per la connessione degli utenti di Microsoft teams all'intera organizzazione. Quando fornisci i dettagli della rete e l'uso dei team, Network Planner calcola i requisiti di rete per la distribuzione di team e la voce cloud tra le posizioni fisiche dell'organizzazione.

![Screenshot di Network Planner](media/network-planner.png)

Network Planner consente di:

- Creare rappresentazioni dell'organizzazione usando i siti e gli utenti tipo consigliati Microsoft (dipendenti di Office, operatori remoti e sistema room di Teams).

    > [!NOTE]
    > Gli utenti tipo consigliati sono stati sviluppati in base a dati provenienti da scenari di uso ottimale dei team e modelli di utilizzo tipici. Puoi tuttavia creare fino a tre utenti personalizzati oltre ai tre utenti tipo consigliati.

- Generare report e calcolare i requisiti di larghezza di banda per l'utilizzo dei team.

Per usare Network Planner, è necessario essere un amministratore globale, un amministratore del servizio teams o un amministratore delle comunicazioni di teams.

## <a name="create-a-custom-persona"></a>Creare un utente personalizzato

Seguire questa procedura per creare una persona personalizzata:

1. Accedere a Network Planner nell'interfaccia di amministrazione di Microsoft teams.

2. Nella scheda **personas** fare clic su **+ persona personalizzata**. 

3. Nel riquadro **nuova persona personalizzata** aggiungere un nome e una descrizione per il nuovo utente.

4. Selezionare le autorizzazioni che l'utente utilizzerà nell'organizzazione.

5. Fai clic su **Salva**.

## <a name="build-your-plan"></a>Creare un piano

Seguire questa procedura per iniziare a creare il piano di rete:

1. Accedere a Network Planner nell'interfaccia di amministrazione di Microsoft teams.

2. Nella scheda **piano di rete** fare clic su **Aggiungi piano di rete**.

3. Immettere un nome e una descrizione per il piano di rete. Il piano di rete verrà visualizzato nell'elenco dei piani disponibili.

4. Fare clic sul nome del piano per selezionare il nuovo piano.

5. Aggiungere siti per creare una rappresentazione della configurazione di rete dell'organizzazione.

    A seconda della rete dell'organizzazione, è consigliabile usare i siti per rappresentare un edificio, una posizione di Office o qualcos'altro. I siti potrebbero essere connessi da una rete WAN per consentire la condivisione di connessioni Internet e/o PSTN. Per ottenere risultati ottimali, creare siti con connessioni locali prima di creare siti che si connettono in remoto a Internet o PSTN.

    Per creare un sito:

    1. Aggiungere un nome e una descrizione per il sito.

    2. In **impostazioni di rete**aggiungere il numero di utenti di rete in tale sito (obbligatorio).

    3. Aggiungere dettagli di rete: abilitato per WAN, capacità WAN, uscita Internet (**locale** o **remoto**) e uscita PSTN (nessuno, locale o remoto).

      > [!NOTE]
      > È necessario aggiungere numeri di capacità WAN e Internet per visualizzare suggerimenti specifici sulla larghezza di banda quando si genera un report.

    4. Fai clic su **Salva**.

## <a name="create-a-report"></a>Creare un report

Dopo aver aggiunto tutti i siti, è possibile creare un report, come indicato di seguito.

1. Nella scheda **report** fare clic su **Avvia report**.

2. Per ogni sito creato, distribuire il numero di utenti in tutte le persone disponibili. Se si usano gli utenti di Microsoft recommended, il numero verrà distribuito automaticamente (80% di Office Worker e 20% remote Worker).

3. Dopo aver completato la distribuzione, fare clic su **genera report**.

    Il report generato visualizzerà i requisiti di larghezza di banda in diverse visualizzazioni in modo da poter comprendere chiaramente l'output:
    - Una tabella con singoli calcoli visualizzerà i requisiti di larghezza di banda per ogni attività consentita.
    - In una visualizzazione aggiuntiva verranno visualizzate le esigenze generali della larghezza di banda con le raccomandazioni.

4. Fai clic su **Salva**. Il report sarà disponibile nell'elenco report per la visualizzazione successiva.

## <a name="example-scenario"></a>Scenario di esempio

Per un esempio di come usare la pianificazione della rete per configurare un piano di rete e generare un report usando questi passaggi, scaricare il [Deck di PowerPoint di Planner di rete](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo in inglese).
