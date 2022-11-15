---
title: Guida alle operazioni per Microsoft Teams
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Attività necessarie per la gestione dei servizi di Teams, tra cui il monitoraggio dell'integrità dei servizi, la valutazione e la garanzia della qualità e dell'utilizzo della rete.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: be2cea73868bbd6a974242e2a6f8c3d31730e087
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019442"
---
# <a name="operate-my-service"></a>Gestire il servizio

Questo articolo offre una panoramica dei requisiti per il corretto funzionamento dei servizi vocali cloud per l'organizzazione. Usando correttamente i servizi vocali cloud, è possibile essere certi di offrire un'esperienza affidabile e di alta qualità per l'organizzazione.

## <a name="introduction-to-the-operations-guide"></a>Introduzione alla Guida alle operazioni

La Guida alle operazioni offre una panoramica di tutte le attività e le attività necessarie come parte della funzione di gestione dei servizi per Microsoft Teams.

La gestione dei servizi è un argomento generale che riguarda le operazioni quotidiane del servizio Microsoft Teams dopo che è stato distribuito e abilitato per gli utenti. Il servizio Teams comprende Microsoft 365 o Office 365 e i componenti dell'infrastruttura distribuiti in locale (ad esempio, rete).

La nozione di gestione dei servizi non è probabilmente un nuovo concetto per la maggior parte delle organizzazioni. È possibile che siano già stati implementati processi e attività associati ai servizi esistenti. Detto questo, probabilmente è possibile aumentare i processi correnti quando si pianifica la gestione dei servizi oggi per supportare Teams in futuro.

La gestione dei servizi comprende tutte le attività e i processi coinvolti nella gestione end-to-end di Teams. Come accennato in precedenza, alcuni componenti della gestione dei servizi, ovvero l'infrastruttura di cui è parte il servizio microsoft 365 o Office 365, sono responsabilità di Microsoft, mentre il cliente è responsabile per gli utenti della gestione dei vari aspetti di Teams, della rete e degli endpoint forniti.

Le attività in questa guida sono raggruppate in otto categorie, come illustrato nel diagramma seguente. Ognuna di queste categorie verrà espansa nelle sezioni seguenti.

![Diagramma che illustra un elenco di categorie di attività e attività.](media/operate-my-service-image1.png "Diagramma che illustra un elenco di categorie di attività e attività comprese nella gestione dei servizi per Teams. Il diagramma illustra anche che la gestione dei servizi è in gran parte un'attività del cliente.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere come verranno implementate le operazioni per Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Esamina la Guida operativa per intero.</li><li>Implementare una strategia operativa in linea con gli obiettivi dell'organizzazione per garantire la qualità e l'affidabilità dei carichi di lavoro vocali nel cloud.</li><li>Controlla [monitora la qualità delle chiamate](monitor-call-quality-qos.md).</li><li> Implementare una strategia operativa per eseguire regolarmente le recensioni sulla qualità dell'esperienza per assicurarsi che la distribuzione voce cloud funzioni con le funzionalità di picco.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mapping del ruolo operativo

La pianificazione intrapreso per le operazioni durante la fase Divisione è critica, perché le attività operative iniziano quando sono abilitati i primi utenti pilota. Questa guida elenca le attività e le attività che devono essere eseguite su base giornaliera, settimanale, mensile o in base alle esigenze per mantenere una distribuzione di Teams di alta qualità. Questa guida fornisce informazioni e indicazioni su come eseguire queste attività e attività critiche.

Uno dei componenti fondamentali di una distribuzione riuscita è garantire che la pianificazione eseguita all'inizio della fase Division includa la determinazione di chi sarà responsabile dell'esecuzione di attività specifiche. Dopo aver compreso quali attività e attività si applicano alla distribuzione, è necessario comprenderle e seguirle dai gruppi o dai singoli utenti assegnati.

Ogni team identificato deve rivedere e concordare le attività e le responsabilità identificate e iniziare la preparazione. Questo può includere formazione e preparazione, fornire aggiornamenti al piano per il personale o assicurarsi che i provider esterni siano pronti per la consegna.

Le attività e i ruoli definiti in questa guida dovrebbero essere validi nella maggior parte degli scenari, ma ogni distribuzione di Teams è univoca; È quindi possibile usare questa guida come punto di partenza per personalizzare le attività e i ruoli predefiniti in base alle proprie esigenze.

Assicurarsi che ogni team responsabile abbia una buona comprensione delle attività necessarie per eseguire il servizio. È fondamentale che ogni team accetti e sottoscriva la propria responsabilità nell'organizzazione prima dell'inizio della prima distribuzione pilota.

Dopo aver stipulato un accordo, i team corrispondenti dovrebbero iniziare a rendere operativo il proprio ruolo.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td>
<td><ul><li>Usare questo documento per facilitare l'esercizio di mappatura del ruolo operativo.</li><li>Incontrarsi con i rispettivi team di supporto per assegnare nomi a ogni elemento nell'elenco delle attività richieste.</li><li>Ottenere l'accettazione o la firma per i ruoli assegnati.</li><li>Assicurarsi che i team corrispondenti abbiano la formazione, la preparazione e le risorse appropriate per completare le attività richieste.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dipendenze del servizio Teams

Microsoft Teams riunisce tecnologie in Microsoft 365 o Office 365 per fornire un hub per il lavoro in team. Ecco alcuni esempi:

-   Azure Active Directory (Azure AD) fornisce servizi di autenticazione e autorizzazione per Teams.

-   Exchange Online offre funzionalità avanzate come il blocco a fini giudiziari e l'individuazione elettronica.

-   SharePoint Online offre la possibilità di condividere file nei canali e OneDrive for Business offre un meccanismo per la condivisione di file all'interno di una chat privata.

Le organizzazioni possono anche sfruttare gli investimenti esistenti nell'infrastruttura locale. Ad esempio, gli account Active Directory locale esistenti possono essere usati per l'autenticazione sfruttando Azure AD Connect. Alcune versioni di Exchange Server possono essere usate al posto di Exchange Online.

Queste tecnologie si uniscono per offrire agli utenti una suite di comunicazione intelligente, collaborativa e ricca. Questa stretta integrazione è un vantaggio fondamentale di Teams, ma determina anche un requisito per la gestione dei servizi in queste tecnologie.

Questa guida illustra le aree di interesse principali per gestire il servizio Teams. Molto probabilmente sono in atto piani di gestione dei servizi per le tecnologie di supporto da cui dipende Teams. In caso contrario, sarà necessario stabilire piani di gestione dei servizi adeguati anche per questi componenti tecnologici (sia in locale che online). In questo modo gli utenti potranno usufruire di un'esperienza affidabile e di alta qualità con Teams.

#### <a name="references"></a>Riferimenti 

[Panoramica di Microsoft Teams](teams-overview.md)

[Interazione tra Exchange e Microsoft Teams](exchange-teams-interact.md)

[Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams](sharepoint-onedrive-interact.md)

[Coesistenza e interoperabilità di Microsoft Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Attività della Guida operativa

Le sezioni seguenti offrono una panoramica delle attività necessarie per il corretto funzionamento del servizio Microsoft Teams. Includono riferimenti a strumenti, informazioni contestuali e altri contenuti che consentono di comprendere l'attività e di assistere l'utente nelle iniziative di preparazione.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorare l'integrità dei servizi

È importante comprendere l'integrità generale del servizio Microsoft Teams in modo da poter avvisare proattivamente gli altri utenti dell'organizzazione di qualsiasi evento che influisca sul servizio. Come descritto in precedenza, Teams dipende da altri servizi di Microsoft 365 o Office 365 come Azure Active Directory, Exchange Online, SharePoint Online e OneDrive for Business. Per questo motivo, è altrettanto importante monitorare l'integrità dei servizi dipendenti.

Incorporare questa attività nel processo di gestione degli eventi imprevisti per informare proattivamente gli utenti, l'helpdesk e i team operativi per prepararsi a gestire le escalation degli utenti.

Le sezioni seguenti descrivono gli strumenti che è possibile usare per monitorare gli [interventi di assistenza](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) che interessano il servizio Teams. Nella tabella seguente è riportato un riepilogo dei vantaggi di ogni strumento e del momento in cui è consigliabile usarli.

| Strumento di monitoraggio                       | Vantaggi                                            | Quando usare                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Interfaccia di amministrazione di Microsoft 365                     | Disponibile da qualsiasi dispositivo con un browser supportato. | Da usare quando non sono necessarie notifiche in tempo reale.                                          |
| Microsoft 365 o Amministrazione di Office 365 app                  | Fornisce notifiche push al dispositivo mobile.  | Da usare quando è necessario ricevere una notifica di richieste di assistenza mentre si è in viaggio.                  |
| Microsoft System Center               | Integrazione con Microsoft System Center.           | Da usare quando sono necessarie funzionalità di monitoraggio avanzate e supporto delle notifiche.                       |
| API Microsoft 365 o Office 365 Service Communications | Accesso programmatico a Microsoft 365 o Office 365 integrità dei servizi.   | Usare questa opzione quando è necessaria l'integrazione con uno strumento di monitoraggio di terze parti o se si vuole creare una soluzione personalizzata. |

> [!NOTE]
> Solo le persone a cui è assegnato il ruolo **di amministratore globale** o amministratore del servizio possono visualizzare **l'integrità** dei servizi.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoraggio con il interfaccia di amministrazione di Microsoft 365

Il [interfaccia di amministrazione di Microsoft 365](https://portal.office.com/) fornisce un [dashboard Integrità dei](https://portal.office.com/adminportal/home#/servicehealth) servizi in cui è possibile visualizzare l'integrità corrente del servizio teams oltre ai servizi dipendenti.

### <a name="monitoring-with-the-mobile-app"></a>Monitoraggio con l'app per dispositivi mobili

L'app Microsoft 365 o Amministrazione di Office 365 è disponibile su Apple iOS, Android e Windows (PC e dispositivi mobili). L'app fornisce agli amministratori dei servizi informazioni sull'integrità dei servizi e sulle modifiche imminenti. L'app supporta le notifiche push che possono avvisare l'utente quasi immediatamente dopo la pubblicazione di un avviso. In questo modo è possibile mantenersi aggiornati sullo stato, sull'integrità e su eventuali modifiche imminenti al servizio. Il supporto delle notifiche lo rende lo strumento di monitoraggio consigliato per gli amministratori. Per ulteriori informazioni, vedere:

[app per dispositivi mobili Amministrazione di Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Scaricare l'app Amministrazione di Office 365 per dispositivi mobili](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoraggio con Microsoft System Center

Microsoft System Center è una piattaforma di gestione integrata che consente di gestire data center, dispositivi client e ambienti IT cloud ibridi. Office 365 amministratori che utilizzano System Center hanno ora la possibilità di importare il Office 365 Management Pack, che consente loro di visualizzare tutte le comunicazioni di servizio all'interno di Operations Manager in System Center. Questo strumento consente di accedere allo stato dei servizi sottoscritti, agli interventi di assistenza attivi e risolti e alle comunicazioni del Centro messaggi (modifiche imminenti). Per altre informazioni, vedere il post di [blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true) seguente.

Se si sfrutta System Center per monitorare l'integrità dei servizi di Teams (e i servizi dipendenti), è possibile personalizzare ulteriormente il Management Pack per avvisare o avvisare gruppi o persone specifiche che sono state identificate per reagire agli incidenti.
Questi gruppi possono includere proprietari del servizio, helpdesk, gruppi di supporto di secondo livello e di terzo livello e responsabili degli eventi nell'organizzazione.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoraggio per scenari avanzati

È possibile monitorare l'integrità dei servizi e le modifiche imminenti sfruttando l'API Office 365 Service Communications per accedere all'integrità dei servizi Office 365 e alle modifiche a livello di programmazione. Usare questa API per creare uno strumento di monitoraggio personalizzato o per connettere gli strumenti di monitoraggio esistenti per Office 365 le comunicazioni di servizio, semplificando potenzialmente il monitoraggio dell'ambiente. Per altre informazioni, vedi [Office 365 per sviluppatori Enterprise](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività               | Descrizione                                                                                                                                                                                                               | Cadenza   | Team assegnato |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorare l'integrità dei servizi | Monitorare in modo proattivo l'integrità dei servizi di Microsoft Teams (e i servizi dipendenti) usando gli strumenti disponibili. I servizi dipendenti includono: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | In tempo reale |               |
| Notifica di evento imprevisto  | Notificare agli stakeholder interni gli eventi che influiscono sul servizio Teams. Gli stakeholder interni possono includere utenti, helpdesk e responsabili degli incidenti.                                                                          | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[Come controllare l'integrità dei servizi Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificare l'integrità dei servizi per Microsoft Teams](service-health.md)

[Integrità e continuità dei servizi](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gestire le modifiche dell'organizzazione

Microsoft Teams è un servizio basato sul cloud. Con questo viene la possibilità di fornire nuove caratteristiche e funzionalità a un ritmo rapido. L'offerta di innovazione continua offre un vantaggio evidente alle organizzazioni, ma queste modifiche devono essere gestite in modo appropriato all'interno dell'organizzazione per evitare la resistenza degli utenti o l'escalation al supporto tecnico.

Aggiornamenti a Teams vengono distribuite automaticamente agli utenti. Gli utenti avranno sempre a disposizione il client e le funzionalità più recenti nel servizio Teams. Non è possibile gestire l'implementazione degli aggiornamenti di Teams per gli utenti, quindi è di fondamentale importanza gestire il cambiamento attraverso programmi efficaci di comunicazione, formazione e adozione. Se gli utenti sono a conoscenza del cambiamento, hanno ricevuto una formazione sui vantaggi e hanno la possibilità di sfruttare le nuove funzionalità&mdash;, saranno in grado di adattarsi più rapidamente e accogliere con favore la modifica.

### <a name="monitoring-for-change"></a>Monitoraggio delle modifiche

Il primo passaggio nella gestione delle modifiche consiste nel monitorare le modifiche pianificate per Teams. La fonte migliore per monitorare queste modifiche è la [roadmap Office 365](https://products.office.com/business/office-365-roadmap), che elenca le funzionalità attualmente in fase di sviluppo, distribuite ai clienti o avviate completamente. È possibile cercare funzionalità specifiche di Teams usando il filtro fornito oppure scaricare la roadmap in un file di Excel per un'ulteriore analisi. Per ogni funzionalità, la roadmap fornisce una breve descrizione, insieme alla data di rilascio prevista.

Nel [blog di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog) è possibile conoscere le procedure consigliate, le tendenze e le notizie sugli aggiornamenti dei prodotti Teams. Prevediamo di trovare gli aggiornamenti principali delle funzionalità di Teams che verranno annunciati qui. È anche possibile sottoscrivere il blog tramite un feed RSS. È quindi possibile aggiungere [il feed RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) direttamente in un canale di Teams, in modo che tutte le notizie importanti vengano recapitate direttamente all'interno di Teams.

Tutte le funzionalità rilasciate sono documentate nelle [Note sulla versione per Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Ecco un elenco delle funzionalità rilasciate per i desktop, il Web e i dispositivi mobili. Lo stesso set di note sulla versione è disponibile anche nella scheda **Novità della** [Guida](get-help-in-microsoft-teams.md).

Acquisire familiarità con le risorse disponibili e assicurarsi di assegnare i proprietari applicabili per il monitoraggio delle modifiche.

### <a name="planning-for-change"></a>Pianificazione del cambiamento

Ora che si è a conoscenza delle prossime modifiche al servizio Teams, il passaggio successivo consiste nel preparare e pianificare di conseguenza. Valutare ogni modifica per determinare quali modifiche richiedono comunicazioni agli utenti, campagne di sensibilizzazione, formazione per team o utenti di supporto o campagne di valutazione e adozione delle funzionalità. Questo è il ruolo principale di un team di gestione delle modifiche nell'organizzazione. Di seguito è riportata una raccolta di tabelle di esempio che consentono di pianificare le modifiche.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Funzionalità: Registrazione cloud (data di rilascio: gennaio 2018)

**Traccia generale**

| Conformità alle modifiche | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Revisione legale   | Completato     | Questa funzionalità è un prerequisito per l'onboarding del team di formazione. | Team di progetto  |

**Gestione delle modifiche tecniche**

|       Conformità alle modifiche       | Stato |                      Note/passaggi successivi                      |    Proprietario     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Modifiche IT necessarie      |  Sì   | Amministrazione deve abilitare la registrazione solo per gli utenti identificati. | Team di supporto |
| Preparazione tecnica completata |  Sì   |                                                            | Team di supporto |
|                              |        |                                                            |              |

**Gestione delle modifiche degli utenti** 

| Conformità alle modifiche | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Impatto sull'utente                  | Bassa                  |                                                                 |                        |
| Requisiti di conformità dell'utente      | Sì                  |                                                                 |                        |
| Comunicazioni pronte         | No                   | È stato redatto un messaggio e-mail di comunicazione, in attesa di revisione.            | Team di comunicazione    |
| Formazione pronta               | Sì                  | La formazione sfrutterà i video microsoft esistenti.                | Team di formazione          |

**Traccia stato**

| Conformità alle modifiche | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Stato del rilascio               | in corso          | Revisione in sospeso da parte dello sponsor esecutivo.               | Team di gestione delle modifiche |
| Firma di rilascio             |                      |                                                                 |                        |
| Data di rilascio                 |                      |                                                                 |                        |

Per altre informazioni sulla pianificazione per la gestione delle modifiche con Teams, vedere [Creare una strategia di gestione delle modifiche per Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività               | Descrizione                                                                                                                                                                                                                | Cadenza   | Team assegnato |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitora per la modifica     | Monitorare le modifiche imminenti al servizio Microsoft Teams.                                                                                                                                                                   | Quotidiana     |               |
| Pianificazione del cambiamento    | Valutare e pianificare nuove caratteristiche e funzionalità, tra cui piani di comunicazione, campagne di sensibilizzazione e formazione.                                                                                                     | In base alle esigenze |               |
| Conformità degli utenti             | Eseguire campagne di comunicazione, consapevolezza o formazione mirate per assicurarsi che gli utenti siano pronti per la prossima modifica.                                                                                                        | In base alle esigenze |               |
| Preparazione del team di supporto | Eseguire campagne di comunicazione, consapevolezza o formazione mirate per assicurarsi che il team di supporto sia pronto. I team di supporto possono includere il team "White Glove", gli helpdesk, il supporto di Livello 2 o Livello 3, i partner esterni e così via. | In base alle esigenze |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Valutare l'utilizzo di Teams

Dopo l'inizio del progetto pilota iniziale, è fondamentale stabilire una cadenza regolare per misurare l'utilizzo effettivo di Teams. In questo modo l'organizzazione può ottenere informazioni approfondite sull'allineamento dell'utilizzo effettivo con l'utilizzo previsto durante la fase Divisione. Anche se questa sezione è incentrata sull'utilizzo di Teams, ciò dovrebbe far parte di uno sforzo più ampio per misurare e valutare Office 365'utilizzo complessivo.

La verifica frequente dell'utilizzo nelle prime fasi della distribuzione offre la possibilità di:

-   Verificare se gli utenti usano Teams.

-   Identificare le potenziali sfide all'adozione prima di creare problemi critici nell'intera organizzazione.

-   Verificare se esistono discrepanze tra i requisiti della fase di previsione e l'utilizzo effettivo.

Se l'utilizzo non è quello previsto, è possibile che si sia verificato un problema di distribuzione o che il piano di adozione non venga eseguito correttamente o che si sia verificato un altro problema. A seconda del motivo effettivo del basso utilizzo, l'amministratore del servizio deve collaborare con i team correlati per rimuovere le barriere di utilizzo.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Misurazione dell'utilizzo con il interfaccia di amministrazione di Microsoft 365

I dati di utilizzo di Teams sono disponibili nel dashboard dei report. I dati di utilizzo di Teams sono disponibili in tre diversi report. Il primo report fornisce una visualizzazione multiprodotto del modo in cui gli utenti comunicano e collaborano usando i vari servizi in Office 365. Questo report è disponibile qui: [Office 365 report utenti attivi](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Gli altri due report sono specifici di Teams e forniscono ulteriori dettagli sull'utilizzo di Teams dal punto di vista dell'utente e del dispositivo. Entrambi i report sono disponibili qui:

[Report utilizzo dispositivi Microsoft Teams](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Report attività degli utenti di Microsoft Teams](/microsoftteams/teams-analytics-and-reports/user-activity-report)

#### <a name="required-permissions"></a>Autorizzazioni necessarie

I report sull'utilizzo nell'interfaccia di amministrazione sono accessibili agli utenti a cui è stato assegnato un **ruolo di amministratore globale** o un ruolo di amministratore specifico del prodotto (**amministratore di Exchange**, **amministratore di Skype for Business**, **amministratore di SharePoint**).

Inoltre, il ruolo di **lettore Report** è disponibile per gli utenti che richiedono l'accesso ai report, ma non eseguono attività che richiedono autorizzazioni a livello di amministratore. Assegnare questo ruolo per fornire report sull'utilizzo a chiunque sia uno stakeholder, per monitorare e promuovere l'adozione. Per altre informazioni sui diversi ruoli disponibili, vedere [Informazioni sui ruoli di amministratore Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Valutazione dell'utilizzo

Dopo aver usato il dashboard Dei report per misurare l'utilizzo, è importante confrontare l'utilizzo misurato con gli indicatori di successo chiave definiti durante la fase Divisione del progetto. È possibile definire un indicatore KSI che potrebbe essere definito come utilizzo attivo o indirettamente collegato all'utilizzo attivo.

È importante identificare eventuali variazioni tra l'utilizzo effettivo e pianificato prima di riprendere l'implementazione ad altri siti o utenti. È probabile che nell'ambito di questa attività si identifichi l'apprendimento dell'organizzazione che è possibile sfruttare per garantire che il prossimo batch di siti o utenti non riscontri gli stessi problemi.

In primo luogo, stabilire se si tratta di un adozione o di un problema tecnico. Iniziare analizzando gli elementi seguenti, per determinare dove si trova il problema.

1.  Convalidare la qualità eseguendo una verifica della qualità dell'esperienza (vedere [Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md) per maggiori dettagli).

2.  Collaborare con il team helpdesk per verificare che non vi siano problemi tecnici di tendenza che impediscono agli utenti di accedere al servizio o di usarlo. Se esistono tendenze del problema, usare la sezione risoluzione [dei problemi degli endpoint](#endpoint-troubleshooting) più avanti in questo articolo per provare a risolvere il problema prima di ottenere supporto.

3.  Collaborare con il team di formazione e adozione per raccogliere feedback diretto dagli utenti (vedere [Valutare la valutazione della valutazione](#assess-user-sentiment) degli utenti più avanti in questo articolo) e verificare l'efficacia delle attività di sensibilizzazione e adozione.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività                         | Descrizione                                                                                                                      | Cadenza   | Team assegnato |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Misurare l'utilizzo (fase di abilitazione) | Misurare e valutare l'utilizzo di Teams man mano che i siti continuano a essere caricati durante la fase di abilitazione. Risolvere i problemi di utilizzo in base alle esigenze. | Settimanale    |               |
| Misurare l'utilizzo (fase del valore dell'unità)                           | Misurare e valutare l'utilizzo di Teams nella fase drive value (dopo il completamento della distribuzione). Risolvere i problemi di utilizzo in base alle esigenze. | Bisettimanale  |               |
| Aggiornare il piano di adozione             | Aggiornare il piano di adozione in base al confronto tra l'utilizzo misurato e i target di pianificazione.                                         | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[Informazioni sul interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Report attività nel interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Valutare la valutazione della valutazione degli utenti

La comprensione della valutazione degli utenti può fungere da indicatore chiave per valutare il successo della distribuzione di Teams. Il feedback degli utenti può guidare le modifiche nell'organizzazione; Potrebbero essere incluse modifiche ai piani di comunicazione, ai programmi di formazione o al modo in cui si offre supporto agli utenti.

È importante ricevere feedback in anticipo e continuare a valutare la valutazione della valutazione dell'utente per tutto il ciclo di vita del progetto e non solo. Usare le indicazioni seguenti per determinare l'intervallo in cui l'organizzazione cercherà il feedback:

-   **Inizio del progetto**: valutando il sentiment degli utenti all'inizio del progetto, è possibile ottenere una visione preliminare dell'opinione degli utenti sull'esperienza di Teams.

-   **Dopo le principali attività cardine**: raccogliendo feedback per tutto il ciclo di vita del progetto, è possibile valutare continuamente la valutazione degli utenti e apportare modifiche in base alle esigenze. Ciò è particolarmente utile dopo le principali attività cardine.

-   **Conclusione del progetto**: la valutazione della valutazione della valutazione dell'opinione degli utenti alla fine di un progetto indica quanto è stato fatto e dove è ancora necessario lavorare e consente di confrontare i risultati rispetto al sondaggio precedente.

-   **In corso**: Continuare a misurare la valutazione dell'utente per un tempo indefinito. Le modifiche apportate ai sentimenti degli utenti potrebbero essere dovute a modifiche nell'ambiente dell'organizzazione o al servizio Teams. Esaminando la valutazione dell'utente a intervalli regolari, è possibile comprendere il livello di prestazioni dei team di gestione dei servizi e il modo in cui l'organizzazione risponde alle modifiche apportate al servizio Teams.

La valutazione della valutazione dell'utente può essere effettuata con diversi metodi. Possono includere sondaggi tramite posta elettronica, colloqui in stile telefono o di persona oppure la semplice creazione di un canale di feedback in Teams o Yammer. Per altre informazioni, vedere [Procedure consigliate per i metodi di feedback degli utenti in Microsoft Teams](best-practices-feedback.md).

È anche possibile utilizzare un approccio a livello di settore per valutare la valutazione della valutazione degli utenti denominata net promoto score (NPS), descritta nella sezione seguente.

### <a name="nps"></a>Nps 

Il punteggio netto dei promotori (NPS) è una metrica di fidelizzazione dei clienti a livello di settore e un buon approccio da usare per valutare il sentiment degli utenti. NPS può essere calcolato ponendo due domande: "È probabile che consiglierai Teams a un collega?", seguito dalla domanda della figura a mano libera "Perché?"

NPS è un indice, compreso tra -100 e 100, che misura la disponibilità di un cliente a raccomandare il prodotto o il servizio di una società. NPS si basa su un sondaggio anonimo che viene recapitato agli utenti tramite posta elettronica o altri mezzi elettronici. NPS misura la fedeltà tra un fornitore e un consumatore. Consiste in una sola domanda, che chiede agli utenti di valutare la loro esperienza da 1 a 10, con la possibilità di fornire commenti aggiuntivi. Gli utenti vengono quindi classificati in base alle valutazioni seguenti:

-   9 o 10 sono promotori: appassionati fedeli che promuoveranno il vostro servizio e alimenteranno gli altri.

-   7 o 8 sono passivi: soddisfatti ma non entusiastici, vulnerabili a un altro servizio o offerta.

-   Da 1 a 6 sono detrattori: clienti infelici che possono danneggiare il servizio e ostacolare la crescita.

![Diagramma che illustra la scala NPS.](media/operate-my-service-image2.png "Questo diagramma illustra la scala NPS. Mostra che le classifiche da 0 a 6 sono detrattori, da 7 a 8 sono passive e da 9 a 10 sono promotori.")

Anche se il numero NPS di base è utile, si otterrà il massimo dall'analisi dei commenti degli utenti. Ti aiuteranno a capire perché l'utente consiglierebbe o meno Teams ad altri. Questi commenti possono fornire feedback utili per aiutare i team di gestione di progetti o servizi a comprendere le modifiche necessarie per fornire un servizio di qualità.

Per fornire sondaggi NPS all'organizzazione, è possibile sfruttare lo strumento di sondaggio online preferito.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività              | Descrizione                                                                                                                                                                         | Cadenza   | Team assegnato |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Valutare la valutazione della valutazione degli utenti | Acquisire e valutare la valutazione della valutazione degli utenti tramite sondaggi o colloqui oppure tramite un canale di feedback in Teams o Yammer.                                                                 | In base alle esigenze |               |
| Aggiornare i piani di adozione | Favorire la modifica nell'organizzazione in base al feedback degli utenti; ciò può includere modifiche ai piani di comunicazione, ai programmi di formazione o al modo in cui si offre supporto agli utenti. | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Uso di Yammer per raccogliere feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Procedure consigliate per il feedback degli utenti](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gestire la qualità della rete

Molti elementi di pianificazione di base vanno nell'ottimizzazione, nel ridimensionamento destro e nella correzione dell'infrastruttura di rete per garantire un percorso efficiente e di alta qualità al servizio Microsoft Teams. Le attività e i requisiti di pianificazione sono coperti dalle linee guida per [la conformità alla rete](3-envision-evaluate-my-environment.md#network-readiness) . Le reti spesso evolvono nel tempo a causa di aggiornamenti, espansione o altri requisiti aziendali. È importante tenere conto dei requisiti di Teams nelle attività di pianificazione della rete.

Anche se la pianificazione della rete è un aspetto fondamentale di una distribuzione di Teams, è altrettanto importante assicurarsi che la rete rimanga integro e rimanga aggiornata, in base ai mutevoli requisiti aziendali o tecnici.

Per garantire l'integrità della rete, è necessario eseguire una serie di attività operative a intervalli regolari.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività                                                       | Descrizione                                                                                                                                                                                                                                                                                                                                                                 | Cadenza                | Team assegnato |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Monitorare indirizzi IP e URL di Office 365                                | Monitorare eventuali modifiche ai [Office 365 URL e intervalli di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) usando il [feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fornito e avviando una richiesta di modifica ai gruppi di rete applicabili.                                                                                                                                | Quotidiana                  |               |
| Aggiornare la rete in base alle modifiche apportate agli INDIRIZZI IP e agli URL Office 365 | Aggiornare i componenti di rete applicabili (firewall, server proxy, VPN, firewall lato client e così via) per riflettere le modifiche apportate agli [URL e agli intervalli di indirizzi IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).                                                                                                                                                              | In base alle esigenze              |               |
| Fornire i dati dell'edificio                                          | Fornire informazioni aggiornate sulla subnet al campione di qualità (o agli stakeholder interessati) per assicurarsi che [le definizioni dell'edificio in Call Quality Dashboard](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) siano mantenute aggiornate. | In base alle esigenze              |               |
| Implementare la modifica                                               | Implementare le modifiche alla rete per supportare la modifica dei requisiti aziendali e tecnici di Teams. Gli elementi di rete possono includere:<ul><li>Firewall</li><li>Vpn</li><li>Reti cablate e Wi-Fi</li><li>Connettività Internet ed ExpressRoute</li><li>DNS</li></ul>     | In base alle esigenze              |               |
| Monitoraggio e creazione di report di rete                               | Monitorare l'end-to-end della rete per individuare le tendenze di disponibilità, utilizzo e capacità usando gli attuali strumenti di gestione della rete di terze parti e le funzionalità di creazione di report disponibili dai provider di rete. Usare i dati di tendenza per la pianificazione della capacità di rete.                                                                                                            | Ogni giorno, settimanalmente, mensilmente |               |
| Pianificazione della capacità                                              | Collaborare con i proprietari dei servizi di Teams per comprendere i requisiti aziendali e tecnici in evoluzione che potrebbero comportare ulteriori modifiche della capacità.                                | In base alle esigenze              |               |
| Risoluzione dei problemi di rete e correzione                        | Aiutare gli helpdesk di Teams, i proprietari dei servizi e gli stakeholder principali a risolvere e correggere i problemi relativi alla connettività, all'affidabilità o alla qualità di Teams. Gli elementi di rete possono includere:<ul><li>Firewall</li><li>Vpn</li><li>Reti cablate e Wi-Fi</li><li>Connettività Internet ed ExpressRoute</li><li>DNS</li></ul>    | In base alle esigenze              |               |
| Test di ripristino di emergenza e disponibilità elevata                | Eseguire test regolari di disponibilità elevata e ripristino di emergenza sull'infrastruttura di rete per assicurarsi che soddisfi gli obiettivi a livello di servizio indicati (SLO) o contratti di servizio (SLA) per il servizio Teams.                                                                                                                                                  | Mensile                |               |


### <a name="references"></a>Riferimenti 

[URL e intervalli di indirizzi IP per Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Schema dei dati di compilazione](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Valutare e garantire la qualità 

Tutte le organizzazioni hanno bisogno di un gruppo o di una persona per essere responsabili della qualità. Questo è il ruolo più importante nella gestione dei servizi. Il ruolo Quality Champion viene assegnato a una persona o a un gruppo appassionato dell'esperienza degli utenti.
Questo ruolo richiede le competenze necessarie per identificare le tendenze nell'ambiente e la sponsorizzazione per lavorare con altri team per la correzione. Il candidato migliore per il campione di qualità è in genere il proprietario del servizio clienti. A seconda delle dimensioni e della complessità dell'organizzazione, può trattarsi di qualsiasi persona o gruppo con la passione di garantire un'esperienza utente di alta qualità.

Il quality champion sfrutta gli strumenti e i processi documentati esistenti, ad esempio Call Quality Dashboard (CQD), per monitorare l'esperienza utente, identificare le tendenze di qualità e favorire la correzione quando necessario.
Il campione di qualità dovrebbe lavorare con i rispettivi team per condurre azioni correttive e segnalare a un comitato di orientamento i progressi e eventuali problemi aperti.

Leggi [Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md), che descrive le attività che valutano e forniscono indicazioni per la correzione in aree chiave che hanno il maggiore impatto sul miglioramento dell'esperienza utente. Le linee guida fornite in questo articolo sono incentrate sull'uso di Call Quality Dashboard come strumento principale per segnalare e analizzare ogni area, con particolare attenzione all'audio per massimizzare l'adozione e l'impatto. Qualsiasi ottimizzazione apportata alla rete per migliorare l'esperienza audio si tradurrà direttamente in miglioramenti nella condivisione di video e desktop.

Si consiglia vivamente di designare il campione di qualità all'inizio. Dopo essere stati nominati, dovrebbero iniziare a familiarizzare con [monitora il contenuto di qualità delle chiamate](monitor-call-quality-qos.md) e i materiali di formazione associati.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività                               | Descrizione                                                                                                                                                                                                                                                                                                 | Cadenza                             | Team assegnato |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nomina e addestrare i campioni di qualità | Nomina e addestrare un campione di qualità.                                                                                                                                                                                                                                                                   | In base alle esigenze                           |               |
| Eseguire valutazioni di qualità dell'esperienza (QER)     | Eseguire un QER per identificare le tendenze in materia di qualità e affidabilità, esaminare i target definiti e segnalare agli stakeholder principali dell'organizzazione.                                                                                                                            | Mensile (settimanale durante le distribuzioni) |               |
| Correzione unità                      | Coordinare le azioni correttive in tutta l'organizzazione in base alle valutazioni e ai risultati di QER.                                                                                                                                                                                                           | In base alle esigenze                           |               |
| Aggiornare i dati dell'edificio in Call Quality Dashboard            | Aggiornare o aggiungere nuove definizioni di edificio in Call Quality Dashboard quando vengono apportate modifiche alla rete (vedere [Upload Building information](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | In base alle esigenze                           |               |
| Ricoprire il ruolo di Quality Champion      | Responsabilità end-to-end per la qualità nell'organizzazione. Ciò include:<ul><li>Assicurarsi che il QER venga eseguito regolarmente.</li><li>Segnalare lo stato di qualità alle principali parti interessate.</li><li>Verificare che le definizioni dei dati dell'edificio siano aggiornate.</li><li>Coordinare le azioni correttive in tutta l'organizzazione per garantire agli utenti un'esperienza di alta qualità con Teams.</li></ul>          | Quotidiana                               |               |



### <a name="references"></a>Riferimenti 


[Caricare i dati del tenant e dell'edificio in Call Quality Dashboard](CQD-upload-tenant-building-data.md)

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gestire gli endpoint

Gli endpoint di Microsoft Teams possono essere definiti come qualsiasi PC, Mac, tablet o dispositivo mobile (o qualsiasi altro dispositivo) che esegue il client Teams. Il termine *endpoint* non comprende solo il dispositivo stesso, ma anche il modo in cui un utente si connette al dispositivo, ad esempio usando il microfono o l'altoparlante integrato del dispositivo, gli auricolari o un auricolare ottimizzato. Dopo la distribuzione, gli endpoint non devono essere dimenticati. Gli endpoint di Teams richiedono cure e manutenzione continue. Le sezioni seguenti descrivono aree specifiche su cui concentrarsi.

### <a name="endpoint-requirements"></a>Requisiti degli endpoint

Uno dei principali vantaggi di Teams è che il client viene mantenuto aggiornato automaticamente. I client nel PC e nel Mac vengono aggiornati tramite un processo in background che controlla la presenza di nuove build e scarica il nuovo client quando l'app è inattiva. Le app per dispositivi mobili di Teams vengono mantenute aggiornate tramite i rispettivi store di app.

Il client teams ha requisiti minimi in termini di piattaforma software sottostante. Questi requisiti potrebbero cambiare nel corso del tempo e quindi è importante monitorarli per le modifiche. Ad esempio, il client Teams ha una versione minima di iOS. Se il client usa un browser Internet, è necessario mantenere aggiornato anche il browser. Un elenco delle piattaforme supportate è disponibile in [Ottieni client per Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewall endpoint

I firewall lato client possono avere un impatto significativo sull'esperienza utente.
I firewall lato client possono influire sulla qualità delle chiamate e persino impedire l'avvio di una chiamata. Dopo aver configurato le esclusioni appropriate nel firewall client, è necessario mantenerle aggiornate in base alle informazioni contenute in [URL e intervalli di indirizzi IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges). Il fornitore di terze parti fornirà indicazioni specifiche su come aggiornare le esclusioni.

### <a name="wi-fi-drivers"></a>driver Wi-Fi

Wi-Fi driver potrebbero essere problematici. Ad esempio, un driver potrebbe avere comportamenti di roaming molto aggressive tra i punti di accesso che possono indurre inutili cambi di punto di accesso, determinando una bassa qualità delle chiamate. Un driver di Wi-Fi con prestazioni insufficienti potrebbe essere individuato tramite una verifica della qualità dell'esperienza (vedi [Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md) per maggiori dettagli). È essenziale implementare un processo basato sulla qualità che monitori i nuovi driver di Wi-Fi e assicuri che vengano testati prima di essere distribuiti alla popolazione di utenti generale.

### <a name="endpoint-management"></a>Gestione degli endpoint

Deve essere disponibile e mantenuto un catalogo di endpoint e dispositivi di interfaccia supportati, ad esempio cuffie. Questo catalogo includerà un elenco di dispositivi approvati che sono stati selezionati e convalidati nell'ambito delle fasi Divisione e Onboard. In genere, vengono selezionati dispositivi specifici per ogni tipo di utente tipo nell'organizzazione per soddisfare le esigenze degli attributi di tale persona. Tutti gli endpoint hanno un ciclo di vita ed è necessario gestire i contratti dei fornitori, la garanzia, la sostituzione, la distribuzione e i criteri di riparazione associati a questi dispositivi.

### <a name="endpoint-troubleshooting"></a>Risoluzione dei problemi degli endpoint

Anche se hai seguito le indicazioni precedenti, gli utenti dell'organizzazione potrebbero comunque riscontrare problemi con Teams. Anche se il problema potrebbe non riguardare l'endpoint stesso, i sintomi del problema vengono in genere visualizzati tramite il client all'utente. Le indicazioni seguenti hanno lo scopo di fornire i passaggi generali che è possibile eseguire per risolvere il problema. non deve essere una guida completa alla risoluzione dei problemi. I passaggi vengono forniti in un ordine specifico, ma non devono essere seguiti esplicitamente e potrebbero non essere applicabili, a seconda della natura del problema.

1.  **Convalidare l'integrità dei servizi:** Il problema che un utente potrebbe riscontrare può essere correlato a un evento che influisce negativamente sul servizio teams o sui servizi dipendenti. Come primo passaggio, è consigliabile verificare che non ci siano problemi di servizio attivi. Consulta [Come controllare Office 365 integrità dei servizi](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Ricordare di controllare lo stato dei servizi dipendenti, ad esempio Exchange, SharePoint OneDrive for Business. Il monitoraggio dell'integrità dei servizi viene discusso in modo più dettagliato nella sezione precedente [Monitoraggio dell'integrità dei servizi](#monitor-service-health).

2.  **Convalidare la connettività client:** I problemi di connettività causano problemi di funzionalità o di accesso in Teams. È consigliabile, in particolare per i nuovi siti o posizioni, convalidare la connettività al servizio. Assicurarsi che per ogni sito siano seguite le indicazioni seguenti Office 365 [URL e intervalli di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). È possibile sfruttare lo [strumento di valutazione della rete Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) per eseguire un test di connettività per verificare che le porte multimediali siano state aperte correttamente per le funzionalità vocali nel cloud. I passaggi dettagliati su come eseguire i test di connettività sono disponibili nelle linee guida sulla [conformità alla rete](3-envision-evaluate-my-environment.md#network-readiness) .

3.  **Controllare l'elenco dei problemi noti:** Consulta [Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams) per determinare se uno di questi problemi ha influito negativamente sull'utente. Seguire la soluzione alternativa fornita (se disponibile) per risolvere il problema.

4.  **Visita la community di Microsoft Teams:** La [community di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) offre spazi dedicati per Teams. La community di Teams fornisce un elenco di discussioni, post di blog e annunci incentrati su Teams. È possibile pubblicare una domanda o cercare le soluzioni al problema nelle discussioni precedenti.

5.  **Contattare supporto tecnico Microsoft:** è possibile contattare supporto tecnico Microsoft per problemi con Teams online o tramite telefono. Per informazioni, vedere [Contattare il supporto per i prodotti aziendali](/microsoft-365/admin/contact-support-for-business-products).
    Per i clienti Premier, le richieste di supporto possono essere avviate seguendo le indicazioni in Contattare il supporto per Microsoft Teams (clienti Premier).For Premier customers, requests can be initiated by following the guidance at [Contact support for Microsoft Teams (Premier customers)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività                 | Descrizione                                                                                                                                                                                                                                                                                                                                                                     | Cadenza   | Team assegnato |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisiti degli endpoint    | Assicurarsi che l'endpoint di Teams continui a soddisfare tutti i requisiti software per Teams elencati in [Ottieni client per Microsoft Teams](get-clients.md).                                                                                                                                                                                       | Mensile   |               |
| Firewall endpoint       | Mantenere le esclusioni appropriate nel firewall dell'endpoint in base alle informazioni contenute in [URL e intervalli di indirizzi IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges). Il fornitore di terze parti fornirà indicazioni specifiche su come mantenere le esclusioni. Sottoscrivere il [feed RSS](https://support.office.com/o365ip/rss) per ricevere automaticamente una notifica delle modifiche. | In base alle esigenze |               |
| driver Wi-Fi            | Testa e aggiorna Wi-Fi driver nel PC. Convalidare i risultati con Call Quality Dashboard ([Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | In base alle esigenze |               |
| Gestione degli endpoint      | Gestire il catalogo degli endpoint supportati e dei dispositivi di interfaccia (ad esempio le cuffie). Gestisci i contratti dei fornitori, la garanzia, la distribuzione, la sostituzione e i criteri di riparazione.                                                                                                                                                                                                        | Mensile   |               |
| Risoluzione dei problemi degli endpoint | Le attività di risoluzione dei problemi possono includere la verifica della connettività, la consulenza dell'elenco dei problemi noti, la raccolta di log, l'analisi e l'escalation a fornitori supporto tecnico Microsoft o di terze parti.                                                                                                                                                                                               | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[URL e intervalli di indirizzi IP per Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Ottenere i client per Microsoft Teams](get-clients.md)

[Community di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)

[Verificare l'integrità dei servizi per Microsoft Teams](service-health.md)

[Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore](/microsoft-365/admin/contact-support-for-business-products)

[Contatta il supporto tecnico Premier](https://support.microsoft.com/premier/contacts)

[Video sulla risoluzione dei problemi di Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gestire Teams

Dopo aver distribuito il servizio Microsoft Teams, è necessario eseguire diverse attività relative alla sua amministrazione. Le attività vanno dall'amministrazione del servizio e dei singoli utenti alla pianificazione della capacità e al provisioning delle licenze e dei numeri di telefono. Le sezioni seguenti illustrano alcune di queste attività di amministrazione comuni.

### <a name="service-administration"></a>Amministrazione del servizio

Il servizio Teams ha più impostazioni che possono essere configurate a livello di tenant.
Le modifiche apportate alle impostazioni del tenant interessano tutti gli utenti abilitati per Teams. Per un elenco dettagliato di queste impostazioni, vedere [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md).

### <a name="user-administration"></a>Amministrazione utenti

Per supportare gli utenti, un'organizzazione potrebbe richiedere un numero qualsiasi di attività correlate, ovvero le attività specifiche variano da un'organizzazione all'altra. Infine, queste attività devono essere gestite da un team di supporto a cui sono stati assegnati questi compiti operativi. Le attività seguenti sono in genere necessarie per supportare gli utenti in Teams.

#### <a name="general-tasks"></a>Attività generali

[Gestire l'accesso degli utenti a Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Attività comuni per sistema telefonico

[Assegnare, modificare o rimuovere il numero di telefono di un utente](./assign-change-or-remove-a-phone-number-for-a-user.md)

[Assegnare o modificare l'indirizzo per gli interventi di emergenza di un utente](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Creare e impostare dial plan](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Attività comuni per le audioconferenze

[Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)

[Cambiare i numeri di telefono del bridge per i servizi di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Gestione delle licenze

Man mano che l'organizzazione cresce o si creano contratti, è importante pianificare le licenze per esigenze attuali e future. È disponibile una licenza di base di Teams, oltre alle licenze per le funzionalità vocali cloud [Sistema](here-s-what-you-get-with-phone-system.md) telefonico e [Audioconferenza](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing#requirements-for-audio-conferencing).

Per Teams, le licenze Sistema telefonico richiedono licenze [di Piani per chiamate](calling-plan-landing-page.md) associate. La licenza del Piano per chiamate consente all'utente di effettuare e ricevere chiamate telefoniche nazionali e/o internazionali. Questi piani sono basati sull'utilizzo e sono associati a pool di minuti. I [Crediti comunicazioni](what-are-communications-credits.md) di provisioning ti consentiranno di non esaurire mai il servizio.

I servizi di audioconferenza consentono servizi di conferenza telefonica con accesso esterno a pagamento e servizi di conferenza telefonica con accesso esterno nazionali. Gli scenari di conferenza telefonica con accesso esterno gratuito o di accesso esterno non nazionale potrebbero comportare costi aggiuntivi per i quali sono necessari [Crediti comunicazioni](what-are-communications-credits.md) .

I Crediti comunicazioni possono integrare le licenze Per piano per chiamate e Audioconferenza. Sia le licenze per il Piano per chiamate che i Crediti comunicazioni sono basati sull'utilizzo e pertanto devono essere monitorati e sottoposti a provisioning di conseguenza.

Puoi sfruttare il [report utilizzo PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) per monitorare l'utilizzo dei minuti per i piani di chiamata e dei Crediti comunicazioni. In base ai risultati di questa attività, è possibile modificare le licenze di conseguenza. Presto disponibile, verrà offerto un report pool di [minuti PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) per assistere in modo più efficace questa attività.

### <a name="telephone-number-management"></a>Gestione dei numeri di telefono

Esistono due metodi per acquisire numeri in Teams: puoi trasferire numeri di telefono da un altro provider o puoi effettuare il provisioning dei numeri direttamente dall'inventario numeri di Microsoft. Entrambi i metodi sono descritti in [Recupero di numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md).

È previsto un limite al numero di numeri di telefono che è possibile effettuare dal magazzino numeri di Microsoft. I limiti sono determinati da un numero di fattori dettagliati in [Quanti numeri di telefono puoi ottenere?](how-many-phone-numbers-can-you-get.md).
I limiti dipendono dal tipo di numeri: numeri verdi di servizio, numeri di servizio a pagamento e numeri di abbonato (utente). Ognuno ha i propri limiti e deve essere gestito in modo indipendente. Se si sta per raggiungere il limite o se è stato raggiunto il limite, è possibile applicare un incremento al limite. Questa procedura è descritta nell'articolo del paragrafo precedente.

A volte il provisioning di un numero potrebbe non essere disponibile in un'area geografica in cui il servizio è disponibile. Per informazioni sul processo di richiesta dei numeri, vedere [Gestire i numeri di telefono per l'organizzazione](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Creazione di team (facoltativo)

Per impostazione predefinita, tutti gli utenti con una cassetta postale in Exchange Online hanno le autorizzazioni per creare gruppi di Microsoft 365 e, di conseguenza, un team in Microsoft Teams. Se si vuole avere un controllo più rigoroso e [limitare la creazione di nuovi team](assign-roles-permissions.md) (e quindi la creazione di nuovi gruppi di Microsoft 365), è possibile delegare i diritti di creazione e gestione dei gruppi a un set di amministratori. Se l'organizzazione vuole continuare con questa opzione, vedere la procedura descritta in questo articolo per consentire agli utenti di inviare richieste elaborate da un team assegnato.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività                    | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                             | Cadenza   | Team assegnato |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Amministrazione del servizio      | Amministrazione delle impostazioni di Teams a livello di tenant.                                                                                                                                                                                                                                                                                                                                                                           | In base alle esigenze |               |
| Amministrazione utenti         | Amministrazione delle impostazioni basate sull'utente e delle licenze in Teams.                                                                                                                                                                                                                                                                                                                                                           | In base alle esigenze |               |
| Gestione delle licenze          | È possibile pianificare le esigenze attuali e future per le licenze basate sull'utente e sui consumi (Piani per chiamate e Crediti comunicazioni) sfruttando il [report utilizzo PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e il report pool di [minuti PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Settimanale    |               |
| Gestione dei numeri di telefono | Gestire i numeri di telefono disponibili per la crescita futura e modificare i livelli di inventario in base alle esigenze dell'organizzazione.                                                                                                                                                                                                                                                                                                | Settimanale    |               |
| Creazione di team (facoltativo)    | Rivedere ed elaborare le richieste per la creazione di team.                                                                                                                                                                                                                                                                                                                                                                          | In base alle esigenze |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Migliorare e monitorare la qualità delle chiamate

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md) include una serie di attività che valutano e forniscono indicazioni per la correzione in aree chiave che hanno il maggiore impatto sul miglioramento dell'esperienza utente, come illustrato di seguito.

![Diagramma delle aree da esaminare durante una verifica della qualità dell'esperienza.](media/plan-my-service-management-image2.png "Le aree chiave da esaminare durante una verifica della qualità dell'esperienza: audio, affidabilità e risultati dei sondaggi degli utenti.")

Valutando e rimediando continuamente le aree descritte nella guida, è possibile ridurne il potenziale per influire negativamente sull'esperienza utente. La maggior parte dei problemi di esperienza utente riscontrati in una distribuzione può essere raggruppata nelle categorie seguenti:

-   Configurazione proxy o firewall incompleta

-   Scarsa copertura Wi-Fi

-   Larghezza di banda insufficiente

-   Vpn

-   Uso di dispositivi audio non ottimizzati o incorporati

-   Subnet o dispositivi di rete problematici

Le linee guida fornite in [Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md) sono incentrate sull'uso di Call Quality Dashboard (CQD) Online come strumento principale per segnalare e analizzare ogni area descritta, con particolare attenzione all'audio per massimizzare l'adozione e l'impatto. Qualsiasi ottimizzazione apportata alla rete per migliorare l'esperienza audio si tradurrà direttamente in miglioramenti nella condivisione di video e desktop.

Si consiglia vivamente di designare il campione di qualità all'inizio. Dopo essere stati nominati, dovrebbero iniziare a familiarizzare con il contenuto in [Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md).

<!--ENDOFSECTION-->