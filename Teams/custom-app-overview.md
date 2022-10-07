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
ms.date: 09/25/2022
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
ms.openlocfilehash: 42c970f3b354ac1f5b490359f0df9bcc01e97019
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494769"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Comprendere e gestire app personalizzate e caricate in sideload

Microsoft Teams consente agli sviluppatori all'interno dell'organizzazione di creare, testare e distribuire app personalizzate per gli utenti interni dell'organizzazione. Tali app sono denominate app personalizzate o app Line of Business. L'organizzazione può richiedere la creazione di app personalizzate per requisiti specifici dell'organizzazione. Gli amministratori controllano l'implementazione e le autorizzazioni per le app personalizzate usando varie impostazioni e criteri.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="Screenshot che mostra come consentire le app personalizzate nell'organizzazione nel riquadro delle impostazioni a livello di organizzazione." lightbox="media/custom-app-orgwide-setting.png":::

Dopo aver consentito l'uso di un'app personalizzata, gli utenti finali possono trovarla selezionando **Built per la tua organizzazione** nella barra di spostamento sinistra di Teams Store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Schermata delle app personalizzate nello store di Teams nell'app desktop di Teams." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Informazioni sul trasferimento locale di app personalizzate

Quando sviluppi app personalizzate e prima di distribuirle agli utenti finali, gli sviluppatori testano le app aggiungendola a Teams Store per testare. Gli sviluppatori possono eseguire il test autonomamente o con un gruppo di utenti specificato, ma l'app non è disponibile per gli altri utenti finali dell'organizzazione tramite lo Store. Questo metodo è detto trasferimento locale delle app e si applica solo alle app personalizzate.

Gli sviluppatori possono caricare un'applicazione per renderla disponibile ai membri di un team specifico, in genere per testare un'applicazione in fase di sviluppo. L'uso di un'app in questo modo limita il suo utilizzo agli sviluppatori dell'app e non richiede l'approvazione dell'amministratore, purché quest'ultimo consenta il sideloading in Teams.

Gli sviluppatori possono condividere un'app in sideload con un team specifico senza inviarla al catalogo app di Teams. Rende l'app personalizzata caricata in sideload disponibile per un gruppo limitato di utenti finali, ma non disponibile nell'app store dell'organizzazione per tutti gli utenti finali.

Come amministratore, è possibile disabilitare il sideloading delle app per tutti gli sviluppatori. Se si disconosce il sideloading, gli sviluppatori possono comunque testare le loro applicazioni creando un [tenant di test separato](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una volta completato lo sviluppo di app personalizzate, gli sviluppatori richiedono agli amministratori di distribuire l'app personalizzata agli utenti finali. Per informazioni dettagliate, vedere [come pubblicare un'app personalizzata](/microsoftteams/upload-custom-apps). Gli amministratori consentono (o bloccano) l'uso di un'app personalizzata per tutti gli utenti o per utenti specifici.

## <a name="allow-developers-to-upload-custom-apps"></a>Consentire agli sviluppatori di caricare app personalizzate

Nei criteri di configurazione delle app è possibile creare un criterio personalizzato o modificare il criterio globale per consentire il caricamento di app personalizzate. Per creare un criterio personalizzato e applicarlo a utenti specifici, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **App di Teams** > **[Criteri di configurazione](https://admin.teams.microsoft.com/policies/app-setup)**.
1. Selezionare **Aggiungi**.
1. Specificare un nome e una descrizione per il criterio.
1. Attivare o disattivare **Carica app personalizzate**.
1. [Applicare il criterio agli utenti](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) che sviluppano app personalizzate e sono autorizzati a caricarle.

> [!NOTE]
> Per modificare questa impostazione, consenti app personalizzate nelle [impostazioni delle app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).

## <a name="related-articles"></a>Articoli correlati

* [Gestire criteri e impostazioni per le app personalizzate](teams-custom-app-policies-and-settings.md)
* [Informazioni sui criteri per gestire le app](app-policies.md)
* [Informazioni sulle app di terze parti](overview-third-party-apps.md)
