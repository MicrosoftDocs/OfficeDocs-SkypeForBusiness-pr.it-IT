---
title: Adobe Acrobat come visualizzatore PDF predefinito in Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Informazioni su come impostare Adobe Acrobat come visualizzatore PDF predefinito per visualizzare e modificare i file PDF in Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 9e8860c10e74d5dc06f73632b33b6c94ea792a09
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299245"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat come visualizzatore PDF predefinito in Microsoft Teams

> [!NOTE]
> Adobe Acrobat come esperienza PDF predefinita in Microsoft Teams è attualmente disponibile solo in anteprima pubblica. Per usare questa funzionalità, gli amministratori devono [abilitare l'anteprima pubblica](public-preview-doc-updates.md#enable-public-preview) per il tenant e assicurarsi che gli utenti finali modifichino la versione client di Teams in anteprima pubblica.

Gli amministratori possono impostare Adobe Acrobat come app predefinita per visualizzare e modificare i file PDF in Microsoft Teams. Gli utenti finali possono visualizzare, cercare, commentare e annotare i file PDF senza dover sottoscrivere un abbonamento ad Adobe Acrobat o possedere un ID Adobe.

Per configurare l'app di Adobe Acrobat come gestore predefinito per i file PDF nel tenant, completare i passaggi seguenti come prerequisiti:

* [Consentire l'app di Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Installare l'app di Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Consentire l'app di Adobe Acrobat nel tenant

Prima di configurare l'app, assicurarsi di aver consentito l'uso delle app nel tenant, di aver esplicitamente consento l'app di Adobe Acrobat e che i criteri di autorizzazione dell'app lo consentano. Per configurare Adobe Acrobat come app predefinita per i file PDF, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e passare a **App di Teams** > **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Cercare l'app di Adobe Acrobat e selezionarla.

1. Nella scheda **Autorizzazioni**, selezionare **Verifica autorizzazione**.

   :::image type="content" source="media/permission-policy.png" alt-text="Screenshot dell'autorizzazione dell'app nell'interfaccia di amministrazione di Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Selezionare **Accetta**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installare l'app di Adobe Acrobat per tutti gli utenti

Per assegnare e rendere disponibile l'app di Adobe Acrobat per tutti gli utenti, seguire questa procedura:

1. Nell'interfaccia di amministrazione di Teams passare a **App di Teams** > [**Criteri di configurazione**](https://admin.teams.microsoft.com/policies/app-setup).

1. Nella scheda **Gestisci criteri** selezionare **Globale (impostazione predefinita a livello di organizzazione)**, quindi selezionare **Modifica**.

   :::image type="content" source="media/setup-policies.png" alt-text="Screenshot dei criteri di configurazione dell'app di Adobe Acrobat nell'interfaccia di amministrazione di Teams.":::

1. In App installate selezionare **Aggiungi app**.

1. Cercare in **Adobe Acrobat**, selezionare **Aggiungi** accanto al nome dell'app, quindi selezionare **Aggiungi**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Screenshot che mostra come aggiungere l'app di Adobe Acrobat per tutti gli utenti." lightbox="media/add-adobe-acrobat-app.png":::

1. Selezionare **Salva**.

Dopo aver selezionato Salva, Teams utilizza Adobe Acrobat app come gestore predefinito per i file PDF.

Se si desidera autorizzare selettivamente l'applicazione di Adobe Acrobat per alcuni utenti o per un gruppo, è possibile assegnare un[criterio di autorizzazione app personalizzato](teams-app-permission-policies.md).

Conoscere le informazioni seguenti su tale funzionalità:

* Dopo la configurazione del criterio, in genere sono necessarie [alcune ore](teams-app-setup-policies.md) affinché l'app sia disponibile per gli utenti.
* La visualizzazione dei file PDF aggiunti nei canali come scheda e la visualizzazione dei file PDF nell'app Assegnazioni continua a essere basata sull'esperienza nativa di Teams.
* Adobe Acrobat come visualizzatore PDF predefinito in Teams funziona solo su client desktop e Web. Non è supportato nel client per dispositivi mobili.
* Gli utenti devono disporre di un piano Adobe Acrobat per poter usare gli strumenti premium come Esporta PDF, Organizza pagine, Combina file, Comprimi PDF e Proteggi PDF.
* Per disinstallare l'app, gli utenti finali possono rimuoverla dal client Teams. L'amministratore può rimuovere l'app di Adobe Acrobat tramite i criteri di configurazione.
* Se si blocca l'applicazione Adobe Acrobat, rimuoverla dal criterio di configurazione. Assicura che l'esperienza dell’utente finale torni a all’uso del visualizzatore nativo di file PDF.
* Dal client desktop di Teams, se si verificano problemi durante l'accesso all'app di Adobe Acrobat, usare Teams nel browser per accedere.
