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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Questo articolo illustra come vengono aggiornate le app Microsoft, le app personalizzate e le app di terze parti in Microsoft Teams.
ms.openlocfilehash: bcd06b9814b03d917014d8136f51a280e30007d1
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272061"
---
# <a name="update-apps-in-microsoft-teams"></a>Aggiornare le app in Microsoft Teams

Nella maggior parte dei casi, dopo che gli sviluppatori di app pubblicano un aggiornamento dell'app, la nuova versione viene visualizzata automaticamente per gli utenti. Esistono tuttavia alcuni aggiornamenti al manifesto di [Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) che richiedono l'accettazione da parte dell'utente per il completamento:

* È stato aggiunto o rimosso un bot.
* La proprietà "botId" di un bot esistente è stata modificata.
* La proprietà "isNotificationOnly" di un bot esistente è stata modificata.
* È stata aggiunta la funzionalità SupportsCalling, SupportsVideo e SupportsFiles di un bot.
* È stata aggiunta un'estensione per la messaggistica.
* È stato aggiunto un nuovo connettore.
* Le autorizzazioni all'interno di "Autorizzazione" sono state aggiunte o modificate.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Nuova versione disponibile." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Opzione di aggiornamento per un'app." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> Il processo di aggiornamento si applica a tutti gli aggiornamenti delle app Microsoft, alle app personalizzate e alle app di terze parti.
