---
title: Usare Pianificazione rete per Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: L'amministratore può imparare a usare Network Planner per determinare i requisiti di rete per Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045555"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usare Pianificazione rete per Microsoft Teams

Network Planner è un nuovo strumento disponibile nell'interfaccia di amministrazione di Teams. Per trovarlo, vai a **Pianificazione** > **pianificazione rete**. In pochi passaggi, Planner rete consente di determinare e organizzare i requisiti di rete per la connessione Microsoft Teams utenti all'interno dell'organizzazione. Quando si specificano i dettagli della rete e l'uso di Teams, Network Planner calcola i requisiti di rete per la distribuzione di Teams e Cloud Voice nei luoghi fisici dell'organizzazione.

![Screenshot di Pianificazione della rete.](media/network-planner.png)

Pianificazione della rete consente di:

- Creare rappresentazioni dell'organizzazione tramite siti e utenti tipo consigliati da Microsoft (office worker, lavoratori remoti e Teams sistema di sale).

    > [!NOTE]
    > I utenti tipo consigliati sono stati sviluppati in base ai dati provenienti da scenari di utilizzo ottimale Teams e modelli di utilizzo tipici. Tuttavia, è possibile creare fino a tre utenti tipo personalizzati oltre ai tre utenti tipo consigliati.

- Generare report e calcolare i requisiti di larghezza di banda per Teams utilizzo.

Per usare Pianificazione rete, è necessario essere un amministratore globale, un amministratore Teams o un amministratore delle comunicazioni di Teams.

## <a name="create-a-custom-persona"></a>Creare un utente tipo personalizzato

Seguire questa procedura per creare un utente tipo personalizzato:

1. Passare a Pianificazione della rete nell'interfaccia di amministrazione di Microsoft Teams.

2. Nella scheda **Utenti tipo** fare clic su **+ Persona personalizzata**. 

3. Nel riquadro **Nuovo utente tipo personalizzato** aggiungere un nome e una descrizione per il nuovo utente tipo.

4. Selezionare le autorizzazioni che verranno usate dall'utente tipo all'interno dell'organizzazione.

5. Fare clic su **Salva**.

## <a name="build-your-plan"></a>Crea il tuo piano

Segui questi passaggi per iniziare a creare il tuo piano di rete:

1. Passare a Pianificazione della rete nell'interfaccia di amministrazione di Microsoft Teams.

2. Nella scheda **Piano di** rete fare clic su **Aggiungi un piano di rete**.

3. Immettere un nome e una descrizione per il piano di rete. Il piano di rete verrà visualizzato nell'elenco dei piani disponibili.

4. Fare clic sul nome del piano per selezionare il nuovo piano.

5. Aggiungere siti per creare una rappresentazione della configurazione di rete dell'organizzazione.

    A seconda della rete dell'organizzazione, è consigliabile usare i siti per rappresentare un edificio, un ufficio o altro. I siti potrebbero essere connessi da una WAN per consentire la condivisione di connessioni Internet e/o PSTN. Per risultati ottimali, creare siti con connessioni locali prima di creare siti che si connettono in remoto a Internet o PSTN.

    Per creare un sito:

    1. Aggiungere un nome e una descrizione per il sito.

    2. In **Impostazioni di** rete aggiungi il numero di utenti di rete nel sito (obbligatorio).

    3. Aggiungere i dettagli di rete: abilitato per WAN, capacità WAN, uscita Internet (**locale** o **remota**) e uscita PSTN (nessuna, locale o remota).

      > [!NOTE]
      > È necessario aggiungere i numeri di capacità WAN e Internet per visualizzare suggerimenti specifici sulla larghezza di banda quando si genera un report.

    4. Fare clic su **Salva**.

## <a name="create-a-report"></a>Creare un report

Dopo aver aggiunto tutti i siti, è possibile creare un report come indicato di seguito.

1. Nella scheda **Report** fare clic su **Avvia report**.

2. Per ogni sito creato, distribuire il numero di utenti tra i personaggi tipo disponibili. Se si usano i utenti tipo consigliati da Microsoft, il numero verrà distribuito automaticamente (80% office worker e 20% remote worker).

3. Dopo aver completato la distribuzione, fare clic su **Genera report**.

    Il report generato mostrerà i requisiti di larghezza di banda in diverse visualizzazioni in modo da poter comprendere chiaramente l'output:
    - Una tabella con singoli calcoli visualizza i requisiti di larghezza di banda per ogni attività consentita.
    - Una visualizzazione aggiuntiva mostrerà le esigenze complessive di larghezza di banda con suggerimenti.

4. Fare clic su **Salva**. Il report sarà disponibile nell'elenco dei report per la visualizzazione successiva.

## <a name="example-scenario"></a>Scenario di esempio

Per un esempio su come usare Pianificazione rete per configurare un piano di rete e generare un report con questa procedura, scaricare la [presentazione Network planner How-To PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo in inglese).
