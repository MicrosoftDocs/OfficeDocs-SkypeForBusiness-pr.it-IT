---
title: Esperienza di aggiornamento delle app in Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: In questo articolo viene illustrato come aggiornare le app Microsoft, le app personalizzate e le app di terze parti in Microsoft Teams.
ms.openlocfilehash: cf4a062cd035feb0850a64c49a4c2363de0badce
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190312"
---
# <a name="update-apps-in-microsoft-teams"></a>Aggiornare le app in Microsoft Teams

Nella maggior parte dei casi, dopo che gli sviluppatori di app hanno pubblicato un aggiornamento dell'app, la nuova versione viene visualizzata automaticamente per gli utenti. Tuttavia, ci sono alcuni aggiornamenti al [manifesto Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) che richiedono l'accettazione dell'utente per completare:

* Un bot è stato aggiunto o rimosso
* La proprietà "botId" di un bot esistente è stata modificata
* Proprietà "isNotificationOnly" di un bot esistente modificata
* È stata aggiunta la funzionalità SupportsCalling, SupportsVideo e SupportsFiles di un bot
* È stata aggiunta un'estensione di messaggistica
* È stato aggiunto un nuovo connettore
* Le autorizzazioni all'interno di "Autorizzazione" sono state aggiunte o modificate

![nuova versione disponibile.](media/manage-your-custom-apps-update1.png)

![opzione di aggiornamento per un'app.](media/manage-your-custom-apps-update2.png)

> [!NOTE]
> Il processo di aggiornamento si applica a tutti gli aggiornamenti delle app Microsoft, delle app personalizzate e delle app di terze parti.
