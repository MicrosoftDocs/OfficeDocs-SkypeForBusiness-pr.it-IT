---
title: Guida al funzionamento per Microsoft Teams
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Attività e attività necessarie per la gestione dei servizi di Teams, tra cui monitoraggio dell'integrità dei servizi e valutazione e verifica della qualità e dell'utilizzo della rete.
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

Questo articolo offre una panoramica dei requisiti per il corretto funzionamento dei servizi vocali cloud per l'organizzazione. Il corretto funzionamento dei servizi vocali cloud assicura un'esperienza affidabile e di alta qualità per l'organizzazione.

## <a name="introduction-to-the-operations-guide"></a>Introduzione alla Guida alle operazioni

La Guida alle operazioni offre una panoramica di tutte le attività e le attività necessarie nell'ambito della funzione di gestione dei servizi per Microsoft Teams.

La gestione del servizio è un argomento generale che illustra le operazioni quotidiane del servizio Microsoft Teams dopo la distribuzione e l'a attivazione per gli utenti. Il servizio Teams comprende Microsoft 365 o Office 365 e i componenti dell'infrastruttura distribuiti in locale (ad esempio la rete).

Molto probabilmente non si tratta di un nuovo concetto per la maggior parte delle organizzazioni. Potrebbero essere già stati implementati processi e attività associati a servizi esistenti. Detto questo, è probabile che sia possibile incrementare i processi correnti quando si pianifica oggi stesso la gestione dei servizi per supportare Teams in futuro.

La gestione del servizio comprende tutte le attività e i processi coinvolti nella gestione end-to-end di Teams. Come detto in precedenza, alcuni componenti della gestione dei servizi, ovvero l'infrastruttura costituita dal servizio Microsoft 365 o Office 365 stesso, sono di responsabilità di Microsoft, mentre il cliente è responsabile per gli utenti per la gestione dei vari aspetti di Teams, della rete e degli endpoint forniti.

Le attività e le attività di questa guida sono raggruppate in otto categorie, come illustrato nel diagramma seguente. Ognuna di queste categorie verrà espansa nelle sezioni seguenti.

![Diagramma che illustra un elenco di categorie di attività e attività](media/operate-my-service-image1.png "Diagramma che illustra un elenco di categorie di attività e attività costituite dalla gestione dei servizi per Teams. Il diagramma illustra anche che la gestione dei servizi è in gran parte un'attività del cliente.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidi come verranno implementate le operazioni per Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Esaminare completamente la Guida alle operazioni.</li><li>Implementare una strategia di gestione allineata agli obiettivi dell'organizzazione per offrire qualità e affidabilità dei carichi di lavoro vocali nel cloud.</li><li>Controlla [la qualità delle chiamate di Monitor.](monitor-call-quality-qos.md)</li><li> Implementare una strategia operativa per eseguire regolarmente revisioni della qualità dell'esperienza per verificare che la distribuzione cloud voice funzioni alle sue massime funzionalità.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mapping dei ruoli operativi

La pianificazione delle operazioni eseguite durante la fase divisione è fondamentale, perché le attività operative iniziano quando sono abilitati i primi utenti del progetto pilota. Questa guida elenca le attività e le attività che devono essere eseguite su base giornaliera, settimanale, mensile o necessaria per mantenere una distribuzione di Teams di alta qualità. Questa guida fornisce informazioni e indicazioni su come eseguire queste attività critiche.

Un componente fondamentale per una distribuzione corretta è garantire che la pianificazione eseguita nella fase iniziale di Envision includa l'individuazione dei responsabili dell'esecuzione di attività specifiche. Dopo aver compreso quali attività e attività si applicano alla distribuzione, è necessario comprenderle e seguirle con i gruppi o gli utenti assegnati.

Ogni team identificato deve rivedere e concordare le attività e le responsabilità identificate e iniziare la preparazione. Questo può includere formazione e preparazione, fornire aggiornamenti al piano per il personale o verificare che i provider esterni siano pronti per la distribuzione.

Le attività e i ruoli definiti in questa guida devono essere validi nella maggior parte degli scenari, ma ogni distribuzione di Teams è univoca; È quindi possibile usare questa guida come punto di partenza per personalizzare le attività e i ruoli predefiniti in base alle proprie esigenze.

Assicurarsi che ogni team che può eseguire il servizio abbia una buona comprensione delle attività necessarie per l'esecuzione del servizio. È essenziale che ogni team accetti e sliti la responsabilità all'interno dell'organizzazione prima dell'inizio del primo progetto pilota.

Una volta raggiunto un accordo, i team corrispondenti dovrebbero iniziare a operare sui loro ruoli.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td>
<td><ul><li>Usare questo documento per facilitare l'esercizio di mappatura del ruolo operativo.</li><li>Incontrare i rispettivi team di supporto per assegnare nomi a ogni voce nell'elenco delle attività richieste.</li><li>Ottenere l'accettazione o l'approvazione per i ruoli assegnati.</li><li>Assicurarsi che i team corrispondenti dispongono delle risorse, della preparazione e della formazione appropriate per completare le attività richieste.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dipendenze dei servizi di Teams

Microsoft Teams riunisce le tecnologie di Microsoft 365 o Office 365 per fornire un hub per il lavoro in team. Gli esempi includono:

-   Azure Active Directory (Azure AD) fornisce servizi di autenticazione e autorizzazione per Teams.

-   Exchange Online offre caratteristiche avanzate come il blocco a livello legale e l'e-discovery.

-   SharePoint Online offre la possibilità di condividere file nei canali e OneDrive for Business fornisce un meccanismo per la condivisione di file all'interno di una chat privata.

Le organizzazioni possono anche sfruttare gli investimenti esistenti nell'infrastruttura locale. Ad esempio, gli account di Active Directory locali esistenti possono essere usati per l'autenticazione usando Azure AD Connect. Alcune versioni di Exchange Server possono essere usate al posto di Exchange Online.

Queste tecnologie si uniscono per fornire agli utenti una famiglia di prodotti di comunicazione ricca, collaborativa e intelligente. Questa stretta integrazione è un vantaggio fondamentale di Teams, ma determina anche un requisito per la gestione dei servizi in tutte queste tecnologie.

Questa guida illustra le aree chiave di interesse per la gestione del servizio Teams. Molto probabilmente sono in essere piani di gestione dei servizi per le tecnologie di supporto da cui dipende Teams. In caso contrario, sarà necessario definire piani di gestione dei servizi adeguati anche per questi componenti della tecnologia (locale e online). In questo modo gli utenti potranno usufruire di un'esperienza affidabile e di alta qualità con Teams.

#### <a name="references"></a>Riferimenti 

[Panoramica di Microsoft Teams](teams-overview.md)

[Interazione tra Exchange e Microsoft Teams](exchange-teams-interact.md)

[Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams](sharepoint-onedrive-interact.md)

[Coesistenza e interoperabilità di Microsoft Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Attività della Guida al funzionamento

Le sezioni seguenti offrono una panoramica delle attività necessarie per gestire correttamente il servizio Microsoft Teams. Includono riferimenti a strumenti, informazioni contestuali e altri contenuti che consentono di comprendere l'attività e di assistere nelle iniziative di preparazione.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorare l'integrità dei servizi

È importante comprendere l'integrità generale del servizio Microsoft Teams, in modo da avvisare proattivamente gli altri utenti dell'organizzazione di qualsiasi evento che influisca sul servizio. Come descritto in precedenza, Teams dipende da altri servizi di Microsoft 365 o Office 365 come Azure Active Directory, Exchange Online, SharePoint Online e OneDrive for Business. Per questo aspetto, è altrettanto importante monitorare l'integrità dei servizi dipendenti.

Incorporare questa attività nel processo di gestione degli incidenti per informare in modo proattivo gli utenti, l'help desk e i team di operazioni per prepararsi a gestire le escalation degli utenti.

Le sezioni seguenti descrivono gli strumenti che è possibile usare per monitorare gli incidenti [di servizio](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) che interessano il servizio Teams. Nella tabella seguente è incluso un riepilogo dei vantaggi di ogni strumento e quando è consigliabile usarli.

| Strumento di monitoraggio                       | Vantaggi                                            | Quando usare                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Interfaccia di amministrazione di Microsoft 365                     | Disponibile su qualsiasi dispositivo con un browser supportato. | Usare questa opzione quando non sono necessarie notifiche in tempo reale.                                          |
| App Amministratore di Microsoft 365 o Office 365                  | Fornisce notifiche push al dispositivo mobile.  | Usare questa opzione quando è necessario ricevere una notifica degli incidenti del servizio mentre si è in viaggio.                  |
| Microsoft System Center               | Integrazione con Microsoft System Center.           | Quando sono necessarie funzionalità di monitoraggio avanzate e supporto per le notifiche.                       |
| API per le comunicazioni di servizio di Microsoft 365 o Office 365 | Accesso programmatico all'integrità dei servizi di Microsoft 365 o Office 365.   | Quando è necessaria l'integrazione con uno strumento di monitoraggio di terze parti o si vuole creare una soluzione personalizzata. |

> [!NOTE]
> Solo gli utenti a cui è assegnato **il ruolo di amministratore globale** o amministratore **del** servizio possono visualizzare l'integrità dei servizi.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoraggio con l'interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di [Microsoft 365](https://portal.office.com/) fornisce un [dashboard](https://portal.office.com/adminportal/home#/servicehealth) integrità dei servizi in cui è possibile visualizzare l'integrità corrente del servizio Teams oltre ai servizi dipendenti.

### <a name="monitoring-with-the-mobile-app"></a>Monitoraggio con l'app per dispositivi mobili

L'app Amministrazione di Microsoft 365 o Office 365 è disponibile in Apple iOS, Android e Windows (PC e dispositivi mobili). L'app fornisce agli amministratori dei servizi informazioni sull'integrità dei servizi e le modifiche imminenti. L'app supporta le notifiche push che possono avvisare l'utente quasi immediatamente dopo la posta di un avviso. In questo modo è possibile essere sempre al corrente sullo stato, l'integrità e le modifiche imminenti al servizio. Il supporto delle notifiche lo rende lo strumento di monitoraggio consigliato agli amministratori. Per ulteriori informazioni, vedere:

[App Amministrazione di Office 365 per dispositivi mobili](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Scaricare l'app Amministrazione di Office 365 per dispositivi mobili](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoraggio con Microsoft System Center

Microsoft System Center è una piattaforma di gestione integrata che consente di gestire data center, dispositivi client e ambienti IT cloud ibridi. Gli amministratori di Office 365 che usano System Center ora hanno la possibilità di importare Office 365 Management Pack, che consente di visualizzare tutte le comunicazioni di servizio all'interno di Operations Manager in System Center. Questo strumento consente di accedere allo stato dei servizi sottoscritti, agli eventi imprevisti attivi e risolti e alle comunicazioni del Centro messaggi (modifiche imminenti). Per altre informazioni, vedere il post di [blog seguente.](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)

Se si usa System Center per monitorare l'integrità dei servizi di Teams (e dei servizi dipendenti), è possibile personalizzare ulteriormente il Management Pack in modo da avvisare o inviare notifiche a specifici gruppi o persone identificate per reagire agli incidenti.
Questi gruppi possono includere proprietari del servizio, help desk, gruppi di supporto di secondo livello e terzo livello e responsabili degli incidenti nell'organizzazione.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoraggio per scenari avanzati

È possibile monitorare l'integrità dei servizi e le modifiche imminenti sfruttando l'API per le comunicazioni di servizio di Office 365 per accedere all'integrità e alle modifiche dei servizi di Office 365 a livello di programmazione. Usare questa API per creare uno strumento di monitoraggio personalizzato o connettere gli strumenti di monitoraggio esistenti alle comunicazioni dei servizi di Office 365, semplificando così il monitoraggio dell'ambiente. Per altre informazioni, vedere [Office 365 per sviluppatori Enterprise.](https://developer.microsoft.com/office)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/necessarie

| Attività               | Descrizione                                                                                                                                                                                                               | Cadenza   | Team assegnato |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorare l'integrità dei servizi | Monitorare proattivamente l'integrità dei servizi di Microsoft Teams (e dei servizi dipendenti) usando gli strumenti disponibili. I servizi dipendenti includono Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | In tempo reale |               |
| Notifica evento imprevisto  | Informare gli stakeholder interni degli eventi che interessano il servizio Teams. Gli stakeholder interni possono includere utenti, help desk e responsabili degli incidenti.                                                                          | Se necessario |               |

### <a name="references"></a>Riferimenti 

[Come verificare l'integrità dei servizi di Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificare l'integrità dei servizi per Microsoft Teams](service-health.md)

[Integrità e continuità dei servizi](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gestire la modifica dell'organizzazione

Microsoft Teams è un servizio basato sul cloud. In questo modo è possibile fornire rapidamente nuove caratteristiche e funzionalità. Offrire l'innovazione continua è un vantaggio ovvio per le organizzazioni, ma queste modifiche devono essere gestite in modo appropriato all'interno dell'organizzazione per evitare la resistenza degli utenti o le escalation al proprio help desk.

Gli aggiornamenti a Teams vengono installati automaticamente per gli utenti. Gli utenti avranno sempre a disposizione il client e le funzionalità più recenti nel servizio Teams. Non è possibile gestire l'implementazione degli aggiornamenti di Teams per gli utenti, quindi è fondamentale gestire il cambiamento attraverso efficaci programmi di comunicazione, formazione e adozione. Se gli utenti sono consapevoli del cambiamento, sono informati sui vantaggi e hanno la possibilità di sfruttare le nuove funzionalità, potranno adattarsi più rapidamente e accogliere &mdash; il cambiamento.

### <a name="monitoring-for-change"></a>Monitoraggio della modifica

Il primo passaggio nella gestione delle modifiche consiste nel monitorare le modifiche pianificate per Teams. La fonte migliore per il monitoraggio di queste modifiche è la roadmap di [Office 365,](https://products.office.com/business/office-365-roadmap)in cui sono elencate le caratteristiche attualmente in fase di sviluppo, in fase di distribuzione ai clienti o avviate completamente. È possibile cercare funzionalità specifiche di Teams usando il filtro disponibile oppure scaricare la roadmap in un file di Excel per ulteriori analisi. Per ogni caratteristica, la roadmap fornisce una breve descrizione, insieme alla data di rilascio prevista.

Nel [blog di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)sono disponibili informazioni su procedure consigliate, tendenze e notizie sugli aggiornamenti dei prodotti Teams. Ci si aspetta di trovare importanti aggiornamenti delle funzionalità di Teams da annunciare qui. È anche possibile sottoscrivere il blog tramite un feed RSS. È quindi possibile aggiungere [il feed RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) direttamente in un canale di Teams, in modo che tutte le notizie importanti vengono recapitate direttamente all'interno di Teams.

Tutte le funzionalità rilasciate sono documentate nelle Note [sulla versione per Microsoft Teams.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
Ecco un elenco delle funzionalità rilasciate per desktop, Web e dispositivi mobili. Lo stesso set di note sulla versione è disponibile anche nella scheda **Novità** della [Guida.](get-help-in-microsoft-teams.md)

Acquisire familiarità con le risorse disponibili e assicurarsi di assegnare i proprietari applicabili da monitorare per le modifiche.

### <a name="planning-for-change"></a>Pianificazione delle modifiche

Ora che si è a conoscenza delle imminenti modifiche al servizio Teams, il passaggio successivo consiste nel prepararsi e pianificare di conseguenza. Valutare ogni modifica per determinare quali modifiche richiedono la comunicazione agli utenti, campagne di consapevolezza, formazione per team o utenti di supporto oppure campagne di valutazione e adozione delle funzionalità. Questo è il ruolo principale di un team di gestione delle modifiche nell'organizzazione. Di seguito è riportata una raccolta di tabelle di esempio utili per pianificare le modifiche.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Funzionalità: Registrazione cloud (data di rilascio: gennaio 2018)

**Traccia generale**

| Cambia conformità | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Revisione legale   | Completato     | Questa caratteristica rappresenta un prerequisito per l'onboarding del team di formazione. | Team di progetto  |

**Gestione tecnica delle modifiche**

|       Cambia conformità       | Stato |                      Note/passaggi successivi                      |    Proprietario     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Modifiche IT necessarie      |  Sì   | L'amministratore deve abilitare la registrazione solo per gli utenti identificati. | Team di supporto |
| Preparazione tecnica completata |  Sì   |                                                            | Team di supporto |
|                              |        |                                                            |              |

**Gestione delle modifiche degli utenti** 

| Cambia conformità | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Impatto sugli utenti                  | Bassa                  |                                                                 |                        |
| È necessaria la conformità degli utenti      | Sì                  |                                                                 |                        |
| Pronto per le comunicazioni         | No                   | È stato inviato un messaggio di posta elettronica di comunicazione, ovvero una revisione in sospeso.            | Team di comunicazione    |
| Formazione pronta               | Sì                  | Per la formazione verrà utilizzato il video Microsoft esistente.                | Team di formazione          |

**Traccia stato**

| Cambia conformità | Stato   | Note/passaggi successivi | Proprietario |
|----|----|----|-----|
| Stato di rilascio               | in corso          | Revisione in sospeso da parte dello sponsor della direzione.               | Team di gestione delle modifiche |
| Rilasciare l'accesso             |                      |                                                                 |                        |
| Data di rilascio                 |                      |                                                                 |                        |

Per altre informazioni sulla pianificazione della gestione delle modifiche con Teams, vedere [Creare una strategia di gestione delle modifiche per Microsoft Teams.](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/necessarie

| Attività               | Descrizione                                                                                                                                                                                                                | Cadenza   | Team assegnato |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorare le modifiche     | Monitorare le modifiche imminenti al servizio Microsoft Teams.                                                                                                                                                                   | Ogni giorno     |               |
| Pianificazione delle modifiche    | Valutare e pianificare nuove caratteristiche e funzionalità, inclusi i piani di comunicazione, campagne di consapevolezza e formazione.                                                                                                     | Se necessario |               |
| Conformità degli utenti             | Eseguire campagne mirate di comunicazione, consapevolezza o formazione per assicurarsi che gli utenti siano pronti per il prossimo cambiamento.                                                                                                        | Se necessario |               |
| Supporto per la preparazione del team | Eseguire campagne mirate di comunicazione, consapevolezza o formazione per assicurarsi che il team di supporto sia pronto. I team di supporto possono includere il team "guanti bianchi", helpdesk, supporto di Livello 2 o Livello 3, partner esterni e così via. | Se necessario |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Valutare l'utilizzo di Teams

Dopo l'inizio del progetto pilota iniziale, è fondamentale stabilire una cadenza regolare per misurare l'effettivo utilizzo di Teams. In questo modo l'organizzazione può ottenere informazioni approfondite sull'allineamento dell'utilizzo effettivo con quello previsto durante la fase divisione. Anche se questa sezione è incentrata sull'utilizzo di Teams, questo dovrebbe far parte di un impegno più ampio per misurare e valutare l'utilizzo generale di Office 365.

L'analisi frequente dell'utilizzo nelle prime fasi della distribuzione offre l'opportunità di:

-   Verificare se gli utenti usano Teams.

-   Identificare le potenziali sfide di adozione prima di creare problemi critici in tutta l'organizzazione.

-   Comprendere se esistono discrepanze tra i requisiti della fase di pianificazione e l'utilizzo effettivo.

Se l'utilizzo non è quello previsto, potrebbe essere dovuto a un problema di distribuzione o al fatto che il piano di adozione non viene eseguito correttamente o che ci siano altri problemi. A seconda del motivo effettivo alla base del basso utilizzo, l'amministratore del servizio deve collaborare con i team correlati per rimuovere le barriere di utilizzo.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Misurazione dell'utilizzo con l'interfaccia di amministrazione di Microsoft 365

I dati di utilizzo di Teams sono disponibili nel dashboard Report. I dati sull'utilizzo di Teams sono disponibili in tre diversi report. Il primo report fornisce una visualizzazione tra prodotti di come gli utenti comunicano e collaborano usando i vari servizi di Office 365. Questo report è disponibile qui: Report utenti attivi di [Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Gli altri due report sono specifici di Teams e forniscono ulteriori dettagli sull'utilizzo di Teams dal punto di vista dell'utente e del dispositivo. Entrambi i report sono disponibili qui:

[Report utilizzo dispositivi Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Report Attività degli utenti di Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Autorizzazioni necessarie

I report sull'utilizzo nell'interfaccia di amministrazione sono  accessibili agli utenti a cui è stato assegnato un ruolo di amministratore globale o a un ruolo di amministratore specifico del prodotto (amministratore di **Exchange,** amministratore **di Skype for Business,** amministratore **di SharePoint).**

Inoltre, il **ruolo** di lettore di report è disponibile per gli utenti che richiedono l'accesso ai report, ma non esegue attività che richiedono autorizzazioni a livello di amministratore. Assegnare questo ruolo per fornire report sull'utilizzo a chiunque sia uno stakeholder, per monitorare e guidare l'adozione. Per altre informazioni sui diversi ruoli disponibili, vedere Informazioni sui ruoli di [amministratore di Office 365.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>Valutazione dell'utilizzo

Dopo aver usato il dashboard per la creazione di report per misurare l'utilizzo, è importante confrontare l'utilizzo misurato con gli indicatori di successo chiave definiti durante la fase di definizione del progetto. È possibile definire un KSI che potrebbe essere definito come utilizzo attivo o che sia indirettamente collegato all'utilizzo attivo.

È importante identificare eventuali variazioni tra l'utilizzo effettivo e quello pianificato prima di riprendere l'implementazione ad altri siti o utenti. È probabile che le risorse didattiche dell'organizzazione verranno identificate nell'ambito di questa attività che è possibile sfruttare per assicurarsi che il gruppo successivo di siti o utenti non incontri gli stessi problemi.

Prima di tutto, specifica se si tratta di un problema di adozione o tecnico. Iniziare esaminando gli elementi seguenti, nell'ordine, per determinare dove si trova il problema.

1.  Convalidare la qualità eseguendo una verifica della qualità dell'esperienza (per maggiori dettagli, vedere Migliorare e monitorare la qualità delle chiamate per [Teams).](monitor-call-quality-qos.md)

2.  Collaborare con il team helpdesk per verificare che non ci siano problemi tecnici di tendenza che impediscono agli utenti di accedere al servizio o di usarlo. Se esistono tendenze dei problemi, usare la sezione sulla risoluzione dei problemi [degli endpoint](#endpoint-troubleshooting) più avanti in questo articolo per provare a risolvere il problema prima di coinvolgere il supporto.

3.  Collaborare con il team di formazione e adozione [](#assess-user-sentiment) per raccogliere il feedback diretto degli utenti (vedere Valutare l'esperienza degli utenti più avanti in questo articolo) e verificare l'efficacia delle attività di consapevolezza e adozione.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/necessarie

| Attività                         | Descrizione                                                                                                                      | Cadenza   | Team assegnato |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Misurare l'utilizzo (fase di abilitazione) | Misurare e valutare l'utilizzo di Teams mentre i siti continuano a essere onboarded durante la fase di abilitazione. Risolvere i problemi di utilizzo come richiesto. | Settimanale    |               |
| Misurare l'utilizzo (fase del valore dell'unità)                           | Misurare e valutare l'utilizzo di Teams nella fase Drive Value (dopo il completamento della distribuzione). Risolvere i problemi di utilizzo come richiesto. | Bisettimana  |               |
| Aggiornare il piano di adozione             | Aggiornare il piano di adozione in base alla misurazione dell'utilizzo rispetto agli obiettivi di pianificazione.                                         | Se necessario |               |

### <a name="references"></a>Riferimenti 

[Informazioni sull'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Report attività nell'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Valutare il grado di valutazione dell'utente

La comprensione del valutazione dell'utente può fungere da indicatore chiave per la valutazione del successo della distribuzione di Teams. Il feedback degli utenti può guidare le modifiche all'interno dell'organizzazione; ad esempio modifiche ai piani di comunicazione, ai programmi di formazione o al modo in cui si offre supporto agli utenti.

È importante ricevere feedback tempestivi e continuare a valutare il valutazione del livello di valutazione dell'utente per l'intero ciclo di vita del progetto e oltre. Usare le indicazioni seguenti per determinare l'intervallo in cui l'organizzazione cercherà di inviare feedback:

-   **Inizio del progetto:** valutando il livello di esperienza dell'utente all'inizio del progetto, è possibile avere una visione iniziale di come gli utenti hanno un'esperienza in Teams.

-   **Dopo le principali attività cardine:** raccogliendo feedback per l'intero ciclo di vita del progetto, è possibile valutare in modo continuo la valutazione degli utenti e apportare le modifiche necessarie. Questo è particolarmente utile dopo le principali attività cardine.

-   **Conclusione del** progetto: valutare il grado di valutazione dell'utente alla fine di un progetto ti dirà quanto è stato fatto bene e dove deve ancora essere svolto il lavoro e ti consentirà di confrontare i risultati con il sondaggio precedente.

-   **Continua:** continuare a misurare il grado di valutazione degli utenti a tempo indefinito. Le variazioni nell'esperienza dell'utente possono essere dovute a modifiche all'ambiente dell'organizzazione o al servizio Teams. Sulla base del grado di valutazione dell'utente a intervalli regolari, è possibile comprendere l'andamento dei team di gestione dei servizi e il modo in cui l'organizzazione risponde alle modifiche al servizio Teams.

La valutazione dell'utente può essere valutata con diversi metodi. Possono includere sondaggi tramite posta elettronica, colloqui di persona o al telefono o semplicemente la creazione di un canale di feedback in Teams o Yammer. Per altre informazioni, vedere Le [procedure consigliate per i metodi di feedback degli utenti in Microsoft Teams.](best-practices-feedback.md)

È anche possibile usare un approccio a livello di settore per valutare il valore dell'utente chiamato punteggio di promotore netto (NPS), descritto nella sezione seguente.

### <a name="nps"></a>NPS 

Il punteggio net promoter (NPS) è una metrica di fidelizzazione dei clienti a livello di settore e un buon approccio da usare per valutare il livello di soddisfazione dell'utente. È possibile effettuare il calcolo di NPS ponendo due domande: "È probabile che consiglii Teams a un collega?", seguita dalla domanda in formato libero "Perché?"

NPS è un indice, compreso tra -100 e 100, che misura la disponibilità del cliente a raccomandare il prodotto o il servizio di un'azienda. NPS si basa su un sondaggio anonimo che viene recapitato agli utenti tramite posta elettronica o altri mezzi elettronici. NPS misura la fidelizzazione tra un provider e un cliente. È costituita da una sola domanda, che chiede agli utenti di valutare l'esperienza da 1 a 10, con la possibilità di fornire commenti aggiuntivi. Gli utenti vengono quindi classificati in base alle valutazioni seguenti:

-   9 o 10 sono promotori: appassionati di fedeltà che promuovono il servizio e favoriscono gli altri.

-   7 o 8 sono passivi: soddisfatti, ma non presenti, vulnerabili a un altro servizio o offerta.

-   Da 1 a 6 sono i detrattori: clienti insoddisfatto che possono danneggiare il servizio e compromettere la crescita.

![Diagramma che illustra la scala NPS](media/operate-my-service-image2.png "Questo diagramma mostra la scala NPS. Indica che le classifiche da 0 a 6 sono detrattori, da 7 a 8 passive e da 9 a 10 promoter.")

Anche se il numero di NPS di base è utile, si otterrà il massimo dall'analisi dei commenti degli utenti. Ti aiuteranno a capire perché l'utente dovrebbe (o non vorrebbe) consigliare Teams ad altri. Questi commenti possono fornire feedback preziosi per aiutare i team di gestione del progetto o del servizio a comprendere le modifiche necessarie per fornire un servizio di qualità.

Per fornire sondaggi NPS all'organizzazione, è possibile usare lo strumento di sondaggio online preferito.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/in base alle esigenze

| Attività              | Descrizione                                                                                                                                                                         | Cadenza   | Team assegnato |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Valutare il grado di valutazione dell'utente | Acquisire e valutare il valutazione del valutazione dell'utente usando sondaggi o colloqui oppure tramite un canale di feedback in Teams o Yammer.                                                                 | Se necessario |               |
| Aggiornare i piani di adozione | Guidare il cambiamento nell'organizzazione in base al feedback degli utenti; può includere modifiche ai piani di comunicazione, programmi di formazione o il modo in cui si offre supporto agli utenti. | Se necessario |               |

### <a name="references"></a>Riferimenti 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Uso di Yammer per raccogliere feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Procedure consigliate per il feedback degli utenti](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gestire la qualità della rete

Molti elementi di base della pianificazione consentono di ottimizzare, ridimensionare e correggere l'infrastruttura di rete per garantire un percorso efficiente ed di alta qualità al servizio Microsoft Teams. Le attività e i requisiti di pianificazione sono trattati nelle linee [guida sulla conformità della](3-envision-evaluate-my-environment.md#network-readiness) rete. Le reti si evolvono spesso nel tempo a causa di aggiornamenti, espansione o altri requisiti aziendali. È importante tenere conto dei requisiti per Teams nelle attività di pianificazione della rete.

Anche se la pianificazione della rete è un aspetto fondamentale di una distribuzione di Teams, è altrettanto importante assicurarsi che la rete rimanga integra e resti sempre attuale, in base alle mutevoli esigenze aziendali o tecniche.

Per garantire l'integrità della rete, è necessario eseguire una serie di attività a intervalli regolari.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/necessarie

| Attività                                                       | Descrizione                                                                                                                                                                                                                                                                                                                                                                 | Cadenza                | Team assegnato |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Monitorare IP e URL di Office 365                                | Monitorare le modifiche apportate agli URL e agli intervalli di indirizzi IP di [Office 365](https://aka.ms/o365ips) usando il [feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fornito e avviare una richiesta di modifica ai gruppi di rete applicabili.                                                                                                                                | Ogni giorno                  |               |
| Aggiornare la rete in base alle modifiche apportate agli URL e agli IP di Office 365 | Aggiornare i componenti di rete applicabili (firewall, server proxy, VPN, firewall lato client e così via) per riflettere le modifiche apportate agli URL e agli intervalli di indirizzi IP per [Office 365.](https://aka.ms/o365ips)                                                                                                                                                              | Se necessario              |               |
| Fornire i dati dell'edificio                                          | Fornire informazioni aggiornate sulla subnet al campione della qualità (o agli stakeholder interessati) per assicurarsi che le definizioni di edificio [in CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) siano aggiornate. | Se necessario              |               |
| Implementare le modifiche                                               | Implementare le modifiche sulla rete per supportare la modifica dei requisiti aziendali e tecnici di Teams. Gli elementi di rete possono includere:<ul><li>Firewall</li><li>VPN</li><li>Reti cablate e Wi-Fi rete</li><li>Connettività Internet ed ExpressRoute</li><li>DNS</li></ul>     | Se necessario              |               |
| Monitoraggio della rete e creazione di report                               | Monitorare la rete end-to-end per individuare le tendenze di disponibilità, utilizzo e capacità usando gli strumenti di gestione di rete di terze parti esistenti e le funzionalità di creazione di report disponibili dai provider di rete. Usare i dati di tendenza per la pianificazione della capacità di rete.                                                                                                            | Ogni giorno, settimanalmente, ogni mese |               |
| Pianificazione della capacità                                              | Collaborare con i proprietari dei servizi Di Teams per comprendere la modifica dei requisiti aziendali e tecnici che potrebbero guidare ulteriori cambiamenti alla capacità.                                | Se necessario              |               |
| Risoluzione dei problemi e correzioni di rete                        | Aiuta gli helpdesk di Teams, i proprietari dei servizi e i principali stakeholder a risolvere e risolvere i problemi relativi alla connettività, all'affidabilità o alla qualità di Teams. Gli elementi di rete possono includere:<ul><li>Firewall</li><li>VPN</li><li>Reti cablate e Wi-Fi rete</li><li>Connettività Internet ed ExpressRoute</li><li>DNS</li></ul>    | Se necessario              |               |
| Test di ripristino di emergenza e disponibilità elevata                | Eseguire regolari test di disponibilità elevata e ripristino di emergenza sull'infrastruttura di rete per assicurarsi che soddisfi gli obiettivi indicati per il livello di servizio (SLO, Service Level Agreement) o i contratti di servizio (SLA, Service Level Agreement) per il servizio Teams.                                                                                                                                                  | Mensile                |               |


### <a name="references"></a>Riferimenti 

[URL e intervalli di indirizzi IP per Office 365](https://aka.ms/o365ips)

[Creazione di uno schema dati](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Valutare e garantire la qualità 

Tutte le organizzazioni necessitano di un gruppo o di una persona per essere contabilizzabili per la qualità. Questo è il ruolo più importante nella gestione dei servizi. Il ruolo Campione qualità viene assegnato a una persona o a un gruppo che si è appassionati dell'esperienza degli utenti.
Questo ruolo richiede le competenze necessarie per identificare le tendenze nell'ambiente e la sponsorizzazione di collaborare con altri team per guidare la correzione. Il candidato migliore per il campione della qualità è in genere il proprietario del servizio clienti. A seconda delle dimensioni e della complessità dell'organizzazione, può trattarsi di qualsiasi persona o gruppo con una passione per assicurare un'esperienza utente di alta qualità.

Il campione della qualità sfrutta gli strumenti e i processi documentati esistenti, come Call Quality Dashboard (CQD), per monitorare l'esperienza dell'utente, identificare le tendenze della qualità e guidare la correzione, se necessario.
Il campione della qualità dovrebbe collaborare con i rispettivi team per guidare le azioni correttive e segnalare a un comitato competente lo stato di avanzamento e gli eventuali problemi aperti.

Leggere Migliorare e monitorare la qualità delle chiamate per [Teams,](monitor-call-quality-qos.md)che descrive le attività che valutano e forniscono indicazioni correttive nelle aree chiave che hanno il maggior impatto sul miglioramento dell'esperienza utente. Le indicazioni fornite in questo articolo riguardano l'uso di CQD come strumento principale per la creazione di report e l'analisi di ogni area, concentrando l'attenzione sull'audio per ottimizzare l'adozione e l'impatto. Le ottimizzazioni apportate alla rete per migliorare l'esperienza audio verranno anche tradotte direttamente in miglioramenti nella condivisione di video e desktop.

È consigliabile nominare il campione della qualità fin dall'inizio. Dopo essere stati nominati, dovrebbero iniziare a familiarizzare con monitora la qualità delle chiamate [e](monitor-call-quality-qos.md) i materiali di formazione associati.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/necessarie

| Attività                               | Descrizione                                                                                                                                                                                                                                                                                                 | Cadenza                             | Team assegnato |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nominare e formare campioni della qualità | Nominare e formare un campione della qualità.                                                                                                                                                                                                                                                                   | Se necessario                           |               |
| Eseguire revisioni della qualità dell'esperienza (QER)     | Eseguire un QER per identificare le tendenze in termini di qualità e affidabilità, esaminare i target definiti e creare report con i principali stakeholder dell'organizzazione.                                                                                                                            | Mensile (settimanale durante le distribuzioni) |               |
| Correzione delle unità                      | Coordinare le attività di correzione in tutta l'organizzazione in base alle valutazioni e ai risultati del QER.                                                                                                                                                                                                           | Se necessario                           |               |
| Aggiornare i dati di edificio in CQD            | Aggiornare o aggiungere nuove definizioni di edificio in CQD quando vengono apportate modifiche alla rete (vedere [Caricare informazioni sull'edificio).](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) | Se necessario                           |               |
| Ricos fill the Quality Champion role      | Responsabilità end-to-end per la qualità nell'organizzazione. Ciò include:<ul><li>Assicurarsi che il QER venga diretto regolarmente.</li><li>È possibile creare una relazione con i principali stakeholder sullo stato della qualità.</li><li>Verificare che le definizioni dei dati di edificio siano aggiornate.</li><li>Coordinare le attività di correzione in tutta l'organizzazione per garantire agli utenti un'esperienza di alta qualità con Teams.</li></ul>          | Ogni giorno                               |               |



### <a name="references"></a>Riferimenti 


[Caricare i dati del tenant e dell'edificio in CQD](CQD-upload-tenant-building-data.md)

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gestire gli endpoint

Gli endpoint di Microsoft Teams possono essere definiti come qualsiasi PC, Mac, tablet o dispositivo mobile (o qualsiasi altro) dispositivo che esegue il client teams. *L'endpoint* del termine non comprende solo il dispositivo stesso, ma anche il modo in cui un utente si connette al dispositivo, ad esempio usando il microfono o l'altoparlante incorporato del dispositivo, gli auricolari o un auricolare ottimizzato. Dopo la distribuzione, gli endpoint non devono essere dimenticati. Gli endpoint di Teams richiedono un'assistenza e manutenzione continua. Le sezioni seguenti descrivono le aree specifiche su cui concentrarsi.

### <a name="endpoint-requirements"></a>Requisiti endpoint

Uno dei vantaggi principali di Teams è che il cliente viene mantenuto aggiornato automaticamente. I client nel PC e nel Mac vengono aggiornati usando un processo in background che verifica la presenza di nuove build e scarica il nuovo client quando l'app è inattiva. Le app per dispositivi mobili di Teams vengono mantenute al corrente attraverso i rispettivi store di app.

Il client Teams ha requisiti minimi in termini di piattaforma software sottostante. Questi requisiti potrebbero cambiare nel tempo, quindi è importante monitorarli per verificarne le modifiche. Ad esempio, il client Teams ha una versione minima di iOS. Se il client usa un browser Internet, è necessario tenere sempre sotto controllo anche il browser. Un elenco delle piattaforme supportate è disponibile in [Ottieni client per Microsoft Teams.](get-clients.md)

### <a name="endpoint-firewalls"></a>Firewall endpoint

I firewall lato client possono avere un impatto significativo sull'esperienza utente.
I firewall sul lato client possono influire sulla qualità delle chiamate e persino impedire che venga stabilita una chiamata. Dopo aver configurato le esclusioni appropriate nel firewall client, è necessario mantenere le esclusioni aggiornate in base alle informazioni contenute negli URL e negli intervalli di indirizzi IP per [Office 365.](https://aka.ms/o365ips) Il fornitore di terze parti avrà indicazioni specifiche su come aggiornare le esclusioni.

### <a name="wi-fi-drivers"></a>Wi-Fi driver

Wi-Fi driver potrebbero essere problematici. Ad esempio, un driver potrebbe avere comportamenti di roaming molto aggressivi tra i punti di accesso che possono indurre il passaggio da un punto di accesso non necessario a un altro, con una qualità scarsa della chiamata. Un driver di prestazioni Wi-Fi prestazioni scadente può essere individuato attraverso una verifica della qualità dell'esperienza (per maggiori dettagli, vedi Migliorare e monitorare la qualità delle chiamate per [Teams).](monitor-call-quality-qos.md) È essenziale implementare un processo basato sulla qualità che monitori i nuovi driver di Wi-Fi e garantisca che vengano testati prima di essere distribuiti alla popolazione generale degli utenti.

### <a name="endpoint-management"></a>Gestione degli endpoint

Deve essere disponibile e gestito un catalogo di endpoint e dispositivi di interfaccia supportati (ad esempio cuffie). Questo catalogo includerà un elenco dei dispositivi approvati che sono stati selezionati e convalidati nell'ambito delle fasi di envision e onboarding. In genere, per ogni tipo di utente tipo nell'organizzazione vengono selezionati dispositivi specifici che soddisfano le esigenze degli attributi del tipo. Tutti gli endpoint hanno un ciclo di vita ed è necessario gestire i contratti dei fornitori, la garanzia, la sostituzione, la distribuzione e la riparazione associati a questi dispositivi.

### <a name="endpoint-troubleshooting"></a>Risoluzione dei problemi dell'endpoint

Anche se hai seguito le istruzioni precedenti, gli utenti della tua organizzazione potrebbero ancora avere problemi con Teams. Anche se il problema potrebbe non riguardare l'endpoint stesso, i sintomi del problema vengono in genere estinti dal client all'utente. Le indicazioni seguenti sono destinate a fornire i passaggi generali che è possibile eseguire per risolvere il problema; non è destinato a essere una guida completa per la risoluzione dei problemi. I passaggi vengono forniti in un ordine specifico, ma non devono essere seguiti esplicitamente e potrebbero non essere applicabili, a seconda della natura del problema.

1.  **Convalidare l'integrità del servizio:** Il problema riscontrato da un utente può essere correlato a un evento che influisce negativamente sul servizio Teams o sui relativi servizi dipendenti. Come primo passaggio, è consigliabile verificare l'assenza di problemi del servizio attivi. Vedere [Come verificare l'integrità dei servizi di Office 365.](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)
    Verificare lo stato dei servizi dipendenti, ad esempio Exchange, SharePoint, OneDrive for Business. Il monitoraggio dell'integrità dei servizi viene descritto in modo più dettagliato nella sezione precedente, [Monitorare l'integrità dei servizi.](#monitor-service-health)

2.  **Verificare la connettività dei client:** I problemi di connettività causano problemi di funzionalità o di accesso in Teams. È consigliabile, soprattutto per i nuovi siti o posizioni, convalidare la connettività al servizio. Assicurarsi che per ogni sito siano seguite le indicazioni seguenti per URL e intervalli di indirizzi IP per [Office 365.](https://aka.ms/o365ips) È possibile usare lo [strumento di valutazione della](https://www.microsoft.com/download/details.aspx?id=53885) rete Microsoft per eseguire un test di connettività per verificare che le porte dei supporti multimediali siano state aperte correttamente per le funzionalità vocali del cloud. I passaggi dettagliati su come eseguire i test di connettività sono forniti nelle istruzioni [per la conformità della](3-envision-evaluate-my-environment.md#network-readiness) rete.

3.  **Controllare l'elenco dei problemi noti:** Consulta [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) per determinare se l'utente è stato interessato in modo negativo da uno di questi problemi. Seguire la soluzione alternativa disponibile, se disponibile, per risolvere il problema.

4.  **Visitare la community di Microsoft Teams:** La [community di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) offre spazi dedicati per Teams. La community di Teams offre un elenco di discussioni, post di blog e annunci centrati su Teams. È possibile pubblicare una domanda o cercare soluzioni a un problema nelle discussioni precedenti.

5.  **Contatta il Supporto tecnico Microsoft:** È possibile contattare il supporto tecnico Microsoft per problemi con Teams online o telefonicamente. Per informazioni, vedere [Contattare il supporto per i prodotti per le aziende.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
    Per i clienti Premier, le richieste di supporto possono essere avviate seguendo le indicazioni in Contattare il [supporto per Microsoft Teams (clienti Premier).](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/necessarie

| Attività                 | Descrizione                                                                                                                                                                                                                                                                                                                                                                     | Cadenza   | Team assegnato |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisiti endpoint    | Assicurarsi che l'endpoint di Teams soddisfi tutti i requisiti software per Teams elencati in [Ottieni client per Microsoft Teams.](get-clients.md)                                                                                                                                                                                       | Mensile   |               |
| Firewall endpoint       | Mantenere le esclusioni appropriate nel firewall dell'endpoint in base alle informazioni negli URL e negli intervalli di indirizzi [IP per Office 365.](https://aka.ms/o365ips) Il fornitore di terze parti avrà indicazioni specifiche su come mantenere le esclusioni. Sottoscrivere [il feed RSS](https://support.office.com/o365ip/rss) per ricevere automaticamente una notifica delle modifiche. | Se necessario |               |
| Wi-Fi driver            | Testare e aggiornare Wi-Fi driver nel PC. Convalidare i risultati utilizzando CQD[(Migliorare e monitorare la qualità delle chiamate per Teams).](monitor-call-quality-qos.md)                                                                                                                                                                                                                                                                   | Se necessario |               |
| Gestione degli endpoint      | Gestire il catalogo di endpoint e dispositivi di interfaccia supportati (ad esempio cuffie). Gestire i contratti dei fornitori, la garanzia, la distribuzione, la sostituzione e le politiche di riparazione.                                                                                                                                                                                                        | Mensile   |               |
| Risoluzione dei problemi dell'endpoint | Le attività di risoluzione dei problemi possono includere la verifica della connettività, la consulenza dell'elenco dei problemi noti, la raccolta dei log, l'analisi e l'escalation al supporto tecnico Microsoft o ai fornitori di terze parti.                                                                                                                                                                                               | Se necessario |               |

### <a name="references"></a>Riferimenti 

[URL e intervalli di indirizzi IP per Office 365](https://aka.ms/o365ips)

[Ottenere i client per Microsoft Teams](get-clients.md)

[Community di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Verificare l'integrità dei servizi per Microsoft Teams](service-health.md)

[Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Contatta il supporto Tecnico Premier](https://support.microsoft.com/premier/contacts)

[Risoluzione dei problemi relativi al video in Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gestire Teams

Dopo la distribuzione del servizio Microsoft Teams, sarà necessario eseguire diverse attività relative all'amministrazione. Le attività vanno dall'amministrazione del servizio e dei singoli utenti alla pianificazione della capacità e al provisioning delle licenze e dei numeri di telefono. Le sezioni seguenti descrivono alcune di queste attività di amministrazione comuni.

### <a name="service-administration"></a>Amministrazione dei servizi

Il servizio Teams ha più impostazioni che possono essere configurate a livello di tenant.
Le modifiche apportate alle impostazioni del tenant interessano tutti gli utenti abilitati per Teams. Per un elenco dettagliato di queste impostazioni, vedere [Gestire le impostazioni di Microsoft Teams per l'organizzazione.](enable-features-office-365.md)

### <a name="user-administration"></a>Amministrazione utenti

Per supportare gli utenti, un'organizzazione potrebbe richiedere un numero qualsiasi di attività correlate, che variano da un'organizzazione alla successiva. In ultima analisi, queste attività devono essere gestite da un team di supporto a cui sono state assegnate queste mansioni operative. Per supportare gli utenti in Teams, in genere sono necessarie le attività seguenti.

#### <a name="general-tasks"></a>Attività generali

[Gestire l'accesso degli utenti a Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Attività comuni per Sistema telefonico

[Assegnare, modificare o rimuovere il numero di telefono di un utente](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)

[Assegnare o modificare l'indirizzo per gli interventi di emergenza di un utente](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Attività comuni per le audioconferenze

[Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)

[Cambiare i numeri di telefono del bridge per i servizi di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Gestione delle licenze

Man mano che l'organizzazione cresce o si stipulano contratti, è importante pianificare le licenze per le esigenze attuali e future. È disponibile una licenza di Teams di base, oltre alla licenza per le funzionalità vocali cloud[(Sistema telefonico](here-s-what-you-get-with-phone-system.md) e [Audioconferenza).](https://products.office.com/skype-for-business/audio-conferencing)

Per Teams, le licenze Sistema telefonico richiedono licenze [di Piani per chiamate](calling-plan-landing-page.md) associate. Le licenze del Piano per chiamate consentono di effettuare e ricevere chiamate telefoniche nazionali e/o internazionali. Questi piani sono in base all'uso e sono associati pool di minuti. Il [provisioning dei Crediti comunicazioni](what-are-communications-credits.md) ti garantirà sempre la qualità del servizio.

I servizi di audioconferenza sono a numero verde e i servizi di conferenza telefonica con accesso esterno nazionali. I Servizi di conferenza telefonica con accesso esterno a numero verde o gli scenari di chiamata in uscita non nazionali potrebbero comportare ulteriori addebiti per i [Crediti](what-are-communications-credits.md) comunicazioni necessari.

I Crediti comunicazioni possono integrare sia le licenze del Piano per chiamate che delle audioconferenze. Sia le licenze del Piano per chiamate che i Crediti comunicazioni sono in base all'uso e quindi devono essere monitorati ed ese ne per il provisioning.

Puoi sfruttare il [report sull'utilizzo di PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) per monitorare l'utilizzo dei minuti del Piano per chiamate e Crediti comunicazioni. In base ai risultati di questa attività, è possibile modificare le licenze di conseguenza. A breve, offriremo un report di pool di minuti [PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) per facilitare l'esecuzione di questa attività.

### <a name="telephone-number-management"></a>Gestione dei numeri di telefono

Ci sono due metodi per acquisire numeri in Teams: puoi eseguire il trasferimento di numeri di telefono da un altro provider oppure effettuare il provisioning dei numeri direttamente dal numero di inventario di Microsoft. Entrambi i metodi sono descritti in [Ottenere numeri di telefono per gli utenti.](getting-phone-numbers-for-your-users.md)

È previsto un limite per il numero di numeri di telefono di cui è possibile effettuare il provisioning dall'inventario dei numeri di Microsoft. I limiti sono determinati da una serie di fattori che illustrano quanti numeri [di telefono puoi ottenere?](how-many-phone-numbers-can-you-get.md)
I limiti dipendono dal tipo di numeri: numeri di servizio a numero verde, numeri di servizio a numero verde e numeri di abbonato (utente). Ognuno ha limiti propri e deve essere gestito in modo indipendente. Se si sta per raggiungere il limite (o se è stato raggiunto), è possibile applicare un incremento al limite. Questo processo è descritto nell'articolo del paragrafo precedente.

A volte non è possibile effettuare il provisioning di un numero in un'area geografica in cui il servizio è disponibile. Per informazioni sul processo di richiesta dei numeri, vedi [Gestire i numeri di telefono per l'organizzazione.](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

### <a name="team-creation-optional"></a>Creazione di team (facoltativo)

Per impostazione predefinita, tutti gli utenti con una cassetta postale in Exchange Online hanno le autorizzazioni per creare gruppi di Microsoft 365 e, di conseguenza, un team in Microsoft Teams. Se si vuole un controllo più stretto e limitare la creazione di nuovi team [(e](assign-roles-permissions.md#permissions-to-create-teams) quindi la creazione di nuovi gruppi di Microsoft 365), è possibile delegare i diritti di creazione e gestione di gruppi a un gruppo di amministratori. Se l'organizzazione vuole continuare con questa opzione, vedere la procedura descritta in questo articolo per consentire agli utenti di inviare richieste elaborate da un team assegnato.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Attività giornaliere/settimanali/mensili/necessarie

| Attività                    | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                             | Cadenza   | Team assegnato |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Amministrazione dei servizi      | Amministrazione delle impostazioni di Teams a livello di tenant.                                                                                                                                                                                                                                                                                                                                                                           | Se necessario |               |
| Amministrazione utenti         | Amministrazione delle impostazioni basate sull'utente e delle licenze in Teams.                                                                                                                                                                                                                                                                                                                                                           | Se necessario |               |
| Gestione delle licenze          | Pianificare le esigenze attuali e future per le licenze basate su utente e a consumo (Piani per chiamate e Crediti comunicazioni) sfruttando il report sull'utilizzo di [PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e il report pool di minuti [PSTN.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) | Settimanale    |               |
| Gestione dei numeri di telefono | Gestire i numeri di telefono disponibili per la crescita futura e modificare i livelli dell'inventario in base alle esigenze dell'organizzazione.                                                                                                                                                                                                                                                                                                | Settimanale    |               |
| Creazione di team (facoltativo)    | Esaminare ed elaborare le richieste di creazione del team.                                                                                                                                                                                                                                                                                                                                                                          | Se necessario |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Migliorare e monitorare la qualità delle chiamate

[Migliorare e monitorare la qualità delle](monitor-call-quality-qos.md) chiamate per Teams include un set di attività che valutano e forniscono indicazioni per la correzione nelle aree chiave che hanno il maggior impatto sul miglioramento dell'esperienza utente, come illustrato di seguito.

![Diagramma delle aree da esaminare durante una verifica della qualità dell'esperienza](media/plan-my-service-management-image2.png "Aree chiave da esaminare durante una verifica della qualità: audio, affidabilità e risultati dei sondaggi degli utenti.")

Valutando e correndo continuamente le aree descritte nella guida, è possibile ridurre il rischio di influire negativamente sull'esperienza utente. La maggior parte dei problemi di esperienza utente che si verificano in una distribuzione può essere raggruppata nelle categorie seguenti:

-   Configurazione incompleta del firewall o del proxy

-   Copertura Wi-Fi scarsa

-   Larghezza di banda insufficiente

-   VPN

-   Uso di dispositivi audio non supportati o incorporati

-   Subnet o dispositivi di rete problematici

Le indicazioni fornite in Migliorare e monitorare la qualità delle chiamate per [Teams](monitor-call-quality-qos.md) riguardano l'uso di Call Quality Dashboard (CQD) Online come strumento principale per la segnalazione e l'analisi di ogni area descritta, concentrando l'attenzione sull'audio per ottimizzare l'adozione e l'impatto. Le ottimizzazioni apportate alla rete per migliorare l'esperienza audio verranno anche tradotte direttamente in miglioramenti nella condivisione di video e desktop.

Consigliamo vivamente di nominare il campione della qualità fin dall'inizio. Dopo essere stati nominati, dovrebbero iniziare ad acquisire familiarità con i contenuti in Migliora e monitorare [la qualità delle chiamate per Teams.](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->
