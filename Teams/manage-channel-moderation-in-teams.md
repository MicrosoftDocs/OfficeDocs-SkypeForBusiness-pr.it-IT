---
title: Configurare e gestire la moderazione dei canali
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come configurare i canali per la moderazione in Microsoft Teams, incluso come aggiungere membri del team come moderatori dei canali.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52fb88d6371c033713c5b14d96ecf2a9211420b0
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562365"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurare e gestire la moderazione dei canali in Microsoft Teams

In Microsoft Teams, i proprietari del team possono attivare la moderazione per un canale standard per controllare chi può avviare nuovi post e rispondere ai post in quel canale.

I proprietari del team possono anche aggiungere membri del team come moderatori. Il proprietario di un team potrebbe non avere le competenze in materia a livello di canale per supportare al meglio la moderazione del canale. Consentendo a specifici membri del team di moderare un canale, la responsabilità di gestire il contenuto e il contesto all'interno di un canale viene condivisa tra i proprietari del team e i moderatori del canale. Ad esempio, il proprietario di un team può aggiungere proprietari di aziende o proprietari di contenuti come moderatori, per poter controllare la condivisione delle informazioni in quel canale.

> [!NOTE]
> La moderazione del canale è disponibile per i canali standard. Non è disponibile per il canale Generale o per i canali privati o condivisi.

## <a name="what-can-a-channel-moderator-do"></a>Cosa può fare un moderatore di canale?

I moderatori di canale possono:

- Avvia nuovi post nel canale. Quando la moderazione è attivata per un canale, solo i moderatori possono avviare nuovi post in quel canale.
- Aggiungere e rimuovere membri del team come moderatori in un canale. Tenere presente che, per impostazione predefinita, i proprietari dei team sono moderatori di canali e non possono essere rimossi.
- Controllare se i membri del team possono rispondere ai messaggi del canale esistenti e se bot e connettori possono inviare messaggi del canale.

## <a name="scenarios"></a>Scenari

Ecco alcuni esempi di come l'organizzazione può usare la moderazione del canale in Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Usare un canale come canale di annuncio

Il team di marketing usa un canale specifico per condividere gli annunci e i risultati finali principali del progetto. A volte i membri del team pubblicano contenuti nel canale che appartengono in modo più appropriato ad altri canali. Il proprietario del team vuole limitare la condivisione delle informazioni nel canale solo agli annunci, in modo che i membri del team possano usare quel canale per mantenersi aggiornati sugli elementi importanti.

In questo scenario, il proprietario del team aggiunge i lead di marketing come moderatori in modo che possano pubblicare annunci nel canale e impedisce ai membri del team di rispondere ai messaggi in quel canale.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Usare un canale per le discussioni di classe in Teams per l'istruzione

In Teams per l'istruzione, un insegnante di scienze vuole usare un canale per coinvolgere gli studenti in discussioni mirate su argomenti specifici della classe.

In questo scenario, l'insegnante consente ai loro assistenti di insegnare di moderare il canale. Gli assistenti docente possono quindi creare nuovi post per avviare e condurre discussioni con gli studenti.

## <a name="manage-channel-moderation"></a>Gestire la moderazione del canale

In Teams, vai al canale, fai clic su **Altre opzioni ...** >  **Gestisci canale**. Da qui è possibile attivare e disattivare la moderazione, aggiungere membri del team come moderatori e impostare le preferenze.

La moderazione del canale è un'impostazione per canale. Non esiste alcuna impostazione a livello di tenant per la moderazione del canale. Se desideri che aggiungiamo un'impostazione di moderazione del canale a livello di tenant, richiedila nel [portale di Teams Feedback](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![le preferenze per la gestione della moderazione del canale in teams.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Attivare o disattivare la moderazione per un canale

Per impostazione predefinita, la moderazione è disattivata, il che significa che le normali impostazioni del canale si applicano ai proprietari e ai membri del team. Ad esempio, è possibile limitare i nuovi post solo ai membri del team o consentire a tutti, inclusi gli utenti guest, di iniziare nuovi post.

Per attivare la moderazione per un canale, in **Moderazione del canale** fare clic su **Attivato**. Quando la moderazione del canale è attivata, solo i moderatori possono iniziare nuovi post. 

### <a name="add-or-remove-channel-moderators"></a>Aggiungere o rimuovere moderatori di canale

In **Chi sono i moderatori?** fare clic su **Gestisci** e quindi aggiungere o rimuovere membri del team come moderatori. I proprietari del team e i moderatori possono aggiungere e rimuovere altri moderatori.  

### <a name="set-team-member-permissions"></a>Impostare le autorizzazioni per i membri del team

In **Autorizzazioni membri del team** selezionare le caselle di controllo accanto alle attività da consentire.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica su team e canali in Teams](teams-channels-overview.md)
