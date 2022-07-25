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
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002339"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Adobe Acrobat come visualizzatore pdf predefinito in Teams

> [!NOTE]
> Adobe Acrobat come esperienza PDF predefinita in Teams è attualmente disponibile solo in anteprima pubblica. Prima di usare questa caratteristica, [abilitare l'anteprima pubblica](public-preview-doc-updates.md#enable-public-preview) per il tenant. Assicurarsi che gli utenti finali modifichino la versione client di Teams in anteprima pubblica per provare Adobe Acrobat come visualizzatore PDF in Teams.

Gli amministratori possono impostare Adobe Acrobat come app predefinita per visualizzare e modificare i file PDF in Microsoft Teams. Gli utenti finali non hanno bisogno di un abbonamento Adobe Acrobat o di un Adobe ID per visualizzare, cercare, commentare e annotare i file PDF.

## <a name="set-up-adobe-acrobat-app"></a>Configurare l'app Adobe Acrobat

Per configurare Adobe Acrobat come app predefinita per la visualizzazione dei file PDF, attenersi alla seguente procedura:

1. Accedere all'interfaccia di amministrazione di Teams e passare **all'app** >  Teams **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Cercare l'app Adobe Acrobat e selezionare **l'app Adobe Acrobat** .

   > [!NOTE]
   >
   > * Assicurati che lo stato dell'app Adobe Acrobat sia impostato su **Consentito**. Altrimenti, abilita l'interruttore **Consentito** .
   > * Se è presente un'impostazione di amministratore esistente nei criteri di autorizzazione dell'app o nelle impostazioni dell'app a livello di organizzazione che ha bloccato l'app, assicurarsi di consentire l'app nei criteri [di autorizzazione dell'app](teams-app-permission-policies.md) o nelle [impostazioni dell'app a livello di organizzazione](teams-app-permission-policies.md).

1. Nella scheda **Autorizzazioni** selezionare **Rivedi autorizzazione**.

1. Selezionare **Accetta**.

   :::image type="content" source="media/permission-policy.png" alt-text="Screenshot dell'autorizzazione dell'app nell'interfaccia di amministrazione di Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installare l'app Adobe Acrobat per tutti gli utenti

È possibile utilizzare il criterio globale (impostazione predefinita a livello di organizzazione) per assegnare e rendere l'app Adobe Acrobat disponibile per tutti gli utenti. Questo passaggio attiva un segnale in Teams per impostare l'app come gestore di file predefinito per i file PDF. Per assegnare l'app Adobe Acrobat a tutti gli utenti, attenersi alla seguente procedura:

1. Nell'interfaccia di amministrazione di Teams passare a [**Criteri di configurazione**](https://admin.teams.microsoft.com/policies/app-setup) **delle app** >  di Teams.

1. Nella scheda **Gestisci criteri** selezionare **Globale (impostazione predefinita a livello di organizzazione)** e quindi selezionare **Modifica**.

   :::image type="content" source="media/setup-policies.png" alt-text="Screenshot dei criteri di configurazione per l'app Adobe Acrobat nell'interfaccia di amministrazione di Teams.":::

1. In App installate seleziona **Aggiungi app**.

1. Cerca **in Adobe Acrobat**, seleziona **Aggiungi** accanto al nome dell'app e quindi seleziona **Aggiungi**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Screenshot che mostra come aggiungere l'app Adobe Acrobat per tutti gli utenti." lightbox="media/add-adobe-acrobat-app.png":::

1. Selezionare **Salva**.

Dopo aver selezionato Salva, l'app Adobe Acrobat è configurata con Teams per aprire tutti i file PDF nell'app Adobe Acrobat dall'app chat, canale o file.

Se si vuole consentire in modo selettivo l'app Adobe Acrobat per alcuni utenti specifici o per un gruppo, è possibile assegnare criteri di [autorizzazione per le app personalizzate](teams-app-permission-policies.md).

Conoscere le informazioni seguenti su questa funzionalità:

* Dopo aver configurato i criteri, in genere sono necessarie [alcune ore](teams-app-setup-policies.md) prima che l'app sia disponibile per gli utenti.
Dopo aver configurato i criteri, l'app installata sarà disponibile per gli utenti dopo alcune ore.
* La visualizzazione dei file PDF aggiunti nei canali come scheda e la visualizzazione dei file PDF nell'app attività continua a essere basata sull'esperienza nativa di Teams.
* Adobe Acrobat come visualizzatore PDF predefinito in Teams funziona solo su client desktop e Web. Non è supportato nel client per dispositivi mobili.
* Gli utenti hanno bisogno di un piano Adobe Acrobat per usare strumenti premium come Esporta PDF, Organizza pagine, Combina file, Comprimi PDF e Proteggi PDF.

> [!NOTE]
> Dal client desktop di Teams, se si verificano problemi durante l'accesso all'app Adobe Acrobat, è possibile aprire Teams nel browser ed effettuare l'accesso. Si tratta di problemi noti che saranno risolti entro settembre 2022.

## <a name="faqs"></a>Faq

* Come rimuovere l'app Adobe Acrobat dal client teams?
  
  Gli utenti finali possono disinstallare l'app dal client Teams e l'amministratore può rimuovere l'app Adobe Acrobat dai criteri di configurazione.

* Gli amministratori possono bloccare l'app Adobe Acrobat una volta impostata come gestore predefinito?
  
  Sì, ma prima che l'amministratore blocchi l'app, rimuovere i criteri di configurazione per assicurarsi che gli utenti finali vengano ripristinati in modo sicuro nell'esperienza predefinita di Teams.
