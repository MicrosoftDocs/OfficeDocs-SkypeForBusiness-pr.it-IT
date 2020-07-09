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
description: Attività e attività necessarie per la gestione dei servizi di teams, incluso il monitoraggio dell'integrità dei servizi e la valutazione e garanzia della qualità e dell'uso della rete.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1762c3462f4758766f3b6996539b5c83342eedd6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085112"
---
# <a name="operate-my-service"></a>Gestire il servizio

Questo articolo offre una panoramica dei requisiti per il corretto funzionamento dei servizi vocali cloud per l'organizzazione. Con il corretto funzionamento dei servizi cloud Voice, puoi essere certo di offrire un'esperienza di alta qualità ed affidabile per l'organizzazione.

## <a name="introduction-to-the-operations-guide"></a>Introduzione alla Guida alle operazioni

La Guida alle operazioni offre una panoramica di tutte le attività e le attività necessarie nell'ambito della funzione di gestione dei servizi per Microsoft teams.

La gestione dei servizi è un argomento ampio che include le operazioni quotidiane del servizio Microsoft teams dopo che è stato distribuito e abilitato per gli utenti. Il servizio teams include Microsoft 365 o Office 365 e i componenti dell'infrastruttura distribuiti localmente (ad esempio, Networking).

La nozione di gestione dei servizi non è probabilmente un nuovo concetto per la maggior parte delle organizzazioni. I processi e le attività associati ai servizi esistenti potrebbero essere già stati implementati. In questo caso, puoi probabilmente migliorare i tuoi processi correnti quando pianifichi la gestione dei servizi oggi per supportare i team in futuro.

La gestione dei servizi comprende tutte le attività e i processi coinvolti nella gestione dei team end-to-end. Come indicato in precedenza, alcuni componenti della gestione dei servizi, ovvero l'infrastruttura che include il servizio Microsoft 365 o Office 365 stesso, sono responsabili di Microsoft, mentre il cliente è responsabile per gli utenti di gestire i vari aspetti dei team, della rete e degli endpoint forniti.

Le attività e le attività in questa guida sono raggruppate in otto categorie, come illustrato nel diagramma seguente. Ognuna di queste categorie verrà espansa nelle sezioni seguenti.

![Diagramma che illustra un elenco di categorie di attività e attività](media/operate-my-service-image1.png "Diagramma che descrive un elenco di categorie di attività e attività che la gestione dei servizi per i team include. Il diagramma descrive anche la gestione dei servizi in gran parte un'attività del cliente.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere in che modo verranno implementate le operazioni per i team.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Esaminare la Guida alle operazioni in completa.</li><li>Implementa una strategia operativa che si allinea con gli obiettivi dell'organizzazione per offrire la qualità e l'affidabilità dei carichi di lavoro cloud Voice.</li><li>Rivedere la [qualità delle chiamate di monitoraggio](monitor-call-quality-qos.md).</li><li> Implementare una strategia operativa per eseguire regolarmente le recensioni sulla qualità delle esperienze per verificare che la distribuzione di cloud Voice sia operativa alle sue capacità di picco.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mapping dei ruoli operativi

La pianificazione intrapresa per le operazioni durante la fase di previdenza è fondamentale, perché le attività operative iniziano quando sono abilitati i primi utenti pilota. Questa guida elenca le attività e le attività che devono essere eseguite su base giornaliera, settimanale, mensile o necessaria per mantenere una distribuzione di team di alta qualità. Questa guida fornisce informazioni e indicazioni su come eseguire queste attività e operazioni critiche.

Un componente cruciale di una distribuzione corretta consiste nel garantire che la pianificazione eseguita all'inizio della fase di previdenza includa la determinazione di chi sarà responsabile dell'esecuzione di attività specifiche. Dopo aver individuato le attività e le attività che si applicano alla distribuzione, è necessario che siano comprese e seguite dai gruppi o dagli individui assegnati.

Ogni team che identifichi deve rivedere e concordare le attività e le responsabilità identificate e iniziare la preparazione. Questo potrebbe includere formazione e disponibilità, fornendo aggiornamenti al piano di personale o assicurando che i provider esterni siano pronti per la distribuzione.

Le attività e i ruoli definiti in questa guida devono essere validi nella maggior parte degli scenari, ma ogni distribuzione dei team è univoca; di conseguenza, è possibile usare questa guida come punto di partenza per personalizzare le attività e i ruoli predefiniti per soddisfare le proprie esigenze.

Assicurarsi che ogni team responsabile abbia una buona conoscenza delle attività necessarie per eseguire il servizio. È fondamentale che ogni team accetti e firmi le proprie responsabilità nell'organizzazione prima che inizi il primo pilota.

Dopo aver effettuato un contratto, i team corrispondenti dovrebbero iniziare a operazionalizzare i ruoli.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td>
<td><ul><li>Usare questo documento per facilitare l'esercizio di mapping dei ruoli operativi.</li><li>Riunione con i rispettivi team di supporto per assegnare nomi a ogni voce nell'elenco delle attività richieste.</li><li>Ottenere accettazione o disconnessione nei ruoli assegnati.</li><li>Assicurarsi che i team corrispondenti dispongano della formazione, della disponibilità e delle risorse appropriate per completare le attività richieste.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dipendenze del servizio Teams

Microsoft teams raggruppa tecnologie in Microsoft 365 o Office 365 per creare un hub per il lavoro di gruppo. Gli esempi includono:

-   Azure Active Directory (Azure AD) offre servizi di autenticazione e autorizzazione per i team.

-   Exchange Online offre funzionalità avanzate come il blocco legale e l'e-Discovery.

-   SharePoint Online offre la possibilità di condividere file nei canali e OneDrive for business offre un meccanismo per la condivisione di file all'interno di una chat privata.

Le organizzazioni possono anche sfruttare gli investimenti esistenti nell'infrastruttura locale. Ad esempio, gli account Active Directory locali esistenti possono essere usati per l'autenticazione sfruttando Azure AD Connect. È possibile usare alcune versioni di Exchange Server al posto di Exchange Online.

Queste tecnologie si uniscono per creare una famiglia di comunicazioni intelligente, ricca e collaborativa per gli utenti. Questa stretta integrazione è un vantaggio chiave per i team, ma guida anche un requisito per la gestione dei servizi in queste tecnologie.

Questa guida illustra le aree principali dello stato di attivazione per gestire il servizio teams. È molto probabile che siano previsti piani di gestione dei servizi per le tecnologie di supporto da cui dipende teams. In caso contrario, è necessario stabilire piani di gestione dei servizi appropriati per i componenti della tecnologia (sia online che locale). In questo modo gli utenti potranno godere di un'esperienza affidabile e di alta qualità con i team.

#### <a name="references"></a>Riferimenti 

[Panoramica di Microsoft Teams](teams-overview.md)

[Interazione tra Exchange e Microsoft Teams](exchange-teams-interact.md)

[Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams](sharepoint-onedrive-interact.md)

[Coesistenza e interoperabilità di Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Attività Guida operativa

Le sezioni seguenti forniscono una panoramica delle attività necessarie per il corretto funzionamento del servizio Microsoft teams. Includono riferimenti ad strumenti, informazioni contestuali e contenuti aggiuntivi per aiutarti a comprendere l'attività e ad aiutarti in iniziative di preparazione.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorare l'integrità dei servizi

È importante comprendere l'integrità complessiva del servizio Microsoft teams, in modo da poter avvisare proattivamente gli altri utenti dell'organizzazione di qualsiasi evento che influisce sul servizio. Come descritto in precedenza, teams dipende da altri servizi Microsoft 365 o Office 365, ad esempio Azure Active Directory, Exchange Online, SharePoint Online e OneDrive for business. Per questo motivo, è ugualmente importante monitorare l'integrità dei servizi dipendenti.

Incorporare questa attività nel processo di gestione degli incidenti per informare in modo proattivo gli utenti, l'helpdesk e i team operativi per prepararsi a gestire le escalation degli utenti.

Nelle sezioni seguenti vengono descritti gli strumenti che è possibile sfruttare per monitorare gli [eventi imprevisti del servizio](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) che influiscono sul servizio teams. Un riepilogo dei vantaggi di ogni strumento e quando è necessario utilizzarne uno è incluso nella tabella seguente.

| Strumento di monitoraggio                       | Vantaggi                                            | Quando usare                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Interfaccia di amministrazione di Microsoft 365                     | Disponibile da qualsiasi dispositivo con un browser supportato. | USA quando non hai bisogno di notifiche in tempo reale.                                          |
| App di amministrazione di Microsoft 365 o Office 365                  | Fornisce notifiche push al dispositivo mobile.  | USA quando devi ricevere notifiche sugli incidenti del servizio mentre sei in viaggio.                  |
| Microsoft System Center               | Integrazione con Microsoft System Center.           | Usare quando sono necessarie funzionalità di monitoraggio avanzate e supporto delle notifiche.                       |
| API di Communications Service di Microsoft 365 o Office 365 | Accesso a livello di programmazione a Microsoft 365 o Office 365 Service Health.   | Usare quando è necessaria l'integrazione con uno strumento di monitoraggio di terze parti o si vuole creare una soluzione personalizzata. |

> [!NOTE]
> Solo gli utenti a cui è assegnato il ruolo di amministratore **globale** o di **amministrazione del servizio** possono visualizzare l'integrità dei servizi.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoraggio con l'interfaccia di amministrazione di Microsoft 365

L'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com/) offre un [dashboard di integrità dei servizi](https://portal.office.com/adminportal/home#/servicehealth) in cui è possibile visualizzare l'integrità corrente del servizio teams oltre ai servizi dipendenti.

### <a name="monitoring-with-the-mobile-app"></a>Monitoraggio con l'app per dispositivi mobili

L'app di amministrazione Microsoft 365 o Office 365 è disponibile in Apple iOS, Android e Windows (PC e dispositivi mobili). L'app fornisce agli amministratori dei servizi informazioni sull'integrità dei servizi e sulle modifiche imminenti. L'app supporta le notifiche push che possono avvisarti quasi subito dopo la pubblicazione di un Advisory. In questo modo è possibile mantenere aggiornati lo stato, l'integrità e le eventuali modifiche imminenti al servizio. Il supporto delle notifiche rende lo strumento di monitoraggio consigliato per gli amministratori. Per altre informazioni, vedere:

[App per dispositivi mobili amministratore di Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Scaricare l'app di amministrazione di Office 365 per dispositivi mobili](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoraggio con Microsoft System Center

Microsoft System Center è una piattaforma di gestione integrata che consente di gestire i Data Center, i dispositivi client e gli ambienti IT di cloud ibrido. Gli amministratori di Office 365 che usano System Center ora hanno la possibilità di importare il Management Pack di Office 365, che consente loro di visualizzare tutte le comunicazioni dei servizi all'interno di Operations Manager in System Center. L'uso di questo strumento consente di accedere allo stato dei servizi sottoscritti, agli eventi di servizio attivi e risolti e alle comunicazioni del centro messaggi (modifiche imminenti). Per altre informazioni, vedere il post di [Blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)seguente.

Se si leverage System Center per monitorare l'integrità dei servizi di Teams (e i servizi dipendenti), è possibile personalizzare ulteriormente il Management Pack per avvisare o avvisare specifici gruppi o individui che sono stati identificati per rispondere agli incidenti.
Questi gruppi possono includere i proprietari dei servizi, gli helpdesk, i gruppi di supporto di secondo livello e di terzo livello e i responsabili degli incidenti nell'organizzazione.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoraggio per scenari avanzati

È possibile monitorare l'integrità dei servizi e le modifiche imminenti sfruttando l'API di Communications Service di Office 365 per accedere all'integrità del servizio di Office 365 e alle modifiche a livello di codice. Usare questa API per creare uno strumento di monitoraggio personalizzato o connettere gli strumenti di monitoraggio esistenti alle comunicazioni di servizio di Office 365, semplificando in modo potenzialmente il monitoraggio dell'ambiente. Per altre informazioni, vedere [Office 365 per gli sviluppatori Enterprise](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/necessarie

| Attività               | Descrizione                                                                                                                                                                                                               | Cadenza   | Team assegnato |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorare l'integrità dei servizi | Monitorare in modo proattivo il servizio integrità dei servizi Microsoft teams, (e i servizi dipendenti) usando gli strumenti disponibili. I servizi dipendenti includono: Exchange Online, SharePoint Online, OneDrive for business, Azure Active Directory. | In tempo reale |               |
| Notifica degli incidenti  | Segnalare agli stakeholder interni gli eventi che influiscono sul servizio teams. Gli stakeholder interni possono includere utenti, helpdesk e gestori di eventi.                                                                          | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[Come controllare l'integrità dei servizi di Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificare l'integrità dei servizi per Microsoft Teams](service-health.md)

[Integrità e continuità dei servizi](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gestire le modifiche dell'organizzazione

Microsoft teams è un servizio basato su cloud. Con questo viene la possibilità di apportare nuove funzionalità e funzionalità a un ritmo rapido. La realizzazione di un'innovazione continua offre un evidente vantaggio per le organizzazioni, ma queste modifiche devono essere gestite in modo appropriato all'interno dell'organizzazione per evitare che l'utente abbia resistenze o escalation all'helpdesk.

Gli aggiornamenti dei team vengono distribuiti automaticamente agli utenti. Gli utenti avranno sempre il client e le funzionalità più recenti disponibili nel servizio teams. Non è possibile gestire l'implementazione degli aggiornamenti di teams agli utenti, pertanto è importante gestire la modifica attraverso programmi di comunicazione, formazione e adozione efficaci. Se gli utenti sono a conoscenza della modifica, hanno colto i vantaggi e hanno il potere di sfruttare le nuove funzionalità &mdash; che sapranno adattare più rapidamente e accogliere positivamente la modifica.

### <a name="monitoring-for-change"></a>Monitoraggio per la modifica

Il primo passaggio della gestione delle modifiche sta monitorando le modifiche pianificate per i team. L'origine migliore per il monitoraggio di queste modifiche è la [Roadmap di Office 365](https://products.office.com/business/office-365-roadmap), che elenca le caratteristiche attualmente in fase di sviluppo, che vengono distribuite ai clienti o che sono state completamente avviate. Puoi cercare funzionalità specifiche per i team usando il filtro fornito oppure scaricare la roadmap in un file di Excel per un'ulteriore analisi. Per ogni caratteristica, la roadmap fornisce una breve descrizione, insieme alla data di rilascio prevista.

Nel [Blog di Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)è possibile conoscere le procedure consigliate, le tendenze e le notizie sugli aggiornamenti del prodotto teams. Aspettiamo di trovare gli aggiornamenti principali delle funzionalità per i team da annunciare qui. Puoi anche sottoscrivere il blog tramite un feed RSS. È quindi possibile aggiungere [il feed RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) direttamente a un canale di teams, in modo che tutte le notizie importanti vengano consegnate direttamente all'interno dei team.

Tutte le caratteristiche rilasciate sono documentate nelle [Note sulla versione per Microsoft teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Qui troverai un elenco delle caratteristiche rilasciate per i dispositivi desktop, Web e mobile. Lo stesso set di note sulla versione è disponibile anche nella scheda **novità** della [Guida](get-help-in-microsoft-teams.md).

Acquisire familiarità con le risorse disponibili e assicurarsi di assegnare i proprietari applicabili per monitorare la modifica.

### <a name="planning-for-change"></a>Pianificazione della modifica

Ora che sei a conoscenza delle prossime modifiche al servizio teams, il passaggio successivo consiste nel preparare e pianificare di conseguenza. Valutare ogni modifica per determinare quali modifiche richiedono la comunicazione agli utenti, alle campagne di sensibilizzazione, alla formazione per i team o agli utenti di supporto o alle campagne di valutazione e adozione delle funzionalità. Questo è il ruolo principale di un team di gestione delle modifiche nell'organizzazione. Di seguito è riportata una raccolta di tabelle di esempio che consentono di pianificare la modifica.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Caratteristica: registrazione cloud (data di rilascio: 2018 gennaio)

**Traccia generale**

| Modificare la conformità | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Revisione legale   | Completato     | Questa caratteristica è un prerequisito per l'onboard del team di formazione. | Team di progetto  |

**Gestione delle modifiche tecniche**

|       Modificare la conformità       | Stato |                      Note/passaggi successivi                      |    Proprietario     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Modifiche necessarie      |  Sì   | L'amministratore deve abilitare la registrazione solo per gli utenti identificati. | Team di supporto |
| Preparazione tecnica completata |  Sì   |                                                            | Team di supporto |
|                              |        |                                                            |              |

**Gestione delle modifiche degli utenti** 

| Modificare la conformità | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Impatto dell'utente                  | Bassa                  |                                                                 |                        |
| Richiesta di conformità degli utenti      | Sì                  |                                                                 |                        |
| Comunicazioni pronte         | No                   | Il messaggio di posta elettronica di comunicazione è stato redatto: revisione in sospeso.            | Team comunicazioni    |
| Formazione pronta               | Sì                  | La formazione sfrutterà il video Microsoft esistente.                | Team di formazione          |

**Indicatore di stato**

| Modificare la conformità | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Stato rilascio               | in corso          | Revisione in sospeso da sponsor esecutivo.               | Team di gestione delle modifiche |
| Rilasciare il segno di disconnessione             |                      |                                                                 |                        |
| Data di rilascio                 |                      |                                                                 |                        |

Per altre informazioni sulla pianificazione della gestione delle modifiche con i team, vedere [creare una strategia di gestione delle modifiche per Microsoft teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/necessarie

| Attività               | Descrizione                                                                                                                                                                                                                | Cadenza   | Team assegnato |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorare la modifica     | Monitorare le modifiche imminenti al servizio Microsoft teams.                                                                                                                                                                   | Quotidiana     |               |
| Pianificazione della modifica    | Valutare e pianificare le nuove caratteristiche e funzionalità, inclusi i piani di comunicazione, le campagne di sensibilizzazione e la formazione.                                                                                                     | In base alle esigenze |               |
| Disponibilità degli utenti             | Eseguire campagne di comunicazione, sensibilizzazione o formazione mirate per garantire che gli utenti siano pronti per la modifica imminente.                                                                                                        | In base alle esigenze |               |
| Supporto della disponibilità del team | Eseguire campagne di comunicazione, sensibilizzazione o formazione mirate per garantire che il team di supporto sia pronto. I team di supporto possono includere il team "guanto bianco", gli helpdesk, il supporto di Tier 2 o Tier 3, i partner esterni e così via. | In base alle esigenze |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Valutare l'utilizzo di Teams

Dopo l'avvio del progetto pilota iniziale, è fondamentale stabilire una cadenza regolare per misurare l'utilizzo effettivo dei team. Questo consente all'organizzazione di acquisire informazioni approfondite sul modo in cui l'utilizzo effettivo viene allineato con l'utilizzo previsto durante la fase di previsione. Anche se questa sezione si basa sull'utilizzo di teams, questo dovrebbe essere incluso in uno sforzo più ampio per misurare e valutare l'utilizzo complessivo di Office 365.

La revisione dell'uso frequente all'inizio della distribuzione offre la possibilità di:

-   Verificare se gli utenti usano teams.

-   Identificare le potenziali sfide per l'adozione prima di creare problemi critici nell'organizzazione.

-   Capire se esistono discrepanze tra i requisiti di fase di prevedibilità e l'utilizzo effettivo.

Se l'utilizzo non è quello previsto, potrebbe essere dovuto a un problema di distribuzione o il piano di adozione non viene eseguito correttamente o un altro problema. A seconda del motivo effettivo dietro l'utilizzo ridotto, l'amministratore del servizio deve collaborare con i team correlati per rimuovere le barriere d'uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Misurazione dell'utilizzo con l'interfaccia di amministrazione di Microsoft 365

I dati sull'utilizzo di teams sono disponibili nel dashboard di Reporting. I dati di utilizzo dei team possono essere trovati in tre diversi report. Il primo report offre una visualizzazione incrociata del modo in cui gli utenti comunicano e collaborano usando i vari servizi in Office 365. Questo report può essere trovato qui: [report utenti attivi di Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Gli altri due report sono specifici per i team e contengono ulteriori dettagli sull'utilizzo dei team da un punto di vista dell'utente e del dispositivo. Entrambi i report possono essere trovati qui:

[Report sull'utilizzo di dispositivi Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Report attività utente di Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Autorizzazioni necessarie

I report sull'utilizzo nell'interfaccia di amministrazione possono essere raggiunti da persone a cui è stato assegnato un ruolo di **amministratore globale** o da un ruolo di amministratore specifico del prodotto (**amministratore di Exchange**, **amministratore di Skype for business**, **amministratore di SharePoint**).

Inoltre, il ruolo **lettore report** è disponibile per gli utenti che richiedono l'accesso ai report, ma non eseguono attività che richiedono autorizzazioni a livello di amministratore. Si assegna questo ruolo per specificare i report sull'utilizzo per tutti i soggetti interessati, per monitorare e guidare l'adozione. Per altre informazioni sui diversi ruoli disponibili, vedere [informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Valutazione dell'utilizzo

Dopo aver usato il dashboard di Reporting per misurare l'uso, è importante confrontare l'uso misurato con gli indicatori key success (KSIs) definiti durante la fase di predisposizione del progetto. Puoi definire un KSI che può essere definito come uso attivo o uno collegato indirettamente all'uso attivo.

È importante identificare eventuali variazioni tra l'utilizzo effettivo e quello pianificato prima di riprendere l'implementazione in altri siti o utenti. È probabile che tu possa identificare le informazioni organizzative nell'ambito di questa attività che puoi sfruttare per verificare che il prossimo batch di siti o utenti non riscontri gli stessi problemi.

Prima di tutto, individuare se si tratta di un'adozione o di un problema tecnico. Iniziare esaminando gli elementi seguenti, in ordine, per determinare dove si trova il problema.

1.  Convalidare la qualità eseguendo una revisione di qualità dell'esperienza (vedere [migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md) per maggiori dettagli).

2.  Collaborare con il team dell'helpdesk per verificare che non ci siano problemi tecnici di tendenza che impediscono agli utenti di accedere o usare il servizio. Se esistono le tendenze del problema, usare la sezione [risoluzione dei problemi di endpoint](#endpoint-troubleshooting) più avanti in questo articolo per provare a risolvere il problema prima di coinvolgere il supporto.

3.  Collaborare con il team di formazione e adozione per raccogliere il feedback diretto degli utenti (vedere [valutare i sentimenti degli](#assess-user-sentiment) utenti più avanti in questo articolo) e verificare l'efficacia delle attività di sensibilizzazione e adozione.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/necessarie

| Attività                         | Descrizione                                                                                                                      | Cadenza   | Team assegnato |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Uso della misura (fase di abilitazione) | Misurare e valutare l'utilizzo dei team mentre i siti continuano a essere onboarded durante la fase di abilitazione. Risolvere i problemi di utilizzo come richiesto. | Settimanale    |               |
| Uso delle misure (fase valore unità)                           | Misurare e valutare l'utilizzo dei team nella fase valore unità (al termine della distribuzione). Risolvere i problemi di utilizzo come richiesto. | Bisettimanale  |               |
| Aggiornare il piano di adozione             | Aggiornare il piano di adozione in base al confronto tra l'uso misurato e gli obiettivi di pianificazione.                                         | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[Informazioni sull'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Report attività nell'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Valutare il sentimento degli utenti

La comprensione del sentimento degli utenti può fungere da indicatore chiave per misurare il successo della distribuzione dei team. Il feedback degli utenti può guidare le modifiche nell'organizzazione; Questo potrebbe includere modifiche ai piani di comunicazione, ai programmi di formazione o al modo in cui offri il supporto agli utenti.

È importante ricevere feedback precocemente e continuare a valutare il sentimento degli utenti in tutto il ciclo di vita del progetto e non solo. Usare le indicazioni seguenti per determinare l'intervallo in cui l'organizzazione cercherà il feedback:

-   **Inizio del progetto**: valutando il sentimento degli utenti all'inizio del progetto, è possibile ottenere una visione iniziale del modo in cui gli utenti sentono l'esperienza dei team.

-   **Dopo le principali attività cardine**: raccogliendo feedback in tutto il ciclo di vita del progetto, è possibile valutare il sentimento degli utenti su base continuativa e apportare le modifiche necessarie. Questo è particolarmente utile dopo importanti attività cardine.

-   **Conclusione del progetto**: valutare il sentimento degli utenti alla fine di un progetto ti dirà quanto hai fatto e dove deve essere ancora fatto il lavoro e ti permettono di confrontare i risultati con il sondaggio precedente.

-   **Continuo: continuare**a misurare il sentimento degli utenti a tempo indeterminato. Le modifiche apportate ai sentimenti degli utenti potrebbero essere dovute alle modifiche apportate all'ambiente dell'organizzazione o alle modifiche nel servizio teams. Misurando i sentimenti degli utenti a intervalli regolari, è possibile capire in che modo i team di gestione dei servizi stanno eseguendo e in che modo l'organizzazione risponde alle modifiche apportate al servizio teams.

Il sentimento degli utenti può essere valutato tramite molti metodi diversi. Possono includere sondaggi tramite posta elettronica, interviste di tipo in-persona o telefono oppure semplicemente creare un canale di feedback in teams o Yammer. Per altre informazioni, vedere [procedure consigliate per i metodi di feedback degli utenti in Microsoft teams](best-practices-feedback.md).

Puoi anche usare un approccio dell'intero settore per valutare il sentimento degli utenti chiamato NET Promotor Score (NPS), descritto nella sezione seguente.

### <a name="nps"></a>NPS 

NET Promoter Score (NPS) è una metrica di fidelizzazione dei clienti di dell'intero settore e un buon approccio da usare per valutare il sentimento degli utenti. I server dei criteri di gruppo possono essere calcolati ponendo due domande: "con quale probabilità si consiglia di consigliare team a un collega?", seguito dalla domanda a mano libera, "perché?"

NPS è un indice, che va da-100 a 100, che misura la volontà del cliente di consigliare il prodotto o il servizio di una società. NPS si basa su un sondaggio anonimo che viene recapitato agli utenti tramite posta elettronica o altri mezzi elettronici. NPS misura la lealtà tra un provider e un utente. È costituito da una sola domanda, che chiede agli utenti di valutare l'esperienza da 1 a 10, con l'opzione di fornire ulteriori commenti. Gli utenti vengono quindi classificati in base alle valutazioni seguenti:

-   9 o 10 sono promotori: entusiasti leali che promuovono il servizio e ne alimentano altri.

-   7 o 8 sono passivi: soddisfatti ma non entusiasti, vulnerabili a un altro servizio o a un'offerta.

-   Da 1 a 6 sono detrattori: clienti insoddisfatti che possono danneggiare il servizio e impedire la crescita.

![Diagramma che illustra la scala NPS](media/operate-my-service-image2.png "Questo diagramma mostra la scala NPS. Mostra che le classifiche da 0 a 6 sono detrattori, da 7 a 8 passivi e da 9 a 10 promotori.")

Anche se il numero di NPS di base è utile, otterrai il valore massimo analizzando i commenti degli utenti. Ti aiuteranno a comprendere il motivo per cui l'utente non consiglia i team ad altri. Questi commenti possono fornire un valido feedback per consentire ai team di gestione di progetti o servizi di comprendere le modifiche necessarie per fornire un servizio di qualità.

Per creare sondaggi NPS per l'organizzazione, è possibile sfruttare lo strumento di sondaggio online preferito.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/in base alle esigenze

| Attività              | Descrizione                                                                                                                                                                         | Cadenza   | Team assegnato |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Valutare il sentimento degli utenti | Acquisire e valutare il sentimento degli utenti usando sondaggi o interviste o tramite un canale di feedback in teams o Yammer.                                                                 | In base alle esigenze |               |
| Aggiornare i piani di adozione | Modifica dell'unità nell'organizzazione in base al feedback degli utenti; Questo può includere modifiche ai piani di comunicazione, ai programmi di formazione o al modo in cui offri il supporto agli utenti. | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[Score Net Promoter](https://en.wikipedia.org/wiki/Net_Promoter)

[Uso di Yammer per raccogliere commenti e suggerimenti](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Procedure consigliate per il feedback degli utenti](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gestire la qualità della rete

Molti elementi di pianificazione di base vengono ottimizzati, dimensionati a destra e correttivi nell'infrastruttura di rete per garantire un percorso efficiente di alta qualità per il servizio Microsoft teams. Le attività di pianificazione e i requisiti sono coperti dalle indicazioni per la [conformità della rete](3-envision-evaluate-my-environment.md#network-readiness) . Le reti si evolvono spesso nel tempo a causa di aggiornamenti, espansioni o altri requisiti aziendali. È importante tenere conto dei requisiti per i team nelle attività di pianificazione della rete.

Anche se la pianificazione della rete è un aspetto cruciale della distribuzione di teams, è ugualmente importante garantire che la rete rimanga in buona salute e rimanga aggiornata, in base alla modifica dei requisiti aziendali o tecnici.

Per garantire l'integrità della rete, è necessario eseguire una serie di attività operative a intervalli regolari.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/necessarie

| Attività                                                       | Descrizione                                                                                                                                                                                                                                                                                                                                                                 | Cadenza                | Team assegnato |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Monitorare gli URL e gli indirizzi IP di Office 365                                | Monitorare le eventuali modifiche apportate agli [intervalli di URL e indirizzi IP di Office 365](https://aka.ms/o365ips) tramite il [feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fornito e avviare una richiesta di modifica ai gruppi di rete applicabili.                                                                                                                                | Quotidiana                  |               |
| Aggiornare la rete in base alle modifiche apportate agli indirizzi IP e agli URL di Office 365 | Apportare aggiornamenti ai componenti di rete applicabili (firewall, server proxy, VPN, firewall lato client e così via) per riflettere le modifiche apportate agli [URL e agli intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips).                                                                                                                                                              | In base alle esigenze              |               |
| Fornisci dati della creazione                                          | Fornisci informazioni di subnet aggiornate al campione di qualità (o alle parti interessate) per assicurarti che le [definizioni edilizie in Call Quality dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) vengano mantenute aggiornate. | In base alle esigenze              |               |
| Implementare la modifica                                               | Implementare le modifiche nella rete per supportare la modifica dei requisiti tecnici e aziendali per i team. Gli elementi di rete possono includere:<ul><li>Firewall</li><li>VPN</li><li>Reti cablate e Wi-Fi</li><li>Connettività Internet e ExpressRoute</li><li>DNS</li></ul>     | In base alle esigenze              |               |
| Monitoraggio e creazione di report di rete                               | Monitorare la fine della rete per la disponibilità, l'utilizzo e le tendenze della capacità utilizzando gli strumenti di gestione della rete di terze parti esistenti e le funzionalità di creazione di report disponibili nei provider di rete. Usare i dati di tendenza per la pianificazione della capacità di rete.                                                                                                            | Giornaliera, settimanale, mensile |               |
| Pianificazione della capacità                                              | Collaborare con i proprietari del servizio teams per comprendere la modifica dei requisiti aziendali e tecnici che potrebbero guidare ulteriori modifiche alla capacità.                                | In base alle esigenze              |               |
| Risoluzione dei problemi di rete e correzione                        | Aiutare gli helpdesk team, i proprietari dei servizi e i principali stakeholder per risolvere i problemi relativi alla connettività, all'affidabilità o alla qualità del team. Gli elementi di rete possono includere:<ul><li>Firewall</li><li>VPN</li><li>Reti cablate e Wi-Fi</li><li>Connettività Internet e ExpressRoute</li><li>DNS</li></ul>    | In base alle esigenze              |               |
| Ripristino di emergenza e test di disponibilità elevata                | Eseguire regolari test per la disponibilità elevata e il ripristino di emergenza nell'infrastruttura di rete per verificare che soddisfi gli obiettivi del livello di servizio (SLOs) o i contratti di servizio per il servizio teams.                                                                                                                                                  | Mensile                |               |


### <a name="references"></a>Riferimenti 

[URL e intervalli di indirizzi IP per Office 365](https://aka.ms/o365ips)

[Schema dati della creazione](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Valutare e garantire la qualità 

Tutte le organizzazioni hanno bisogno di un gruppo o di un individuo per essere responsabili della qualità. Questo è il ruolo più importante nella gestione dei servizi. Il ruolo di campione di qualità viene assegnato a una persona o un gruppo appassionato dell'esperienza degli utenti.
Questo ruolo richiede le competenze necessarie per identificare le tendenze nell'ambiente e la sponsorizzazione per collaborare con altri team per gestire i correttivi. Il candidato migliore per il campione di qualità è in genere il proprietario del servizio clienti. A seconda delle dimensioni e della complessità dell'organizzazione, potrebbe essere una persona o un gruppo con una passione per garantire un'esperienza utente di alta qualità.

Il campione della qualità sfrutta gli strumenti esistenti e i processi documentati, come Call Quality Dashboard (Call Quality Dashboard), per monitorare l'esperienza degli utenti, identificare le tendenze di qualità e correggere le esigenze.
Il campione di qualità dovrebbe collaborare con i rispettivi team per eseguire azioni correttive e segnalare a un comitato direttivo informazioni sullo stato di avanzamento e su eventuali problemi aperti.

Leggere [migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md), che descrive include attività che valutano e supportano le indicazioni per il risanamento in aree chiave che hanno un impatto maggiore sul miglioramento dell'esperienza utente. Le linee guida fornite in questo articolo si riferiscono all'uso di Call Quality dashboard come strumento principale per segnalare e analizzare ogni area, con un particolare interesse per l'audio per massimizzare l'adozione e l'impatto. Le eventuali ottimizzazioni apportate alla rete per migliorare l'esperienza audio si traducono anche direttamente nei miglioramenti della condivisione di video e desktop.

Ti consigliamo vivamente di nominare il campione di qualità in anticipo. Dopo essere stati nominati, dovrebbero iniziare a familiarizzarsi con il contenuto della [qualità delle chiamate di monitoraggio](monitor-call-quality-qos.md) e i materiali di formazione associati.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/necessarie

| Attività                               | Descrizione                                                                                                                                                                                                                                                                                                 | Cadenza                             | Team assegnato |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nominare e formare campioni di qualità | Nominare e formare un campione di qualità.                                                                                                                                                                                                                                                                   | In base alle esigenze                           |               |
| Eseguire recensioni di qualità delle esperienze (QERs)     | Eseguire una QER per identificare le tendenze di qualità e affidabilità, rivederle con obiettivi definiti e segnalarle ai principali stakeholder dell'organizzazione.                                                                                                                            | Mensile (settimanale durante le distribuzioni) |               |
| Correzione delle unità                      | Coordina gli sforzi di correzione per l'intera organizzazione in base alle valutazioni e ai risultati di QER.                                                                                                                                                                                                           | In base alle esigenze                           |               |
| Aggiornare i dati della creazione in Call Quality dashboard            | Aggiornare o aggiungere nuove definizioni di edificio in Call Quality dashboard quando vengono apportate modifiche alla rete (vedere [caricare le informazioni sull'edificio](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | In base alle esigenze                           |               |
| Riempire il ruolo di campione di qualità      | Responsabilità end-to-end per la qualità nell'organizzazione. Ciò include:<ul><li>Verificare che QER sia stato eseguito regolarmente.</li><li>Segnalare i principali stakeholder per lo stato di qualità.</li><li>Verificare che le definizioni dei dati dell'edificio siano aggiornate.</li><li>Coordinare gli sforzi di bonifica nell'organizzazione per garantire agli utenti un'esperienza di alta qualità con i team.</li></ul>          | Quotidiana                               |               |



### <a name="references"></a>Riferimenti 


[Caricare i dati del tenant e della creazione in Call Quality dashboard](CQD-upload-tenant-building-data.md)

[Migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gestire gli endpoint

Gli endpoint di Microsoft teams possono essere definiti come qualsiasi PC, Mac, tablet o dispositivo mobile (o qualsiasi altro) che esegua il client teams. Il termine *endpoint* non solo include il dispositivo stesso, ma il modo in cui un utente si connette al dispositivo, ad esempio usando il microfono o l'altoparlante incorporato del dispositivo, gli auricolari o un auricolare ottimizzato. Dopo la distribuzione, gli endpoint non devono essere dimenticati. Gli endpoint teams richiedono assistenza e manutenzione continua. Le sezioni seguenti descrivono aree specifiche in cui concentrarsi.

### <a name="endpoint-requirements"></a>Requisiti endpoint

Uno dei vantaggi principali di teams è che il client è mantenuto aggiornato automaticamente. I client del PC e del Mac vengono aggiornati usando un processo in background che verifica la ricerca di nuove compilazioni e Scarica il nuovo client quando l'app è inattiva. Le app teams per dispositivi mobili vengono mantenute aggiornate nei rispettivi negozi di app.

Il client Teams ha requisiti minimi in termini di piattaforma software sottostante. Questi requisiti potrebbero cambiare nel tempo e quindi è importante monitorarli per le modifiche. Ad esempio, il client Teams ha una versione minima di iOS. Se il client usa un browser Internet, anche il browser deve essere mantenuto aggiornato. Un elenco di piattaforme supportate può essere trovato in [ottenere client per Microsoft teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewall endpoint

I firewall lato client possono avere un impatto significativo sull'esperienza utente.
I firewall lato client possono influire sulla qualità delle chiamate e persino impedire la creazione di una chiamata. Dopo aver configurato le opportune esclusioni sul firewall client, è necessario mantenerle aggiornate in base alle informazioni contenute negli [URL e negli intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips). Il fornitore di terze parti avrà indicazioni specifiche su come aggiornare le esclusioni.

### <a name="wi-fi-drivers"></a>Driver Wi-Fi

I driver Wi-Fi potrebbero essere problematici. Ad esempio, un driver potrebbe avere comportamenti di roaming molto aggressivi tra i punti di accesso in grado di indurre una commutazione di Access Point non necessaria, con una qualità di chiamata scadente. Un driver Wi-Fi con prestazioni scarse potrebbe essere scoperto attraverso una valutazione della qualità dell'esperienza (vedere [migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md) per maggiori dettagli). È essenziale implementare un processo basato sulla qualità che monitora i nuovi driver Wi-Fi e assicura che siano testati prima di essere distribuiti nel popolamento generale degli utenti.

### <a name="endpoint-management"></a>Gestione endpoint

Un catalogo di endpoint e dispositivi di interfaccia supportati, ad esempio auricolari, deve essere disponibile e mantenuto. Questo catalogo includerà un elenco dei dispositivi approvati selezionati e convalidati come parte delle fasi di visualizzazione e di bordo. In genere, i dispositivi specifici vengono selezionati per ogni tipo di persona nell'organizzazione per soddisfare le esigenze degli attributi di tale persona. Tutti gli endpoint hanno un ciclo di vita ed è necessario gestire i contratti fornitore, la garanzia, la sostituzione, la distribuzione e i criteri di ripristino associati a questi dispositivi.

### <a name="endpoint-troubleshooting"></a>Risoluzione dei problemi di endpoint

Anche se sono state seguite le indicazioni precedenti, gli utenti dell'organizzazione potrebbero essere ancora in difficoltà con i team. Anche se il problema potrebbe non essere l'endpoint stesso, i sintomi del problema vengono in genere riportati all'utente tramite il client. Le linee guida seguenti sono destinate a eseguire le operazioni generali che è possibile eseguire per risolvere il problema. non è destinata a essere una guida completa per la risoluzione dei problemi. I passaggi sono forniti in un ordine specifico, ma non devono essere seguiti esplicitamente e potrebbero non essere applicabili, a seconda della natura del problema.

1.  **Convalida integrità del servizio:** Il problema che un utente potrebbe provare può essere correlato a un evento che influisce negativamente sul servizio teams o sui servizi dipendenti. Come primo passo, ti consigliamo di confermare che non ci sono problemi di servizio attivo. Consultare [come controllare l'integrità dei servizi di Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Ricordarsi di controllare lo stato dei servizi dipendenti, ad esempio Exchange, SharePoint, OneDrive for business. Il monitoraggio dell'integrità dei servizi viene illustrato in modo più dettagliato nella sezione precedente, [monitora l'integrità dei servizi](#monitor-service-health).

2.  **Convalidare la connettività client:** I problemi di connettività causano problemi di funzionalità o di accesso in teams. È consigliabile (soprattutto per i nuovi siti o posizioni) che si convalida la connettività al servizio. Verificare che per ogni sito siano seguite le indicazioni seguenti per gli [URL e gli intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips) . Puoi sfruttare lo strumento di [valutazione della rete Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) per eseguire un test di connettività per verificare che le porte multimediali siano state aperte correttamente per le funzionalità di cloud Voice. I passaggi dettagliati su come eseguire i test di connettività vengono forniti nelle linee guida per la [conformità della rete](3-envision-evaluate-my-environment.md#network-readiness) .

3.  **Selezionare l'elenco dei problemi noti:** Consultare [risoluzione dei problemi relativi ai team](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) per determinare se l'utente è stato influenzato negativamente da uno di questi problemi. Seguire la soluzione alternativa fornita (se disponibile) per risolvere il problema.

4.  **Visitare la community di Microsoft teams:** La [community di Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) offre spazi dedicati per i team. La community teams fornisce un elenco di discussioni, post di Blog e annunci incentrati sui team. È possibile pubblicare una domanda o eseguire ricerche in discussioni precedenti per risolvere il problema.

5.  **Contattare il supporto tecnico Microsoft:** È possibile contattare il supporto tecnico Microsoft per problemi con teams online o tramite telefono. Per informazioni, vedere [contattare il supporto per i prodotti business](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).
    Per i clienti Premier, le richieste di supporto possono essere avviate seguendo le indicazioni [per contattare il supporto per Microsoft Teams (clienti Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/necessarie

| Attività                 | Descrizione                                                                                                                                                                                                                                                                                                                                                                     | Cadenza   | Team assegnato |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisiti endpoint    | Verificare che l'endpoint teams continui a soddisfare tutti i requisiti software per i team elencati in [ottenere client per Microsoft teams](get-clients.md).                                                                                                                                                                                       | Mensile   |               |
| Firewall endpoint       | Gestire le esclusioni appropriate nel firewall endpoint in base alle informazioni contenute negli [URL e negli intervalli di indirizzi IP di Office 365](https://aka.ms/o365ips). Il fornitore di terze parti avrà indicazioni specifiche su come mantenere le esclusioni. Sottoscrivere il [feed RSS](https://support.office.com/o365ip/rss) per ricevere automaticamente una notifica delle modifiche. | In base alle esigenze |               |
| Driver Wi-Fi            | Testare e aggiornare i driver Wi-Fi nel PC. Convalidare i risultati usando Call Quality Dashboard ([migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | In base alle esigenze |               |
| Gestione endpoint      | Gestire il catalogo di endpoint e dispositivi di interfaccia supportati, ad esempio auricolari. Gestire i contratti fornitore, la garanzia, la distribuzione, la sostituzione e i criteri di ripristino.                                                                                                                                                                                                        | Mensile   |               |
| Risoluzione dei problemi di endpoint | La risoluzione dei problemi può includere la verifica della connettività, l'elenco dei problemi noti, la raccolta del log, l'analisi e l'escalation del supporto Microsoft o di fornitori di terze parti.                                                                                                                                                                                               | In base alle esigenze |               |

### <a name="references"></a>Riferimenti 

[URL e intervalli di indirizzi IP per Office 365](https://aka.ms/o365ips)

[Ottenere i client per Microsoft Teams](get-clients.md)

[Community di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Verificare l'integrità dei servizi per Microsoft Teams](service-health.md)

[Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Contattare il supporto Premier](https://support.microsoft.com/premier/contacts)

[Risoluzione dei problemi relativi ai team video](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gestire Teams

Dopo la distribuzione del servizio Microsoft teams, è necessario eseguire diverse attività relative alla propria amministrazione. Le attività variano dall'amministrazione del servizio e dei singoli utenti alla pianificazione della capacità e al provisioning di licenze e numeri di telefono. Le sezioni seguenti includono alcune di queste attività comuni di amministrazione.

### <a name="service-administration"></a>Amministrazione del servizio

Il servizio teams include più impostazioni che possono essere configurate a livello di tenant.
Le modifiche apportate alle impostazioni del tenant influenzano tutti gli utenti abilitati per i team. Per un elenco dettagliato di queste impostazioni, vedere [gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md).

### <a name="user-administration"></a>Amministrazione utenti

Per supportare gli utenti, un'organizzazione può richiedere qualsiasi numero di attività correlate: le attività specifiche variano da un'organizzazione a quella successiva. In definitiva, queste attività devono essere gestite da un team di supporto a cui sono stati assegnati questi compiti operativi. Le attività seguenti sono in genere necessarie per supportare gli utenti in teams.

#### <a name="general-tasks"></a>Attività generali

[Gestire l'accesso degli utenti a Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Attività comuni per il sistema telefonico

[Assegnare, modificare o rimuovere il numero di telefono di un utente](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)

[Assegnare o modificare l'indirizzo per gli interventi di emergenza di un utente](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Attività comuni per i servizi di audioconferenza

[Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)

[Cambiare i numeri di telefono del bridge per i servizi di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Gestione delle licenze

Man mano che l'organizzazione cresce o si contrae, è importante pianificare le licenze per le esigenze attuali e future. È disponibile una licenza di base per i team, oltre a licenze per le funzionalità di cloud Voice ([sistema telefonico](here-s-what-you-get-with-phone-system.md) e servizi di [audioconferenza](https://products.office.com/skype-for-business/audio-conferencing)).

Per i team, le licenze del sistema telefonico richiedono licenze per i [piani di chiamata](calling-plan-landing-page.md) associate. Le licenze per i piani di chiamata consentono di effettuare e ricevere chiamate telefoniche nazionali e/o internazionali. Questi piani sono basati sull'uso e hanno associato minuti per i pool. Il provisioning dei crediti per le [comunicazioni](what-are-communications-credits.md) garantirà che non si esaurisca mai il servizio.

I servizi di audioconferenza consentiti per le conferenze telefoniche con accesso esterno a pedaggio e per le conferenze telefoniche esterne. I servizi di conferenza telefonica con accesso esterno a numero verde o gli scenari di chiamata in uscita non nazionali possono causare ulteriori addebiti per i quali sono necessari i crediti per le [comunicazioni](what-are-communications-credits.md) .

I crediti per comunicazioni possono integrare sia le licenze per il piano chiamante che i servizi di audioconferenza. Sia le licenze del piano di chiamata che i crediti per le comunicazioni sono basati sull'utilizzo e devono quindi essere monitorati e provisionati per conseguenza.

Puoi sfruttare il [report sull'utilizzo PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) per monitorare l'uso dei minuti del piano di chiamata e i crediti per le comunicazioni. In base ai risultati di questa attività, è possibile modificare la licenza di conseguenza. Presto sarà disponibile un report per i [pool di minuti PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) per facilitare l'assistenza per questa attività.

### <a name="telephone-number-management"></a>Gestione di numeri di telefono

Esistono due metodi per acquisire numeri in teams: è possibile trasferire i numeri di telefono da un altro provider oppure è possibile eseguire il provisioning dei numeri direttamente dall'inventario numerico Microsoft. Entrambi i metodi sono descritti in [recupero di numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md).

È previsto un limite per il numero di numeri di telefono che è possibile eseguire dall'inventario dei numeri di Microsoft. I limiti sono determinati da una serie di fattori dettagliati in [quanti numeri di telefono puoi ottenere?](how-many-phone-numbers-can-you-get.md).
I limiti dipendono dal tipo di numeri, ad esempio numeri di servizio gratuiti, numeri di servizio a pedaggio e numeri di abbonato (utente). Ognuno ha i propri limiti e deve essere gestito in modo indipendente. Se si sta avvicinando al limite (o si è raggiunto il limite), è possibile applicare un incremento al limite. Questo processo è descritto nell'articolo del paragrafo precedente.

In alcuni casi non è possibile eseguire il provisioning di un numero in un'area geografica in cui è disponibile il servizio. Per informazioni sul processo per la richiesta di numeri, vedere [gestire i numeri di telefono per l'organizzazione](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Creazione del team (facoltativo)

Per impostazione predefinita, tutti gli utenti con una cassetta postale in Exchange Online hanno le autorizzazioni per creare gruppi di Microsoft 365 e quindi un team in Microsoft teams. Se si vuole avere un controllo più stretto e [limitare la creazione di nuovi team](assign-roles-permissions.md#permissions-to-create-teams) (e quindi la creazione di nuovi gruppi Microsoft 365), è possibile delegare i diritti di creazione e gestione del gruppo a un set di amministratori. Se l'organizzazione vuole perseguire questa opzione, vedere il processo descritto in questo articolo per consentire agli utenti di inviare richieste elaborate da un team assegnato.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività quotidiane/settimanali/mensili/necessarie

| Attività                    | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                             | Cadenza   | Team assegnato |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Amministrazione del servizio      | Amministrazione di impostazioni team a livello di tenant.                                                                                                                                                                                                                                                                                                                                                                           | In base alle esigenze |               |
| Amministrazione utenti         | Amministrazione di impostazioni basate sull'utente e licenze in teams.                                                                                                                                                                                                                                                                                                                                                           | In base alle esigenze |               |
| Gestione delle licenze          | Pianificare le esigenze attuali e future per le licenze basate su utenti e consumi (piani di chiamata e crediti di comunicazione) sfruttando il report [utilizzo PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e i [pool di minuti PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Settimanale    |               |
| Gestione di numeri di telefono | Gestire i numeri di telefono disponibili per la crescita futura e regolare i livelli di inventario per soddisfare le esigenze dell'organizzazione.                                                                                                                                                                                                                                                                                                | Settimanale    |               |
| Creazione del team (facoltativo)    | Rivedere ed elaborare le richieste per la creazione del team.                                                                                                                                                                                                                                                                                                                                                                          | In base alle esigenze |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Migliorare e monitorare la qualità delle chiamate

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md) include un set di attività che valutano e includono indicazioni per il risanamento in aree chiave che hanno un impatto maggiore sul miglioramento dell'esperienza utente, come illustrato di seguito.

![Diagramma delle aree da esaminare durante una revisione della qualità dell'esperienza](media/plan-my-service-management-image2.png "Le aree principali da esaminare durante una revisione di qualità dell'esperienza: audio, affidabilità e risultati del sondaggio degli utenti.")

Valutando e rimediando continuamente le aree descritte nella Guida, è possibile ridurre le proprie potenzialità per influire negativamente sull'esperienza utente. La maggior parte dei problemi di esperienza utente incontrati in una distribuzione può essere raggruppata nelle categorie seguenti:

-   Firewall o configurazione proxy incompleta

-   Scarsa copertura Wi-Fi

-   Larghezza di banda insufficiente

-   VPN

-   Uso di dispositivi audio non ottimizzati o incorporati

-   Subnet problematiche o dispositivi di rete

Le indicazioni fornite in [migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md) si basano sull'uso di Call Quality Dashboard (Call Quality Dashboard) online come strumento principale per segnalare e analizzare ogni area descritta, con un particolare interesse per l'audio per massimizzare l'adozione e l'impatto. Le eventuali ottimizzazioni apportate alla rete per migliorare l'esperienza audio si traducono anche direttamente nei miglioramenti della condivisione di video e desktop.

Ti consigliamo vivamente di nominare il campione di qualità in anticipo. Dopo essere stati nominati, dovrebbero iniziare a familiarizzare con il contenuto [per migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md).

<!--ENDOFSECTION-->
