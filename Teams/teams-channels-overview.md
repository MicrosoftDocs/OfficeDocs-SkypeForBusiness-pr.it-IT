---
title: Panoramica dei team e i canali in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sui team, canali e app disponibili per una vasta gamma di esigenze, ad esempio amministrazione, pianificazione di eventi, vendite e altro ancora.
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97af2abe8542a885f8a0056ed90f2a61330ba8a0
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711930"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Panoramica dei team e i canali in Microsoft Teams

Per iniziare è necessario capire come Microsoft Teams consente a singoli team di organizzarsi e collaborare nei i vari scenari aziendali:

- **Team** sono una combinazione di persone, contenuti e strumenti intorno a vari progetti e obiettivi all'interno di un'organizzazione.

    - I team possono essere configurati come privati e accessibili ai soli utenti invitati.
    - I team possono anche essere creati per essere pubblici e aperti e chiunque all'interno dell'organizzazione può partecipare (fino a 10.000 membri).
    
    Un team è progettato per riunire un gruppo di persone che collabora a stretto contatto al fine di portare a termine un'attività. I team possono essere dinamici per il lavoro basato su progetti (ad esempio, il lancio di un prodotto, la creazione di un centro operazioni digitali), nonché in corso, per riflettere la struttura interna dell'organizzazione (ad esempio, reparti e sedi degli uffici). Le conversazioni, i file e le note presenti nei canali del team sono visibili solo ai membri del team.

- **Canali** sono sezioni dedicate all'interno di un team allo scopo di mantenere le conversazioni organizzate su specifici argomenti, progetti, discipline e su tutto ciò di cui ha bisogno il team. I file che vengono condivisi nel canale (nella scheda File) vengono archiviati in SharePoint. Per altre informazioni, leggere [Modalità di interazione di SharePoint Online e OneDrive for Business con Teams](SharePoint-OneDrive-interact.md).

    - I canali sono luoghi in cui avvengono le conversazioni e dove si svolge il lavoro. I canali possono essere aperti a tutti i membri del team (canali standard), ai membri del team selezionati ([canali privati](private-channels.md)) o alle persone selezionate sia all'interno che all'esterno del team ([canali condivisi](shared-channels.md)).
    - I canali sono particolarmente utili se estesi con app che includono schede, connettori e bot che aumentano il loro valore per i membri del team. Per altre informazioni, vedere [App, bot e connettori in Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Per informazioni sull'uso dei team e i canali, vedere [Teams e canali](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499).

Per informazioni sui limiti associati all'uso di Teams, vedere [Limiti e specifiche per Microsoft Teams](/microsoftteams/limits-specifications-teams).

## <a name="membership-roles-and-settings"></a>Appartenenza, ruoli e impostazioni

**Appartenenza al team**

Quando Teams è attivato per l'intera organizzazione, i proprietari del team possono invitare chiunque nell'organizzazione con cui collaborano a unirsi al proprio team. Teams consente ai proprietari dei team di aggiungere facilmente gli utenti dell'organizzazione tramite il nome. A seconda delle impostazioni dell'organizzazione, le persone esterne all'organizzazione possono essere aggiunte ai team come utenti guest o come partecipanti esterni nei canali condivisi. Per altre informazioni, vedere [Accesso guest in Microsoft Teams](guest-access.md). 

I proprietari del team possono anche creare un team basato su un gruppo di Microsoft 365 esistente. Tutte le modifiche apportate all'appartenenza al gruppo verranno sincronizzate automaticamente con Teams.

**Ruoli del team**

Esistono due ruoli principali in Teams: 

- **Proprietario del team**: la persona che crea il team. I proprietari del team possono assegnare il ruolo di comproprietario del team a qualsiasi membro nel momento in cui viene invitato a partecipare o in qualsiasi momento successivo all'adesione al team. La presenza di più comproprietari consente di condividere le responsabilità relative alla gestione, alle impostazioni e all'appartenenza al team, inclusi gli inviti.
- **Membri del team**: gli utenti che vengono invitati dai proprietari a far parte del proprio team.

Inoltre, se viene configurata la moderazione i proprietari e i membri del team possono assumere le funzioni di moderatore per un canale. I moderatori possono avviare nuovi post nel canale e controllare se i membri del team possono rispondere ai messaggi esistenti nel canale. I proprietari del team possono assegnare i moderatori a un canale. Per impostazione predefinita, i proprietari del team assumono le funzioni di moderatori. I moderatori possono aggiungere o rimuovere altri moderatori all'interno del canale. Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

> [!NOTE]
> Quando si aggiunge un proprietario del team, questo viene aggiunto anche come membro, tranne quando il team viene creato nell'Interfaccia di amministrazione di Teams o quando un team viene aggiunto a un gruppo di Microsoft 365 nuovo o esistente.

**Impostazioni del team** 

I proprietari del team possono gestire le impostazioni a livello di team direttamente in Teams. Le impostazioni includono la possibilità di aggiungere un'immagine del team, impostare le autorizzazioni tra i membri del team per la creazione di canali standard, privati e condivisi, l'aggiunta di schede e connettori, @mentioning l'intero team o canale e l'utilizzo di GIF, adesivi e meme.

Gli amministratori di Teams in Microsoft 365 hanno accesso alle impostazioni a livello di sistema nell'Interfaccia di amministrazione di Teams. Queste impostazioni possono influire sulle opzioni e le impostazioni predefinite che i proprietari visualizzano nelle impostazioni del team. Ad esempio, è possibile abilitare un canale predefinito, "Generale", per annunci, discussioni e risorse a livello di team, che verranno visualizzati in tutti i team.

Per impostazione predefinita, tutti gli utenti hanno le autorizzazioni per creare un team. Per modificare questa impostazione vedere [Assegnare ruoli e autorizzazioni in Teams](assign-roles-permissions.md).

Un'attività essenziale della pianificazione iniziale per incoraggiare gli utenti a collaborare con Teams consiste nell'aiutare gli utenti a comprendere come Teams può migliorare la collaborazione nella vita quotidiana. Parlare con gli utenti e invitarli a considerare gli scenari aziendali in cui collaborano in modo frammentato. Riunirli in un canale con le schede pertinenti che consentiranno loro di portare a termine le attività. Uno dei casi più significativi di utilizzo di Teams è all'interno dei processi interorganizzativi.

> [!NOTE]
> Quando si crea un nuovo team o un canale privato o condiviso in Teams, viene creato automaticamente un sito del team in SharePoint. Per modificare la descrizione o la classificazione del sito per questo sito del team, passare alle [impostazioni in Microsoft Teams](https://support.microsoft.com/office/bf39798f-90d2-44fb-a750-55fa05a56f1d)del canale corrispondente.
>
> Altre informazioni sulla gestione dei [siti dei team connessi a Microsoft Teams](/SharePoint/teams-connected-sites).

## <a name="channel-feature-comparison"></a>Confronto delle funzionalità del canale

La tabella seguente mostra un confronto delle funzionalità di Teams per ogni tipo di canale.

|Funzionalità|Canale standard|Canale privato|Canale condiviso|
|:-------|:---------------|:--------------|:-------------|
|Le persone possono essere aggiunte al canale senza aggiungerle al team.|No|No|Sì|
|L'appartenenza al canale può essere limitata a un sottoinsieme del team.|No|Sì|Sì|
|Il canale può essere condiviso direttamente con altri team.|No|No|Sì|
|Il canale può essere condiviso direttamente con il team padre.|N/D|No|Sì|
|Gli utenti guest possono partecipare al canale.|Sì|Sì|No|
|I partecipanti esterni (B2B Direct Connessione) possono partecipare al canale.|No|No|Sì|
|Ogni canale ha un sito SharePoint dedicato.|No|Sì|Sì|
|Riunioni pianificate|Sì|No|Sì|
|Planner|Sì|No|No|
|Bot, connettori ed estensioni di messaggistica|Sì|No|No|
|Supportata nei team di classe|Sì|Sì|No|
|Tag|Sì|No|No|
|Analytics|Sì|Sì|No|

## <a name="org-wide-teams"></a>Team a livello di organizzazione

Se l'organizzazione non ha più di 10.000 utenti, è possibile creare un team a livello di organizzazione. I team a livello di organizzazione forniscono agli utenti una modalità automatica di partecipazione a un singolo team di collaborazione. Per altre informazioni, incluse le procedure consigliate per la creazione e la gestione di un team a livello di organizzazione, vedere [Creare un team a livello di organizzazione in Microsoft Teams](create-an-org-wide-team.md).

## <a name="next-steps"></a>Passaggi successivi

Per esaminare un elenco delle decisioni importanti da adottare per l'implementazione di Teams, vedere [Chat, team, canali e app in Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).
