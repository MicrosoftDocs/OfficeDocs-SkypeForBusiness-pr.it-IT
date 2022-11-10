---
title: Esperienza di aggiornamento delle app in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Questo articolo illustra come vengono aggiornate le app Microsoft, le app personalizzate e le app di terze parti in Microsoft Teams e in che modo gli amministratori agevolano questi processi.
ms.openlocfilehash: d419e1ed29c6a1cd7a7390bdc0d5eb69371d8547
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912795"
---
# <a name="role-of-an-admin-in-upgrading-teams-apps"></a>Ruolo di un amministratore nell'aggiornamento delle app Teams

Gli amministratori di Teams possono aiutare gli utenti finali a ottenere l'ultima versione delle app. A tale scopo, completano una o entrambe le attività seguenti:

* [Aggiorna le app di terze parti](#updates-to-third-party-apps) disponibili in Teams Store quando lo sviluppatore o il fornitore dell'app fornisce una nuova versione.
* [Aggiornare le app personalizzate](#updates-to-custom-apps) disponibili solo nell'organizzazione quando lo sviluppatore invia una nuova versione.

## <a name="updates-to-third-party-apps"></a>Aggiornamenti ad app di terze parti

Per installare e usare un'app, gli utenti devono concedere le autorizzazioni per accedere ai servizi e alle informazioni necessari. Nella maggior parte dei casi, quando una nuova versione di un'app installata è disponibile in Teams Store, l'app viene aggiornata automaticamente per tutti gli utenti. Tuttavia, alcune modifiche specifiche apportate alla nuova versione dell'app richiedono di nuovo l'autorizzazione di un utente. Questa ripetizione dell'accettazione da parte dell'utente garantisce la consapevolezza delle modifiche, ad esempio la funzionalità o l'accesso alle informazioni personali. Gli amministratori di Teams possono [fornire le autorizzazioni per un'app per conto degli utenti](app-permissions-admin-center.md).

Se gli sviluppatori di app apportano una o più delle modifiche seguenti alle app, gli utenti finali devono approvare l'aggiornamento dell'app.

* Aggiungi un bot. Modificare l'ID del bot usando la `botId` proprietà.
* Modificare la `isNotificationOnly` proprietà di un bot esistente che potrebbe modificare le notifiche del bot.
* Modificare `SupportsCalling`, `SupportsVideo`e `SupportsFiles` le proprietà di un bot esistente per aggiungere funzionalità per chiamare, riprodurre video e caricare o scaricare file.
* Aggiungere o rimuovere le autorizzazioni nell'autorizzazione.
* Aggiungere o rimuovere un'estensione di messaggistica, aggiungere una scheda gruppo, aggiungere un connettore o un canale.
* Modificare i [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) parametri nel nel file manifesto.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Aggiornamenti alle app personalizzate

Le app personalizzate create e distribuite all'interno dell'organizzazione sono disponibili per gli utenti del tenant o dell'organizzazione. L'amministratore di Teams aggiorna un'app personalizzata alla nuova versione quando viene fornita una nuova versione dagli sviluppatori dell'organizzazione. Per altre informazioni, vedere [come gli amministratori gestiscono le app personalizzate](custom-app-overview.md).

## <a name="related-articles"></a>Articoli correlati

* [Informazioni sullo schema manifesto per gli aggiornamenti eseguiti nelle app](/microsoftteams/platform/resources/schema/manifest-schema).
* [Informazioni sulla gestione delle app personalizzate](custom-app-overview.md).
