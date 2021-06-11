---
title: Anteprima pubblica in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sull'anteprima pubblica in Microsoft Teams. Provare le nuove funzionalità e fornire commenti e suggerimenti.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0719e68dcbf1c73c15ee58e8c7d6be08f359aa5
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863257"
---
# <a name="microsoft-teams-public-preview"></a>Anteprima pubblica in Microsoft Teams

> [!NOTE]
> Le funzionalità incluse nell'anteprima potrebbero non essere complete e potrebbero subire modifiche prima di essere disponibili nella versione pubblica. Sono disponibili solo a scopo di valutazione ed esplorazione. Non supportato in Office 365 Government Community Cloud (GCC).

L'anteprima pubblica per Microsoft Teams offre accesso anticipato alle funzionalità non rilasciate in Teams. Le anteprime consentono di esplorare e testare le funzionalità imminenti. Microsoft è lieta di ricevere feedback sulle funzionalità presentate nelle anteprime pubbliche. L'anteprima pubblica è abilitata per gli utenti di Teams, pertanto non è necessario preoccuparsi per l'impatto sull'intera organizzazione.

Per un elenco delle funzionalità disponibili nell'anteprima pubblica di Teams, visitare [Note sulla versione del Canale corrente (Anteprima) di Office](/officeupdates/current-channel-preview).

## <a name="set-the-update-policy"></a>Impostare i criteri di aggiornamento

L'anteprima pubblica è abilitata per singolo utente e l'opzione per attivarla è controllata da un criterio amministrativo. I criteri di aggiornamento vengono usati per gestire gli utenti delle anteprime di Teams e Office che visualizzano le funzionalità non definitive o di anteprima nell'app di Teams. È possibile usare il criterio globale (impostazione predefinita a livello dell'organizzazione) e personalizzarlo oppure creare uno o più criteri personalizzati per gli utenti. Questo criterio deve essere assegnato a utenti specifici in quanto non sovrascrive il criterio globale.

1. Accedere all'interfaccia di amministrazione.
2. Selezionare **Teams**>**Criteri di aggiornamento**.

   ![Selezionare l'opzione Aggiorna criteri](media/updatePolicies.png)

3. Selezionare **Aggiungi**.
4. Assegnare un nome ai criteri di aggiornamento, aggiungere una descrizione e attivare **Mostra le funzionalità di anteprima**.

È anche possibile impostare il criterio tramite PowerShell usando il cmdlet `CsTeamsUpdateManagementPolicy`.

## <a name="enable-public-preview"></a>Abilitare l'anteprima pubblica

Per abilitare l'anteprima pubblica su un client desktop o Web, è necessario eseguire le operazioni seguenti:

1. Selezionare i tre puntini a sinistra del profilo per visualizzare il menu di Teams.
2. Selezionare **Informazioni** > **Anteprima pubblica**.
3. Selezionare **Passa all'anteprima pubblica**.

## <a name="related-topics"></a>Argomenti correlati

[Anteprima pubblica per sviluppatori](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
