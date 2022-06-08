---
title: Distribuire team su vasta scala per gli operatori in prima linea in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come distribuire i team su vasta scala per gli operatori in prima linea nell'organizzazione.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947229"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Distribuire team su vasta scala per gli operatori in prima linea in Microsoft Teams

> [!NOTE]
> Questa funzionalità è attualmente in anteprima privata. Se desideri partecipare all'anteprima privata, contattaci [all'dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Panoramica
 
L'organizzazione può avere molti team che si usano per promuovere la comunicazione e la collaborazione tra la forza lavoro in prima linea, che si trovano in diversi punti vendita, sedi e ruoli. Attualmente, non esiste una soluzione semplice per distribuire, configurare e gestire questi team e utenti su vasta scala.

Stiamo creando una soluzione per consentire agli amministratori di distribuire e gestire i team su vasta scala.

Ecco una panoramica delle funzionalità attualmente disponibili per la creazione e la gestione di un numero elevato di team alla volta e di ciò che stiamo pianificando per il prossimo futuro.

||Disponibile oggi |Più tardi nel 2022  |
|---------|---------|---------|
|**Numero di team che è possibile creare per batch**|Fino a 100 |Fino a 500|
|**Numero di utenti che è possibile aggiungere per team**|Fino a 25|Fino a 25|

La distribuzione dei team su vasta scala consente di:

- Creare team usando modelli predefiniti o modelli personalizzati.
- Aggiungere utenti ai team come proprietari o membri.
- Gestire i team su vasta scala aggiungendo o rimuovendo utenti dai team esistenti.
- È possibile ricevere una notifica tramite posta elettronica, inclusi il completamento, lo stato e gli eventuali errori. I proprietari e i membri del team ricevono una notifica.

## <a name="how-to-deploy-teams-at-scale"></a>Come distribuire i team su vasta scala

> [!NOTE]
> Prima di distribuire i team, assicurarsi che tutti i proprietari dei team abbiano una licenza di Teams.

Seguire questa procedura per distribuire un numero elevato di team alla volta.

Si usa il ```New-CsBatchTeamsDeployment``` cmdlet per inviare un batch di team da creare. Per ogni batch viene generato un ID di orchestrazione. È quindi possibile usare il ```Get-CsBatchTeamsDeployment``` cmdlet per tenere traccia dello stato e dello stato di ogni batch.

1. Installare PowerShell versione 7 o successiva. Per indicazioni dettagliate, vedere [Installazione di PowerShell in Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Eseguire PowerShell in modalità amministratore.
1. Eseguire quanto segue per disinstallare qualsiasi modulo di Teams PowerShell installato in precedenza.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Se viene visualizzato un messaggio di errore, l'impostazione è già stata impostato. Procedere con il passaggio successivo.
1. Scaricare e installare [l'ultima versione del modulo di Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Eseguire quanto segue per connettersi a Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Quando richiesto, accedere con le credenziali di amministratore.

1. Eseguire quanto segue per ottenere un elenco dei comandi nel modulo di PowerShell di Teams.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Verifica che e ```New-CsBatchTeamsDeployment``` ```Get-CsBatchTeamsDeployment``` siano elencati.

1. Eseguire quanto segue per distribuire un batch di team. È possibile immettere fino a cinque indirizzi di posta elettronica nel parametro **UsersToNotify** .

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. Eseguire le operazioni seguenti per verificare lo stato del batch inviato.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Inviaci il tuo feedback

Apprezziamo il tuo feedback. Usabilità, affidabilità, prestazioni&mdash;, benvenuto tutto!

Invia [dscale@microsoft.com](mailto:dscale@microsoft.com) e includi l'ID di orchestrazione e il file di errore, se disponibile.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica di PowerShell di Teams](teams-powershell-overview.md)
