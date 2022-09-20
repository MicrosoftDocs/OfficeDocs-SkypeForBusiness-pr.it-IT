---
title: Gestire app personalizzate e caricate in sideload
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Comprendere quali sono le app personalizzate e le app sideload in Microsoft Teams e gestire le app per regolamentarne il comportamento, l'implementazione e le autorizzazioni.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4ba559d605f1465fda7caf9b253c18864c8b4c20
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837376"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Comprendere e gestire app personalizzate e caricate in sideload

Microsoft Teams consente agli sviluppatori all'interno dell'organizzazione di creare, testare e distribuire app personalizzate per gli utenti interni dell'organizzazione. Tali app sono denominate app personalizzate o app Line of Business. L'organizzazione può richiedere la creazione di app personalizzate per requisiti specifici dell'organizzazione.

L'amministratore ha il controllo di consentire o bloccare tali app per l'intera organizzazione o per utenti specifici. Gli sviluppatori nell'organizzazione possono compilare soluzioni personalizzate con basso impiego di codice usando l'integrazione di Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Gli sviluppatori possono inviare le app personalizzate tramite Teams per l'approvazione da parte dell'amministratore. È possibile usare i criteri di configurazione delle app per controllare l'implementazione, la distribuzione e le autorizzazioni delle app personalizzate.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Screenshot che mostra come consentire le app personalizzate nell'organizzazione nel riquadro delle impostazioni a livello di organizzazione." lightbox="media/custom-app-policy.png":::

Dopo aver consentito l'uso di un'app personalizzata, gli utenti finali possono trovarla selezionando **Built per la tua organizzazione** nella barra di spostamento sinistra di Teams Store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Schermata delle app personalizzate nello store di Teams nell'app desktop di Teams." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Informazioni sul trasferimento locale di app personalizzate

Quando sviluppi app personalizzate e prima di distribuirle agli utenti finali, gli sviluppatori testano le app aggiungendola a Teams Store per testare. Gli sviluppatori possono eseguire il test autonomamente o con un gruppo di utenti specificato, ma l'app non è disponibile per gli altri utenti finali dell'organizzazione tramite lo Store. Questo metodo è detto trasferimento locale delle app e si applica solo alle app personalizzate.

Gli sviluppatori possono caricare un'applicazione per renderla disponibile ai membri di un team specifico, in genere per testare un'applicazione in fase di sviluppo. L'uso di un'app in questo modo limita il suo utilizzo agli sviluppatori dell'app e non richiede l'approvazione dell'amministratore, purché quest'ultimo consenta il sideloading in Teams.

Gli sviluppatori possono condividere un'app in sideload con un team specifico senza inviarla al catalogo app di Teams. Rende l'app personalizzata caricata in sideload disponibile per un gruppo limitato di utenti finali, ma non disponibile nell'app store dell'organizzazione per tutti gli utenti finali.

Come amministratore, è possibile disabilitare il sideloading delle app per tutti gli sviluppatori. Se si disconosce il sideloading, gli sviluppatori possono comunque testare le loro applicazioni creando un [tenant di test separato](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una volta completato lo sviluppo di app personalizzate, gli sviluppatori richiedono agli amministratori di distribuire l'app personalizzata agli utenti finali. Per informazioni dettagliate, vedere [come pubblicare un'app personalizzata](/microsoftteams/upload-custom-apps). Gli amministratori possono consentire o impedire l'uso di un'app personalizzata per utenti specifici.

## <a name="allow-developers-to-upload-custom-apps"></a>Consentire agli sviluppatori di caricare app personalizzate

È possibile creare un criterio personalizzato o modificare il criterio globale per consentire o bloccare le app personalizzate in base alle esigenze aziendali. Per creare un criterio personalizzato che consente agli sviluppatori dell'organizzazione di caricare app personalizzate, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **App di Teams** > **[Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Selezionare **Aggiungi**.

1. Specificare un nome e una descrizione per il criterio.

1. Attivare o disattivare **Carica app personalizzate**.

> [!NOTE]
> Per modificare questa impostazione, consenti app di terze parti nelle impostazioni delle app a [livello di organizzazione](manage-apps.md#manage-org-wide-app-settings) del tuo tenant.

## <a name="related-articles"></a>Articoli correlati

* [Gestire le impostazioni e i criteri delle app personalizzate](teams-custom-app-policies-and-settings.md)
* [Informazioni sui criteri per gestire le app](app-policies.md)
* [Informazioni sulle app di terze parti](overview-third-party-apps.md)
