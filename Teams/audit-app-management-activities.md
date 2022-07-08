---
title: Cercare gli eventi di gestione delle app nei log di controllo
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Informazioni su come controllare le attività dell'app Teams di utenti e amministratori dell'organizzazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 77c7ac5d80304e82f1309e3a22b21c17d106a58c
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647833"
---
# <a name="audit-for-app-management-activities-and-events"></a>Audit per le attività e gli eventi di gestione delle app

Microsoft Purview Audit (Standard) in Microsoft 365 consente di cercare i record di controllo delle attività eseguite nei vari servizi di Microsoft 365 da utenti finali e amministratori.

Prima di eseguire una ricerca di controllo, assicurarsi di completare i prerequisiti seguenti:

* [Ottenere la sottoscrizione dell'organizzazione e le licenze utente](/microsoft-365/compliance/set-up-basic-audit).
* [Attivare il controllo nel Portale di conformità di Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Assegnare autorizzazioni per la ricerca nel log di controllo](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Cercare gli eventi dell'app nei log di controllo in Teams

I log di controllo per gli eventi delle app in Teams consentono di analizzare azioni specifiche. Anche se è possibile cercare nei log un'ampia gamma di azioni, la tabella seguente elenca alcune delle azioni dell'app Teams registrate. È anche possibile eseguire ricerche in attività correlate a connettori, bot, schede e così via.

| Azione dell'app Teams                  | Nome attività                | Descrizione                                              |
|-----------------------------------|------------------------------|:---------------------------------------------------------|
| **App installata**                 | `AppInstalled`               | Viene installata un'app.                                     |
| **App aggiornata**                  | `AppUpgraded`                | Un'app viene aggiornata alla versione più recente nel catalogo. |
| **App disinstallata**               | `AppUninstalled`             | Un'app viene disinstallata.                                   |
| **App pubblicata**                 | `AppPublishedToCatalog`      | Al catalogo viene aggiunta un'app.                          |
| **App aggiornata**                   | `AppUpdatedInCatalog`        | Un'app viene aggiornata nel catalogo.                        |
| **App eliminata**                   | `AppDeletedFromCatalog`      | Un'app viene eliminata dal catalogo.                      |
| **Eliminate tutte le app dell'organizzazione** | `DeletedAllOrganizationApps` | Tutte le app dell'organizzazione sono state eliminate dal catalogo.          |

Per un elenco completo delle attività di Teams controllate, vedere [Attività di Teams](audit-log-events.md#teams-activities) e [Turni nelle attività di Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Anche gli eventi delle app dei canali privati vengono registrati come quelli per Teams e i canali standard.

Usare lo strumento di ricerca log di audit nel Centro conformità per cercare i record di controllo. Per cercare i log di controllo degli eventi dell'app, seguire questa procedura:

1. Accedere a Portale di conformità di Microsoft Purview e passare a **Controllo** > **[ soluzioni](https://compliance.microsoft.com/auditlogsearch)**.
1. Nella pagina di controllo, aggiornare i campi seguenti in base alle proprie esigenze:

   * **Intervallo di data e ora**: selezionare la data di inizio e di fine.
   * **Attività**: immettere le attività di Microsoft Teams. Nell'elenco, selezionare una o più attività dell'app. Per trovare rapidamente le attività di Teams, è possibile cercare la parola `Teams activities` nel campo di ricerca **Attività**.
   * **File, cartella o sito**: immettere il nome del file o un URL o parte di esso.
   * **Utenti**: aggiungere gli utenti di cui si vuole eseguire la ricerca nel log di controllo.

1. Selezionare **Cerca**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Cercare le attività di Teams nel Portale di conformità di Microsoft Purview per controllare gli eventi di Teams." lightbox="media/compliance-search-teams-activities.png":::

Dopo aver cercato il segno di controllo nel portale di conformità, è possibile esportare i record di controllo come file CSV. Per altre informazioni, vedere [Esportare, configurare e visualizzare i log di controllo](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Quando una delle attività precedenti viene eseguita da un utente o un amministratore, Teams genera e archivia un record di controllo. In Audit (Standard), i record vengono conservati per 90 giorni, quindi è possibile cercare le attività che si sono verificate negli ultimi tre mesi.

## <a name="see-also"></a>Vedere anche

* [Cercare il segno di controllo nel portale di conformità](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Panoramica di Microsoft Purview Audit Premium](/microsoft-365/compliance/advanced-audit).
* [Attivare o disattivare il controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
