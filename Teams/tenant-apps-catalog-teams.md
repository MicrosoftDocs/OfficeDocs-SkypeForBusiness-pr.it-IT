---
title: Pubblicare app nel catalogo delle app del tenant di Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Linee guida per la pubblicazione di app nel catalogo delle app tenant di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161615"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>Pubblicare app nel catalogo delle app del tenant di Microsoft Teams
=======================================================

Puoi usare il catalogo delle app del tenant di Microsoft teams per testare e distribuire le applicazioni line-of-business alla tua organizzazione.

Il catalogo delle app tenant teams consente di distribuire applicazioni line-of-business costruite appositamente per l'organizzazione e di affidarsi a tutte le funzioni aziendali critiche.

Per pubblicare le app per l'organizzazione, accedere al client teams usando un account con il ruolo amministratore globale o servizio teams e quindi seguire i passaggi seguenti.

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>Pubblicare un'app nel catalogo dell'app tenant dal client Teams

> [!NOTE]
> Questa procedura descrive come pubblicare un'app usando il client teams. Puoi anche pubblicare un'app nella pagina **Gestisci app** nell'interfaccia di amministrazione di Microsoft teams. Per altre informazioni, vedere [gestire le app in teams](manage-apps.md).

### <a name="get-a-teams-app-package"></a>Ottenere un pacchetto dell'app Teams

Viene creato un pacchetto dell'app teams con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Una volta che hai il pacchetto dell'app, puoi aggiungerlo al catalogo app tenant. Mentre tutti gli utenti dell'organizzazione possono visualizzare il catalogo delle app, solo gli amministratori globali e i servizi di teams hanno la possibilità di pubblicarli e gestirli.

### <a name="go-to-the-tenant-app-catalog"></a>Vai al catalogo app tenant

Avviare teams ed eseguire l'accesso usando le credenziali di amministratore del servizio globale o teams. Seleziona **app** sul lato sinistro dell'app e quindi seleziona la nuova sezione denominata per l'organizzazione specifica (in questo esempio, contoso). Gli utenti dell'organizzazione possono visualizzare le app nel catalogo e installarle per i team di cui fanno parte.

![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>Aggiungere un'app al catalogo dell'app tenant

1. Nella pagina **app** selezionare **carica un caricamento di un'app** > personalizzata**per contoso**.

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image02.png)

    Puoi anche scegliere **carica per me o i miei team**, che si chiama *sideload*. Sideload rende l'app disponibile solo per i team o per i team selezionati.)

2. Passare al pacchetto dell'app e selezionarlo e quindi fare clic su **Apri**.

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image03.png)

Quando si torna al catalogo dell'app tenant, la nuova app Enterprise sarà presente. Ricordati che solo tu e i membri dell'organizzazione hai accesso a questo catalogo app.

### <a name="update-an-app-in-the-tenant-app-catalog"></a>Aggiornare un'app nel catalogo app tenant

1. Dal catalogo dell'app tenant selezionare "**...**" nell'angolo in alto a destra dell'app che vuoi aggiornare.

2. Passare al pacchetto dell'app aggiornata e selezionarlo e quindi fare clic su **Apri**.

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image04.png)

L'app verrà aggiornata alla versione 2,0. Puoi anche eliminare l'app per l'intera società da questo menu.

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>Usare l'interfaccia di amministrazione di Microsoft teams per gestire il catalogo delle app tenant

Se si hanno app che necessitano di correzioni di bug, è possibile disabilitare temporaneamente le app per gli utenti in un criterio di autorizzazione per le app.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di autorizzazione**delle **app teams**.
2. Selezionare i criteri di autorizzazione per le app che si desidera modificare e quindi fare clic su **modifica**.
3. In **app tenant**selezionare **Blocca app specifiche e Consenti a tutti gli altri**e quindi aggiungere le app che si vuole bloccare.

La disattivazione di un'app impedisce agli utenti di interagire con l'app, senza eliminare completamente l'app. Questi controlli offrono maggiore flessibilità e controllo per la gestione delle app nell'organizzazione.

Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).