---
title: Usare Pianificazione reti per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: L'amministratore può imparare a usare Network Planner per determinare i requisiti di rete per Microsoft Teams.
localization_priority: Normal
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
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611800"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usare Pianificazione reti per Microsoft Teams

Network Planner è un nuovo strumento disponibile nell'interfaccia di amministrazione di Teams. Per trovare questa scheda, vedere **Pianificazione rete**  >  **planner.** In pochi passaggi, Network Planner consente di determinare e organizzare i requisiti di rete per connettere gli utenti di Microsoft Teams all'interno dell'organizzazione. Quando fornisci i dettagli della rete e l'utilizzo di Teams, Network Planner calcola i requisiti di rete per la distribuzione di Teams e della voce sul cloud nelle posizioni fisiche della tua organizzazione.

![Screenshot di Pianificazione rete](media/network-planner.png)

Pianificazione rete consente di:

- Creare rappresentazioni dell'organizzazione usando siti e utenti tipo consigliati da Microsoft (utenti dell'ufficio, lavoratori remoti e teams room system).

    > [!NOTE]
    > I utenti tipo consigliati sono stati sviluppati sulla base dei dati degli scenari di utilizzo ottimali di Teams e dei modelli di utilizzo tipici. È tuttavia possibile creare fino a tre utenti tipo personalizzati in aggiunta ai tre tipi di utenti tipo consigliati.

- Generare report e calcolare i requisiti di larghezza di banda per l'utilizzo di Teams.

Per usare Pianificazione rete, è necessario essere un amministratore globale, un amministratore dei servizi di Teams o un amministratore delle comunicazioni di Teams.

## <a name="create-a-custom-persona"></a>Creare un utente tipo personalizzato

Seguire questa procedura per creare un utente tipo personalizzato:

1. Passare a Pianificazione reti nell'interfaccia di amministrazione di Microsoft Teams.

2. Nella scheda **Utenti tipo** fare clic su + Utente **tipo personalizzato.** 

3. Nel riquadro **Nuovo utente tipo** personalizzato aggiungere un nome e una descrizione per il nuovo utente tipo.

4. Selezionare le autorizzazioni che questo utente tipo userà all'interno dell'organizzazione.

5. Fare clic su **Salva**.

## <a name="build-your-plan"></a>Creare il piano

Seguire questa procedura per iniziare a creare il piano di rete:

1. Passare a Pianificazione reti nell'interfaccia di amministrazione di Microsoft Teams.

2. Nella scheda **Piano di rete** fare clic su Aggiungi un piano di **rete.**

3. Immettere un nome e una descrizione per il piano di rete. Il piano di rete verrà visualizzato nell'elenco dei piani disponibili.

4. Fare clic sul nome del piano per selezionare il nuovo piano.

5. Aggiungere siti per creare una rappresentazione della configurazione di rete dell'organizzazione.

    A seconda della rete dell'organizzazione, è possibile usare i siti per rappresentare un edificio, una sede o altro. I siti potrebbero essere connessi tramite una WAN per consentire la condivisione di connessioni Internet e/o PSTN. Per risultati ottimali, creare siti con connessioni locali prima di creare siti che si connettono in remoto a Internet o PSTN.

    Per creare un sito:

    1. Aggiungere un nome e una descrizione per il sito.

    2. In **Impostazioni di** rete aggiungere il numero di utenti di rete nel sito (obbligatorio).

    3. Aggiungere dettagli di rete: abilitato per WAN, capacità WAN, uscita Internet **(locale** o **remota)** e uscita PSTN (nessuna, locale o remota).

      > [!NOTE]
      > È necessario aggiungere i numeri wan e la capacità Internet per visualizzare consigli specifici per la larghezza di banda quando si genera un report.

    4. Fare clic su **Salva**.

## <a name="create-a-report"></a>Creare un report

Dopo aver aggiunto tutti i siti, è possibile creare un report nel modo seguente.

1. Nella scheda **Report** fare clic su **Avvia un report.**

2. Per ogni sito creato, distribuire il numero di utenti tra i tipi di utenti tipo disponibili. Se si usano i gruppi di utenti tipo consigliati da Microsoft, il numero verrà distribuito automaticamente (80% di lavoratori in ufficio e 20% di lavoratori remoti).

3. Dopo aver completato la distribuzione, fare clic **su Genera report.**

    Il report generato mostrerà i requisiti di larghezza di banda in diverse visualizzazioni diverse, in modo da poter comprendere chiaramente l'output:
    - Una tabella con singoli calcoli visualizza i requisiti di larghezza di banda per ogni attività consentita.
    - Una visualizzazione aggiuntiva mostra le esigenze di larghezza di banda complessive con consigli.

4. Fare clic su **Salva**. Il report sarà disponibile nell'elenco dei report per poter essere visualizzato successivamente.

## <a name="example-scenario"></a>Scenario di esempio

Per un esempio su come usare Pianificazione rete per configurare un piano di rete e generare un report con questa procedura, scaricare Network [Planner How-To PowerPoint Deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo in inglese).
