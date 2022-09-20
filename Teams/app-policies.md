---
title: Panoramica dei criteri delle app per gestire le app in Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
search.appverid: ''
description: Informazioni sui criteri di autorizzazione delle app, i criteri di configurazione delle app e i criteri delle app personalizzati usati per gestire le app in Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: ad7e99d10ebf53c7a85394edda84061f6caf0d29
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837566"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>Panoramica dei criteri delle app usati per gestire l'accesso alle app

Microsoft Teams usa i criteri per disciplinare l'accesso e il comportamento di installazione. I criteri consentono agli amministratori di Teams di controllare il comportamento dell'app seguente:

* Configurare l'accesso delle app per gli utenti a livello granulare. Ciò consente a ogni utente finale di usare solo le app consentite dall'amministratore.

* Aggiungere le app pertinenti per un utente specifico. Ciò consente agli utenti finali di iniziare facilmente e di accedere rapidamente alle app pertinenti, dal momento che le app aggiunte vengono installate automaticamente senza alcun intervento.

## <a name="app-permission-policies"></a>Criteri di autorizzazione delle app

Con i criteri di autorizzazione per le app, l'amministratore di Teams può controllare quali app sono disponibili per gli utenti specifici dell'organizzazione. È possibile definire il mapping di accesso esatto tra l'app e l'utente o qualsiasi combinazione di entrambi. Ad esempio, è possibile consentire alcune app per tutti gli utenti, consentire alcune app per un gruppo specifico di utenti oppure consentire un'app specifica per un utente specifico.

I criteri di autorizzazione per le app si applicano a tutti i tipi di app disponibili in Teams. Ad esempio, è possibile usare i criteri di autorizzazione per le app per distribuire gradualmente un'app di terze parti o un'app personalizzata, consentendola per utenti specifici.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Screenshot di criteri di autorizzazione delle app." lightbox="media/app-permission-policy.png":::

Per altre informazioni, vedere [Gestire i criteri e le impostazioni app personalizzate](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Criteri di configurazione delle app

I criteri di configurazione delle app consentono di personalizzare l'esperienza dell'app per gli utenti. È possibile scegliere le app che si desidera aggiungere alla barra dell'app nei client di Teams e l'ordine in cui vengono visualizzate nei client Web, desktop e per dispositivi mobili.

Ecco alcuni esempi di come usare i criteri di configurazione delle app:

* Installare le applicazioni per gli utenti finali nel loro ambiente personale di Teams. Ciò aiuta a favorire la consapevolezza e l'adozione delle app desiderate. Ad esempio, è possibile aggiungere un'app personalizzata di selezione del personale e gestione dei ruoli per i membri del team delle risorse umane.
* Aggiungere in modo selettivo le app di base, come Chat, Teams e Chiamate.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Screenshot dei criteri di configurazione delle app nell’interfaccia di amministrazione di Microsoft Teams." lightbox="media/app-setup-policy.png":::

Per altre informazioni, vedere [come gestire i criteri di configurazione delle app](teams-app-setup-policies.md).

## <a name="custom-app-policies"></a>Criteri delle app personalizzate

Teams consente agli sviluppatori all'interno dell'organizzazione di creare, testare e distribuire app personalizzate per gli utenti interni dell'organizzazione. Gli sviluppatori possono inviare le loro app personalizzate tramite Teams per l'approvazione da parte degli amministratori. È possibile usare i criteri di configurazione delle app per controllare chi nell'organizzazione può caricare app personalizzate. Gli amministratori possono consentire agli utenti finali dell'organizzazione di usare app personalizzate e gli sviluppatori possono caricare app personalizzate, usando le impostazioni delle app a livello di organizzazione.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Screenshot che mostra come consentire le app personalizzate nell'organizzazione nel riquadro delle impostazioni a livello di organizzazione." lightbox="media/custom-app-policy.png":::

Per altre informazioni, vedere [come gestire i criteri e le impostazioni delle app personalizzate](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Articoli correlati

* [Gestire Teams con i criteri](manage-teams-with-policies.md)
