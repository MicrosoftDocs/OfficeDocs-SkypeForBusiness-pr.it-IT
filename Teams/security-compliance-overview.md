---
title: Panoramica della sicurezza e della conformità
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Panoramica delle funzionalità Microsoft Teams sicurezza e conformità, tra cui privacy e crittografia, controllo e creazione di report e altro ancora.
ms.localizationpriority: medium
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
ms.openlocfilehash: 03a4192a753a834c6af99927370b2856ff4d817d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590770"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicurezza e conformità in Microsoft Teams

> [!IMPORTANT]
> Per informazioni su come garantire al meglio la sicurezza mentre tutti lavorano da casa durante **l'epidemia di COVID-19,** leggere questi articoli:
>  - [12 principali attività per i team di sicurezza per supportare il lavoro da casa](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Ottimizzare la connettività di Microsoft 365 o Office 365 per gli utenti remoti tramite split tunneling per VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aggiornamento del 2 aprile 2020: [guida Teams sicurezza](teams-security-guide.md)


Microsoft Teams è basato sull'Microsoft 365 e Office 365 cloud di livello enterprise su larga scala, che offre le funzionalità avanzate di sicurezza e conformità previste dai clienti. Per altre informazioni sulla pianificazione della sicurezza in Microsoft 365 o [Office 365,](/microsoft-365/security/office-365-security/security-roadmap) la roadmap per la sicurezza è un buon punto di partenza. Per altre informazioni sulla pianificazione della conformità in Microsoft 365 o Office 365, è possibile iniziare con Pianificare la conformità & [sicurezza.](/microsoft-365/compliance/plan-for-security-and-compliance)


Questo articolo fornisce altre informazioni sulla sicurezza e la conformità Teams specifiche. Non perderti questi video di Microsoft Mechanics sulla sicurezza e la conformità:

- [Microsoft Teams Essentials per IT: Sicurezza e conformità](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Microsoft Teams per la sicurezza e la conformità](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> In quanto cliente di Microsoft 365 o Office 365, si è proprietari e si controllano i dati. Microsoft non usa i dati dell'utente per altro che per fornire all'utente il servizio sottoscritto. I provider di servizi non analizzano la posta elettronica, i documenti o i team per la pubblicità o per scopi non correlati ai servizi. Microsoft non ha accesso al contenuto caricato. Come OneDrive e SharePoint in Microsoft 365, i dati dei clienti rimangono all'interno del tenant. Per altre informazioni sulla sicurezza e sull'attendibilità, vedere il [Centro protezione Microsoft.](https://microsoft.com/trustcenter) Teams gli stessi principi e indicazioni del Centro protezione Microsoft.

## <a name="security"></a>Sicurezza

Teams applica l'autenticazione a due fattori a livello di team e dell'organizzazione, l'accesso Single Sign-On tramite Active Directory e la crittografia dei dati in transito e in pausa. I file vengono archiviati in SharePoint e sono supportati da SharePoint crittografia. Le note vengono archiviate in OneNote e sono supportate da OneNote crittografia. I OneNote dati vengono archiviati nel sito SharePoint team. La scheda Wiki può essere usata anche per la raccolta di note e il relativo contenuto viene archiviato anche all'interno del sito SharePoint team.

Leggere [i modelli di identità e](identify-models-authentication.md) l'autenticazione per [](sign-in-teams.md) informazioni più approfondite sull'autenticazione e Teams e il funzionamento dell'autenticazione moderna, in particolare con l'autenticazione moderna.

Poiché Teams collabora con SharePoint, OneNote, Exchange e altro ancora, è consigliabile gestire la sicurezza in Microsoft 365 o Office 365 all-up. Per altre informazioni, vedere come configurare l'organizzazione Microsoft 365 [o Office 365 per una maggiore sicurezza.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> Attualmente, [i canali privati](private-channels.md) supportano funzionalità limitate di sicurezza e conformità. Il supporto per il set completo di funzionalità di sicurezza e conformità nei canali privati sarà presto disponibile.

### <a name="advanced-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat Protection (ATP) è disponibile per Microsoft Teams, insieme a SharePoint e OneDrive, applicazioni che si integrano con Teams per la gestione dei contenuti. ATP consente di determinare se il contenuto di queste applicazioni è dannoso e di bloccare il contenuto dall'accesso degli utenti.

La modalità di gestione del contenuto interessato dopo il rilevamento è fino alle impostazioni selezionate in Microsoft 365 o Office 365. È consigliabile considerare tutte le applicazioni quando si tratta di configurare ATP e, per ulteriori letture, ATP per [SharePoint, OneDrive](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) e Microsoft Teams avrà informazioni dettagliate su come iniziare.

### <a name="safe-links"></a>Cassaforte Collegamenti

Anche se al momento i collegamenti sicuri ATP (Advanced Threat Protection) non sono disponibili in Microsoft Teams, ora sono [in](/microsoft-365/security/office-365-security/atp-safe-links-for-teams) anteprima pubblica tramite tap (Technology Adoption Program) e, anche se non è impostata una data di rilascio per la disponibilità generale, questo articolo verrà aggiornato al momento dell'arrivo. Nel frattempo, per informazioni sui collegamenti Microsoft 365 o Office 365 Cassaforte, vedere Collegamenti [Cassaforte ATP.](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) I collegamenti Cassaforte atp sono disponibili sia nel piano [ATP 1 che nel piano ATP 2.](/microsoft-365/security/office-365-security/office-365-atp)

### <a name="safe-attachments"></a>Cassaforte Allegati

Cassaforte allegati è una caratteristica progettata per migliorare la sicurezza degli utenti controllando e rilevando allegati dannosi. Gli amministratori globali [](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies) o della sicurezza creano criteri per la gestione di questi allegati sospetti dannosi per impedirne l'invio agli utenti, l'esecuzione di clic e azioni. Cassaforte protezione degli allegati è disponibile per SharePoint, OneDrive e Microsoft Teams e Microsoft 365 o Office 365 Advanced Threat [Protection Piano 1](/microsoft-365/security/office-365-security/office-365-atp) e 2 hanno questa funzionalità. Altre informazioni sui Cassaforte allegati e su come possono aiutare a proteggere l'organizzazione in Cassaforte [allegati in Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/atp-safe-attachments).

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero più alto che indica più azioni di miglioramento intraprese. È disponibile nel centro sicurezza [Microsoft 365 sicurezza.](https://security.microsoft.com/securescore) Seguendo i consigli di Secure Score è possibile proteggere l'organizzazione dalle minacce. Da un dashboard centralizzato nel centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle Microsoft 365, delle app e dei dispositivi. Microsoft Teams ora sono disponibili consigli su Secure Score e gli amministratori sono invitati a monitorare la loro posizione di sicurezza sulla piattaforma.

Secure Score aiuta le organizzazioni:
- Report sullo stato corrente della posizione di sicurezza dell'organizzazione.
- Migliorare la loro posizione di sicurezza fornendo individuabilità, visibilità, indicazioni e controllo.
- Confrontare con i benchmark e stabilire indicatori di prestazioni chiave (KPI).


### <a name="how-conditional-access-policies-work-for-teams"></a>Funzionamento dei criteri di accesso condizionale per Teams

Microsoft Teams si basa molto su Exchange Online, SharePoint e Skype for Business Online per scenari di produttività di base, come riunioni, calendari, chat di interoperabilità e condivisione di file. I criteri di accesso condizionale impostati per queste app cloud si applicano Microsoft Teams quando un utente accede direttamente a Microsoft Teams in qualsiasi client.

Microsoft Teams è supportato separatamente come app cloud nei Azure Active Directory di accesso condizionale. I criteri di accesso condizionale impostati per l'app Microsoft Teams cloud vengono applicati Microsoft Teams quando un utente esegue l'accesso. Tuttavia, senza i criteri corretti in altre app come Exchange Online e SharePoint, gli utenti potrebbero comunque essere in grado di accedere direttamente a tali risorse. Per altre informazioni sulla configurazione di criteri di accesso condizionale nel portale di Azure, vedere Azure Active Directory [Guida introduttiva.](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams client desktop per Windows e Mac supportano l'autenticazione moderna. L'autenticazione moderna consente di eseguire l'accesso in base alla Azure Active Directory di autenticazione Microsoft Office applicazioni client su più piattaforme.

Microsoft Teams'applicazione desktop supporta AppLocker.  Per altre informazioni sui prerequisiti di AppLocker, vedere: Requisiti per l'uso di [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Conformità

Teams include un'ampia gamma di informazioni utili per le aree di conformità, tra cui la conformità delle comunicazioni per canali, chat e allegati, criteri di conservazione, protezione dalla perdita dei dati (DLP), eDiscovery e blocco legale per canali, chat e file, ricerca nel log di controllo e gestione di applicazioni mobili con Microsoft Intune. Di seguito sono disponibili alcune informazioni su tutti questi argomenti e si può passare alla Centro conformità Microsoft 365 [per](https://compliance.microsoft.com) gestire queste impostazioni.

### <a name="information-barriers"></a>Barriere alle informazioni

Le barriere alle informazioni sono criteri messi in atto dagli amministratori di Teams per fare cose come impedire a persone o gruppi di comunicare tra loro (quando non è necessario che lo facciano, o un motivo normativo per impedire loro di farlo) e consente anche di impostare criteri relativi ad elementi come ricerche ed eDiscovery (illustrato di seguito). Questi criteri possono influire sugli utenti nelle chat 1:1, nelle chat di gruppo o a livello di team. La funzionalità Barriera informazioni è disponibile nel cloud pubblico e a partire da gennaio 2021 è stata pubblicata nel cloud GCC.

Per altre informazioni su questo argomento, vedere Barriere [alle informazioni in Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>Conformità delle comunicazioni

La conformità delle comunicazioni in Microsoft 365 consente di aggiungere utenti ai criteri nell'ambito che possono essere configurati per esaminare le comunicazioni Microsoft Teams per linguaggio offensivo, informazioni riservate e informazioni correlate agli standard interni e normativi. Le comunicazioni in chat e gli allegati associati nei canali di Teams pubblici e privati, nelle singole chat e negli allegati possono essere analizzati per ridurre al minimo i rischi di comunicazione nell'organizzazione. Per altre informazioni su come configurare i criteri per rilevare, acquisire e intervenire per le comunicazioni Teams inappropriati, vedere Conformità delle comunicazioni [in Microsoft 365](/microsoft-365/compliance/communication-compliance).

### <a name="retention-policies"></a>Criteri di conservazione

I criteri di conservazione in Microsoft Teams consentono sia di conservare i dati importanti per l'organizzazione, per motivi normativi, legali, aziendali o di altro tipo, sia di rimuovere contenuti e comunicazioni non rilevanti per la conservazione. È anche possibile usare i criteri di conservazione per conservare i dati per un periodo di tempo e quindi eliminarli. Per altre informazioni, vedere [Criteri di conservazione in Microsoft Teams](retention-policies.md).

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Applicare [etichette di riservatezza per](/microsoft-365/compliance/sensitivity-labels) proteggere e regolare l'accesso ai contenuti aziendali riservati creati durante la collaborazione all'interno dei team. Ad esempio, applicare etichette che configurano la privacy (pubblica o privata) dei team, controllano l'accesso guest e la condivisione esterna e gestiscono l'accesso da dispositivi non gestiti. Per altre informazioni, vedere Etichette di riservatezza [in Microsoft Teams](sensitivity-labels.md).

### <a name="data-loss-prevention-dlp"></a>Prevenzione della perdita dei dati

La prevenzione della perdita dei dati (DLP) in Microsoft Teams, così come la più grande storia di prevenzione della perdita dei dati per Microsoft 365 o Office 365, ruota intorno alla preparazione aziendale per quanto riguarda la protezione di documenti e dati riservati. Per quanto riguarda le informazioni riservate nei messaggi o nei documenti, i criteri di prevenzione della perdita dei dati saranno in grado di garantire agli utenti di non condividere questi dati riservati con le persone sbagliate.

Per informazioni sulla prevenzione della perdita dei dati in Teams, vedere Prevenzione della perdita dei dati [per Microsoft Teams](/microsoft-365/compliance/dlp-microsoft-teams). Un buon articolo per i problemi di prevenzione della perdita dei dati di O365 è [Panoramica della prevenzione della perdita dei dati.](/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

L'individuazione elettronica, o eDiscovery, è l'aspetto elettronico dell'identificazione, della raccolta e della produzione di informazioni archiviate elettronicamente (ESI) in risposta a una richiesta di produzione in un'applicazione legale o in un'indagine. Le funzionalità includono la gestione dei casi, la conservazione, la ricerca, l'analisi e l'esportazione di Teams dati. Sono inclusi chat, messaggi e file, riepiloghi di riunioni e chiamate. Per Teams riunioni e chiamate, viene creato e reso disponibile in eDiscovery un riepilogo degli eventi avvenuti nella riunione e nella chiamata.

Per altre informazioni su come eseguire Microsoft 365 o Office 365 eDiscovery nel Centro sicurezza e nel Centro conformità ed eseguire la ricerca di contenuto di conformità per il contenuto di Teams, vedere i collegamenti seguenti:

 - [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

 - [Ricerca contenuto](/microsoft-365/compliance/search-for-content)

Abbiamo un articolo Teams specifico per altre informazioni, [eDiscovery delle chat guest-to-guest.](eDiscovery-investigation.md)

I clienti possono sfruttare eDiscovery [o Advanced eDiscovery](/microsoft-365/compliance/office-365-advanced-ediscovery) in base alle proprie esigenze. La tabella seguente illustra le differenze tra le due opzioni:

|&nbsp; |eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Gestione dei casi     |X        |X         |
|Controllo di accesso  |X         |X         |
|Ricerche contenuto     |X         | X        |
|Blocco/i   |X         | X        |
|Esportare     |X         |X         |
|Rilevamento duplicazione     |-         |X         |
|Ricerche per pertinenza con Machine Learning    |-         |X         |
|Analisi dei dati non strutturati      |-         |X         |

### <a name="legal-hold"></a>Blocco legale

Durante la controversia legale, potrebbe essere necessario che tutti i dati associati a un utente (responsabile) o a un team siano mantenuti non modificabili, in modo che possano essere usati come prova per il caso. A questo scopo, è possibile impostare un blocco legale per un utente (cassetta postale utente) o un team. Per un blocco legale del team, la cassetta postale del team può essere inserita nei blocchi seguenti:

- In-Place blocco (viene applicato un blocco a un sottoinsieme della cassetta postale o della raccolta siti tramite query di destinazione o contenuto filtrato) oppure
- Blocco per controversia legale (l'intera cassetta postale o la raccolta siti viene messa in blocco).

In entrambi i casi, una volta impostato il blocco, si assicura che, anche se gli utenti finali eliminano o modificano i messaggi del canale presenti nella cassetta postale del gruppo, le copie non modificabili di tale contenuto vengono mantenute e disponibili tramite la ricerca eDiscovery. I blocchi legali vengono in genere applicati nel contesto di un caso di eDiscovery.

Vedere [Panoramica dei criteri di conservazione per](/microsoft-365/compliance/retention-policies) altre informazioni sulla conservazione e sui blocchi nel Centro conformità Microsoft 365. Per altre Teams informazioni specifiche sul blocco legale, è anche possibile impostare un blocco legale per un utente o un [team](legal-hold.md) di Microsoft Teams per saperne di più.

### <a name="compliance-content-search"></a>Ricerca contenuto conformità

La ricerca di contenuto può essere usata per cercare tutti Teams dati tramite funzionalità di filtro avanzate. I dati risultanti possono essere esportati in un contenitore specifico per il supporto della conformità e della controversia legale. Questa operazione può essere eseguita con o senza un caso di eDiscovery. In questo modo gli amministratori della conformità possono raccogliere Teams dati tra tutti gli utenti, rivederlo ed esportarlo per un'ulteriore elaborazione. Fare riferimento a [Ricerca contenuto](/microsoft-365/compliance/content-search) per altre informazioni su come eseguire una ricerca di contenuto di conformità per Microsoft Teams e altri contenuti Microsoft 365 o Office 365 nel Centro conformità Microsoft 365.

> [!TIP]
> Usando la ricerca contenuto, è possibile filtrare fino Microsoft Teams solo contenuto, ad esempio Messaggi di chat e canali, Riunioni e Chiamate, se necessario.

Per altre informazioni Teams sulla configurazione della ricerca contenuto, vedere Ricerca [contenuto in Microsoft Teams](content-search.md).

### <a name="auditing-and-reporting"></a>Controllo e creazione di report

La ricerca nel log di controllo si collega direttamente al Centro conformità Microsoft 365 e consente di impostare avvisi, oltre a creare report sugli eventi di controllo, consentendo l'esportazione di set di eventi specifici o generici del carico di lavoro per l'uso da parte degli amministratori e l'analisi in una sequenza temporale di controllo illimitata. È possibile configurare avvisi per tutti i dati del log di controllo all'interno del Centro conformità Microsoft 365 e filtrare ed esportare questi dati per un'ulteriore analisi. Vedere Cercare nel [log di controllo per](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) altre informazioni su come eseguire una ricerca nel log di controllo per Microsoft 365 o Office 365. Per altre informazioni sulla ricerca di Microsoft Teams eventi nel Centro conformità Microsoft 365, è anche disponibile l'attivazione del controllo [in](audit-log-events.md) Teams per la revisione.

## <a name="customer-key"></a>Codice Cliente

Microsoft 365 offre un ulteriore livello di crittografia al di sopra della crittografia del servizio per il contenuto. Usando le chiavi fornite, Customer Key crittografa diversi tipi di dati in Microsoft Teams. Usando customer key a livello di applicazione, Customer Key crittografa Teams file archiviati in SharePoint Online. Per informazioni, vedere [Crittografia dei servizi con codice Customer Key](/microsoft-365/compliance/customer-key-overview). 

Usando customer key a livello di tenant, Customer Key crittografa:
- Teams chat (chat 1:1, chat di gruppo, chat di riunione e conversazioni del canale)
- Teams multimediali (immagini, frammenti di codice, video e immagini wiki)
- Teams registrazioni di chiamate e riunioni archiviate in Teams archiviazione
- Teams chat
- Teams suggerimenti di chat per Cortana
- Teams di stato per altre informazioni, vedere Panoramica del codice Customer Key per [Microsoft 365 a](/microsoft-365/compliance/customer-key-tenant-level) livello di tenant e leggere il blog di Microsoft Teams che illustra il supporto del codice Customer Key per Microsoft Teams ora in [Anteprima](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)pubblica. Per informazioni sulla versione Microsoft Information Protection che includeva customer key a livello di tenant, vedere Annuncio di nuove funzionalità di Microsoft Information Protection per conoscere e proteggere [i dati riservati.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>Privacy

In Microsoft, la protezione dei dati è la nostra priorità più alta. Per informazioni sulle procedure di privacy, leggere:  

- [Privacy presso Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Il nostro impegno per la privacy e la sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Per i professionisti IT: Privacy e sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architettura di protezione delle informazioni

La figura seguente indica il flusso di inserimento dei dati Teams a Exchange e SharePoint per Teams file e messaggi.

> [!div class="mx-imgBorder"]
> ![Diagramma del flusso di lavoro dei Teams dati da Exchange e SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figura seguente indica il flusso di inserimento di Teams riunioni e la chiamata dei dati Exchange.

> [!div class="mx-imgBorder"]
> ![Diagramma del flusso di lavoro di Teams riunioni e chiamata dei dati Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Può essere necessario un ritardo di 24 ore per individuare Teams contenuto.

## <a name="licensing"></a>Licenze

Per quanto riguarda le funzionalità di protezione delle informazioni, Microsoft 365, Office 365 e le licenze autonome associate determineranno il set di funzionalità disponibile.

Per informazioni su come determinare le esigenze di gestione delle licenze per implementare le funzionalità per la sicurezza e la conformità, vedere i requisiti [di](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) licenza per le caratteristiche di sicurezza e conformità.

> [!NOTE]
> Non è necessario che ricerca contenuto ed eDiscovery siano abilitati nel Centro sicurezza & conformità.

## <a name="location-of-data-in-teams"></a>Posizione dei dati in Teams

I dati di Teams risiedono nell'area geografica associata all'organizzazione Office 365 o Microsoft 365 dell'utente. Per vedere quali aree geografiche sono attualmente supportate, vedere Posizione [dei dati in Microsoft Teams](location-of-data-in-teams.md).

Se è necessario vedere quale area geografica ospita [](https://portal.office.com/adminportal/home)i dati per il tenant, passare al profilo interfaccia di amministrazione di Microsoft 365  >  **Impostazioni**  >  **dell'organizzazione.** Scorrere verso il basso fino a **Posizione dati**.

> [!div class="mx-imgBorder"]
> ![Screenshot della tabella Posizione dati che include Teams nell'interfaccia di amministrazione](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Standard di conformità

Teams usa gli standard [seguenti: ISO 27001,](/microsoft-365/compliance/offering-iso-27001) [ISO 27018,](/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 e SOC 2,](/microsoft-365/compliance/offering-soc) [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)e [EU Model Clauses (EUMC).](/microsoft-365/compliance/offering-eu-model-clauses) All'interno del framework di conformità Microsoft, Microsoft classifica Microsoft 365 e Office 365 applicazioni e servizi in quattro categorie. Ogni categoria è definita da impegni di conformità specifici che devono essere rispettati per un servizio Microsoft 365 o Office 365 o un servizio Microsoft correlato per essere elencato in tale categoria.

I dettagli sono disponibili in [Risorse per la protezione dei dati.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams supporta anche la conformità cloud Security Alliance.

## <a name="related-topics"></a>Argomenti correlati

[Microsoft 365 Sicurezza](/microsoft-365/security/)

[Microsoft 365 Conformità](/microsoft-365/compliance/)

[Offerte di conformità Microsoft](/microsoft-365/compliance/offering-home)
