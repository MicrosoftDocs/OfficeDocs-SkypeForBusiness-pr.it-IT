---
title: Esperienza di aggiornamento delle app in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Questo articolo illustra come vengono aggiornate le app Microsoft, le app personalizzate e le app di terze parti in Microsoft Teams e in che modo gli amministratori agevolano questi processi.
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299045"
---
# <a name="update-apps-in-microsoft-teams"></a>Aggiornare le app in Microsoft Teams

Nella maggior parte dei casi, quando una nuova versione di un'app è disponibile nello store di Teams, l'app viene aggiornata automaticamente per gli utenti. Tuttavia, alcune modifiche specifiche nella nuova versione dell'app richiedono l'accettazione da parte dell'utente per l'aggiornamento dell'app. L'accettazione da parte dell'utente garantisce la consapevolezza in merito alle modifiche, quali funzionalità o accessi. Se gli sviluppatori di app apportano le seguenti modifiche specifiche alle app di Microsoft Teams, gli utenti finali devono approvare l'aggiornamento dell'app:

* Viene aggiunto un bot.
* La proprietà `botId` di un bot esistente o la proprietà `isNotificationOnly` viene modificata.
* `SupportsCalling` del bot e `SupportsVideo` la funzionalità `SupportsFiles` vengono aggiunte.
* È stata aggiunta un'estensione per la messaggistica.
* Le autorizzazioni all'interno di Autorizzazione vengono aggiunte o modificate.
* `Id` o `ApplicationPermissionsHash` o entrambi vengono modificati all'interno di `webApplicationInfo`.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>Articoli correlati

* [Informazioni sullo schema manifesto per gli aggiornamenti eseguiti nelle app](/microsoftteams/platform/resources/schema/manifest-schema).
