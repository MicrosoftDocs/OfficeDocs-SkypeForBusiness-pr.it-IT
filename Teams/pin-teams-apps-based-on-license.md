---
title: Personalizzare Teams per i dipendenti in prima linea
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza dell'app personalizzata per i dipendenti in prima linea in Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774185"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Personalizzare Teams per i dipendenti in prima linea

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>Panoramica

Teams offre un modo semplice per aggiungere app per i lavoratori in prima linea. Questa caratteristica consente di aggiungere app basate sulla licenza per offrire ai tuoi dipendenti in prima linea un'esperienza di prima classe in Teams personalizzata in base alle loro esigenze.

Con l'esperienza dell'app in prima linea personalizzata, i dipendenti in prima linea ottengono le app più pertinenti in Teams senza alcuna azione da parte dell'amministratore.

## <a name="tailored-frontline-app-experience"></a>Esperienza dell'app in prima linea personalizzata

Le app vengono aggiunte alla barra dell'app, ovvero la barra nella parte inferiore dei client mobili Teams (iOS e Android) e sul lato del client desktop Teams. Le app seguenti sono aggiunte per gli utenti che hanno una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt):

- [Attività](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Team](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie-talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Attività](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Turni](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Approvazioni](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams mobile**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="L'esperienza dell'app in prima linea su misura Teams mobile" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams desktop**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="L'esperienza dell'app in prima linea personalizzata Teams desktop" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Controlli di amministrazione

> [!NOTE]
> **L'impostazione Aggiunta utenti** deve essere attivata nel criterio di configurazione globale [dell'app](teams-app-setup-policies.md) (impostazione predefinita a livello di organizzazione) per l'applicazione di questa caratteristica.

L'esperienza dell'app in prima linea personalizzata è  controllata dall'impostazione Mostra app personalizzate a livello di organizzazione [](manage-apps.md#manage-org-wide-app-settings) nella pagina Gestisci app dell'interfaccia Teams di amministrazione. Se la funzionalità è attivata, tutti gli utenti dell'organizzazione che dispongono di una licenza F otterrà l'esperienza personalizzata dell'app.

Tenere presente che tutti i criteri di [configurazione delle app](teams-app-setup-policies.md) personalizzati assegnati agli utenti hanno la precedenza. Questo significa che se a un utente è già assegnato un criterio di configurazione dell'app personalizzato, l'utente ottiene la configurazione definita nei criteri di configurazione delle app personalizzate. Per altre informazioni sul funzionamento della caratteristica con i Teams delle app, inclusi i criteri di configurazione delle app globali, vedere la sezione [](#scenarios) Scenari più avanti in questo articolo.

Questa funzionalità è attivata per impostazione predefinita. Tuttavia, se non si vuole usare l'esperienza dell'app in prima linea personalizzata fornita da Microsoft, è possibile disattivare la funzionalità. Per disattivare o attivare la funzionalità:

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare a Teams **app** >  di gestione delle **app e quindi** selezionare Impostazioni **dell'app a livello di organizzazione**.
2. In **App personalizzate impostare** l'interruttore Mostra **app personalizzate** su **Disattivato** o **Attivato**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Screenshot dell'impostazione Mostra app personalizzate nella pagina Gestisci app dell'interfaccia Teams di amministrazione" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Scenari

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>In che modo l'esperienza dell'app in prima linea personalizzata influisce sui criteri di configurazione delle app globali?

Scopri come funziona l'esperienza dell'app in prima linea personalizzata insieme ai criteri di configurazione delle app globali. Gli scenari in questa tabella si applicano ai lavoratori in prima linea che hanno una licenza F e ai criteri di configurazione globali dell'app, con l'opzione **Aggiunta utenti** attivata.

|Se... |Quindi... |
|---------|---------|
|Un worker in prima linea ha il criterio di configurazione dell'app globale e la funzionalità è disattivata. |Il worker in prima linea ottiene le app definite nei criteri di configurazione delle app globali.|
|Un worker in prima linea ha il criterio di configurazione dell'app globale e la funzionalità è attivata.     | Il worker in prima linea ottiene l'esperienza dell'app in prima linea personalizzata. Le app definite nei criteri di configurazione delle app globali vengono aggiunte sotto le app personalizzate.      |
|Il criterio di configurazione dell'app globale viene aggiornato e la caratteristica è attivata.     |Il worker in prima linea ottiene l'esperienza dell'app in prima linea personalizzata e le app definite nei criteri di configurazione delle app globali vengono aggiunte sotto le app personalizzate.         |
|Un worker in prima linea ha i criteri di configurazione dell'app globale e **l'aggiunta degli utenti** è disattivata. |Il worker in prima linea ottiene le app definite nei criteri di configurazione delle app globali.|
|Un worker in prima linea ha i criteri di configurazione delle app globali e i criteri di configurazione delle app globali vengono modificati in modo da includere un'app line-of-business (LOB) nella seconda posizione nell'elenco delle app. |L'app LOB viene aggiunta sotto le app personalizzate. Il worker in prima linea può modificare l'ordine dell'app se **l'aggiunta dell'utente** è impostata su .         |
|Un worker in prima linea ha il criterio di configurazione globale e il criterio di configurazione dell'app globale viene modificato in modo da includere i turni nella prima posizione.  |I turni vengono aggiunti alla sesta posizione, come definito dall'esperienza dell'app in prima linea personalizzata. Il worker in prima linea può modificare l'ordine dell'app se **l'aggiunta dell'utente** è impostata su .          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Come funziona l'esperienza dell'app in prima linea personalizzata con altri criteri Teams app?

Scopri come funziona l'esperienza dell'app in prima linea personalizzata con altri criteri Teams'app.

|Se...  |Quindi... |
|---------|---------|
La funzionalità è disattivata.   | Il worker in prima linea ottiene le app definite nei criteri di configurazione delle app globali o nei criteri di configurazione delle app personalizzati assegnati.          |
|Un worker in prima linea ha un criterio di configurazione dell'app personalizzato e la funzionalità è attivata.    |Il worker in prima linea ottiene le app definite nei criteri di configurazione delle app personalizzate.          |
|Un'app nell'esperienza dell'app in prima linea personalizzata viene bloccata per un utente o per l'organizzazione.      |L'esperienza dell'app in prima linea personalizzata rispetta i criteri [di autorizzazione dell'app](teams-app-permission-policies.md). Se un'app è bloccata, il worker in prima linea non vede l'app bloccata.           |
|Un'app nell'esperienza dell'app in prima linea personalizzata è già definita in un criterio di configurazione dell'app e la caratteristica è attivata. |L'app viene aggiunta in base all'ordine definito dall'elenco delle app personalizzate.        |
|Un utente ha una licenza E, A o G e la funzionalità è attivata.   | L'utente non ottiene l'esperienza dell'app in prima linea personalizzata. Attualmente, l'esperienza si applica solo agli utenti che hanno una licenza F.        |

> [!NOTE]
> Non è possibile modificare le app o l'ordine delle app nell'esperienza dell'app in prima linea personalizzata. Per il momento, se si vogliono apportare modifiche, è possibile configurare un'esperienza personalizzata. A questo scopo, disattivare prima la caratteristica. Quindi, [creare un criterio di configurazione dell'app personalizzato](teams-app-setup-policies.md) e [assegnarlo a utenti o gruppi](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Articoli correlati

- [Gestire l'app Walkie Talkie in Teams](walkie-talkie.md)
- [Gestire l'app Attività in Teams](manage-tasks-app.md)
- [Gestire l'app Turni in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gestire l'app Approvazioni in Teams](approval-admin.md)
- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
