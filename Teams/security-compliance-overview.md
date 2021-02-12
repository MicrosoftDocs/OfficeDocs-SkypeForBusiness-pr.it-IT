---
title: Panoramica di sicurezza e conformità
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Panoramica delle funzionalità di sicurezza e conformità di Microsoft Teams, tra cui privacy e crittografia, controllo e creazione di report e altro ancora.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c400f6f3fdb0c0cf5abce3a34f05c8488909aab
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122206"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicurezza e conformità in Microsoft Teams

> [!IMPORTANT]
> Per informazioni su come garantire la sicurezza mentre tutti lavorano da casa durante l'epidemia di **COVID-19,** leggere questi articoli:
>  - [12 principali attività per i team di sicurezza per supportare il lavoro da casa](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Ottimizzare la connettività di Microsoft 365 o Office 365 per gli utenti remoti tramite split tunneling per VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aggiornato il 2 aprile 2020: Guida [alla sicurezza di Teams](teams-security-guide.md)


Microsoft Teams si basa sul cloud di livello aziendale e su Microsoft 365 e Office 365, che offre le funzionalità avanzate di sicurezza e conformità che i clienti si aspettano. Per altre informazioni sulla pianificazione della sicurezza in Microsoft 365 o Office 365, la [roadmap](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) per la sicurezza è un buon punto di partenza. Per altre informazioni sulla pianificazione della conformità in Microsoft 365 o Office 365, è possibile iniziare con Piano per la sicurezza [& conformità.](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)


Questo articolo fornirà altre informazioni sulla sicurezza e la conformità specifiche di Teams. È possibile guardare questi video di Microsoft Mechanics relativi a sicurezza e conformità:

- [Microsoft Teams Essentials per IT: Sicurezza e conformità](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Controlli di Microsoft Teams per la sicurezza e la conformità](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> I clienti di Microsoft 365 o Office 365 hanno la proprietà e il controllo dei dati. Microsoft non usa i dati personali se non per fornire all'utente il servizio a cui è stato sottoscritto un abbonamento. In qualità di provider di servizi, Microsoft non analizza la posta elettronica, i documenti o i team dell'utente per scopi pubblicitari o non correlati al servizio. Microsoft non ha accesso al contenuto caricato. Come OneDrive e SharePoint in Microsoft 365, i dati dei clienti rimangono all'interno del tenant. Ulteriori informazioni sulla protezione e la sicurezza sono disponibili nel [Centro protezione Microsoft.](https://microsoft.com/trustcenter) Teams segue le stesse linee guida e gli stessi principi del Centro protezione Microsoft.

## <a name="security"></a>Sicurezza

Teams applica l'autenticazione a due fattori a livello di team e di organizzazione, Single #A0 tramite Active Directory e la crittografia dei dati in transito e in archivio. I file vengono archiviati in SharePoint e supportati dalla crittografia di SharePoint. Le note vengono archiviate in OneNote e supportate dalla crittografia di OneNote. I dati di OneNote vengono archiviati nel sito di SharePoint del team. La scheda Wiki può essere usata anche per la gestione di note e il relativo contenuto è archiviato anche all'interno del sito di SharePoint del team.

Leggere [i modelli di identità e l'autenticazione](identify-models-authentication.md) per ottenere informazioni più approfondite sull'autenticazione e Teams e sul funzionamento dell'autenticazione [moderna,](sign-in-teams.md) in particolare.

Poiché Teams collabora con SharePoint, OneNote, Exchange e altro ancora, è importante avere una gestione comoda della sicurezza in Microsoft 365 o Office 365. Per altre informazioni, vedere come [configurare Microsoft 365 o l'organizzazione di Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)per una maggiore sicurezza.

> [!NOTE]
> Attualmente, [i canali privati](private-channels.md) supportano caratteristiche di sicurezza e conformità limitate. Il supporto per il set completo di caratteristiche di sicurezza e conformità nei canali privati sarà disponibile a breve.

### <a name="advanced-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat Protection (ATP) è disponibile per Microsoft Teams, insieme a SharePoint e OneDrive, applicazioni che si integrano con Teams per la gestione dei contenuti. ATP consente di determinare se il contenuto di queste applicazioni è dannoso per natura e di bloccarne l'accesso da parte degli utenti.

Il modo in cui il contenuto interessato viene gestito dopo il rilevamento, in base alle impostazioni selezionate in Microsoft 365 o Office 365. Si consiglia vivamente di prendere in considerazione tutte le applicazioni per quanto riguarda la configurazione di ATP e, per ulteriori letture, ATP per [SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) e Microsoft Teams avrà informazioni dettagliate su come iniziare.

### <a name="safe-links"></a>Collegamenti sicuri

Al momento i collegamenti sicuri di Advanced Threat Protection (ATP) non sono disponibili in Microsoft Teams, ma ora sono [in](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) anteprima pubblica tramite il programma Technology Adoption Program (TAP), mentre la data di rilascio per la disponibilità generale non è impostata, questo articolo verrà aggiornato non quando arriva l'ora specificata. Nel frattempo, per informazioni sui collegamenti sicuri di Microsoft 365 o Office 365, vedere [Collegamenti sicuri ATP.](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) I collegamenti sicuri ATP sono disponibili sia nel [Piano ATP 1 che nel Piano ATP 2.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

### <a name="safe-attachments"></a>Allegati sicuri

Gli allegati sicuri sono una funzionalità progettata per migliorare la sicurezza degli utenti controllando e rilevando gli allegati dannosi. Gli amministratori globali [](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) o della sicurezza creano criteri per gestire questi allegati sospetti dannosi per impedire loro di essere inviati agli utenti, selezionati e su cui agire. Questa funzionalità è disponibile per SharePoint, OneDrive e Microsoft Teams e Microsoft 365 o Office 365 Advanced Threat Protection Plan 1 e [2.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) Per altre informazioni sugli allegati sicuri e su come possono proteggere l'organizzazione, vedere Allegati sicuri [in Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score è una misura per la sicurezza di un'organizzazione, con un numero più alto che indica altre azioni di miglioramento intraprese. È disponibile nel Centro sicurezza [PC di Microsoft 365.](https://security.microsoft.com/securescore) Seguendo i suggerimenti di Secure Score è possibile proteggere l'organizzazione dalle minacce. Da un dashboard centralizzato nel centro sicurezza di Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle loro identità, app e dispositivi Microsoft 365. Microsoft Teams ora ha consigli su Secure Score e gli amministratori sono invitati a monitorare il loro stato di sicurezza sulla piattaforma.

Secure Score aiuta le organizzazioni a:
- Report sullo stato corrente dell'impostazione della sicurezza dell'organizzazione.
- Migliorare l'orientamento alla sicurezza fornendo funzionalità di individuazione, visibilità, indicazioni e controllo.
- Confrontare con benchmark e definire indicatori di prestazioni chiave (KPI).


### <a name="how-conditional-access-policies-work-for-teams"></a>Funzionamento dei criteri di accesso condizionale per Teams

Microsoft Teams si basa in larga parte su Exchange Online, SharePoint e Skype for Business Online per scenari di produttività di base, come riunioni, calendari, chat interoperabili e condivisione di file. I criteri di accesso condizionale impostati per queste app cloud si applicano a Microsoft Teams quando un utente accede direttamente a Microsoft Teams, su qualsiasi client.

Microsoft Teams è supportato separatamente come app cloud nei criteri di accesso condizionale di Azure Active Directory. I criteri di accesso condizionale impostati per l'app cloud Microsoft Teams si applicano a Microsoft Teams quando un utente accede. Tuttavia, senza i criteri corretti in altre app come Exchange Online e SharePoint, gli utenti potrebbero comunque essere in grado di accedere a queste risorse direttamente. Per altre informazioni sulla configurazione di un criterio di accesso condizionale nel portale di Azure, vedere la Guida introduttiva [di Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

I client desktop di Microsoft Teams per Windows e Mac supportano l'autenticazione moderna. L'autenticazione moderna porta l'accesso in base ad AdAL (Azure Active Directory Authentication Library) per Microsoft Office applicazioni client su piattaforme diverse.

L'applicazione desktop Microsoft Teams supporta AppLocker.  Per altre informazioni sui prerequisiti di AppLocker, vedere: Requisiti per usare [AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Conformità

Teams include un'ampia gamma di informazioni utili per le aree di conformità, tra cui la conformità alle comunicazioni per canali, chat e allegati, criteri di conservazione, prevenzione della perdita dei dati (DLP), eDiscovery e blocco a livello legale per canali, chat e file, ricerca nel log di controllo, nonché gestione di applicazioni mobili con Microsoft Intune. Sono disponibili alcune informazioni su tutti gli argomenti seguenti ed è possibile passare al Centro conformità di [Microsoft 365](https://compliance.microsoft.com) per gestire queste impostazioni.

### <a name="information-barriers"></a>Barriere di informazioni

Le barriere di informazioni sono criteri messi in atto dagli amministratori di Teams per eseguire operazioni come impedire a persone o gruppi di comunicare tra loro (quando non è necessaria alcuna attività aziendale o un motivo normativo per bloccarle) e consente anche di impostare criteri relativi a ricerche e eDiscovery (di seguito riportati). Questi criteri possono influire sugli utenti nelle chat 1:1, di gruppo o a livello di team.

Per ulteriori informazioni su questo argomento, vai a [Barriere stradali in Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>Conformità alle comunicazioni

La conformità alle comunicazioni in Microsoft 365 consente di aggiungere utenti ai criteri nell'ambito che possono essere configurati per esaminare le comunicazioni di Microsoft Teams per linguaggio offensivo, informazioni riservate e informazioni correlate agli standard interni e normativi. Le comunicazioni in chat e gli allegati associati nei canali pubblici e privati di Teams, nelle chat individuali e negli allegati possono essere analizzati per ridurre al minimo i rischi di comunicazione nell'organizzazione. Per altre informazioni su come configurare i criteri per rilevare, acquisire e intervenire in caso di comunicazioni inappropriati di Teams, vedere Conformità alle comunicazioni [in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)

### <a name="retention-policies"></a>Criteri di conservazione

I criteri di conservazione in Microsoft Teams consentono di conservare i dati importanti per l'organizzazione, per motivi normativi, legali, aziendali o di altro tipo, e anche di rimuovere contenuti e comunicazioni non rilevanti per essere conservati. È anche possibile usare i criteri di conservazione per mantenere i dati per un certo periodo di tempo e quindi eliminarli. Per altre informazioni, vedere [Criteri di conservazione in Microsoft Teams.](retention-policies.md)

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Applicare [le etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) per proteggere e regolare l'accesso a contenuti aziendali sensibili creati durante la collaborazione all'interno dei team. Ad esempio, applicare etichette che configurano la privacy (pubblica o privata) dei team, controllano l'accesso guest e la condivisione esterna e gestiscono l'accesso dai dispositivi non gestiti. Per altre informazioni, vedere [Etichette di riservatezza in Microsoft Teams.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>Prevenzione della perdita dei dati

La prevenzione della perdita dei dati (DLP) in Microsoft Teams, così come la più ampia storia della prevenzione della perdita dei dati per Microsoft 365 o Office 365, ruota attorno alla preparazione aziendale per quanto riguarda la protezione di documenti e dati riservati. Indipendentemente dagli eventuali problemi relativi alle informazioni riservate nei messaggi o nei documenti, i criteri di prevenzione della perdita dei dati potranno contribuire a garantire che gli utenti non possano condividere questi dati riservati con le persone sbagliate.

Per informazioni sulla prevenzione della perdita dei dati in Teams, vedere [DLP per Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams) Un buon articolo per problemi di prevenzione della perdita dei dati di O365 è [una panoramica della prevenzione della perdita dei dati.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

L'individuazione elettronica, o eDiscovery, è l'aspetto elettronico di identificazione, raccolta e creazione di informazioni archiviate elettronicamente in risposta a una richiesta di produzione in un'indagine o un'indagine legale. Le funzionalità includono la gestione dei casi, la conservazione, la ricerca, l'analisi e l'esportazione dei dati di Teams. Ciò include chat, messaggi e file, riepiloghi di riunioni e chiamate. Per le riunioni e le chiamate di Teams, viene creato e reso disponibile in eDiscovery un riepilogo degli eventi che sono avvenuti durante la riunione e la chiamata.

Per altre informazioni su come eseguire Microsoft 365 o Office 365 eDiscovery nel Centro sicurezza e conformità ed eseguire la ricerca di contenuti relativi alla conformità per i contenuti di Teams, fare clic sui collegamenti seguenti:

 - [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

 - [Ricerca contenuto](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Abbiamo un articolo specifico di Teams per altre informazioni, [eDiscovery delle chat da guest a guest.](eDiscovery-investigation.md)

I clienti possono sfruttare eDiscovery [o Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) in base ai propri requisiti. La tabella seguente illustra le differenze tra le due tabelle:

| |eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Gestione dei casi     |X        |X         |
|Controllo di accesso  |X         |X         |
|Ricerche di contenuto     |X         | X        |
|Blocco/i   |X         | X        |
|Esporta     |X         |X         |
|Rilevamento duplicazione     |-         |X         |
|Ricerche di pertinenza con Machine Learning    |-         |X         |
|Analisi dei dati non strutturata      |-         |X         |

### <a name="legal-hold"></a>Blocco a tutti gli stati

Durante la controversia legale, può essere necessario mantenere non modificabili tutti i dati associati a un utente (responsabile) o a un team, in modo che possano essere usati come prove per il caso. A questo scopo, è possibile impostare un blocco a livello legale per un utente (cassetta postale utente) o per un team. Per un blocco a tutti gli utenti, è possibile usare i blocchi seguenti per la cassetta postale del team:

- In-Place blocco (viene applicato un blocco a un sottoinsieme della cassetta postale o della raccolta siti tramite query mirate o contenuto filtrato) oppure
- Blocco per controversia legale (a tutta la cassetta postale o alla raccolta siti viene posto un blocco).

In entrambi i casi, una volta impostato il blocco, assicura che, anche se gli utenti finali eliminano o modificano i messaggi del canale presenti nella cassetta postale del gruppo, le copie non modificabili del contenuto vengono mantenute e disponibili tramite la ricerca eDiscovery. I blocchi legali vengono in genere applicati nel contesto di un caso di eDiscovery.

Vedere panoramica [dei criteri di conservazione per](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) altre informazioni sulla conservazione e i blocchi nel Centro conformità di Microsoft 365. Per altre informazioni specifiche di Teams sul blocco a livello legale, è anche disponibile un blocco a livello legale per un utente o un team di [Microsoft Teams](legal-hold.md) per ottenere ulteriori informazioni.

### <a name="compliance-content-search"></a>Ricerca contenuto per conformità

La ricerca di contenuto può essere usata per cercare tutti i dati di Teams tramite funzionalità di filtro avanzate. I dati risultanti possono essere esportati in un contenitore specifico per il supporto alla conformità e ai contenziosi legali. Questa operazione può essere eseguita con o senza un caso di eDiscovery. In questo modo gli amministratori della conformità possono raccogliere i dati di Teams per tutti gli utenti, rivedili ed esportali per ulteriori elaborazioni. Vedere Ricerca [](https://docs.microsoft.com/microsoft-365/compliance/content-search) contenuto per altre informazioni su come eseguire una ricerca di contenuto per la conformità per Microsoft Teams e altri contenuti di Microsoft 365 o Office 365 nel Centro conformità di Microsoft 365.

> [!TIP]
> Con la ricerca di contenuti, è possibile filtrare fino a visualizzare solo i contenuti di Microsoft Teams, come messaggi di chat e canali, riunioni e chiamate, se necessario.

Per altre informazioni specifiche di Teams sulla configurazione della ricerca di contenuto, vedere [Ricerca contenuto in Microsoft Teams.](content-search.md)

### <a name="auditing-and-reporting"></a>Controllo e creazione di report

La ricerca nel log di controllo si collega direttamente al Centro conformità di Microsoft 365 e consente di impostare avvisi, nonché report sugli eventi di controllo, consentendo l'esportazione di set di eventi specifici o generici del carico di lavoro per l'uso e l'indagine da parte dell'amministratore in una sequenza temporale di controllo illimitata. È possibile configurare avvisi per tutti i dati del log di controllo nel Centro conformità di Microsoft 365 e filtrare ed esportare questi dati per ulteriori analisi. Vedere cercare nel [log di controllo](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) per altre informazioni su come eseguire una ricerca nel log di controllo per Microsoft 365 o Office 365. Per altre informazioni sulla ricerca di eventi di Microsoft Teams nel Centro conformità di Microsoft 365, è anche disponibile l'attivazione del controllo [in Teams](audit-log-events.md) che è possibile esaminare.

## <a name="customer-key"></a>Codice Cliente

Microsoft 365 offre un ulteriore livello di crittografia al di sopra del servizio di crittografia per il contenuto. Usando le chiavi fornite, Chiave cliente crittografa diversi tipi di dati in Microsoft Teams. Usando Customer Key a livello di applicazione, Customer Key crittografa i file di Teams archiviati in SharePoint Online. Per informazioni, vedere [Crittografia del servizio con codice Product Key del cliente.](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) 

Usando customer key a livello di tenant, Customer Key crittografa:
- Messaggi in chat di Teams (chat 1:1, chat di gruppo, chat delle riunioni e conversazioni del canale)
- Messaggi multimediali di Teams (immagini, frammenti di codice, video e immagini wiki)
- Registrazioni delle chiamate e delle riunioni di Teams archiviate nello spazio di archiviazione di Teams
- Notifiche chat di Teams
- Suggerimenti di chat di Teams da Cortana
- Messaggi di stato di Teams Per altre informazioni, vedere Panoramica del codice Product Key per [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level) a livello di tenant e leggere il blog di Microsoft Teams che illustra il supporto principale dei clienti per Microsoft Teams ora [in anteprima pubblica.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) Per informazioni sulla versione di Microsoft Information Protection che includeva il codice Product Key del cliente a livello di tenant, vedere Come annunciare le nuove funzionalità di Microsoft Information Protection per conoscere e proteggere i [dati riservati.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>Privacy

La protezione dei dati degli utenti è la priorità massima di Microsoft. Per informazioni sulle procedure di privacy, leggere:  

- [Privacy in Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Il nostro impegno verso la privacy e la sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Per i professionisti IT: Privacy e sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architettura di protezione delle informazioni

La figura seguente indica il flusso di inserimento dei dati di Teams verso i file e i messaggi di Exchange e SharePoint per Teams.

> [!div class="mx-imgBorder"]
> ![Diagramma del flusso di lavoro dei dati di Teams verso Exchange e SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figura seguente indica il flusso di inserimento delle riunioni di Teams e le chiamate dei dati a Exchange.

> [!div class="mx-imgBorder"]
> ![Diagramma del flusso di lavoro delle riunioni di Teams e delle chiamate verso Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Per individuare il contenuto di Teams possono essere presenti fino a 24 ore di ritardo.

## <a name="licensing"></a>Licenze

Per quanto riguarda le funzionalità di protezione delle informazioni, il set di caratteristiche disponibile è determinato da abbonamenti a Microsoft 365, abbonamenti a Office 365 e licenze autonome associate.

Per informazioni su come determinare la necessità di implementare le funzionalità per la sicurezza e la conformità, vedere i requisiti di [licenza](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) per le caratteristiche di sicurezza e conformità.

> [!NOTE]
> Non è necessario che ricerca contenuto e eDiscovery siano abilitati nel Centro sicurezza & conformità per funzionare.

## <a name="location-of-data-in-teams"></a>Posizione dei dati in Teams

I dati di Teams risiedono nell'area geografica associata all'organizzazione Office 365 o Microsoft 365 dell'utente. Per vedere quali aree geografiche sono attualmente supportate, vedere [Posizione dei dati in Microsoft Teams.](location-of-data-in-teams.md)

Per vedere quale area geografica ospita dati per il tenant, passare al profilo Organizzazione impostazioni dell'interfaccia di amministrazione di [Microsoft 365.](https://portal.office.com/adminportal/home)  >    >   Scorrere verso il basso fino a **Posizione dati**.

> [!div class="mx-imgBorder"]
> ![Screenshot della tabella Posizione dati che include Teams nell'interfaccia di amministrazione](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Standard di conformità

Teams usa i seguenti standard: [ISO 27001,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001) [ISO 27018,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 e SOC 2,](https://docs.microsoft.com/microsoft-365/compliance/offering-soc) [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)ed [EU Model Clauses (EUMC).](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) All'interno del framework di conformità Microsoft classifica le applicazioni e i servizi di Microsoft 365 e Office 365 in quattro categorie. Ogni categoria è definita da requisiti di conformità specifici che devono essere rispettati perché un servizio di Microsoft 365 o Office 365 o un servizio Microsoft correlato sia incluso in questa categoria.

I dettagli sono disponibili in [Risorse per la protezione dei dati.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams supporta anche la conformità di Cloud Security Alliance.

## <a name="related-topics"></a>Argomenti correlati

[Sicurezza di Microsoft 365](https://docs.microsoft.com/microsoft-365/security/)

[Conformità a Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/)

[Offerte di conformità Microsoft](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
