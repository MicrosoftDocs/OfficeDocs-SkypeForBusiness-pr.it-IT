---
title: Personalizzare le app Teams in base alla licenza
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come aggiungere Teams per gli utenti dell'organizzazione in base alla licenza.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 774688012d4e70a20897cd45aa78883ba7985e68
ms.sourcegitcommit: 1190cd73656dbc9131d46e0a827e28bcd960dfc5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2022
ms.locfileid: "62864039"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>Personalizzare le app Teams in base alla licenza

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> Attualmente, questa funzionalità si applica alle licenze F. Di conseguenza, questo articolo si concentra sull'esperienza dei lavoratori in prima linea. Altri tipi di licenza saranno supportati in futuro.

## <a name="overview"></a>Panoramica

Teams consente di aggiungere app in base alla licenza. Quando un utente accede a Teams con l'esperienza dell'app personalizzata abilitata, l'utente ottiene un'esperienza dell'app personalizzata in base alla licenza.

Questa funzionalità offre agli utenti le app più pertinenti in Teams senza alcuna azione da parte dell'amministratore.

## <a name="tailored-app-experience"></a>Esperienza dell'app personalizzata

Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili Teams (iOS e Android).

App aggiunte per gli utenti che hanno una licenza F:

- Attività
- Chat
- Teams
- Turni
- Attività

## <a name="admin-controls"></a>Controlli di amministrazione

> [!NOTE]
> L'aggiunta di utenti deve essere attivata nel criterio di configurazione globale [dell'app](teams-app-setup-policies.md) (impostazione predefinita a livello di organizzazione) per l'applicazione di questa funzionalità.

La funzionalità dell'esperienza per le app personalizzata è  controllata dall'impostazione Mostra app personalizzate in base alle licenze dell'app [](manage-apps.md#manage-org-wide-app-settings) a livello di organizzazione nella pagina Gestisci app dell'interfaccia di amministrazione di Teams. Se la funzionalità è attivata, tutti gli utenti dell'organizzazione che dispongono di una licenza F otterrà l'esperienza personalizzata dell'app.

Tenere presente che tutti i criteri di configurazione delle app personalizzati assegnati agli utenti hanno la precedenza. Questo significa che se a un utente è già assegnato un criterio di configurazione dell'app personalizzato, l'utente ottiene la configurazione definita nei criteri di configurazione delle app personalizzate. Per altre informazioni sul funzionamento della caratteristica con i criteri di configurazione delle app esistenti applicati nell'organizzazione, vedere la [sezione Scenari di](#scenarios) questo articolo.

Questa funzionalità è attivata per impostazione predefinita. Tuttavia, se non si vuole che l'esperienza dell'app personalizzata fornita da Microsoft sia personalizzata, è possibile disattivare la funzionalità. Per disattivare o attivare la funzionalità:

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare a Teams **app** >  di gestione delle **app e quindi** selezionare Impostazioni **dell'app a livello di organizzazione**.
2. In **App personalizzate impostare** l'interruttore Mostra **app personalizzate** in base alle licenze su **Disattivato** o **Attivato**.

## <a name="scenarios"></a>Scenari

Usare le informazioni in questa tabella per informazioni sul funzionamento della caratteristica esperienza app personalizzata in vari scenari, ad esempio quando sono stati applicati criteri di configurazione delle app esistenti.

|Se...  |Quindi... |
|---------|---------|
|Un utente ha il criterio di configurazione dell'app globale e la funzionalità è attivata.     | L'utente ottiene l'esperienza dell'app personalizzata.        |
|Un utente ha un criterio di configurazione dell'app personalizzato e la caratteristica è attivata.    |L'utente ottiene la configurazione definita nei criteri di configurazione dell'app personalizzati.          |
|La caratteristica è attivata e si aggiornano i criteri di configurazione delle app globali.     |L'utente ottiene l'esperienza dell'app personalizzata in base alla licenza. Le app definite nei criteri di configurazione delle app globali sono ancora aggiunte e vengono visualizzate più in basso nell'elenco delle app aggiunte.          |
|La caratteristica è disattivata.   | L'utente ottiene l'esperienza definita nei criteri di configurazione delle app globali o nei criteri di configurazione delle app personalizzati assegnati.          |
|Un utente ha una licenza E, A o G e la funzionalità è attivata.   | L'utente non ottiene l'esperienza dell'app personalizzata. Attualmente, l'esperienza dell'app personalizzata si applica solo agli utenti che hanno una licenza F.        |
|Un'app nell'esperienza dell'app personalizzata viene bloccata per un utente o per l'organizzazione.      |L'esperienza dell'app personalizzata rispetta i criteri di autorizzazione dell'app. Se un'app è bloccata, gli utenti non potranno vedere l'app bloccata.           |
|Un'app nell'esperienza dell'app personalizzata è già definita in un criterio di configurazione dell'app e la caratteristica è attivata. |L'app viene aggiunta in base all'ordine definito dall'esperienza dell'app personalizzata.        |

> [!NOTE]
> Non è possibile modificare le app o l'ordine delle app nell'esperienza dell'app personalizzata. Per il momento, se si vogliono apportare modifiche, è possibile configurare un'esperienza personalizzata. A questo scopo, disattivare prima la caratteristica. Quindi, [creare un criterio di configurazione dell'app personalizzato](teams-app-setup-policies.md) e [assegnarlo a utenti o gruppi](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Articoli correlati

- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
