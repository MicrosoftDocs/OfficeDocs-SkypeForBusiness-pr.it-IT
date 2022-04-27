---
title: Personalizzare le app Teams per i dipendenti in prima linea
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza app personalizzata per gli operatori in prima linea in Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c3112740ab2b25b0f0107823d41c5b5e2d68f0f
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059307"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Personalizzare le app Teams per i dipendenti in prima linea

> [!NOTE]
> Questa funzionalità è in fase di distribuzione e potrebbe non essere ancora disponibile nell'organizzazione. Per mantenersi aggiornati sulle prossime funzionalità di Teams, consultare la [roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Panoramica

Teams offre un modo semplice per aggiungere app per gli operatori in prima linea. Questa funzionalità consente di aggiungere app in base alla licenza per offrire ai dipendenti in prima linea un'esperienza personalizzata in Teams su misura per le loro esigenze.

Con l'esperienza personalizzata delle app in prima linea, i dipendenti in prima linea ottengono le app più pertinenti in Teams senza che sia necessario alcun intervento da parte dell'amministratore.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VuCH]

## <a name="tailored-frontline-app-experience"></a>Esperienza app in prima linea personalizzate

Le app vengono aggiunte alla barra dell'app, ovvero la barra nella parte inferiore della Teams client mobili (iOS e Android) e sul lato del client desktop Teams. Le app seguenti vengono aggiunte per gli utenti che hanno una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt):

- [Attività](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Team](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie-talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Attività](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Turni](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Approvazioni](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams dispositivo mobile**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="L'esperienza dell'app in prima linea personalizzata su Teams dispositivo mobile" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams desktop**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="L'esperienza dell'app in prima linea personalizzata su Teams desktop" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Controlli di amministrazione

> [!NOTE]
> **Per rendere** effettiva questa funzionalità, l'impostazione per [l'aggiunta dell'utente](teams-app-setup-policies.md) deve essere attivata nei criteri di configurazione delle app globali (impostazione predefinita a livello di organizzazione).

L'esperienza delle app in prima linea personalizzata è controllata dall'impostazione **Mostra app personalizzate** a livello di organizzazione nella pagina [Gestisci app](manage-apps.md#manage-org-wide-app-settings) dell'interfaccia di amministrazione di Teams. Se la funzionalità è attivata, tutti gli utenti dell'organizzazione che hanno una licenza F riceveranno l'esperienza dell'app personalizzata.

Tenere presente che tutti i [criteri di configurazione delle app](teams-app-setup-policies.md) personalizzati assegnati agli utenti hanno la precedenza. Questo significa che se a un utente è già assegnato un criterio di configurazione dell'app personalizzato, l'utente ottiene la configurazione definita nel criterio di configurazione dell'app personalizzato. Per altre informazioni sul funzionamento della funzionalità con Teams criteri delle app, inclusi i criteri di configurazione globale delle app, vedere la sezione [Scenari](#scenarios) più avanti in questo articolo.

Questa funzionalità è attivata per impostazione predefinita. Tuttavia, se non desideri l'esperienza dell'app frontline personalizzata fornita da Microsoft, puoi disattivare la funzionalità. Per attivare o disattivare la funzionalità:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams** **appGesti** >  app e quindi selezionare **Impostazioni app a livello di organizzazione**.
2. In **App personalizzate** imposta **l'interruttore Mostra app personalizzate** su **Disattivato** o **Attivato**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Screenshot dell'impostazione Mostra app personalizzate nella pagina Gestisci app dell'interfaccia di amministrazione di Teams" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Scenari

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>In che modo l'esperienza delle app frontline personalizzate influisce sui criteri di configurazione delle app globali?

Scopri come funziona l'esperienza delle app in prima linea personalizzata insieme ai criteri di configurazione delle app globali. Gli scenari di questa tabella si applicano agli operatori in prima linea che hanno una licenza F e ai criteri di configurazione globale dell'app, con **l'aggiunta dell'utente** attivata.

|Se... |Poi... |
|---------|---------|
|Un frontline worker ha i criteri di configurazione globale dell'app e la funzionalità è disattivata. |Il frontline worker ottiene le app definite nel criterio di configurazione globale delle app.|
|Un frontline worker ha i criteri globali di configurazione dell'app e la funzionalità è attivata.     | Il frontline worker ottiene l'esperienza dell'app in prima linea personalizzata. Le app definite nei criteri di configurazione globale delle app vengono aggiunte sotto le app personalizzate.      |
|Aggiornare i criteri di configurazione globale delle app e la funzionalità è attivata.     |Il frontline worker ottiene l'esperienza dell'app frontline personalizzata e le app definite nei criteri di configurazione globale delle app vengono aggiunte sotto le app personalizzate.         |
|Un frontline worker ha i criteri di configurazione dell'app globali e **l'aggiunta dell'utente** è disattivata. |Il frontline worker ottiene le app definite nel criterio di configurazione globale delle app.|
|Un frontline worker ha i criteri di configurazione globale dell'app e il criterio di configurazione globale delle app viene modificato per includere un'app line-of-business (LOB) nella seconda posizione nell'elenco delle app. |L'app line-of-business viene aggiunta sotto le app personalizzate. Il frontline worker può modificare l'ordine dell'app se **l'aggiunta dell'utente** è attivata.         |
|Un frontline worker ha i criteri di configurazione globale e il criterio di configurazione globale delle app viene modificato per includere Turni nella prima posizione.  |Turni viene aggiunto alla sesta posizione, come definito dall'esperienza dell'app in prima linea personalizzata. Il frontline worker può modificare l'ordine dell'app se **l'aggiunta dell'utente** è attivata.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Come funziona l'esperienza delle app frontline personalizzate con altri criteri delle app Teams?

Scopri come funziona l'esperienza delle app frontline personalizzate con altri criteri delle app Teams.

|Se...  |Poi... |
|---------|---------|
La funzionalità è disattivata.   | Il frontline worker ottiene le app definite nel criterio di configurazione globale delle app o nei criteri di configurazione delle app personalizzati assegnati.          |
|Un frontline worker ha un criterio di configurazione delle app personalizzato e la funzionalità è attivata.    |Il frontline worker ottiene le app definite nei criteri di configurazione delle app personalizzate.          |
|Un'app nell'esperienza dell'app frontline personalizzata viene bloccata per un utente o per l'organizzazione.      |L'esperienza dell'app in prima linea personalizzata rispetta i [criteri di autorizzazione dell'app](teams-app-permission-policies.md). Se un'app è bloccata, il frontline worker non vedrà l'app bloccata.           |
|Un'app nell'esperienza dell'app frontline personalizzata è già definita in un criterio di configurazione dell'app e la funzionalità è attivata. |L'app viene aggiunta in base all'ordine definito dall'elenco di app personalizzate.        |
|Un utente ha una licenza E, A o G e la funzionalità è attivata.   | L'utente non ottiene l'esperienza dell'app frontline personalizzata. Attualmente, l'esperienza si applica solo agli utenti che hanno una licenza F.        |

> [!NOTE]
> Non puoi modificare le app o l'ordine delle app nell'esperienza delle app frontline personalizzate. Per il momento, se si vogliono apportare modifiche, è possibile configurare un'esperienza personalizzata. A questo scopo, disattivare prima di tutto la funzionalità. Creare quindi [criteri di configurazione delle app personalizzati](teams-app-setup-policies.md) e [assegnarli a utenti o gruppi](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Articoli correlati

- [Gestire l'app Walkie-talkie in Teams](walkie-talkie.md)
- [Gestire l'app Attività in Teams](manage-tasks-app.md)
- [Gestire l'app Turni in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gestire l'app Approvazioni in Teams](approval-admin.md)
- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
