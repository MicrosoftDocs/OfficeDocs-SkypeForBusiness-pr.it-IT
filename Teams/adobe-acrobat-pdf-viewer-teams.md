---
title: Adobe Acrobat come visualizzatore PDF predefinito in Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
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
ms.openlocfilehash: 44721429b81b3f502a76a037add7a880e469add5
ms.sourcegitcommit: ed7d3b12d4bfe48863de873360c2ae90bbb15530
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69194987"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Impostare Adobe Acrobat come visualizzatore PDF predefinito in Microsoft Teams

Gli amministratori possono impostare Adobe Acrobat come app predefinita per visualizzare e modificare i file PDF in Microsoft Teams. Gli utenti finali possono visualizzare, cercare, commentare e annotare i file PDF senza dover sottoscrivere un abbonamento ad Adobe Acrobat o possedere un ID Adobe.

Per configurare l'app di Adobe Acrobat come gestore predefinito per i file PDF nel tenant, completare i passaggi seguenti come prerequisiti:

* [Consentire l'app di Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Installare l'app di Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Consentire l'app di Adobe Acrobat nel tenant

Per configurare l'app come visualizzatore PDF predefinito, assicurarsi di [consentire l'uso di app di terze parti](manage-apps.md#manage-org-wide-app-settings) nel tenant. Seguire quindi le istruzioni seguenti per configurare Adobe Acrobat come app predefinita per i file PDF.

1. Accedere all'interfaccia di amministrazione di Teams e accedere **all'app** > **[Teams Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Cercare l'app di Adobe Acrobat e selezionarla. Apre la pagina dei dettagli dell'app.

1. Seleziona la scheda **Autorizzazioni** e quindi seleziona **Rivedi autorizzazione**.

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

Se si vuole consentire in modo selettivo l'app Adobe Acrobat per alcuni utenti o per un gruppo, usare i [criteri di autorizzazione dell'app](teams-app-permission-policies.md).

## <a name="considerations-and-limitations"></a>Considerazioni e limitazioni

Conoscere le informazioni seguenti su tale funzionalità:

* Dopo aver configurato i criteri, in genere [sono necessarie alcune ore](teams-app-setup-policies.md#considerations-and-limitations) prima che l'app sia disponibile per gli utenti.
* L'esperienza PDF nativa dell'app Teams è disponibile per visualizzare i file PDF aggiunti nei canali come scheda e disponibili nell'app Attività.
* Adobe Acrobat come visualizzatore PDF predefinito in Teams funziona solo su client desktop e Web. Non è supportato nel client per dispositivi mobili.
* Gli utenti devono disporre di un piano Adobe Acrobat per poter usare gli strumenti premium come Esporta PDF, Organizza pagine, Combina file, Comprimi PDF e Proteggi PDF.
* Per disinstallare l'app, gli utenti finali possono rimuovere l'app dal client teams. Amministrazione possibile rimuovere l'app Adobe Acrobat usando i criteri di configurazione.
* Se blocchi l'app Adobe Acrobat, rimuovi l'app dai criteri di configurazione. Assicura che l'esperienza dell’utente finale torni a all’uso del visualizzatore nativo di file PDF.
* Se si verificano problemi di accesso all'app Adobe Acrobat nel client desktop di Teams, usare [Teams nel browser](https://teams.microsoft.com/) per accedere.
* Per aggiungere commenti o aggiungere annotazioni ai file PDF, è necessario accedere a un [account Adobe](https://acrobat.adobe.com/us/en/) gratuito.
