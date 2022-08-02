---
title: Adobe Acrobat come visualizzatore pdf predefinito in Teams
author: guptaashish
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
ms.openlocfilehash: 913081ee0efc87d66ed304f3de5e9f00b69232fa
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156744"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat come visualizzatore pdf predefinito in Microsoft Teams

> [!NOTE]
> Adobe Acrobat come esperienza PDF predefinita in Microsoft Teams è attualmente disponibile solo in anteprima pubblica. Per usare questa funzionalità, gli amministratori devono [abilitare l'anteprima pubblica](public-preview-doc-updates.md#enable-public-preview) per il proprio tenant e assicurarsi che gli utenti finali cambino la versione client di Teams in anteprima pubblica.

Gli amministratori possono impostare Adobe Acrobat come app predefinita per visualizzare e modificare i file PDF in Microsoft Teams. Gli utenti finali possono visualizzare, cercare, commentare e annotare i file PDF senza un abbonamento Adobe Acrobat o un Adobe ID.

## <a name="set-up-adobe-acrobat-app"></a>Configurare l'app Adobe Acrobat

Prima di configurare l'app, assicurarsi di consentire l'uso delle app nel tenant, di aver consentito in modo specifico l'app Adobe Acrobat e che i criteri di autorizzazione dell'app lo consentano. Per configurare Adobe Acrobat come app predefinita per i file PDF, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e passare **all'app** >  Teams **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Cerca l'app Adobe Acrobat e selezionala.

1. Nella scheda **Autorizzazioni** selezionare **Rivedi autorizzazione**.

   :::image type="content" source="media/permission-policy.png" alt-text="Screenshot dell'autorizzazione dell'app nell'interfaccia di amministrazione di Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Selezionare **Accetta**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installare l'app Adobe Acrobat per tutti gli utenti

Per assegnare e rendere l'app Adobe Acrobat disponibile per tutti gli utenti, attenersi alla seguente procedura:

1. Nell'interfaccia di amministrazione di Teams passare a [**Criteri di configurazione**](https://admin.teams.microsoft.com/policies/app-setup) **delle app** >  di Teams.

1. Nella scheda **Gestisci criteri** selezionare **Globale (impostazione predefinita a livello di organizzazione)** e quindi selezionare **Modifica**.

   :::image type="content" source="media/setup-policies.png" alt-text="Screenshot dei criteri di configurazione per l'app Adobe Acrobat nell'interfaccia di amministrazione di Teams.":::

1. In App installate seleziona **Aggiungi app**.

1. Cerca **in Adobe Acrobat**, seleziona **Aggiungi** accanto al nome dell'app e quindi seleziona **Aggiungi**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Screenshot che mostra come aggiungere l'app Adobe Acrobat per tutti gli utenti." lightbox="media/add-adobe-acrobat-app.png":::

1. Selezionare **Salva**.

Dopo aver selezionato Salva, Teams usa l'app Adobe Acrobat come gestore di file predefinito per i file PDF.

Se si vuole consentire in modo selettivo l'app Adobe Acrobat per alcuni utenti o per un gruppo, è possibile assegnare criteri di [autorizzazione dell'app personalizzati](teams-app-permission-policies.md).

Conoscere le informazioni seguenti su questa funzionalità:

* Dopo aver configurato i criteri, in genere sono necessarie [alcune ore](teams-app-setup-policies.md) prima che l'app sia disponibile per gli utenti.
* Dopo aver configurato i criteri, l'app installata sarà disponibile per gli utenti dopo alcune ore.
* La visualizzazione dei file PDF aggiunti nei canali come scheda e la visualizzazione dei file PDF nell'app Attività continua a essere basata sull'esperienza nativa di Teams.
* Adobe Acrobat come visualizzatore PDF predefinito in Teams funziona solo su client desktop e Web. Non è supportato nel client per dispositivi mobili.
* Gli utenti hanno bisogno di un piano Adobe Acrobat per usare gli strumenti premium come Esporta PDF, Organizza pagine, Combina file, Comprimi PDF e Proteggi PDF.
* Per disinstallare l'app, gli utenti finali possono rimuovere l'app dal client Teams. Amministrazione possibile rimuovere l'app Adobe Acrobat usando i criteri di configurazione.
* Se blocchi l'app Adobe Acrobat, rimuovila dai criteri di configurazione. Garantisce che l'esperienza utente finale venga ripristinata usando il visualizzatore di file PDF nativo.
* Dal client desktop di Teams, se si verificano problemi durante l'accesso all'app Adobe Acrobat, usare Teams nel browser per accedere.
