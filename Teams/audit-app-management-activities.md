---
title: Cercare gli eventi di gestione delle app nei log di controllo
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Informazioni su come controllare le attività dell'app Teams di utenti e amministratori dell'organizzazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5aee5bf00d486586b4bc8e9583504be5e4a9b922
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251879"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>Cercare nei log di controllo le attività e gli eventi di gestione delle app

Microsoft Purview Audit (Standard) in Microsoft 365 consente di cercare i record di controllo delle attività eseguite nei vari servizi di Microsoft 365 da utenti finali e amministratori.

Prima di eseguire ricerche nei record di controllo, assicurarsi di aver completato i prerequisiti seguenti:

* [Ottenere la sottoscrizione dell'organizzazione e la licenza utente](/microsoft-365/compliance/set-up-basic-audit).
* [Attivare il controllo nel Portale di conformità di Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Assegnare autorizzazioni per la ricerca nel log di controllo](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Cercare gli eventi dell'app nei log di controllo in Teams

I log di controllo per gli eventi delle app in Teams consentono di esaminare azioni specifiche relative alla gestione delle app da parte degli amministratori. Anche se è possibile cercare nei log un'ampia gamma di azioni, la tabella seguente elenca alcune azioni di questo tipo registrate.

| Azione dell'app Teams | Nome attività nel portale | Descrizione  |
|-------|-------|:-------|
| **App installata**                 | `AppInstalled`               | Un'app viene installata o aggiunta a un client di Teams. |
| **App aggiornata**                  | `AppUpgraded`                | Un'app viene aggiornata alla versione più recente nel catalogo. |
| **App disinstallata**               | `AppUninstalled`             | Un'app viene disinstallata o rimossa da un client di Teams.                                   |
| **App pubblicata**                 | `AppPublishedToCatalog`      | Al catalogo viene aggiunta un'app.                          |
| **App aggiornata**                   | `AppUpdatedInCatalog`        | Un'app viene aggiornata nel catalogo.                        |
| **App eliminata**                   | `AppDeletedFromCatalog`      | Un'app viene eliminata dal catalogo.                      |
| **Eliminate tutte le app dell'organizzazione** | `DeletedAllOrganizationApps` | Tutte le app dell'organizzazione sono state eliminate dal catalogo.          |

<!--- organization apps = custom or 3p --->

Per un elenco completo delle attività di Teams controllate, vedere [Attività di Teams](audit-log-events.md#teams-activities) e [Turni nelle attività di Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Gli eventi delle app dei canali privati vengono registrati anche quando tali eventi vengono eseguiti in Teams e nei canali standard.

Per eseguire ricerche nei log di controllo delle attività dell'app Teams, seguire questa procedura:

1. Accedere a Portale di conformità di Microsoft Purview e passare a **Controllo** > **[ soluzioni](https://compliance.microsoft.com/auditlogsearch)**.
1. Nella pagina **Controllo** aggiornare i campi seguenti in base alle esigenze:

   * **Intervallo di date e ore**: selezionare le date di inizio e di fine del periodo di tempo per il quale si desidera controllare i log di controllo.
   * **Attività**: immettere le attività di Microsoft Teams. Nell'elenco, selezionare una o più attività dell'app. Per trovare rapidamente le attività di Teams, è possibile cercare la parola `Teams activities` nel campo di ricerca **Attività**.
   * **File, cartella o sito**: immettere il nome del file o un URL o parte di esso.
   * **Utenti**: aggiungere gli utenti di cui si vuole eseguire la ricerca nel log di controllo.

1. Selezionare **Cerca**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Cercare le attività di Teams nel Portale di conformità di Microsoft Purview per controllare gli eventi di Teams." lightbox="media/compliance-search-teams-activities.png":::

È possibile esportare i record di controllo cercati come file CSV. Per altre informazioni, vedere [Esportare, configurare e visualizzare i log di controllo](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Quando una delle attività precedenti viene eseguita da un utente o un amministratore, Teams genera e archivia un record di controllo. In Audit (Standard), i record vengono conservati per 90 giorni, quindi è possibile cercare le attività che si sono verificate negli ultimi tre mesi.

> [!TIP]
> Se l'amministratore vuole creare un report per utente per sapere se un utente ha bloccato o disattivato un bot, vedere [Capire chi ha bloccato, disattivato o disinstallato un bot](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>Articoli correlati

* [Utilizzare i registri di audit per indagare sull'attività di installazione di Microsoft Power Platform](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [Cercare il segno di controllo nel portale di conformità](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Panoramica di Microsoft Purview Audit Premium](/microsoft-365/compliance/advanced-audit).
* [Attivare o disattivare il controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
