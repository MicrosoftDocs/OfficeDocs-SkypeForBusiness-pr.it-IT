---
title: Usare i team a livello di organizzazione in Microsoft Teams per aiutare tutti a collaborare
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e gestire un team a livello di organizzazione in Teams per consentire a tutti gli utenti di un'organizzazione di piccole e medie dimensioni di collaborare.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- EngageScoreOct2022
- ContentEnagagementFY23
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.openlocfilehash: 5acc918c4fbe3994a93020e7b4b09db4ab1671f3
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198918"
---
# <a name="use-organization-wide-teams-in-microsoft-teams-to-help-everyone-collaborate"></a>Usare i team a livello di organizzazione in Microsoft Teams per aiutare tutti a collaborare

Gli amministratori globali possono creare team a livello di organizzazione che consentono a tutti gli utenti di un'organizzazione di piccole e medie dimensioni di far parte di un singolo team collaborativo. I team a livello di organizzazione includono automaticamente tutti gli utenti dell'organizzazione e mantengono l'appartenenza aggiornata quando gli utenti si aggiungono e lasciano l'organizzazione.

Se l'organizzazione è una novità di Teams e non ha più di 5.000 utenti, viene creato automaticamente un team a livello di organizzazione. I team a livello di organizzazione sono limitati alle organizzazioni con non più di 10.000 utenti. È possibile avere fino a cinque team a livello di organizzazione. 

## <a name="create-an-organization-wide-team"></a>Creare un team a livello di organizzazione

Esistono due modi per creare un team a livello di organizzazione:

- Convertire un team esistente in un team a livello di organizzazione. Passare al nome del team e fare clic su **Altre opzioni** > **Modifica team**.

- [Creare un nuovo team da zero](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) e scegliere l'opzione **A livello di organizzazione** .

    ![Screenshot dell'opzione a livello di organizzazione per creare un team a livello di organizzazione.](media/create-org-wide-team.png "Screenshot dell'opzione a livello di organizzazione per creare un team a livello di organizzazione")

## <a name="types-of-users-in-an-organization-wide-team"></a>Tipi di utenti in un team a livello di organizzazione

Quando viene creato un team a livello di organizzazione, tutti gli amministratori globali e gli amministratori di Teams vengono aggiunti come proprietari del team e tutti gli utenti attivi vengono aggiunti come membri del team. I membri del team non possono lasciare un team a livello di organizzazione, ma i proprietari del team possono aggiungere o rimuovere manualmente gli utenti, se necessario. Quando Teams aggiunge o rimuove automaticamente qualcuno, viene inviata una notifica al canale Generale.

Anche gli utenti senza licenza vengono aggiunti al team. La prima volta che un utente senza licenza accede a Teams, gli viene assegnata una licenza di Microsoft Teams Exploratory. Per altre informazioni sulla licenza esplorativa, vedere [Gestire la licenza esplorativa di Microsoft Teams](teams-exploratory.md).

I tipi di account seguenti non verranno aggiunti al team a livello di organizzazione:

- Account a cui è impedito l'accesso
- Utenti guest
- Account di risorse o servizi (ad esempio, account associati a operatori automatici e code di chiamata)
- Account di sale o attrezzature
- Account basati su una cassetta postale condivisa

> [!NOTE]
> Le sale che non fanno parte di un elenco di sale, apparecchiature e account di risorse potrebbero essere aggiunte o sincronizzate con il team a livello di organizzazione. I proprietari del team possono rimuovere facilmente questi account dal team.

## <a name="options-to-get-the-most-out-of-an-organization-wide-team"></a>Opzioni per sfruttare al massimo un team a livello di organizzazione

Per ottenere il massimo dal team a livello di organizzazione, è consigliabile che i proprietari dei team esercino le attività seguenti:

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Consentire solo ai proprietari del team di pubblicare post nel canale Generale

Ridurre gli elementi di distrazione facendo pubblicare nel canale Generale solo i proprietari del team.

1. Vai al team, individua il canale Generale e quindi seleziona **... Altre opzioni** > **Gestisci canale**.
2. Nella scheda **Impostazioni canale** fare clic su **Autorizzazioni** e quindi selezionare **Solo i proprietari possono pubblicare messaggi**.

### <a name="turn-off-team-and-team-name-mentions"></a>Disattivare le menzioni @canale e @[nome canale]

Ridurre le @menzioni per evitare di sovraccaricare l'organizzazione.

1. Vai al team e fai clic **su ... Altre opzioni** \> **Gestisci team**.
2. Nella scheda **Impostazioni** fare clic su **@mentions** \> disattivare **Mostra ai membri l'opzione per @team o @[nome team]**.

### <a name="automatically-show-important-channels"></a>Mostrare automaticamente i canali importanti

Mostrare canali importanti per assicurarsi che tutti gli utenti dell'organizzazione partecipino a specifiche conversazioni. Per altre informazioni, vedere [Canali preferiti automaticamente per l'intero team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="set-up-channel-moderation"></a>Configurare la moderazione dei canali

Valutare l'opportunità di configurare la moderazione dei canali e di fornire capacità di moderazione ad alcuni membri del team. Quando è configurata la moderazione, ai proprietari del team vengono concesse automaticamente le funzionalità di moderatore. I moderatori possono:

- Controllare chi può iniziare un nuovo post in un canale
- Aggiungere e rimuovere moderatori
- Controllare se i membri del team possono rispondere ai messaggi del canale esistenti
- Controllare se bot e connettori possono inviare messaggi di canale.

Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Rimuovere gli account non idonei

Anche se i membri non possono lasciare un team a livello di organizzazione, è possibile gestire l'elenco dei membri del team rimuovendo gli account che non appartengono. **Assicurarsi di usare Teams per rimuovere gli utenti dal team a livello di organizzazione**. Se si usa un altro modo per rimuovere un utente, ad esempio il interfaccia di amministrazione di Microsoft 365 o da un gruppo in Outlook, è possibile che l'utente venga aggiunto di nuovo al team a livello di organizzazione.

## <a name="related-topics"></a>Argomenti correlati

Guardare un video su [Come creare un team a livello di organizzazione in Microsoft Teams](https://www.youtube.com/watch?v=x3qGlwwCz_w).
