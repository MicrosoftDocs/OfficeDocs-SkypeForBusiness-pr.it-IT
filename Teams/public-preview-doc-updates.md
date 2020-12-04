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
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530983"
---
# <a name="microsoft-teams-public-preview"></a>Anteprima pubblica in Microsoft Teams

> [!NOTE]
> Le funzionalità incluse nell'anteprima potrebbero non essere complete e potrebbero subire modifiche prima di essere disponibili nella versione pubblica. Sono disponibili solo a scopo di valutazione ed esplorazione.

L'anteprima pubblica per Microsoft Teams offre accesso anticipato alle funzionalità non rilasciate in Teams. Le anteprime consentono di esplorare e testare le funzionalità imminenti. Microsoft è lieta di ricevere feedback sulle funzionalità presentata nelle anteprime pubbliche. L'anteprima pubblica è abilitata per ogni utente di Teams, pertanto non è necessario preoccuparsi per l'impatto sull'intera organizzazione.

## <a name="set-the-update-policy"></a>Impostare i criteri di aggiornamento

 L'anteprima pubblica è abilitata per ogni utente e l'opzione per attivarla è controllata da un criterio amministrativo. I criteri di aggiornamento vengono usati per gestire gli utenti delle anteprime di Teams e Office che visualizzano le funzionalità non definitive o di anteprima nell'app di Teams. È possibile usare il criterio globale (impostazione predefinita a livello dell'organizzazione) e personalizzarlo oppure creare uno o più criteri personalizzati per gli utenti. Occorre assegnare il criterio a utenti specifici poiché tale criterio non sovrascrive il criterio globale.

1. Accedere all'interfaccia di amministrazione.
2. Selezionare **Teams**>**Criteri di aggiornamento**.

   ![Selezionare l'opzione Aggiorna criteri](media/updatePolicies.png)

3. Selezionare **Aggiungi**.
4. Assegnare un nome ai criteri di aggiornamento, aggiungere una descrizione e attivare **Mostra le funzionalità di anteprima**.

È anche possibile impostare il criterio tramite PowerShell usando il cmdlet `CsTeamsUpdateManagementPolicy`.

## <a name="enable-public-preview"></a>Abilitare l'anteprima pubblica

Per abilitare l'anteprima pubblica su un client desktop o Web, è necessario eseguire le operazioni seguenti:

1. Selezionare il profilo per visualizzare il menu di Teams.
2. Selezionare **Informazioni** → **Anteprima pubblica**.
3. Selezionare **Passa all'anteprima pubblica**.

## <a name="related-topics"></a>Argomenti correlati

[Anteprima pubblica per sviluppatori](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
