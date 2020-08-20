---
title: Visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell'interfaccia di amministrazione di Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come visualizzare le autorizzazioni richieste dalle app e concedere il consenso dell'amministratore alle app nella pagina Gestisci app dell'interfaccia di amministrazione di Microsoft teams.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814613"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore nell'interfaccia di amministrazione di Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

La pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft teams consente di visualizzare e gestire tutte le app teams per l'organizzazione. Ad esempio, puoi vedere lo stato e le proprietà a livello di organizzazione delle app, approvare o caricare nuove app personalizzate nell'App Store dell'azienda, bloccare o consentire le app a livello di organigramma e gestire le impostazioni dell'app per l'intero organigramma.

In questa sezione puoi anche concedere l'autorizzazione di amministratore a livello di organizzazione alle app che richiedono le autorizzazioni per accedere ai dati e visualizzare le autorizzazioni di consenso specifiche delle risorse (RSC) per le app.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Concedere l'autorizzazione di amministratore a livello di organizzazione a un'app

Come amministratore, puoi rivedere e concedere il consenso alle app che richiedono autorizzazioni per conto di tutti gli utenti dell'organizzazione. Puoi eseguire questa operazione in modo che gli utenti non debbano rivedere e accettare le autorizzazioni richieste dall'app quando avviano l'app. Inoltre, a seconda delle [impostazioni di consenso](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) dell'utente in Azure Active Directory (Azure ad), alcuni utenti potrebbero non essere autorizzati a concedere il consenso alle app che accedono ai dati aziendali.

Gli esempi di autorizzazioni richieste dalle app includono la possibilità di leggere le informazioni archiviate in un team, leggere il profilo di un utente e inviare un messaggio di posta elettronica per conto degli utenti. Per altre informazioni, vedere [autorizzazioni e consenso nell'endpoint della piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent). 

Devi essere un amministratore globale per concedere il consenso a livello di organizzazione a un'app. La colonna **autorizzazioni** indica se un'app dispone delle autorizzazioni necessarie per il consenso. Verrà visualizzato un collegamento **Visualizza dettagli** per ogni app registrata in Azure ad con autorizzazioni che richiedono il consenso. Tieni presente che questo si applica solo alle app personalizzate e di terze parti e. Il collegamento non viene visualizzato o è necessario concedere il consenso dell'amministratore per le app pubblicate da Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Screenshot della colonna autorizzazioni nella pagina Gestisci app":::

Per concedere il consenso a livello di organizzazione a un'app, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.
2. Eseguire una delle operazioni seguenti:
    - Cercare l'app desiderata, fare clic sul nome dell'app per accedere alla pagina dei dettagli dell'app e quindi selezionare la scheda **autorizzazioni** .
    - Ordinare la colonna **autorizzazioni** in ordine decrescente per trovare l'app e quindi selezionare **Visualizza dettagli**. In questo modo viene visualizzata la scheda **autorizzazioni** della pagina Dettagli app.

3. In **autorizzazioni a livello di organizzazione**selezionare **Rivedi le autorizzazioni e il consenso**. Per eseguire questa operazione, è necessario essere un amministratore globale. Questa opzione non è disponibile per gli amministratori del servizio teams.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Screenshot delle autorizzazioni a livello di organizzazione nella scheda autorizzazioni per un'app":::

4. Nella scheda **autorizzazioni** esaminare le autorizzazioni richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Screenshot delle autorizzazioni richieste da un'app":::

    > [!IMPORTANT]
    > La concessione dell'autorizzazione a livello di organizzazione a un'app consente all'app di accedere ai dati della tua azienda. Verificare attentamente le autorizzazioni richieste dall'app prima di concedere il consenso.
5. Se si è d'accordo con le autorizzazioni richieste dall'app, fare clic su **accetta** per concedere il consenso. Un banner viene visualizzato temporaneamente nella parte superiore della pagina per informare che le autorizzazioni richieste sono state concesse per l'app. Ora l'app ha accesso alle risorse specificate per tutti gli utenti dell'organizzazione e a nessun altro verrà richiesto di rivedere le autorizzazioni.

Dopo aver accettato le autorizzazioni, viene visualizzato un messaggio in **autorizzazioni a livello di organizzazione** nella pagina Dettagli app per comunicare che il consenso è stato concesso. Per visualizzare i dettagli sulle autorizzazioni dell'app, fai clic sul collegamento **Azure Active Directory** per accedere alla pagina dell'app nel portale di Azure ad.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Screenshot del messaggio visualizzato quando è stato concesso il consenso":::

Se gli utenti dell'organizzazione possono concedere il consenso e se uno o più utenti hanno concesso il consenso a una determinata app, verrà visualizzato solo il messaggio per comunicare che il consenso è stato concesso e il collegamento di Azure Active Directory. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Visualizzare le autorizzazioni di consenso specifiche delle risorse di un'app

Le autorizzazioni RSC consentono ai proprietari del team di concedere il consenso per un'app per accedere e modificare i dati di un team. Le autorizzazioni RSC sono granulari, autorizzazioni specifiche per i team che definiscono le operazioni che un'app può eseguire in un team specifico. Esempi di autorizzazioni RSC includono la possibilità di creare ed eliminare canali, ottenere le impostazioni per un team e creare e rimuovere le schede dei canali. Le autorizzazioni RSC sono definite nel manifesto dell'app e non in Azure AD.

Concedi il consenso alle autorizzazioni RSC quando Aggiungi l'app a un team. Per altre informazioni, Vedi il consenso specifico per le [risorse (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) e il [consenso specifico delle risorse in teams](resource-specific-consent.md).

Gli amministratori globali e l'amministratore del servizio teams possono visualizzare le autorizzazioni RSC. Per visualizzare le autorizzazioni RSC per un'app, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.
2. Cercare l'app desiderata, fare clic sul nome dell'app per accedere alla pagina dei dettagli dell'app e quindi selezionare la scheda **autorizzazioni** .
3. In **autorizzazioni di consenso specifiche delle risorse di Microsoft Graph (RSC)** esaminare le autorizzazioni RSC richieste dall'app.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Screenshot delle autorizzazioni RSC per un'app":::

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Autorizzazioni e consenso nell'endpoint della piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Consenso specifico delle risorse in teams](resource-specific-consent.md)
- [Consenso specifico per le risorse (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


