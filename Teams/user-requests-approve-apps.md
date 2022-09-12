---
title: Richieste degli utenti per gli amministratori di consentire le app
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Informazioni su come gestire e configurare le richieste degli utenti finali per consentire le app bloccate in un'organizzazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 122d41de6f1cb5ea67a5ce85ba9f8f7d02e26339
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647540"
---
# <a name="manage-user-requests"></a>Gestire le richieste degli utenti

Le app bloccate nell'organizzazione possono influire sulla produttività e la collaborazione degli utenti finali. Le app disponibili in Teams Store ma bloccate nell'organizzazione non possono essere usate dagli utenti finali. Tuttavia, per essere sempre informati, gli utenti finali possono visualizzare le app bloccate, visualizzare le informazioni dell'app e i relativi use case server. Gli utenti richiedono l'approvazione dell'amministratore in modo che usino queste app in Teams, dopo aver valutato la richiesta.

Questa funzionalità fornisce un segnale sulla richiesta di un'app all'interno dell'organizzazione. È possibile visualizzare facilmente il numero aggregato di richieste di app. Consente di prendere una decisione consapevole sulle app da valutare da consentire nell'organizzazione.

L'utente mantiene il controllo completo delle app consentite o bloccate per gli utenti. Se scegli di consentire un'app, i controlli e l'interfaccia utente per gestire le app rimangono invariati.

* L'opzione predefinita invia le richieste utente nell'interfaccia di amministrazione di Teams, dove è possibile [visualizzare le richieste degli utenti e consentire le app richieste](#view-user-requests).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Screenshot che mostra l'opzione per richiedere a un amministratore di approvare un'app bloccata.":::

* Una personalizzazione consente di [configurare l'esperienza utente](#modify-the-default-setting-to-receive-end-user-requests) finale più adatta per l'organizzazione. È possibile fornire un'istruzione personalizzata visualizzata agli utenti finali sulle app bloccate nell'app store di Teams e indirizzare gli utenti a un sito interno per raccogliere le loro richieste.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Screenshot che mostra l'esperienza utente finale per le app nello Store quando un amministratore reindirizza l'URL della richiesta di app consenti a un sito interno.":::

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Modificare l'impostazione predefinita per la ricezione delle richieste degli utenti finali

Per configurare un messaggio personalizzato e reindirizzare gli utenti a un URL specifico dell'organizzazione per richiedere l'approvazione delle app, procedere come segue:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alla pagina **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)** **delle app** >  di Teams.

1. Seleziona Impostazioni app a livello di organizzazione.

1. Per visualizzare un messaggio o un'istruzione personalizzata nell'archivio client di Teams, fornire un SMS nella configurazione Richieste utente.

1. Per fornire un URL specifico dell'organizzazione per raccogliere le richieste degli utenti, eseguire le operazioni seguenti:

   1. Impostare l'opzione Reindirizza le richieste a uno strumento esterno su Attivato.
   1. Fornisci l'URL personalizzato specifico dell'organizzazione.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Screenshot per attivare o disattivare la personalizzazione dell'URL per la richiesta dell'utente di sbloccare l'app nell'interfaccia utente delle impostazioni a livello di organizzazione.":::

1. Selezionare **Salva**.

## <a name="view-user-requests"></a>Visualizzare le richieste degli utenti

Le richieste degli utenti finali ricevute con il metodo predefinito vengono visualizzate nell'interfaccia di amministrazione di Teams. È possibile visualizzare e gestire facilmente le richieste. È consigliabile effettuare una valutazione regolare per verificare la presenza di richieste da parte dell'utente finale. Per visualizzare e consentire le app, procedere come segue:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alla pagina **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)** **delle app** >  di Teams.

1. Scegliere di visualizzare la colonna **Richieste per utenti** . È anche possibile ordinare la colonna.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Screenshot che mostra la colonna per le richieste degli utenti nell'interfaccia di amministrazione di Teams e che può essere ordinata." lightbox="media/user-requests-tac-expanded.png":::

1. Per aprire la pagina dei dettagli dell'app che si vuole consentire, selezionare il nome dell'app.

1. Selezionare **Gestisci richieste**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Screenshot che mostra l'opzione gestisci richieste nella pagina dei dettagli dell'app." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Seguire uno o più dei passaggi seguenti, come visualizzato nella finestra di dialogo popup. La procedura per approvare un'app varia in base al metodo usato per bloccarla.

   * Se l'app viene bloccata tramite criteri di [autorizzazione, modificare i criteri di autorizzazione](teams-app-permission-policies.md).
   * Se l'app è stata bloccata per tutti gli utenti, [consentire l'app](manage-apps.md#allow-and-block-apps).
   * Se tutte le app sono bloccate per tutti gli utenti, [modificare le impostazioni a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

1. Facoltativamente, per passare a una configurazione personalizzata all'URL specifico dell'organizzazione, selezionare il collegamento Configura richieste utente nella finestra di dialogo Gestisci richieste utente. Apre il riquadro Impostazioni app a livello di organizzazione in cui è possibile [configurare l'esperienza di richiesta per l'utente finale](#modify-the-default-setting-to-receive-end-user-requests).

Se si consente un'app dopo aver ricevuto richieste nell'interfaccia di amministrazione di Teams, Teams non informa l'utente finale che la sua richiesta viene agito su. L'utente può controllare l'app in Teams Store per verificare se l'app è consentita. L'opzione Aggiungi l'app è disponibile per l'utente dopo averlo consentito. Se si consente a un'app dopo aver ricevuto richieste tramite il metodo specifico dell'organizzazione, si applicano i meccanismi interni per fornire l'aggiornamento dello stato all'utente finale.

Per reimpostare il numero di richieste di app a zero, ignora le richieste. Se consenti semplicemente un'app, il contatore delle richieste non viene reimpostato su zero.

## <a name="dismiss-user-requests"></a>Ignorare le richieste degli utenti

Per ignorare le richieste di consentire l'app, seguire questa procedura:

1. Selezionare il nome dell'app per cui si desidera ignorare le richieste dell'utente.
1. Selezionare **Gestisci richieste** e quindi **Ignora tutte le richieste** nella finestra di dialogo.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Gli amministratori possono approvare una richiesta dell'utente consentendo un'app o ignorando la richiesta e non intraprendendo alcuna azione.":::

Se si ignora una richiesta, questa non informa l'utente finale che la richiesta viene agito su di essa. Quando si ignora una richiesta di consentire un'app, il numero di richieste nell'interfaccia di amministrazione viene reimpostato su zero. Inoltre, dopo alcune ore di chiusura di una richiesta, gli utenti finali possono richiedere di nuovo che la stessa app sia consentita.

## <a name="related-article"></a>Articolo correlato

* [Panoramica su come gestire le app di terze parti](manage-apps.md).
