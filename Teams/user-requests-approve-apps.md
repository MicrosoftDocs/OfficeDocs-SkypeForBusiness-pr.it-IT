---
title: Richieste degli utenti per gli amministratori
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Informazioni su come gestire e configurare la richiesta dell'utente finale per l'approvazione delle app bloccate in un'organizzazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 0be54f15391793ebc63172df05133bb173da426e
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131055"
---
# <a name="manage-user-requests"></a>Gestire le richieste degli utenti

Le app bloccate nell'organizzazione possono influire sulla produttività e la collaborazione degli utenti finali. Gli utenti finali non possono usare le app bloccate, ma visualizzare tali app e le loro informazioni in Teams Store e richiedere l'approvazione agli amministratori. Dopo aver valutato la richiesta, è possibile scegliere di consentire un'app o ignorare la richiesta.

Questa funzionalità fornisce un segnale sulla richiesta di un'app all'interno dell'organizzazione. È possibile visualizzare facilmente il numero aggregato di richieste per ogni app richiesta. Ti aiuta a prendere una decisione consapevole sulle app da valutare per consentirlo.

L'utente mantiene il controllo completo delle app consentite o bloccate per gli utenti. Se scegli di consentire un'app, i controlli e l'interfaccia utente per gestire le app rimangono invariati.

* L'opzione predefinita invia le richieste degli utenti all'interfaccia di amministrazione di Teams, dove è possibile [visualizzare le richieste degli utenti e consentire le app richieste](#view-and-act-on-user-requests-in-teams-admin-center).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Screenshot che mostra l'opzione per richiedere a un amministratore di approvare un'app bloccata.":::

* Una personalizzazione consente di [configurare l'esperienza utente](#modify-the-default-setting-to-receive-end-user-requests) finale più adatta per l'organizzazione. È possibile fornire un'istruzione o un messaggio personalizzato visualizzato nell'app store di Teams e l'opzione di approvazione della richiesta indirizza gli utenti a un URL specifico dell'organizzazione per raccogliere le loro richieste.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Screenshot che mostra l'esperienza utente finale per le app nello Store quando un amministratore reindirizza l'URL della richiesta di app consenti a un URL specifico dell'organizzazione.":::

## <a name="view-and-act-on-user-requests-in-teams-admin-center"></a>Visualizzare e agire in base alle richieste degli utenti nell'interfaccia di amministrazione di Teams

Le richieste degli utenti finali ricevute con il metodo predefinito vengono visualizzate nell'interfaccia di amministrazione di Teams. È possibile visualizzare e gestire facilmente le richieste. È consigliabile valutare regolarmente la presenza di richieste degli utenti finali. Per visualizzare e consentire le app, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e passare alle app  > **di Teams**[**Gestire le app**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Scegliere di visualizzare la colonna **Richieste per utenti** . È anche possibile ordinare la colonna.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Screenshot che mostra la colonna per le richieste degli utenti nell'interfaccia di amministrazione di Teams e che può essere ordinata." lightbox="media/user-requests-tac-expanded.png":::

1. Per aprire la pagina dei dettagli dell'app che si vuole consentire, selezionare il nome dell'app.

1. Selezionare **Gestisci richieste**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Screenshot che mostra l'opzione gestisci richieste nella pagina dei dettagli dell'app." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Seguire uno o più dei passaggi seguenti, come visualizzato nella finestra di dialogo popup. La procedura per approvare un'app varia in base al metodo usato per bloccarla.

   * Se l'app viene bloccata tramite criteri di [autorizzazione, modificare i criteri di autorizzazione](teams-app-permission-policies.md).
   * Se l'app è stata bloccata per tutti gli utenti, [consentire l'app](manage-apps.md#allow-and-block-apps).
   * Se tutte le app sono bloccate per tutti gli utenti, [modificare le impostazioni a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

Gli utenti finali possono visualizzare l'opzione **Aggiungi** per un'app in Teams Store per verificare se l'app è consentita. Quando si consente un'app dopo aver ricevuto richieste nell'interfaccia di amministrazione di Teams, Teams non informa gli utenti finali che la loro richiesta viene agito su. Quando consenti un'app, il contatore delle richieste non viene reimpostato su zero.

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Modificare l'impostazione predefinita per la ricezione delle richieste degli utenti finali

Teams fornisce un messaggio predefinito per consentire agli utenti di richiedere l'approvazione di un'app. È possibile modificare l'impostazione predefinita per aggiungere un messaggio personalizzato con istruzioni, URL specifico dell'organizzazione o entrambi. Le modifiche vengono visualizzate per ogni app in Teams Store.

Per configurare un messaggio personalizzato e reindirizzare gli utenti a un URL specifico dell'organizzazione, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e passare alle app  > **di Teams**[**Gestire le app**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Nell'angolo in alto a destra seleziona **Impostazioni app a livello di organizzazione**.

1. Per visualizzare un messaggio o un'istruzione personalizzata nell'archivio di Teams, immettere un SMS nel campo di testo in **Configurazione richieste utente**. Il campo ha un limite di 300 caratteri.

1. Per fornire un URL specifico dell'organizzazione per raccogliere le richieste degli utenti, seguire questa procedura:

   1. Attiva l'interruttore **Reindirizza le richieste a un collegamento esterno** .
   1. Fornisci l'URL specifico dell'organizzazione.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Screenshot per attivare o disattivare la personalizzazione dell'URL per le richieste utente nell'interfaccia utente delle impostazioni a livello di organizzazione.":::

1. Selezionare **Salva**.

Se si sceglie di eseguire questa operazione, i metodi per valutare le app di terze parti e consentire le app richieste rimangono invariati.

## <a name="dismiss-user-requests"></a>Ignorare le richieste degli utenti

Per ignorare le richieste, seguire questa procedura:

1. Selezionare il nome dell'app per cui si desidera ignorare le richieste dell'utente.
1. Selezionare **Gestisci richieste**.
1. Nella finestra di dialogo Gestisci richieste utente selezionare **Ignora tutte le richieste**.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Gli amministratori possono approvare una richiesta dell'utente consentendo un'app o ignorando la richiesta e non intraprendendo alcuna azione.":::

Se si ignora una richiesta, questa non informa l'utente finale che la richiesta viene agito su di essa. Quando si ignora una richiesta di consentire un'app, il numero di richieste nell'interfaccia di amministrazione viene reimpostato su zero. Inoltre, dopo alcune ore di chiusura di una richiesta, gli utenti finali possono richiedere di nuovo l'autorizzazione alla stessa app.

## <a name="related-article"></a>Articolo correlato

* [Panoramica su come gestire le app di terze parti](manage-apps.md).
