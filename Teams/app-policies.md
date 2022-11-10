---
title: Panoramica dei criteri delle app per gestire le app in Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: Informazioni sui criteri di autorizzazione delle app e sui criteri di configurazione usati per gestire le app in Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 8e059199d4963004e287b456c98bb80717f849b3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912435"
---
# <a name="know-about-policies-to-manage-access-and-installation-of-teams-apps"></a>Informazioni sui criteri per gestire l'accesso e l'installazione delle app Teams

Microsoft Teams usa i criteri delle app per disciplinare il comportamento di accesso e installazione delle app. I criteri per le app aiutano gli amministratori di Teams a controllare il comportamento dell'app seguente:

* Configurare l'accesso delle app per ogni singolo utente o per un gruppo di utenti. Aiuta l'amministratore a controllare le app consentite per ogni utente finale.

* Aggiungere le app per gli utenti finali rilevanti per le esigenze dell'organizzazione. Inoltre, gli amministratori possono installare app per gli utenti finali senza l'intervento dell'utente. Consente agli utenti finali di iniziare facilmente con le app pertinenti.

* Controllare quali sviluppatori dell'organizzazione possono inviare app personalizzate per l'approvazione dell'amministratore. Consente di controllare l'accesso alle funzionalità di caricamento delle app personalizzate.

## <a name="app-permission-policies"></a>Criteri di autorizzazione delle app

Con i criteri di autorizzazione per le app, l'amministratore di Teams controlla quali app sono disponibili per ogni utente dell'organizzazione. È possibile consentire alcune app per tutti gli utenti, consentire alcune app per un gruppo specifico di utenti oppure consentire app specifiche per utenti specifici. I criteri di autorizzazione per le app funzionano insieme alle impostazioni a livello di organizzazione e consentono o bloccano lo stato di ogni singola app.

I criteri di autorizzazione per le app si applicano a tutti i [tipi di app disponibili in Teams](deploy-apps-microsoft-teams-landing-page.md). Alcuni scenari di esempio in cui si usano i criteri di autorizzazione per le app sono:

* Distribuire gradualmente un'app ad alcuni utenti inizialmente e a tutti gli utenti alla fine.
* Consenti un'app personalizzata per il reclutamento e la gestione dei talenti solo per i membri del reparto risorse umane e bloccala per tutti gli altri utenti dell'organizzazione.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Screenshot di criteri di autorizzazione delle app." lightbox="media/app-permission-policy.png":::

Per altre informazioni, vedere [come gestire i criteri di autorizzazione delle app](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Criteri di configurazione delle app

I criteri di configurazione delle app consentono di configurare come e dove sono le app disponibili per gli utenti nel client di Teams. Scegli le app che vuoi aggiungere alla barra dell'app nei client di Teams e definisci l'ordine in cui vengono visualizzate le app.

L'aggiunta o l'installazione di app consente di aumentare la consapevolezza e l'adozione delle app desiderate nell'organizzazione. Le modifiche si applicano ai client Web, desktop e mobili di Teams.

Alcuni scenari di esempio in cui si usano i criteri di configurazione delle app sono:

* Aggiungi un'app personalizzata per il reclutamento e la gestione dei talenti per i membri del tuo team hr.
* Modificare l'ordine delle [app di base](deploy-apps-microsoft-teams-landing-page.md#core-apps) con il blocco per gli utenti dell'organizzazione.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Screenshot dei criteri di configurazione delle app nell’interfaccia di amministrazione di Microsoft Teams." lightbox="media/app-setup-policy.png":::

Per altre informazioni, vedere [come gestire i criteri di configurazione delle app](teams-app-setup-policies.md).

### <a name="option-to-upload-custom-apps"></a>Opzione per caricare app personalizzate

L'organizzazione può richiedere la creazione di app personalizzate per requisiti specifici dell'organizzazione. Gli sviluppatori all'interno dell'organizzazione possono creare, testare e distribuire app personalizzate per gli utenti interni di Teams dell'organizzazione. I criteri di configurazione delle app consentono di controllare gli utenti dell'organizzazione che possono caricare app personalizzate. Le impostazioni a livello di organizzazione consentono agli utenti finali di usare app personalizzate. I criteri di autorizzazione consentono a utenti finali specifici di usare un'app personalizzata.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Screenshot che mostra come consentire le app personalizzate nell'organizzazione nel riquadro delle impostazioni a livello di organizzazione." lightbox="media/custom-app-policy.png":::

Per altre informazioni, vedere [come gestire criteri e impostazioni per le app personalizzate](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Articoli correlati

* [Gestire Teams con i criteri](manage-teams-with-policies.md)
* [Gestire i criteri di autorizzazione delle app](teams-app-permission-policies.md)
* [Gestire i criteri di configurazione delle app](teams-app-setup-policies.md)
* [Gestire criteri e impostazioni per le app personalizzate](teams-custom-app-policies-and-settings.md)
