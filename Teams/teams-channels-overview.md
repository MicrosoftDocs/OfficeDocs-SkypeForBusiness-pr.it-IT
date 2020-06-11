---
title: Panoramica dei team e i canali in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sui team, canali e app disponibili per una vasta gamma di esigenze, ad esempio amministrazione, pianificazione di eventi, vendite e altro ancora.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a99ec5fdea273c5d9e265e22a77c86ee628da3ab
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690012"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Panoramica dei team e i canali in Microsoft Teams

> [!NOTE]
> Leggere le informazioni seguenti per comprendere le funzionalità di chat, team, canali e app in Teams. Passare poi a [Chat, team, canali e app in Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) per accedere a un elenco di decisioni importanti da adottare per l'implementazione di Teams.

Per iniziare è necessario capire come Microsoft Teams consente a singoli team di organizzarsi e collaborare nei i vari scenari aziendali:

- **Team** sono una combinazione di persone, contenuti e strumenti intorno a vari progetti e obiettivi all'interno di un'organizzazione.

    - I team possono essere configurati come privati e accessibili ai soli utenti invitati.
    - Possono anche essere pubblici e accessibili fino a un massimo di 5000 membri dell'organizzazione.
    
    Un team è progettato per riunire un gruppo di persone che collabora a stretto contatto per portare a termine un attività. I team possono essere dinamici: lavorare sui progetti, ad esempio il lancio di un prodotto, la creazione di una sala operativa digitale, e in maniera stabile nella struttura interna dell'organizzazione, ad esempio i reparti e gli uffici. Le conversazioni, i file e le note presenti nei canali del team sono visibili solo ai membri del team.

- **Canali** sono sezioni dedicate all'interno di un team allo scopo di mantenere le conversazioni organizzate su specifici argomenti, progetti, discipline e su tutto ciò di cui ha bisogno il team. I file che vengono condivisi nel canale (nella scheda File) vengono archiviati in SharePoint. Per altre informazioni, leggere [Modalità di interazione di SharePoint Online e OneDrive for Business con Teams](SharePoint-OneDrive-interact.md).

    - I canali sono luoghi in cui avvengono le conversazioni e dove si svolge il lavoro. Possono essere aperti a tutti i membri del team oppure, se è necessario un pubblico più selezionato, possono essere privati. I canali standard sono destinati alle conversazioni a cui tutti i membri del team possono partecipare, mentre nei [canali privati](private-channels.md) le comunicazioni sono limitate a un ristretto gruppo di persone del team.
    - I vantaggi dei canali sono più evidenti quando si aggiungono app che includono schede, connettori e bot che aumentano la loro utilità per i membri del team. Per altre informazioni, vedere [App, bot e connettori in Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Per informazioni sull'uso dei team e i canali, vedere [Teams e canali](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499).

Questo breve video illustra le procedure consigliate per la creazione di team e canali.

   > [!VIDEO https://www.youtube.com/embed/WkAVgNKn0hs]

<a name="membership-roles-and-settings"></a>Appartenenza, ruoli e impostazioni
------------------------------

**Appartenenza al team**

Quando viene attivato Microsoft Teams per l'intera organizzazione, i proprietari dei team designati possono invitare qualsiasi dipendente con cui collabora a partecipare al team. Microsoft Teams consente ai proprietari dei team di aggiungere facilmente gli utenti dell'organizzazione tramite il nome. In base alle impostazioni dell'organizzazione, è possibile aggiungere ai team utenti guest che appartengono a team esterni all'organizzazione. Vedere [Accesso guest in Microsoft Teams](guest-access.md) per altre informazioni. 

I proprietari del team possono anche creare un team basato su un gruppo Microsoft 365 esistente. Qualsiasi modifica apportata al gruppo verrà sincronizzata automaticamente con Microsoft Teams. La creazione di un team basato su un gruppo Microsoft 365 esistente non solo semplifica il processo di invito e gestione dei membri, ma sincronizza anche i file di gruppo all'interno di Microsoft teams.

**Ruoli all'interno del team**

Esistono due ruoli principali in Microsoft Teams: 

- **Proprietario del team**: la persona che crea il team. I proprietari del team possono assegnare il ruolo di comproprietario del team a qualsiasi membro nel momento in cui viene invitato a partecipare o in qualsiasi momento successivo all'adesione al team. La presenza di più comproprietari consente di condividere le responsabilità relative alla gestione, alle impostazioni e all'appartenenza al team, inclusi gli inviti.
- **Membri del team**: gli utenti che vengono invitati dai proprietari a far parte del proprio team.

Inoltre, se viene configurata la moderazione i proprietari e i membri del team possono assumere le funzioni di moderatore per un canale. I moderatori possono avviare nuovi post nel canale e controllare se i membri del team possono rispondere ai messaggi esistenti nel canale. I proprietari del team possono assegnare i moderatori a un canale. Per impostazione predefinita, i proprietari del team assumono le funzioni di moderatori. I moderatori possono aggiungere o rimuovere altri moderatori all'interno del canale. Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

**Impostazioni del team** 

I proprietari del team possono gestire le impostazioni a livello di team direttamente in Microsoft Teams. Le impostazioni includono la possibilità di aggiungere un'immagine del team, di impostare le autorizzazioni ai membri del team per la creazione di canali standard e [canali privati](private-channels.md), l'aggiunta di schede e connettori, della funzionalità di @ menzione per l'intero team o canale e l'utilizzo di GIF, adesivi e meme.

Richiede tre minuti la visione del video seguente con la guida per i proprietari dei team:

   > [!VIDEO https://www.youtube.com/embed/kalV4dG-oFo]

Se si è un amministratore di Microsoft teams in Microsoft 365 o Office 365, è possibile accedere a impostazioni a livello di sistema nell'interfaccia di amministrazione di Microsoft teams. Queste impostazioni possono influire sulle opzioni e le impostazioni predefinite che i proprietari visualizzano nelle impostazioni del team. Ad esempio, è possibile abilitare un canale predefinito "Generale", per gli annunci a livello di team, le discussioni e le risorse che verranno visualizzate nei team.

Per impostazione predefinita, tutti gli utenti dispongono delle autorizzazioni per creare un team in Microsoft Teams. Per modificare questa impostazione, vedere [Assegnare ruoli e autorizzazioni in Teams](assign-roles-permissions.md). Gli utenti di un gruppo Microsoft 365 esistente possono anche migliorare le autorizzazioni con la funzionalità teams.

Un'attività essenziale della pianificazione iniziale per incoraggiare gli utenti a collaborare con Microsoft Teams consiste nell'aiutare gli utenti a comprendere come Teams può migliorare la collaborazione nella vita quotidiana. Parlare con gli utenti e invitarli a considerare gli scenari aziendali in cui collaborano in modo frammentato. Riunirli in un canale con le schede pertinenti che consentiranno loro di portare a termine le attività. Uno dei casi più significativi di utilizzo di Teams è all'interno dei processi interorganizzativi. 

<a name="example-teams"></a>Team di esempio
--------------

Di seguito sono illustrati alcuni esempi di come i vari tipi di utenti potrebbero affrontare la configurazione dei team, dei canali e delle app (schede/connettori/bot). Questo potrebbe essere un utile spunto per avviare una conversazione su Microsoft Teams con la community di utenti. Se si pensa a come implementare Microsoft Teams nell'organizzazione, tenere presente che è possibile offrire indicazioni su come strutturare il team. Tuttavia, gli utenti hanno il controllo della propria organizzazione. Questi sono solo esempi che consentono ai team di considerare le varie possibilità.

Microsoft Teams è ideale per eliminare le barriere aziendali e favorire i team interfunzionali, pertanto è consigliabile invitare gli utenti a pensare alla funzionalità dei team anziché ai confini dell'organizzazione.

|Tipi di team  |Canali potenziali  |App (schede ![Icona che raffigura una cartella con una scheda](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Connettori ![Icona che raffigura i blocchi di connessione](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bot ![Icona che raffigura un piccolo robot](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Vendite     |Riunione annuale di vendita<br></br> Revisione aziendale trimestrale<br></br> Revisione della pipeline di vendita mensile<br></br> Playbook della vendite |Power BI<br></br>Trello<br></br>CRM<br></br>Bot di riepilogo         |
|Pubbliche relazioni     |Comunicati stampa<br></br>Novità e aggiornamenti<br></br>Verifica dei fatti         |Feed RSS<br></br>Twitter         |
|Pianificazione eventi     |Marketing<br></br>Logistica e pianificazione<br></br>Sede<br></br>Budget         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|Marketing/Commercializzazione   |Ricerca di mercato<br></br>Pilastri della messaggistica<br></br>Piano per le comunicazioni<br></br>Distinta materiali di marketing        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Operazioni tecniche    |Gestione degli eventi imprevisti<br></br>Pianificazione sprint<br></br>Elementi di lavoro<br></br>Infrastruttura e operazioni         |Servizi del team<br></br>Jira<br></br>AzureBot         |
|Team di prodotto      |Strategia<br></br>Marketing<br></br>Vendite<br></br>Operazioni<br></br>Informazioni dettagliate<br></br>Servizi e supporto         |Power BI<br></br>Servizi del team         |
|Finanze    |Anno fiscale in corso<br></br>Pianificazione AF<br></br>Previsione<br></br>Crediti<br></br>Debiti         |Power BI<br></br>Google Analytics         |
|Logistica     |Operazioni di magazzino<br></br>Manutenzione dei veicoli<br></br>Elenchi dei conducenti         |Servizio meteo<br></br>Spostamenti/interruzioni strade<br></br>Programmazione<br></br>Tubot<br></br>Bot UPS         |
|Risorse umane     |Gestione dei talenti<br></br>Selezione del personale<br></br>Pianificazione della verifica delle prestazioni<br></br>Motivazione         |Strumenti della risorse umane<br></br>Siti di pubblicazione di lavoro esterno<br></br>Growbot         |
|Attività interorganizzative <br></br>Team virtuale |Strategia<br></br>Sviluppo del personale<br></br>Concorrenza e ricerca         |Power BI<br></br>Microsoft Stream         |

È possibile creare team in linea con la struttura organizzativa. Si tratta dell'approccio più adatto per i responsabili che desiderano aumentare la motivazione, effettuare valutazioni specifiche del team, rendere trasparenti i processi di onboarding dei dipendenti, discutere dei piani del personale e aumentare la visibilità tra le diverse risorse.  

![Diagramma gerarchico dei team e i canali organizzati in Microsoft Teams.](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Team a livello di organizzazione

Se l'organizzazione non ha più di 5.000 utenti, è possibile creare un team a livello di organizzazione. I team a livello di organizzazione forniscono agli utenti una modalità automatica di partecipazione a un singolo team di collaborazione. Per altre informazioni, incluse le procedure consigliate per la creazione e la gestione di un team a livello di organizzazione, vedere [Creare un team a livello di organizzazione in Microsoft Teams](create-an-org-wide-team.md).
