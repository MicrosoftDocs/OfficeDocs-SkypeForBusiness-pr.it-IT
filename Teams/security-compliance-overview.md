---
title: Panoramica della sicurezza e della conformità
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Panoramica delle caratteristiche di sicurezza e conformità di Microsoft teams, tra cui privacy e crittografia, controllo e creazione di report e altro ancora.
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
ms.openlocfilehash: a9ee7d3d4cd7d877925b649bb3f3b6a8da72ddf0
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937438"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicurezza e conformità in Microsoft Teams

> [!IMPORTANT]
> Per informazioni su come garantire al meglio **la sicurezza mentre tutti lavorano da casa durante l'epidemia di COVID-19**, leggere questi articoli:
>  - [12 principali attività per i team di sicurezza per supportare il lavoro da casa](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Ottimizzare la connettività di Microsoft 365 o Office 365 per gli utenti remoti tramite split tunneling per VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aggiornamento del 2 aprile 2020: [Guida alla sicurezza di teams](teams-security-guide.md)


Microsoft teams è basato sul cloud Microsoft 365 e Office 365 Hyper-Scale, Enterprise-Grade, offrendo le funzionalità di sicurezza e conformità avanzate che i nostri clienti si aspettano. Per altre informazioni sulla pianificazione della sicurezza in Microsoft 365 o Office 365, [la roadmap di sicurezza](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) è un buon punto di partenza. Per altre informazioni sulla pianificazione della conformità in Microsoft 365 o Office 365, è possibile iniziare con [l'articolo piano per la sicurezza e la conformità](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) .


In questo articolo verranno fornite ulteriori informazioni sulla sicurezza e la conformità specifiche per i team. Non perdere questi video di Microsoft Mechanics sulla sicurezza e la conformità:

- [Elementi essenziali di Microsoft teams per it: sicurezza e conformità](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Controlli Microsoft teams per la sicurezza e la conformità](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> Come cliente di Microsoft 365 o Office 365, si è proprietari e si controllano i dati. Microsoft non usa i dati per altro che fornire il servizio a cui si è sottoscritto. In qualità di provider di servizi non analizziamo la posta elettronica, i documenti o i team per la pubblicità o per scopi non correlati ai servizi. Microsoft non ha accesso al contenuto caricato. Come OneDrive e SharePoint in Microsoft 365, i dati dei clienti restano all'interno del tenant. Per altre informazioni sui dati relativi a attendibilità e sicurezza, visitare il [Centro protezione Microsoft](https://microsoft.com/trustcenter). Teams segue le stesse linee guida e i principi del Centro protezione Microsoft.

## <a name="security"></a>Sicurezza

Teams impone l'autenticazione a livello di team e a livello di organizzazione a due fattori, Single Sign-on tramite Active Directory e la crittografia dei dati in transito e a riposo. I file sono archiviati in SharePoint e sono supportate dalla crittografia di SharePoint. Le note sono archiviate in OneNote e sono supportate dalla crittografia di OneNote. I dati di OneNote sono archiviati nel sito del team di SharePoint. La scheda wiki può essere usata anche per l'acquisizione di note e il relativo contenuto viene archiviato anche nel sito del team di SharePoint.

Leggere i [modelli di identità e l'autenticazione](identify-models-authentication.md) per approfondire l'autenticazione e i team e [come funziona l'autenticazione moderna](sign-in-teams.md) in particolare per l'autenticazione moderna.

Poiché teams funziona in collaborazione con SharePoint, OneNote, Exchange e altro ancora, è consigliabile gestire la sicurezza in Microsoft 365 o Office 365 all-up. Per altre informazioni, vedere informazioni su [come configurare l'organizzazione Microsoft 365 o Office 365 per migliorare la sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Attualmente, i [canali privati](private-channels.md) supportano funzionalità limitate di sicurezza e conformità. Il supporto per il set completo di caratteristiche di sicurezza e conformità nei canali privati sarà disponibile a breve.

### <a name="advanced-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat Protection (ATP) è disponibile per Microsoft teams, insieme a SharePoint e OneDrive, applicazioni che si integrano con teams per la gestione del contenuto. ATP consente di determinare se il contenuto di queste applicazioni è di tipo maligno e di bloccare questo contenuto dall'accesso degli utenti.

Modalità di gestione del contenuto interessato dopo il rilevamento dipende dalle impostazioni selezionate in Microsoft 365 o Office 365. Ti consigliamo vivamente di prendere in considerazione tutte le applicazioni per quanto riguarda la configurazione di ATP e per ulteriori informazioni, l'articolo [ATP per SharePoint, OneDrive e Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) fornirà indicazioni dettagliate su come iniziare.

### <a name="safe-links"></a>Collegamenti sicuri

Mentre, in questo momento, i collegamenti sicuri Advanced Threat Protection (ATP) non sono disponibili in Microsoft teams, ora sono in [anteprima pubblica](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) tramite il nostro programma di adozione della tecnologia (TAP) e mentre una data di rilascio per la disponibilità generale non è impostata, verrà aggiornato questo articolo quando arriverà il momento. Nel frattempo, per informazioni sui collegamenti sicuri di Microsoft 365 o Office 365, vedere [collegamenti sicuri ATP](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection). Collegamenti sicuri ATP è disponibile sia in [ATP Plan 1 che in ATP Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide).

### <a name="safe-attachments"></a>Allegati sicuri

Gli allegati sicuri sono una funzionalità progettata per migliorare la sicurezza degli utenti controllando e rilevando gli allegati dolosi. Gli amministratori globali o di sicurezza creano [criteri](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) per la gestione di questi presunti allegati illeciti per impedire che vengano inviati agli utenti, a cui si fa clic e si è agito. La protezione degli allegati sicuri è disponibile per SharePoint, OneDrive e Microsoft teams e Microsoft 365 o Office 365 [Advanced Threat Protection Plan 1 e 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) hanno questa funzionalità. Leggi altre informazioni sugli allegati sicuri e su come possono aiutare a proteggere [l'organizzazione.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="how-conditional-access-policies-work-for-teams"></a>Funzionamento dei criteri di accesso condizionale per i team

Microsoft teams si basa molto su Exchange Online, SharePoint e Skype for business online per scenari di produttività di base, come riunioni, calendari, interoperabilità chat e condivisione di file. I criteri di accesso condizionale impostati per queste app Cloud si applicano a Microsoft teams quando un utente accede direttamente a Microsoft teams-in qualsiasi client.

Microsoft teams è supportato separatamente come app cloud nei criteri di accesso condizionale di Azure Active Directory. I criteri di accesso condizionale impostati per l'app cloud di Microsoft teams si applicano a Microsoft teams quando un utente accede. Tuttavia, senza i criteri corretti per altre app come Exchange Online e SharePoint, gli utenti potrebbero essere ancora in grado di accedere direttamente a tali risorse. Per altre informazioni sulla configurazione di criteri di accesso condizionale in Azure Portal, vedere: [Guida introduttiva di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

I client desktop di Microsoft teams per Windows e Mac supportano l'autenticazione moderna. L'autenticazione moderna porta l'accesso in base alla libreria di autenticazione di Azure Active Directory (ADAL) alle applicazioni client di Microsoft Office tra piattaforme.

L'applicazione desktop Microsoft teams supporta AppLocker.  Per altre informazioni sui prerequisiti di AppLocker, vedere: requisiti per l'uso di [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Conformità

Teams offre una vasta gamma di informazioni utili per le aree di conformità, tra cui conformità delle comunicazioni per canali, chat e allegati, criteri di conservazione, protezione dalla perdita dei dati (DLP), eDiscovery e blocco legale per canali, chat e file, ricerca nel log di controllo e gestione delle applicazioni per dispositivi mobili con Microsoft Intune. Sono state fornite informazioni su tutti questi argomenti e si può accedere al [centro conformità Microsoft 365](https://compliance.microsoft.com) per gestire queste impostazioni.

### <a name="information-barriers"></a>Barriere informative

Gli ostacoli alle informazioni sono criteri messi sul posto dagli amministratori dei team per fare in modo che le persone o i gruppi possano comunicare tra loro (quando non c'è bisogno di un'azienda per farlo o un motivo normativo per impedirne l'esecuzione) e consente inoltre di impostare i criteri relativi a elementi come ricerche e eDiscovery (descritti di seguito). Questi criteri possono influire sugli utenti in chat di 1:1, chat di gruppo o a livello di team.

Per ulteriori informazioni su questo argomento, vedere [barriere informative in Microsoft teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Conformità delle comunicazioni

La conformità delle comunicazioni in Microsoft 365 consente di aggiungere utenti ai criteri in ambito che possono essere configurati per esaminare le comunicazioni di Microsoft teams per il linguaggio offensivo, le informazioni riservate e le informazioni relative agli standard interni e normativi. Le comunicazioni chat e gli allegati associati sia in canali pubblici che privati, le singole chat e gli allegati possono essere analizzati per ridurre al minimo i rischi di comunicazione nell'organizzazione. Per altre informazioni su come configurare i criteri per individuare, acquisire e intervenire per le comunicazioni non appropriate per i team, vedere [conformità delle comunicazioni in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

### <a name="retention-policies"></a>Criteri di conservazione

I criteri di conservazione in Microsoft teams consentono di mantenere i dati importanti per l'organizzazione, per motivi normativi, legali, aziendali o di altro tipo, e anche per rimuovere contenuti e comunicazioni che non sono rilevanti per il mantenimento. È anche possibile usare i criteri di conservazione per mantenere i dati per un periodo di tempo e quindi eliminarli. Per altre informazioni, vedere l'articolo sui [criteri di conservazione in Microsoft teams](retention-policies.md) .

## <a name="sensitivity-labels"></a>Etichette di sensitività

Applicare [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) per proteggere e regolare l'accesso a contenuto aziendale sensibile creato durante la collaborazione all'interno di teams. Ad esempio, applica le etichette che configurano la privacy (pubblico o privato) dei team, controllano l'accesso guest e la condivisione esterna e gestiscono l'accesso da dispositivi non gestiti. Per altre informazioni, vedere l'articolo sulle [etichette di sensitività in Microsoft teams](sensitivity-labels.md) .

### <a name="data-loss-prevention-dlp"></a>Prevenzione della perdita dei dati (DLP)

La prevenzione della perdita dei dati (DLP) in Microsoft teams, oltre alla storia DLP più grande per Microsoft 365 o Office 365, ruota attorno alla disponibilità aziendale quando si tratta di proteggere i dati e i documenti riservati. Indipendentemente dal fatto che siano presenti informazioni riservate in messaggi o documenti, i criteri di prevenzione della perdita dei dati saranno in grado di garantire che gli utenti non condividano questo dato sensibile con le persone sbagliate.

Per informazioni sulla prevenzione della perdita dei dati in teams, consultare [DLP per Microsoft teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams). Un buon articolo per i problemi di Office 365 DLP è una [Panoramica della prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies).

### <a name="ediscovery"></a>eDiscovery

Electronic Discovery, o eDiscovery, è l'aspetto elettronico dell'identificazione, della raccolta e della produzione di informazioni archiviate elettronicamente (ESI) in risposta a una richiesta di produzione in una causa legale o in un'inchiesta. Le funzionalità includono la gestione dei casi, la conservazione, la ricerca, l'analisi e l'esportazione di dati Team. Questo include chat, messaggistica e file, riepiloghi di riunioni e chiamate. Per le riunioni e le chiamate dei team, un riepilogo degli eventi accaduti nella riunione e nella chiamata viene creato e reso disponibile in eDiscovery.

Per altre informazioni su come eseguire Microsoft 365 o Office 365 eDiscovery nel centro sicurezza e conformità e eseguire la ricerca di contenuto di conformità per il contenuto dei team, visitare i collegamenti seguenti:

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[Ricerca contenuto](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Abbiamo un articolo specifico per le squadre per altre informazioni, [eDiscovery delle chat Guest-to-Guest](eDiscovery-investigation.md).

I clienti possono sfruttare eDiscovery o [Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) per i loro requisiti. La tabella seguente illustra le differenze tra i due:

| |eDiscovery  |EDiscovery avanzato  |
|---------|---------|---------|
|Gestione dei casi     |X        |X         |
|Controllo di accesso  |X         |X         |
|Ricerche di contenuto     |X         | X        |
|Blocco/i   |X         | X        |
|Esportazione     |X         |X         |
|Rilevamento della duplicazione     |-         |X         |
|Ricerca della pertinenza con l'apprendimento automatico    |-         |X         |
|Analisi dei dati non strutturata      |-         |X         |

### <a name="legal-hold"></a>Blocco legale

Durante le controversie, potrebbe essere necessario che tutti i dati associati a un utente (custode) o a un team vengano mantenuti come non modificabili, in modo che possano essere usati come elementi di prova per il caso. A questo scopo, è possibile inserire un utente (cassetta postale dell'utente) o un team in attesa legale. Per un blocco legale del team, la cassetta postale del team può essere inserita nelle seguenti esenzioni:

- In-Place blocco (un sottoinsieme della cassetta postale o della raccolta siti tramite query di destinazione o contenuto filtrato viene inserito) oppure
- Blocco per controversia legale (l'intera cassetta postale o raccolta siti viene inserita in attesa).

In entrambi i casi, una volta impostato il blocco, assicura che, anche se gli utenti finali eliminano o modificano i messaggi di canale presenti nella cassetta postale del gruppo, le copie non modificabili del contenuto vengono mantenute e disponibili tramite la ricerca eDiscovery. Le esenzioni legali vengono in genere applicate nel contesto di un caso di eDiscovery.

Vedere la [Panoramica dell'](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) articolo sui criteri di conservazione per comprendere meglio la conservazione e il mantenimento nel centro conformità Microsoft 365. Per altre informazioni specifiche sulle squadre in attesa legale, è anche possibile [inserire un utente o un team di Microsoft teams in un articolo per il blocco legale](legal-hold.md) per saperne di più.

### <a name="compliance-content-search"></a>Ricerca di contenuto di conformità

La ricerca di contenuto può essere usata per cercare tutti i dati dei team tramite ricche funzionalità di filtro. I dati risultanti possono essere esportati in un contenitore specifico per il supporto della conformità e del contenzioso. Questa operazione può essere eseguita con o senza un caso di eDiscovery. In questo modo gli amministratori della conformità possono raccogliere i dati dei team in tutti gli utenti, rivederli ed esportarli per ulteriori elaborazioni. Per altre informazioni su come eseguire una ricerca di contenuto di conformità per Microsoft teams e altri contenuti di Microsoft 365 o Office 365 nel centro conformità Microsoft 365, vedere l'articolo relativo alla [ricerca di contenuti](https://docs.microsoft.com/microsoft-365/compliance/content-search) .

> [!TIP]
> Usando la ricerca di contenuto, è possibile filtrare solo il contenuto di Microsoft teams, ad esempio messaggi di chat e canali, riunioni e chiamate, se necessario.

Per altre informazioni specifiche per le squadre sulla configurazione della ricerca di contenuto, vedere l'articolo [Ricerca contenuto in Microsoft teams](content-search.md) .

### <a name="auditing-and-reporting"></a>Controllo e creazione di report

La ricerca nel log di controllo si connette direttamente al centro conformità Microsoft 365 e offre la possibilità di impostare gli avvisi, nonché di segnalare gli eventi di controllo, consentendo l'esportazione di set di eventi specifici o generici per il carico di lavoro per l'uso dell'amministratore e le indagini in una sequenza temporale di controllo illimitata. È possibile configurare gli avvisi per tutti i dati del log di controllo nel centro conformità Microsoft 365 e filtrare ed esportare questi dati per un'ulteriore analisi. Per altre informazioni su come eseguire una ricerca nel log di controllo per Microsoft 365 o Office 365, vedere la sezione [cercare l'articolo del log di controllo](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) . Per altre informazioni sulla ricerca di eventi Microsoft Teams nel centro conformità Microsoft 365, è anche possibile eseguire il [controllo attiva in teams](audit-log-events.md) per la revisione.

## <a name="privacy"></a>Privacy

In Microsoft proteggere i dati è la priorità più alta. Per informazioni sulle procedure di privacy, leggere:  

- [Privacy in Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Il nostro impegno per la privacy e la sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Per professionisti IT: privacy e sicurezza in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architettura di protezione delle informazioni

La figura seguente indica il flusso di ingestione dei dati del team sia in Exchange che in SharePoint per i file e i messaggi del team.

![Diagramma del flusso di lavoro dei dati di teams in Exchange e SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Nella figura seguente viene indicato il flusso di ingestione delle riunioni di team e la chiamata di dati a Exchange.

![Diagramma del flusso di lavoro delle riunioni di team e chiamata di dati a Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Per individuare il contenuto di teams, è possibile attendere fino a 24 ore di ritardo.

## <a name="licensing"></a>Licenze

Per quanto riguarda le funzionalità di protezione delle informazioni, gli abbonamenti a Microsoft 365, gli abbonamenti a Office 365 e le licenze autonome associate determineranno il set di caratteristiche disponibile.

Per informazioni su come determinare le licenze necessarie per implementare le funzionalità per la sicurezza e la conformità, vedere i [requisiti di licenza](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) per le caratteristiche di sicurezza e conformità.
> [!NOTE]
> La ricerca di contenuto e eDiscovery non devono essere abilitate nel centro sicurezza & conformità per il lavoro.

## <a name="location-of-data-in-teams"></a>Posizione dei dati in Teams

I dati di Teams risiedono nell'area geografica associata all'organizzazione Office 365 o Microsoft 365 dell'utente. Per visualizzare le aree geografiche supportate attualmente, vedere [la posizione dei dati in Microsoft teams](location-of-data-in-teams.md).

Per informazioni sull'area geografica in cui sono alloggiati i dati per il tenant [](https://portal.office.com/adminportal/home), visitare il  >  profilo dell'organizzazione **delle impostazioni** dell'interfaccia di amministrazione di Microsoft 365  >  . Scorrere verso il basso fino a **Posizione dati**.

![Screenshot della tabella della posizione dei dati, inclusi i team nell'interfaccia di amministrazione](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Standard di conformità

Teams USA i seguenti standard: [iso 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001), [ISO 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1 e SOC 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc), [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)e [clausole modello EU (EUMC)](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses). In Microsoft Compliance Framework Microsoft classifica le applicazioni e i servizi Microsoft 365 e Office 365 in quattro categorie. Ogni categoria è definita da specifici impegni di conformità che devono essere soddisfatti per un servizio Microsoft 365 o Office 365 o un servizio Microsoft correlato, da elencare in tale categoria.

I dettagli si trovano nelle risorse per la [protezione dei dati](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides). Teams supporta anche la conformità a Cloud Security Alliance.

## <a name="related-topics"></a>Argomenti correlati

[Sicurezza di Microsoft 365](https://docs.microsoft.com/microsoft-365/security/)

[Conformità a Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/)

[Offerte di conformità Microsoft](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
