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
ms.openlocfilehash: 67be332ee916f30b0341dc3ac03e047558cead0c
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343290"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Impostare Adobe Acrobat come visualizzatore pdf predefinito in Microsoft Teams

Gli amministratori possono impostare Adobe Acrobat come app predefinita per visualizzare e modificare i file PDF in Microsoft Teams. Gli utenti finali possono visualizzare ed eseguire ricerche nei file PDF. Gli utenti possono anche commentare e annotare gratuitamente i file PDF dopo l'accesso.

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

1. Facoltativamente, è possibile consentire SSO con Microsoft Azure Active Directory identità se si dispone di una licenza di Adobe Acrobat. È consigliabile configurare SSO usando le istruzioni in [Configurare l'identità e Single Sign-On](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

Dopo aver completato la configurazione, Teams usa l'app Adobe Acrobat come gestore di file predefinito per i file PDF.

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
* Accedi a un [account Adobe](https://acrobat.adobe.com/us/en/) gratuito per aggiungere commenti o annotazioni sui file PDF. L'app in Teams può offrire funzionalità come l'aggiunta di annotazioni, l'organizzazione, la compressione e la protezione dei file PDF. Per un elenco completo delle funzionalità e dei prerequisiti, vedere [Gestire i file PDF nell'app Teams con Acrobat](https://www.adobe.com/content/dam/dx-dc/pdf/ue/acrobat-msft-teams-feature-comp-ue.pdf).
* Quando si collabora a un documento PDF, questo viene temporaneamente archiviato (fino a 24 ore) nei server Adobe dell'area geografica in cui ci si trova. Questa memoria temporanea è per facilitare l'elaborazione transitoria. I documenti vengono crittografati end-to-end quando vengono trasferiti dal file system locale al server e rimangono crittografati anche sul server. vedi [sicurezza per Acrobat](https://aka.ms/Adobe_Acrobat_Security).
