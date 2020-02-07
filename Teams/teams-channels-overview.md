---
title: Panoramica di team e canali in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sui diversi team, canali e app disponibili per una vasta gamma di requisiti, ad esempio finanza, pianificazione eventi, vendite e altro ancora.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b0a516ae74ea012d8cba4e85509b5b37ee27163
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834886"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Panoramica di team e canali in Microsoft Teams

> [!NOTE]
> Per informazioni su chat, team, canali, & app in teams, vedere la pagina seguente. Quindi, passa a [chat, team, canali, & app in teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) per esaminare un elenco di decisioni importanti per l'implementazione del team.

Iniziamo a pensare a come Microsoft teams consente ai singoli team di organizzare e collaborare in diversi scenari aziendali:

- I **Team** sono una raccolta di persone, contenuti e strumenti che circondano diversi progetti e risultati all'interno di un'organizzazione.

    - I team possono essere creati per essere privati solo per gli utenti invitati.
    - I team possono essere creati anche per essere pubblici e aperti e tutti gli utenti all'interno dell'organizzazione possono partecipare (fino a 5000 membri).
    
    Un team è progettato per riunire un gruppo di persone che lavorano a stretto contatto per ottenere le operazioni. I team possono essere dinamici per il lavoro basato su progetti (ad esempio, l'avvio di un prodotto, la creazione di una sala di guerra digitale), così come in corso, per riflettere la struttura interna dell'organizzazione (ad esempio, i reparti e le posizioni di Office). Le conversazioni, i file e le note nei canali del team sono visibili solo ai membri del team.

- I **canali** sono sezioni dedicate all'interno di un team per organizzare le conversazioni in base a specifici argomenti, progetti, discipline,-qualsiasi cosa funzioni per il team. I file condivisi in un canale (nella scheda file) sono archiviati in SharePoint. Per altre informazioni, vedere [come interagire con i team in SharePoint Online e OneDrive for business](SharePoint-OneDrive-interact.md).

    - I canali sono luoghi in cui si verificano le conversazioni e dove il lavoro viene effettivamente eseguito. I canali possono essere aperti a tutti i membri del team oppure, se hai bisogno di un pubblico più selezionato, possono essere privati. I canali standard sono per le conversazioni che tutti i membri di un team possono partecipare e i [canali privati](private-channels.md) limitano la comunicazione a un sottoinsieme di persone in un team.
    - I canali sono più utili quando si estendono le app che includono schede, connettori e bot che aumentano il loro valore per i membri del team. Per altre informazioni, Vedi [app, bot, & connettori in teams](deploy-apps-microsoft-teams-landing-page.md).
    
Per informazioni sull'uso di team e canali, vedere [team e canali](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499).

Per ulteriori informazioni sulle procedure consigliate per la creazione di team e canali, vedere questo breve video.

   > [!VIDEO https://www.youtube.com/embed/WkAVgNKn0hs]

<a name="membership-roles-and-settings"></a>Appartenenza, ruoli e impostazioni
------------------------------

**Appartenenza al team**

Quando Microsoft teams viene attivato per l'intera organizzazione, i proprietari del team designati possono invitare tutti i dipendenti con cui lavorano per partecipare al proprio team. Microsoft teams rende più facile per i proprietari del team di aggiungere persone nell'organizzazione in base al loro nome. A seconda delle impostazioni dell'organizzazione, i clienti che sono membri del team ma al di fuori dell'organizzazione possono essere aggiunti anche ai team. Per altre informazioni, vedere [accesso guest in Microsoft teams](guest-access.md) . 

I proprietari del team possono anche creare un team in base a un gruppo di Office 365 esistente. Tutte le modifiche apportate al gruppo verranno sincronizzate automaticamente con Microsoft teams. La creazione di un team basato su un gruppo di Office 365 esistente non solo semplifica il processo di invito e gestione dei membri, ma sincronizza anche i file di gruppo all'interno di Microsoft teams.

**Ruoli del team**

In Microsoft teams sono presenti due ruoli principali: 

- **Proprietario del team** : la persona che crea il team. I proprietari del team possono conferire a tutti i membri del team un comproprietario quando li invitano al team o in qualsiasi momento dopo l'adesione al team. La presenza di più proprietari di team consente di condividere le responsabilità della gestione delle impostazioni e dell'appartenenza, inclusi gli inviti.
- **Membri del team** : le persone che i proprietari invitano a partecipare al loro team.

Inoltre, se è stata configurata la moderazione, i proprietari e i membri del team possono avere funzionalità di moderatore per un canale. I moderatori possono avviare nuovi post nel canale e controllare se i membri del team possono rispondere ai messaggi del canale esistenti. I proprietari del team possono assegnare moderatori all'interno di un canale. Per impostazione predefinita, i proprietari del team hanno funzionalità di moderatore. I moderatori all'interno di un canale possono aggiungere o rimuovere altri moderatori all'interno del canale. Per altre informazioni, vedere [configurare e gestire la moderazione dei canali in Microsoft teams](manage-channel-moderation-in-teams.md).

**Impostazioni del team** 

I proprietari del team possono gestire le impostazioni a livello di Team direttamente in Microsoft teams. Le impostazioni includono la possibilità di aggiungere un'immagine del team, impostare le autorizzazioni tra i membri del team per la creazione di canali standard e [privati](private-channels.md), l'aggiunta di schede e connettori, @mentioning l'intero team o canale e l'uso di gif, adesivi e meme.

Tre minuti per vedere questo video di go-to-guide per i proprietari del team:

   > [!VIDEO https://www.youtube.com/embed/7XcDSuw6NR4]

Se si è un amministratore di Microsoft teams in Office 365, è possibile accedere alle impostazioni a livello di sistema nell'interfaccia di amministrazione di Microsoft teams. Queste impostazioni possono avere un impatto sulle opzioni e le impostazioni predefinite per i proprietari del team. Ad esempio, puoi abilitare un canale predefinito, "generale", per gli annunci a livello di Team, le discussioni e le risorse, che verranno visualizzati in tutti i team.

Per impostazione predefinita, tutti gli utenti hanno le autorizzazioni per creare un team in Microsoft Teams (per modificarlo, vedere [assegnare ruoli e autorizzazioni in teams](assign-roles-permissions.md). Gli utenti di un gruppo di Office 365 esistente possono anche migliorare le autorizzazioni con la funzionalità teams.

Una delle principali attività di pianificazione per coinvolgere gli utenti con Microsoft teams è aiutare le persone a pensare e capire in che modo i team possono migliorare la collaborazione nelle loro vite quotidiane. Comunicare con gli utenti e aiutarli a selezionare scenari aziendali in cui attualmente collaborano in modi frammentati. Riuniscili in un canale con le linguette pertinenti che li aiuteranno a svolgere il loro lavoro. Uno dei più potenti casi di utilizzo dei team è un processo interorganizzativo. 

<a name="example-teams"></a>Team di esempio
--------------

Di seguito sono riportati alcuni esempi funzionali del modo in cui i diversi tipi di utenti possono avvicinarsi alla configurazione di Team, canali e app (schede/connettori/bot). Questo potrebbe essere utile per dare il via a una conversazione su Microsoft teams con la community degli utenti. Quando si pensa a come implementare Microsoft teams nell'organizzazione, tenere presente che è possibile creare indicazioni su come strutturare i propri team; Tuttavia, gli utenti hanno il controllo del modo in cui possono organizzarsi autonomamente. Questi sono solo esempi per consentire ai team di iniziare a pensare attraverso le possibilità.

Microsoft teams è ideale per suddividere i silo organizzativi e promuovere team interfunzionali, quindi incoraggia gli utenti a pensare ai team funzionali invece che ai confini dell'organizzazione.

|Tipi di Team  |Canali potenziali  |App (schede ![Icona che descrive una cartella con una tabulazione](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Connectors ![Icona che descrive i blocchi di connessione](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bots ![Icona che descrive un piccolo robot](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Vendite     |Riunione di vendita annuale<br></br> Revisione trimestrale aziendale<br></br> Revisione della pipeline di vendita mensile<br></br> PlayBook vendite |Power BI<br></br>Trello<br></br>CRM<br></br>Riepilogo del bot         |
|Relazioni pubbliche     |Comunicati stampa<br></br>Notizie e aggiornamenti<br></br>Controllo dei fatti         |Feed RSS<br></br>Twitter         |
|Pianificazione eventi     |Marketing<br></br>Logistica e pianificazione<br></br>Sede<br></br>Budget         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|Marketing/Vai al mercato   |Ricerche di mercato<br></br>Pilastri della messaggistica<br></br>Piano di comunicazioni<br></br>Fattura di marketing dei materiali        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Operazioni tecniche    |Gestione degli incidenti<br></br>Pianificazione sprint<br></br>Elementi di lavoro<br></br>Infrastruttura e operazioni         |Servizi team<br></br>JIRA<br></br>AzureBot         |
|Team di prodotto      |Strategia<br></br>Marketing<br></br>Vendite<br></br>Operazioni<br></br>Approfondimenti<br></br>Supporto & servizi         |Power BI<br></br>Servizi team         |
|Finanza    |Fiscale corrente<br></br>Pianificazione FY<br></br>Previsione<br></br>Contabilità clienti<br></br>Account da pagare         |Power BI<br></br>Google Analytics         |
|Logistica     |Operazioni warehouse<br></br>Manutenzione del veicolo<br></br>Roster del driver         |Servizio meteo<br></br>Interruzioni di viaggio/strada<br></br>Planner<br></br>Tubot<br></br>UPS bot         |
|HR     |Gestione dei talenti<br></br>Assunzioni<br></br>Pianificazione della revisione delle prestazioni<br></br>Morale         |Strumenti HR<br></br>Siti di registrazione dei processi esterni<br></br>Growbot         |
|Organizzazione trasversale <br></br>Team virtuale |Strategia<br></br>Sviluppo della forza lavoro<br></br>Competere & ricerca         |Power BI<br></br>Microsoft Stream         |

È possibile creare team che si allineano alla struttura organizzativa. Questo è il modo migliore per i leader che vogliono guidare il morale, avere recensioni specifiche del team, chiarire i processi di onboarding dei dipendenti, discutere i piani della forza lavoro e aumentare la visibilità in una forza lavoro diversificata.  

![Diagramma gerarchico di team e canali organizzati in Microsoft teams.](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Team a livello di organizzazione

Se l'organizzazione non ha più di 5.000 utenti, è possibile creare un team a livello di organigramma. I team a livello di organizzazione rappresentano un modo automatico per consentire a tutti gli utenti di una società di partecipare a un singolo team per la collaborazione. Per altre informazioni, incluse le procedure consigliate per la creazione e la gestione di un team a livello di organizzazione, vedere [creare un team a livello di organizzazione in Microsoft teams](create-an-org-wide-team.md).
