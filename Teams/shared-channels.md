---
title: Canali condivisi in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Scopri come utilizzare e gestire i canali condivisi in Microsoft Teams.
ms.openlocfilehash: d45e2f1ea7f6daef8cd2b4a3af57944629d59a8a
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727868"
---
# <a name="shared-channels-in-microsoft-teams"></a>Canali condivisi in Microsoft Teams

I canali condivisi in Microsoft Teams creano spazi di collaborazione dove è possibile invitare persone che non fanno parte del team. Solo gli utenti proprietari o membri del canale condiviso possono accedervi. Anche se gli utenti guest (persone con account guest di Azure Active Directory nell’organizzazione) non possono essere aggiunti a un canale condiviso, è possibile invitare le persone esterne all'organizzazione a partecipare a un canale condiviso usando connessione diretta B2B di Azure AD.

Sarebbe preferibile usare un canale condiviso quando si collabora con un gruppo di persone che sono membri di team diversi. Ad esempio, le persone dei reparti progettazione, vendite e supporto che lavorano su aspetti diversi di uno stesso progetto o prodotto potrebbero collaborare usando un canale condiviso.

Solo i membri dei canali condivisi possono visualizzare e partecipare ai canali condivisi a cui vengono aggiunti. Gli altri membri del team a cui il canale condiviso è collegato non vedranno il canale.

Quando viene creato un canale condiviso, viene collegato al team padre e non può essere spostato in un altro team. Inoltre, i canali condivisi non possono essere convertiti in canali standard e viceversa.

[Confronta i canali condivisi con altri tipi di canali](/microsoftteams/teams-channels-overview#channel-feature-comparison).

## <a name="getting-started-with-shared-channels"></a>Introduzione ai canali condivisi

Shared channels is enabled by default in Teams. You can choose if people can create shared channels, if they can share them with people outside your organization, and if they can participate in external shared channels by [creating a channel policy](/MicrosoftTeams/teams-policies).

Se si prevede di condividere i canali con persone esterne all'organizzazione, leggere [Pianificare la collaborazione esterna](/microsoft-365/solutions/plan-external-collaboration) per importanti considerazioni sulla pianificazione.

La condivisione di canali con persone esterne all'organizzazione richiede anche la configurazione delle impostazioni di accesso tra tenant in Azure AD. Ogni organizzazione con cui si vogliono condividere i canali deve anch’essa completare questa configurazione. Per informazioni dettagliate, vedere [Collaborare con partecipanti esterni in un canale](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="shared-channel-creation"></a>Creazione di canali condivisi

Solo i proprietari del team possono creare un canale condiviso. I membri del team e gli utenti guest non possono crearli. La possibilità di creare canali condivisi può essere gestita a livello di organizzazione. Usare i [criteri](teams-policies.md) per controllare quali utenti dell'organizzazione sono autorizzati a creare canali condivisi.

La persona che crea un canale condiviso è il proprietario del canale condiviso e solo il proprietario del canale condiviso può aggiungere o rimuovere direttamente le persone da quest’ultimo. (Volendo, è possibile aggiungere più proprietari). Il proprietario di un canale condiviso può aggiungere qualsiasi utente dell'organizzazione al canale condiviso che ha creato. I membri di un canale condiviso dispongono di uno spazio di conversazione sicuro e, quando vengono aggiunti nuovi membri, possono visualizzare tutte le conversazioni del canale condiviso (anche quelle precedenti).

I proprietari del team possono visualizzare i nomi di tutti i canali condivisi nel loro team ed eliminare qualsiasi canale condiviso nel team. I proprietari del team non possono visualizzare i file in un canale condiviso o le conversazioni e l'elenco dei membri di un canale condiviso, a meno che non siano membri di tale canale condiviso.

I membri del team possono visualizzare solo i canali condivisi a cui sono stati aggiunti.

La clonazione di un team non clona i canali condivisi associati.

## <a name="shared-channel-deletion"></a>Eliminazione del canale condiviso

Il canale condiviso eliminato può essere ripristinato entro 30 giorni dall'eliminazione. Quando viene ripristinato un canale condiviso eliminato, verranno ripristinate anche tutte le appartenenze precedenti (condivisione di singoli utenti e team).

I team eliminati possono essere ripristinati entro 30 giorni dall'eliminazione. Quando un team viene eliminato, vengono eliminati anche tutti i canali condivisi. Quando un team eliminato viene ripristinato, vengono ripristinati anche tutti i canali condivisi con tutte le relazioni di condivisione.

Quando un team viene archiviato, la condivisione individuale rimane intatta, ma la condivisione con team diversi dal team padre viene rimossa. Quando viene annullata l’archiviazione del team archiviato, tutti i canali condivisi vengono ripristinati con la sola condivisione individuale.

## <a name="adding-and-removing-owners-and-members"></a>Aggiunta e rimozione di proprietari e membri

Il proprietario di un canale condiviso non può essere rimosso tramite il client di Teams se è l'ultimo proprietario di uno o più canali condivisi.

Se l'ultimo proprietario del canale condiviso lascia l'organizzazione o se viene rimosso dal gruppo di Microsoft 365 associato al team, un membro del canale condiviso dell'organizzazione viene automaticamente promosso come proprietario del canale condiviso. Se non ci sono membri dell'organizzazione da promuovere, il canale condiviso rimarrà senza proprietario. Un amministratore di Teams dovrà assegnare manualmente il proprietario di un canale. È consigliabile aggiungere più proprietari per evitare questa situazione.

I guest, inclusi quelli convertiti in membri (nella proprietà del tipo di utente) non possono essere aggiunti a un canale condiviso.

> [!NOTE]
> I partecipanti esterni devono essere aggiunti usando il proprio UPN, invece del loro indirizzo di posta elettronica, se i due non corrispondono in Azure Active Directory.

## <a name="channel-owner-settings"></a>Impostazioni del proprietario del canale

Ogni canale condiviso ha le proprie impostazioni che possono essere gestite dal proprietario del canale, tra cui la possibilità di aggiungere e rimuovere membri, aggiungere schede e @menzioni per l'intero canale. Queste impostazioni sono indipendenti dalle impostazioni del team padre. Quando viene creato un canale condiviso, questo eredita le impostazioni del team padre, le quali possono essere modificate in seguito, indipendentemente dalle impostazioni del team padre.

Il proprietario del canale condiviso può fare clic su **Gestisci canale** e quindi usare le schede **membri** e **Impostazioni** per aggiungere o rimuovere membri e modificare le impostazioni.

## <a name="shared-channel-owner-and-member-actions"></a>Azioni del proprietario e dei membri del canale condiviso

La tabella seguente illustra le azioni che i proprietari, i membri e gli utenti guest possono eseguire nei canali condivisi.

|Azione  |Proprietario di un team|Membro di un team|Utente guest di un team|Proprietario del canale condiviso|Membro del canale condiviso|Partecipante esterno del canale condiviso|
|---------|---------|---------|---------|---------|---------|---------|
|Crea canale condiviso|Controllato dall’amministratore|Controllato dall’amministratore e dal proprietario del team|No|N/D|No|No|
|Elimina canale condiviso|Sì|No|No|Sì|No|No|
|Lascia il canale condiviso|N/D|N/D|N/D|Sì, a meno che non sia l'ultimo proprietario|Sì|Sì|
|Modifica canale condiviso|No|N/D|N/D|Sì|No|No|
|Ripristina il canale condiviso eliminato|Sì|No|No|Sì|No|No|
|Aggiungere membri|No|N/D|N/D|Sì|No|No|
|Modificare le impostazioni|No|N/D|N/D|Sì|No|No|
|Gestire schede e app|No|N/D|N/D|Sì, le app devono essere installate per il team|Controllato dal proprietario del canale|No|

## <a name="shared-channel-sharepoint-sites"></a>Siti di SharePoint del canale condiviso

Ogni canale condiviso ha [il proprio sito di SharePoint](/SharePoint/teams-connected-sites). Il sito separato serve a garantire che l'accesso ai file del canale condiviso sia limitato ai soli membri del canale condiviso. Questi siti vengono creati con una raccolta documenti per impostazione predefinita e possono essere facilmente migliorate per ottenere siti completi tramite l'[interfaccia di gestione dei siti](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Ogni sito viene creato nella stessa area geografica del sito del team padre. Questi siti semplificati hanno un ID modello personalizzato, "TEAMCHANNEL#1", per semplificare la gestione con PowerShell e API Graph. 

Un sito di canale condiviso eredita l'etichetta di riservatezza del team padre. Questo vale anche se il canale viene condiviso direttamente con un altro team.

> [!NOTE]
> Solo le persone con autorizzazioni di proprietario o membro nel canale avranno accesso al contenuto nel sito del canale condiviso. Solo le persone con i permessi di proprietario o membro nel canale avranno accesso al contenuto nel sito del canale condiviso.

L'appartenenza al proprietario del sito e ai gruppi di membri viene mantenuta sincronizzata con l'appartenenza al canale condiviso. Le autorizzazioni del sito per un sito del canale condiviso non possono essere gestite in modo indipendente tramite SharePoint. 

Teams gestisce il ciclo di vita del sito del canale condiviso. Se il sito viene cancellato al di fuori di Teams, verrà ripristinato automaticamente entro quattro ore, purché il canale condiviso sia ancora attivo. Se il sito viene eliminato definitivamente, verrà eseguito il provisioning di un nuovo sito per il canale condiviso.

Se viene ripristinato un canale condiviso o un team contenente un canale condiviso, i siti verranno ripristinati con esso. Se un sito del canale condiviso viene ripristinato oltre il periodo di eliminazione temporanea di 30 giorni per il canale condiviso, il sito opererà come sito autonomo.

## <a name="shared-channel-messages"></a>Messaggi del canale condiviso

I messaggi del canale condiviso vengono archiviati in una cassetta postale di sistema dedicata associata al canale condiviso anziché alla cassetta postale di gruppo.

Per altre informazioni sull'esecuzione di una ricerca eDiscovery per i messaggi dei canali condivisi, vedere [Eseguire un'analisi eDiscovery dei contenuti in Microsoft Teams](ediscovery-investigation.md).

## <a name="considerations-around-file-access-in-shared-channels"></a>Considerazioni sull'accesso ai file nei canali condivisi

I file, le cartelle e i blocchi appunti di OneNote in un canale condiviso possono essere condivisi con persone esterne al canale (ma non all'esterno dell'organizzazione) usando la [condivisione di file standard di SharePoint](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c).

Se a un utente viene concesso l'accesso a un file, una cartella o un blocco appunti in un canale condiviso tramite SharePoint, la rimozione dell'utente dal team o dal canale condiviso non rimuoverà l'accesso dell'utente al file, alla cartella o al blocco appunti.

Se un blocco appunti esistente viene aggiunto come scheda a un canale condiviso, l'accesso al canale condiviso non verrà modificato e il blocco appunti manterrà le autorizzazioni esistenti.

## <a name="resources-for-your-users"></a>Risorse per gli utenti

Gli articoli seguenti possono essere utili nel caso di utilizzo dei canali condivisi da parte degli utenti dell'organizzazione.

[Creare un canale condiviso in Teams](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Condividere un canale con altre persone in Teams](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[Condividere un canale con un team](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[Perché usare un canale condiviso rispetto ad altri tipi di canale in Teams?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Guest e canali condivisi in Teams](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Ruoli di proprietario e membro del canale condiviso in Teams](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels"></a>Limiti per i canali condivisi

La tabella seguente descrive il numero massimo di canali e di membri.

|Numero massimo di...|Valore|Note|
|:---------|:----|:----|
|Membri di un team|25.000|Include tutti gli utenti del team e i membri diretti nei canali condivisi.|
|Canali condivisi per team|200|Ospitato e condiviso con il team. (Include i canali eliminati durante il periodo di ripristino di 30 giorni).|
|Teams un canale può essere condiviso con|50|Esclusione del team padre|
|Membri in un canale condiviso|5.000 membri diretti, fino a 50 team. (Ogni team con cui viene condiviso il canale viene conteggiato come un membro ai fini di tale limite.)|Gli aggiornamenti in tempo reale sono disponibili solo per 25.000 utenti alla volta e solo 25.000 utenti appariranno nella lista dei canali.|

Si applicano anche le limitazioni seguenti:

- Solo gli account aziendali o dell'istituto di istruzione di Azure AD sono supportati per i partecipanti esterni.

- I canali condivisi supportano le schede tranne Stream, Planner e Forms.

- Bot, connettori ed estensioni dei messaggi non sono supportati.

- I team a livello di organizzazione non sono supportati per essere aggiunti come membri di un canale condiviso.

- Quando si crea un team da un team esistente, qualsiasi canale condiviso nel team esistente non verrà copiato.

- Le notifiche dai canali condivisi non sono incluse nei messaggi di posta elettronica di attività perse.

- I canali condivisi non sono supportati nei team di classe.

## <a name="supported-apps-in-shared-channels"></a>App supportate nei canali condivisi

Per informazioni su come preparare l'app per i canali condivisi, vedere [Come aprire l'app per la collaborazione tra organizzazioni con Microsoft Teams Connect](https://mybuild.microsoft.com/sessions/4d84d73c-08de-4f56-990b-2a73b2037df1).

Le app seguenti sono supportate per l'uso nei canali condivisi. 

- Attività
- Adobe Acrobat Sign
- Asana
- Calendario Pro
- Chiamate
- Chat
- Codice di Vivani
- Conceptboard
- Excel
- FileBrowser
- File
- Flipgrid
- Freehand by InVision
- HeyTaco
- Jira Cloud
- Kahoot!
- Elenchi
- Lucidchart
- Lumio
- MeisterTask
- MindMeister
- Mindomo
- Miro
- Monday.com
- MURAL
- Nearpod
- OneNote
- PDF
- Pear Deck
- PowerPoint
- Priority Matrix
- Quicklinks
- Quizlet
- Salvato
- Scrum-Poker
- Eseguire una ricerca
- SharePoint
- Pagine SharePoint
- Slido
- Smartsheet
- SurveyMonkey
- Attività in una casella
- Teams Manager
- TeamViewer
- Lavoro in team
- Testportal
- TrackingTime
- Trello
- Vevox
- Visio
- VSTS
- Wakelet
- Web
- Wooclap
- Word
- YouTube
- Zendesk
- Zoho Projects

## <a name="related-topics"></a>Argomenti correlati

[Panoramica della connessione diretta B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurare le impostazioni di accesso tra tenant per la connessione diretta B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Panoramica su team e canali in Teams](teams-channels-overview.md)

[Canali privati in Microsoft Teams](/microsoftteams/private-channels)
