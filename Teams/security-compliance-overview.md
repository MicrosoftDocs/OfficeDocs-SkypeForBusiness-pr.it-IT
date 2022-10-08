---
title: Panoramica di sicurezza e conformità
author: MSFTTracyP
ms.author: tracyp
manager: laurawi
ms.date: 04/12/2022
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Una panoramica delle funzionalità di sicurezza e conformità di Microsoft Teams, tra cui privacy e crittografia, controllo e creazione di report e altro ancora.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
- purview-compliance
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d673be29b62097dd2737d24910707bac8ad58d3b
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046886"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicurezza e conformità in Microsoft Teams

> [!IMPORTANT]
> Per informazioni su come garantire al meglio la **sicurezza mentre tutti lavorano da casa durante l'epidemia di XIX-19**, leggi questi articoli:
>  - [12 principali attività per i team di sicurezza per supportare il lavoro da casa](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Ottimizzare la connettività di Microsoft 365 o Office 365 per gli utenti remoti tramite split tunneling per VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aggiornato il 2 aprile 2020: [Guida alla sicurezza di Teams](teams-security-guide.md)


Microsoft Teams si basa su Microsoft 365 e Office 365 cloud di livello aziendale su vasta scala, offrendo le funzionalità avanzate di sicurezza e conformità che i nostri clienti si aspettano. Per altre informazioni sulla pianificazione della sicurezza in Microsoft 365 o Office 365, [la roadmap della sicurezza](/microsoft-365/security/office-365-security/security-roadmap) è un buon punto di partenza. Per altre informazioni sulla pianificazione della conformità in Microsoft 365 o Office 365, è possibile iniziare con [Plan for security & compliance](/microsoft-365/compliance/plan-for-security-and-compliance).


Questo articolo fornirà ulteriori informazioni sulla sicurezza e la conformità specifiche di Teams. Non perderti questi video di Microsoft Mechanics sulla sicurezza e conformità:

- [Microsoft Teams Essentials per l'IT: sicurezza e conformità](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Controlli di Microsoft Teams per sicurezza e conformità](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> In qualità di cliente di Microsoft 365 o Office 365, sei tu il proprietario e il controllo dei tuoi dati. Microsoft non utilizza i tuoi dati per altro che fornire all'utente il servizio a cui si è abbonati. In qualità di provider di servizi, microsoft non analizza la posta elettronica, i documenti o i team dell'utente per scopi pubblicitari o per scopi non correlati al servizio. Microsoft non ha accesso al contenuto caricato. Come OneDrive e SharePoint in Microsoft 365, i dati dei clienti rimangono all'interno del tenant. Ulteriori informazioni sulla fiducia e sulla sicurezza sono disponibili nel [Centro protezione Microsoft](https://microsoft.com/trustcenter). Teams segue le stesse indicazioni e gli stessi principi del Centro protezione Microsoft.

## <a name="security"></a>Sicurezza

Teams applica l'autenticazione a due fattori a livello di team e a livello di organizzazione, il Single Sign-On tramite Active Directory e la crittografia dei dati in transito e inattivi. I file vengono archiviati in SharePoint e supportati dalla crittografia SharePoint. Le note sono archiviate in OneNote e sono supportate dalla crittografia onenote. I dati di OneNote vengono archiviati nel sito di SharePoint del team. La scheda Wiki può essere usata anche per la creazione di note e il relativo contenuto è archiviato anche nel sito di SharePoint del team.

Leggi [Modelli di identità e autenticazione](identify-models-authentication.md) per informazioni più approfondite sull'autenticazione e Teams e [Sul funzionamento dell'autenticazione moderna](sign-in-teams.md) in particolare con l'autenticazione moderna.

Poiché Teams collabora con SharePoint, OneNote, Exchange e altro ancora, è consigliabile avere familiarità con la gestione della sicurezza in Microsoft 365 o Office 365 all-up. Per altre informazioni, vedere [configurare Microsoft 365 o Office 365 organizzazione per una maggiore sicurezza](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Attualmente, i [canali privati](private-channels.md) supportano funzionalità di sicurezza e conformità limitate. Il supporto per il set completo di funzionalità di sicurezza e conformità nei canali privati sarà disponibile a breve.

### <a name="microsoft-defender-for-office-365"></a>Microsoft Defender per Office 365

Microsoft Defender per Office 365 è disponibile per Microsoft Teams, insieme a SharePoint e OneDrive, applicazioni che si integrano con Teams per la gestione dei contenuti. Defender per Office 365 consente di determinare se il contenuto di queste applicazioni è dannoso di natura e bloccarlo dall'accesso degli utenti.

La modalità di gestione del contenuto interessato dopo il rilevamento dipende dalle impostazioni selezionate in Microsoft 365 o Office 365. È consigliabile prendere in considerazione tutte le applicazioni per quanto riguarda la configurazione di Defender per Office 365 e, per un'ulteriore lettura, [una panoramica del funzionamento dei collegamenti sicuri e la procedura per configurarla sono qui](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) per informazioni dettagliate per iniziare.

### <a name="safe-links-in-microsoft-teams"></a>Collegamenti sicuri in Microsoft Teams

Defender per Office 365 collegamenti sicuri sono disponibili in Microsoft Teams. Per altre informazioni sui collegamenti sicuri e su cosa fare con questa funzionalità, vedere [Impostazioni Collegamenti sicuri per Teams](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide). I collegamenti sicuri sono disponibili sia in [Defender per Office 365 Piano 1 che in Piano 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide).

### <a name="safe-attachments"></a>Allegati sicuri

Allegati sicuri è una funzionalità progettata per migliorare la sicurezza degli utenti controllando e rilevando allegati dannosi. Gli amministratori globali o della sicurezza [attivano la funzionalità](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams?view=o365-worldwide) e [creano criteri](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) per la gestione di questi allegati sospetti dannosi per impedire che vengano inviati agli utenti, su cui si è fatto clic e su cui hanno agito.

La protezione degli allegati sicuri è disponibile per SharePoint, OneDrive e Microsoft Teams e Microsoft 365 o Office 365 in [Microsoft Defender per Office 365 Piano 1 e Piano 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide). Per altre informazioni, vedere Allegati sicuri e come possono aiutare a proteggere l'organizzazione in [questo articolo](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide).

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score è una misurazione della postura di sicurezza di un'organizzazione, con un numero più elevato che indica ulteriori azioni di miglioramento eseguite. Può essere trovato nella [Centro sicurezza Microsoft 365](https://security.microsoft.com/securescore). Seguendo i suggerimenti di Secure Score è possibile proteggere l'organizzazione dalle minacce. Da un dashboard centralizzato nel Centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, delle app e dei dispositivi di Microsoft 365. Microsoft Teams ha ora suggerimenti su Secure Score e gli amministratori sono invitati a monitorare la loro posizione di sicurezza sulla piattaforma.

Secure Score aiuta le organizzazioni:
- Report sullo stato corrente dell'approccio di sicurezza dell'organizzazione.
- Migliora la postura di sicurezza fornendo individuabilità, visibilità, guida e controllo.
- Confrontare i benchmark e stabilire indicatori di prestazioni chiave (KPI).

### <a name="how-conditional-access-policies-work-for-teams"></a>Funzionamento dei criteri di accesso condizionale per Teams

Microsoft Teams si basa principalmente su Exchange Online, SharePoint e Skype for Business Online per scenari di produttività di base, come riunioni, calendari, chat di interoperabilità e condivisione di file. I criteri di accesso condizionale impostati per queste app cloud si applicano a Microsoft Teams quando un utente accede direttamente a Microsoft Teams su qualsiasi client.

Microsoft Teams è supportato separatamente come app cloud nei criteri di accesso condizionale di Azure Active Directory. I criteri di accesso condizionale impostati per l'app cloud di Microsoft Teams si applicano a Microsoft Teams quando un utente accede. Tuttavia, senza i criteri corretti in altre app come Exchange Online e SharePoint, gli utenti potrebbero comunque essere in grado di accedere direttamente a tali risorse. Per altre informazioni sulla configurazione di un criterio di accesso condizionale nel portale di Azure, vedere [Guida introduttiva di Azure Active Directory](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

I client desktop di Microsoft Teams per Windows e Mac supportano l'autenticazione moderna. L'autenticazione moderna porta l'accesso basato su Azure Active Directory Authentication Library (ADAL) alle applicazioni client di Microsoft Office su più piattaforme.

L'applicazione desktop Microsoft Teams supporta AppLocker.  Per altre informazioni sui prerequisiti di AppLocker, vedi: Requisiti per l'uso di [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Conformità

Teams offre un'ampia gamma di informazioni utili per le aree di conformità, tra cui la conformità alle comunicazioni per canali, chat e allegati, criteri di conservazione, prevenzione della perdita dei dati(DLP), eDiscovery e blocco legale per canali, chat e file, ricerca nel log di controllo, nonché gestione di applicazioni mobili con Microsoft Intune. Abbiamo fornito alcune informazioni su tutti questi argomenti di seguito e puoi passare al [Portale di conformità di Microsoft Purview](https://compliance.microsoft.com) per gestire queste impostazioni.

### <a name="information-barriers"></a>Barriere informative

Gli ostacoli alle informazioni di Microsoft Purview sono criteri messi in atto dagli amministratori di Teams per impedire ad persone o gruppi di comunicare tra loro (quando non c'è alcuna necessità aziendale di farlo o un motivo normativo per impedirne l'esecuzione) e consente anche di impostare criteri relativi a elementi come le ricerche e eDiscovery (descritti di seguito). Questi criteri possono influire su utenti in chat 1:1, chat di gruppo o a livello di team. La funzionalità Information Barrier è disponibile nel cloud pubblico e a partire da gennaio 2021 è stata distribuita nel cloud GCC.

Per altre informazioni su questo argomento, vedere [Barriere alle informazioni in Microsoft Teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Conformità delle comunicazioni

Conformità delle comunicazioni Microsoft Purview consente di aggiungere utenti a criteri di ambito che possono essere configurati per esaminare le comunicazioni di Microsoft Teams per linguaggio offensivo, informazioni riservate e informazioni relative agli standard interni e normativi. Le comunicazioni di chat e gli allegati associati nei canali di Teams pubblici e privati, nelle singole chat e negli allegati possono essere analizzati per ridurre al minimo i rischi di comunicazione nell'organizzazione. Per altre informazioni su come configurare i criteri per rilevare, acquisire e intervenire in caso di comunicazioni di Teams non appropriate, vedere [Informazioni sulla conformità alle comunicazioni](/microsoft-365/compliance/communication-compliance).

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Applicare [etichette di riservatezza](/microsoft-365/compliance/sensitivity-labels) per proteggere e regolare l'accesso a contenuti aziendali sensibili creati durante la collaborazione all'interno dei team. Ad esempio, applicare etichette che configurano la privacy (pubblica o privata) dei team, controllano l'accesso guest e la condivisione esterna e gestiscono l'accesso da dispositivi non gestiti. Per altre informazioni, consultare [le etichette di riservatezza in Microsoft Teams](sensitivity-labels.md).

### <a name="microsoft-purview-data-loss-prevention-dlp"></a>Prevenzione della perdita dei dati Microsoft Purview (DLP)

La prevenzione della perdita dei dati (DLP) in Microsoft Teams, così come la storia più ampia relativa ai criteri di prevenzione della perdita dei dati per Microsoft Purview, ruotano attorno alla conformità aziendale quando si tratta di proteggere i documenti e i dati sensibili. Indipendentemente da problemi relativi a informazioni riservate in messaggi o documenti, i criteri di prevenzione della perdita dei dati saranno in grado di garantire che gli utenti non condividano questi dati riservati con le persone sbagliate.

Per informazioni sulla prevenzione della perdita dei dati in Teams, consultare [la prevenzione della perdita dei dati per Microsoft Teams](/microsoft-365/compliance/dlp-microsoft-teams). Un buon articolo per i problemi di prevenzione della [perdita dei dati è Informazioni sulla prevenzione della perdita dei dati](/microsoft-365/compliance/dlp-learn-about-dlp).

### <a name="customer-key"></a>Codice cliente

Microsoft 365 offre un ulteriore livello di crittografia oltre alla crittografia del servizio per il contenuto. Usando le chiavi fornite, la chiave cliente crittografa diversi tipi di dati in Microsoft Teams. Usando la chiave del cliente a livello di applicazione, la chiave del cliente crittografa i file di Teams archiviati in SharePoint Online. Per informazioni, vedi [Crittografia del servizio con codice cliente Microsoft Purview](/microsoft-365/compliance/customer-key-overview).

Usando la chiave del cliente a livello di tenant, la chiave del cliente crittografa:
- Messaggi in chat di Teams (chat 1:1, chat di gruppo, chat di riunione e conversazioni di canale)
- Messaggi multimediali di Teams (immagini, frammenti di codice, video e immagini wiki)
- Registrazioni di chiamate e riunioni di Teams archiviate nello spazio di archiviazione di Teams
- Notifiche chat di Teams
- Suggerimenti per le chat di Teams da Cortana
- Messaggi di stato di Teams

Per altre informazioni, vedere [Panoramica del codice Cliente a livello di tenant](/microsoft-365/compliance/customer-key-tenant-level) e leggere il blog di Microsoft Teams che illustra il [supporto dei tasti cliente per Microsoft Teams ora in anteprima pubblica](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893). Per informazioni sulla versione Microsoft Purview Information Protection che includeva codice cliente a livello di tenant, vedere [Annuncio di nuove funzionalità di Microsoft Purview Information Protection per conoscere e proteggere i dati riservati](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692).

### <a name="retention-policies"></a>Criteri di conservazione

I criteri di conservazione in Microsoft Teams consentono di conservare sia i dati importanti per l'organizzazione, per motivi normativi, legali, aziendali o di altro tipo, sia di rimuovere contenuti e comunicazioni non rilevanti da conservare. È anche possibile usare i criteri di conservazione per conservare i dati per un periodo di tempo e quindi eliminarli. Per altre informazioni, vedere [Criteri di conservazione in Microsoft Teams](retention-policies.md).

### <a name="ediscovery"></a>eDiscovery

L'individuazione elettronica, o eDiscovery, è l'aspetto elettronico dell'identificazione, della raccolta e della produzione di informazioni archiviate elettronicamente in risposta a una richiesta di produzione in una causa legale o in un'indagine. Le funzionalità includono la gestione dei casi, la conservazione, la ricerca, l'analisi e l'esportazione dei dati di Teams. Ciò include chat, messaggi e file, riepiloghi di riunioni e chiamate. Per le riunioni e le chiamate di Teams, viene creato e reso disponibile in eDiscovery un riepilogo degli eventi che si sono verificati durante la riunione e la chiamata.

Per altre informazioni su come usare gli strumenti di eDiscovery nel Portale di conformità di Microsoft Purview per cercare contenuti di Teams, vedere i collegamenti seguenti:

- [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

- [Ricerca contenuto](/microsoft-365/compliance/search-for-content)

Abbiamo un articolo specifico di Teams per altre informazioni in [Condurre un'indagine eDiscovery sui contenuti in Microsoft Teams](eDiscovery-investigation.md).

I clienti possono sfruttare eDiscovery o [eDiscovery (Premium)](/microsoft-365/compliance/office-365-advanced-ediscovery) in base alle loro esigenze. La tabella seguente illustra le differenze tra i due:

|&nbsp; |eDiscovery  |eDiscovery (Premium)  |
|---------|---------|---------|
|Gestione dei casi     |X        |X         |
|Controllo di accesso  |X         |X         |
|Ricerche di contenuto     |X         | X        |
|Blocchi   |X         | X        |
|Esportazione     |X         |X         |
|Rilevamento duplicazione     |-         |X         |
|Ricerche di pertinenza con Machine Learning    |-         |X         |
|Analisi dati non strutturata      |-         |X         |

### <a name="legal-hold"></a>Blocco a fini giudiziari

Durante la controversia legale, tutti i dati associati a un utente (custode) o a un team potrebbero essere conservati come non modificabili, in modo che possano essere usati come prova per il caso. A questo scopo, applicare un blocco a un utente (cassetta postale utente) o a un team. Per un blocco a fini giudiziari del team, la cassetta postale del team può essere messa nei blocchi seguenti:

- In-Place blocco (viene applicato un blocco a un sottoinsieme della cassetta postale o della raccolta siti tramite query di destinazione o contenuto filtrato) oppure
- Blocco per controversia legale (all'intera cassetta postale o raccolta siti viene applicato un blocco).

In entrambi i casi, una volta impostato il blocco, garantisce che, anche se gli utenti finali eliminano o modificano i messaggi del canale presenti nella cassetta postale del gruppo, le copie non modificabili del contenuto vengono mantenute e disponibili tramite una ricerca eDiscovery. I blocchi legali vengono in genere applicati nel contesto di un caso di eDiscovery.

Per altre informazioni sulla conservazione e sui blocchi nel Portale di conformità di Microsoft Purview, vedere [Panoramica dei criteri di conservazione](/microsoft-365/compliance/retention-policies). Per altre informazioni specifiche di Teams sul blocco a fini giudiziari, abbiamo anche [un utente o un team di Microsoft Teams a cui applicare un blocco a fini giudiziari](legal-hold.md) per saperne di più.

### <a name="content-search"></a>Ricerca contenuto

La ricerca di contenuto può essere usata per cercare tutti i dati di Teams tramite funzionalità avanzate di filtro. I dati risultanti possono essere esportati in un contenitore specifico per il supporto per la conformità e le controversie legali. Questa operazione può essere eseguita con o senza un caso di eDiscovery. In questo modo gli amministratori della conformità possono raccogliere i dati di Teams tra tutti gli utenti, rivederli ed esportarli per un'ulteriore elaborazione. Vedere [Ricerca contenuto](/microsoft-365/compliance/content-search) per altre informazioni su come eseguire una ricerca di contenuti di conformità per Microsoft Teams e altri contenuti di Microsoft 365 o Office 365 nel Portale di conformità di Microsoft Purview.

> [!TIP]
> Usando la ricerca di contenuti, è possibile filtrare fino a visualizzare solo i contenuti di Microsoft Teams, ad esempio messaggi di chat e canali, riunioni e chiamate, se necessario.

Se desideri altre informazioni specifiche di Teams sulla configurazione della ricerca di contenuto, consulta [Ricerca di contenuto in Microsoft Teams](content-search.md).

### <a name="auditing"></a>Controllo

La ricerca nel log di controllo viene collegata direttamente alla Portale di conformità di Microsoft Purview e consente di impostare avvisi, nonché report sugli eventi di controllo, consentendo l'esportazione di set di eventi specifici o generici del carico di lavoro per l'uso e l'indagine da parte dell'amministratore in una sequenza temporale di controllo illimitata. È possibile impostare avvisi per tutti i dati del log di controllo all'interno del Portale di conformità di Microsoft Purview e filtrare ed esportare questi dati per un'ulteriore analisi. Per altre informazioni sulla ricerca di eventi di Microsoft Teams nel Portale di conformità di Microsoft Purview, vedere [Cercare eventi in Microsoft Teams nel log di controllo](audit-log-events.md).

## <a name="privacy"></a>Privacy

In Microsoft, la protezione dei dati è la nostra massima priorità. Per informazioni sulle procedure relative alla privacy, vedere:  

- [Privacy presso Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Il nostro impegno per la privacy e la sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Per i professionisti IT: Privacy e sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architettura Information Protection

La figura seguente indica il flusso di inserimento dei dati di Teams sia per Exchange che per SharePoint per i file e i messaggi di Teams.

> [!div class="mx-imgBorder"]
> ![Diagramma del flusso di lavoro dei dati di Teams in Exchange e SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figura seguente indica il flusso di inserimento delle riunioni di Teams e i dati delle chiamate a Exchange.

> [!div class="mx-imgBorder"]
> ![Diagramma del flusso di lavoro delle riunioni di Teams e dei dati delle chiamate a Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Può essere necessario attendere fino a 24 ore per individuare il contenuto di Teams.

## <a name="licensing"></a>Licenze

Per quanto riguarda le funzionalità di protezione delle informazioni, gli abbonamenti a Microsoft 365, gli abbonamenti Office 365 e le licenze autonome associate determineranno il set di funzionalità disponibili.

Per informazioni su come determinare la necessità delle licenze di implementare funzionalità per la sicurezza e la conformità, consultare [i requisiti di licenza](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) per le caratteristiche di sicurezza e conformità.

> [!NOTE]
> Non è necessario abilitare ricerca contenuto, eDiscovery (standard) e eDiscovery (Premium) nel Portale di conformità di Microsoft Purview. Per altre informazioni, vedere [Soluzioni microsoft 365 eDiscovery](/microsoft-365/compliance/ediscovery).

## <a name="location-of-data-in-teams"></a>Posizione dei dati in Teams

I dati di Teams risiedono nell'area geografica associata all'organizzazione Office 365 o Microsoft 365 dell'utente. Per vedere quali aree geografiche sono attualmente supportate, consulta [Posizione dei dati in Microsoft Teams](location-of-data-in-teams.md).

Se è necessario vedere quale area contiene i dati per il tenant, passare al profilo [interfaccia di amministrazione di Microsoft 365](https://portal.office.com/adminportal/home) >  **Impostazioni** > **organizzazione**. Scorrere verso il basso fino a **Posizione dati**.

> [!div class="mx-imgBorder"]
> ![Screenshot della tabella Posizione dati che include Teams nell'interfaccia di amministrazione.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Standard di conformità

Teams usa i seguenti standard: [ISO 27001](/microsoft-365/compliance/offering-iso-27001), [ISO 27018](/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1 e SOC 2](/microsoft-365/compliance/offering-soc), [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech) e [EU Model Clauses (EUMC)](/microsoft-365/compliance/offering-eu-model-clauses). All'interno del framework di conformità di Microsoft, Microsoft classifica Microsoft 365 e Office 365 applicazioni e servizi in quattro categorie. Ogni categoria è definita da specifici impegni di conformità che devono essere rispettati affinché un servizio Microsoft 365 o Office 365, o un servizio Microsoft correlato, sia elencato in tale categoria.

I dettagli sono disponibili in Risorse per la [protezione dei dati](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides). Teams supporta anche la conformità a Cloud Security Alliance.

## <a name="related-topics"></a>Argomenti correlati

[Sicurezza di Microsoft 365](/microsoft-365/security/)

[Conformità a Microsoft 365](/microsoft-365/compliance/)

[Offerte di conformità Microsoft](/microsoft-365/compliance/offering-home)
