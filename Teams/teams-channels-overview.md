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
localization_priority: Normal
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
ms.openlocfilehash: 83b95032e89accca311eb66933a9991d4f0ca195
ms.sourcegitcommit: 28b83243411b54760875e7fd137549d5d2182c7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53252641"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Panoramica dei team e i canali in Microsoft Teams

Per iniziare è necessario capire come Microsoft Teams consente a singoli team di organizzarsi e collaborare nei i vari scenari aziendali:

- **Team** sono una combinazione di persone, contenuti e strumenti intorno a vari progetti e obiettivi all'interno di un'organizzazione.

    - I team possono essere configurati come privati e accessibili ai soli utenti invitati.
    - Teams può anche essere creato per essere pubblico e aperto e chiunque all'interno dell'organizzazione può partecipare (fino a 10.000 membri).
    
    Un team è progettato per riunire un gruppo di persone che collabora a stretto contatto per portare a termine un attività. Teams può essere dinamico per il lavoro basato sul progetto, ad esempio il lancio di un prodotto, la creazione di una sala di spedizione digitale, oltre che continuo, per riflettere la struttura interna dell'organizzazione, ad esempio reparti e sedi di uffici. Le conversazioni, i file e le note presenti nei canali del team sono visibili solo ai membri del team.

- **Canali** sono sezioni dedicate all'interno di un team allo scopo di mantenere le conversazioni organizzate su specifici argomenti, progetti, discipline e su tutto ciò di cui ha bisogno il team. I file che vengono condivisi nel canale (nella scheda File) vengono archiviati in SharePoint. Per altre informazioni, leggere [Modalità di interazione di SharePoint Online e OneDrive for Business con Teams](SharePoint-OneDrive-interact.md).

    - I canali sono luoghi in cui avvengono le conversazioni e dove si svolge il lavoro. Possono essere aperti a tutti i membri del team oppure, se è necessario un pubblico più selezionato, possono essere privati. I canali standard sono destinati alle conversazioni a cui tutti i membri del team possono partecipare, mentre nei [canali privati](private-channels.md) le comunicazioni sono limitate a un ristretto gruppo di persone del team.
    - I vantaggi dei canali sono più evidenti quando si aggiungono app che includono schede, connettori e bot che aumentano la loro utilità per i membri del team. Per altre informazioni, vedere [App, bot e connettori in Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Per informazioni sull'uso dei team e i canali, vedere [Teams e canali](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499).

Questo breve video illustra le procedure consigliate per la creazione di team e canali:

- [Suggerimento tecnico: Indicazioni per la](https://youtu.be/WkAVgNKn0hs) creazione Teams & canali privati inclusi i canali privati in Microsoft Teams (21:08 min)

## <a name="membership-roles-and-settings"></a>Appartenenza, ruoli e impostazioni

**Appartenenza al team**

Quando Teams è attivata per l'intera organizzazione, i proprietari del team possono invitare chiunque all'interno dell'organizzazione con cui lavora per unirsi al team. Teams consente ai proprietari del team di aggiungere facilmente persone all'interno dell'organizzazione in base al nome. A seconda delle impostazioni dell'organizzazione, le persone esterne all'organizzazione possono essere aggiunte ai team come guest. Vedere [Accesso guest in Microsoft Teams](guest-access.md) per altre informazioni. 

I proprietari del team possono anche creare un team in base a un gruppo Microsoft 365 team. Tutte le modifiche apportate all'appartenenza al gruppo verranno sincronizzate Teams automaticamente.

**Ruoli all'interno del team**

Esistono due ruoli principali in Teams: 

- **Proprietario del team**: la persona che crea il team. I proprietari del team possono assegnare il ruolo di comproprietario del team a qualsiasi membro nel momento in cui viene invitato a partecipare o in qualsiasi momento successivo all'adesione al team. La presenza di più comproprietari consente di condividere le responsabilità relative alla gestione, alle impostazioni e all'appartenenza al team, inclusi gli inviti.
- **Membri del team**: gli utenti che vengono invitati dai proprietari a far parte del proprio team.

Inoltre, se viene configurata la moderazione i proprietari e i membri del team possono assumere le funzioni di moderatore per un canale. I moderatori possono avviare nuovi post nel canale e controllare se i membri del team possono rispondere ai messaggi esistenti nel canale. I proprietari del team possono assegnare i moderatori a un canale. Per impostazione predefinita, i proprietari del team assumono le funzioni di moderatori. I moderatori possono aggiungere o rimuovere altri moderatori all'interno del canale. Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

> [!NOTE]
> Quando si aggiunge un proprietario del team, vengono aggiunti anche come membri, tranne quando il team viene creato nell'interfaccia di amministrazione di Teams o quando un team viene aggiunto a un gruppo di Microsoft 365 nuovo o esistente.

**Impostazioni del team** 

I proprietari dei team possono gestire le impostazioni a livello di team direttamente Teams. Le impostazioni includono la possibilità di aggiungere un'immagine del team, di impostare le autorizzazioni ai membri del team per la creazione di canali standard e [canali privati](private-channels.md), l'aggiunta di schede e connettori, della funzionalità di @ menzione per l'intero team o canale e l'utilizzo di GIF, adesivi e meme.

Se si è un amministratore Teams in Microsoft 365, si ha accesso alle impostazioni a livello di sistema nell'interfaccia Teams di amministrazione. Queste impostazioni possono influire sulle opzioni e le impostazioni predefinite che i proprietari visualizzano nelle impostazioni del team. Ad esempio, è possibile abilitare un canale predefinito "Generale", per gli annunci a livello di team, le discussioni e le risorse che verranno visualizzate nei team.

Per impostazione predefinita, tutti gli utenti hanno le autorizzazioni per creare un team. Per modificare questa impostazione, vedere [Assegnare ruoli](assign-roles-permissions.md)e autorizzazioni in Teams .

Una delle principali attività di pianificazione iniziale per coinvolgere gli utenti con Teams è aiutare le persone a pensare e a capire in che modo Teams può migliorare la collaborazione nella vita quotidiana. Parlare con gli utenti e invitarli a considerare gli scenari aziendali in cui collaborano in modo frammentato. Riunirli in un canale con le schede pertinenti che consentiranno loro di portare a termine le attività. Uno dei casi più significativi di utilizzo di Teams è all'interno dei processi interorganizzativi. 

## <a name="example-teams"></a>Team di esempio

Di seguito sono illustrati alcuni esempi di come i vari tipi di utenti potrebbero affrontare la configurazione dei team, dei canali e delle app (schede/connettori/bot). Questo può essere utile per avviare una conversazione su Teams con la community degli utenti. Quando si pensa a come implementare Teams all'interno dell'organizzazione, tenere presente che è possibile fornire indicazioni su come strutturare i team. Tuttavia, gli utenti hanno il controllo del modo in cui possono organizzarsi autonomamente. Questi sono solo esempi che consentono ai team di considerare le varie possibilità.

Teams è ideale per abbattere i silos dell'organizzazione e promuovere team interfunzionale, quindi incoraggiare gli utenti a pensare ai team funzionali invece che ai limiti dell'organizzazione.

|Tipi di team  |Canali potenziali  |App (schede ![Icona che raffigura una cartella con una scheda](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Connettori ![Icona che raffigura i blocchi di connessione](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bot ![Icona che raffigura un piccolo robot](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Vendite     |Riunione annuale di vendita<br></br> Revisione aziendale trimestrale<br></br> Revisione della pipeline di vendita mensile<br></br> Playbook della vendite |Power BI<br></br>Trello<br></br>CRM<br></br>Bot di riepilogo         |
|Pubbliche relazioni     |Comunicati stampa<br></br>Novità e aggiornamenti<br></br>Verifica dei fatti         |Feed RSS<br></br>Twitter         |
|Pianificazione eventi     |Marketing<br></br>Logistica e pianificazione<br></br>Sede<br></br>Budget         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|Marketing/Commercializzazione   |Ricerca di mercato<br></br>Pilastri della messaggistica<br></br>Piano per le comunicazioni<br></br>Distinta materiali di marketing        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Operazioni tecniche    |Gestione degli eventi imprevisti<br></br>Pianificazione sprint<br></br>Elementi di lavoro<br></br>Infrastruttura e operazioni         |Servizi del team<br></br>Jira<br></br>AzureBot         |
|Team di prodotto      |Strategia<br></br>Marketing<br></br>Vendite<br></br>Operazioni<br></br>Informazioni dettagliate<br></br>Servizi e supporto         |Power BI<br></br>Servizi del team         |
|Finanze    |Anno fiscale in corso<br></br>Pianificazione AF<br></br>Previsione<br></br>Crediti<br></br>Debiti         |Power BI<br></br>Google Analytics         |
|Logistica     |Operazioni di magazzino<br></br>Manutenzione dei veicoli<br></br>Elenchi dei conducenti         |Servizio meteo<br></br>Spostamenti/interruzioni strade<br></br>Programmazione<br></br>Bot UPS         |
|Risorse umane     |Gestione dei talenti<br></br>Selezione del personale<br></br>Pianificazione della verifica delle prestazioni<br></br>Motivazione         |Strumenti della risorse umane<br></br>Siti di pubblicazione di lavoro esterno<br></br>Growbot         |
|Attività interorganizzative <br></br>Team virtuale |Strategia<br></br>Sviluppo del personale<br></br>Concorrenza e ricerca         |Power BI<br></br>Microsoft Stream         |

È possibile creare team in linea con la struttura organizzativa. Si tratta dell'approccio più adatto per i responsabili che desiderano aumentare la motivazione, effettuare valutazioni specifiche del team, rendere trasparenti i processi di onboarding dei dipendenti, discutere dei piani del personale e aumentare la visibilità tra le diverse risorse.  

![Diagramma gerarchico dei team e i canali organizzati in Microsoft Teams.](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Team a livello di organizzazione

Se l'organizzazione non ha più di 5.000 utenti, è possibile creare un team a livello di organizzazione. I team a livello di organizzazione forniscono agli utenti una modalità automatica di partecipazione a un singolo team di collaborazione. Per altre informazioni, incluse le procedure consigliate per la creazione e la gestione di un team a livello di organizzazione, vedere [Creare un team a livello di organizzazione in Microsoft Teams](create-an-org-wide-team.md).

## <a name="next-steps"></a>Passaggi successivi

Leggi [Chat, team, canali, & app in](deploy-chat-teams-channels-microsoft-teams-landing-page.md) Teams per visualizzare un elenco delle decisioni importanti per l'implementazione Teams utenti.
