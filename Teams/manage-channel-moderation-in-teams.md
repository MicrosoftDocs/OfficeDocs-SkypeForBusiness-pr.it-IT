---
title: Configurare e gestire la moderazione dei canali
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come configurare canali per la moderazione in Microsoft Teams, inclusa la procedura per aggiungere membri del team come moderatori di canale.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822896"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurare e gestire la moderazione dei canali in Microsoft Teams

In Microsoft Teams, i proprietari dei team possono attivare la moderazione per un canale standard per controllare chi può avviare nuovi post e rispondere ai post in quel canale.

I proprietari del team possono anche aggiungere membri del team come moderatori. Un proprietario del team potrebbe non avere le competenze in materia a livello di canale per supportare al meglio la moderazione dei canali. Consentendo a specifici membri del team di moderare un canale, la responsabilità di gestire i contenuti e il contesto all'interno di un canale è condivisa tra i proprietari del team e i moderatori di canale. Ad esempio, un proprietario del team può aggiungere proprietari aziendali o proprietari di contenuti come moderatori, il che consente di controllare la condivisione delle informazioni in quel canale.

> [!NOTE]
> La moderazione dei canali è disponibile per i canali standard. Non è disponibile per il canale Generale o per i canali privati.

## <a name="what-can-a-channel-moderator-do"></a>Cosa può fare un moderatore di canale?

I moderatori dei canali possono:

- Avvia nuovi post nel canale. Quando la moderazione è attivata per un canale, solo i moderatori possono iniziare nuovi post in quel canale.
- Aggiungere e rimuovere membri del team come moderatori di un canale. Tenere presente che, per impostazione predefinita, i proprietari dei team sono moderatori di canale e non possono essere rimossi.
- Controlla se i membri del team possono rispondere ai messaggi del canale esistenti e se bot e connettori possono inviare messaggi del canale.

## <a name="scenarios"></a>Scenari

Ecco alcuni esempi di come l'organizzazione può usare la moderazione dei canali in Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Usare un canale come canale di annuncio

Il team Marketing usa un canale specifico per condividere gli annunci di progetto e i risultati finali principali. A volte i membri del team pubblicano contenuti nel canale che appartengono in modo più appropriato ad altri canali. Il proprietario del team vuole limitare la condivisione di informazioni nel canale solo agli annunci, in modo che i membri del team possano usare quel canale per essere sempre al corrente delle cose importanti.

In questo scenario, il proprietario del team aggiunge i lead di marketing come moderatori in modo che possano pubblicare annunci nel canale e disattivare la possibilità per i membri del team di rispondere ai messaggi in quel canale.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Usare un canale per le discussioni di classe in Teams for Education

In Teams for Education, un insegnante di scienze vuole usare un canale per coinvolgere gli studenti in discussioni mirate su specifici argomenti della classe.

In questo scenario, l'insegnante consente agli assistenti didattici di moderare il canale. Gli assistenti didattici potranno quindi creare nuovi post per avviare e avviare discussioni con gli studenti.

## <a name="manage-channel-moderation"></a>Gestire la moderazione dei canali

In Teams, vai al canale, fai clic **su Altre opzioni...**  >  **Gestisci canale.** Da qui puoi attivare e disattivare la moderazione, aggiungere membri del team come moderatori e impostare le preferenze.

La moderazione dei canali è un'impostazione per canale. Non esiste un'impostazione a livello di tenant per la moderazione dei canali. Per richiedere a Microsoft di aggiungere un'impostazione di moderazione del canale a livello di tenant, richiederla in [Teams UserVoice.](https://microsoftteams.uservoice.com/)

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Attivare o disattivare la moderazione per un canale

Per impostazione predefinita, la moderazione è disattivata, il che significa che le consuete impostazioni del canale si applicano ai proprietari del team e ai membri del team. Ad esempio, è possibile limitare i nuovi post solo ai membri del team o consentire a tutti, compresi gli utenti guest, di creare nuovi post.

Per attivare la moderazione per un canale, in **Moderazione canale** fare clic su **Attiva.** Quando la moderazione dei canali è attivata, solo i moderatori possono iniziare nuovi post. 

### <a name="add-or-remove-channel-moderators"></a>Aggiungere o rimuovere moderatori di canale

In **Chi sono i moderatori?** fai clic su **Gestisci,** quindi aggiungi o rimuovi i membri del team come moderatori. I proprietari e i moderatori del team possono aggiungere e rimuovere altri moderatori.  

### <a name="set-team-member-permissions"></a>Impostare le autorizzazioni per i membri del team

In **Autorizzazioni per i membri** del team selezionare le caselle di controllo accanto alle attività da consentire.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica su team e canali in Teams](teams-channels-overview.md)
