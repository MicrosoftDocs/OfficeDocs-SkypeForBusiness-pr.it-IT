---
title: Panoramica della sicurezza e della conformità in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Una panoramica delle caratteristiche di sicurezza e conformità di Microsoft teams, inclusi il controllo e la creazione di report, la ricerca di contenuto di conformità, eDiscovery e altro ancora.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9e9b07ed1ca995d673ef6ea79652cb880c4dff6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243191"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Panoramica della sicurezza e della conformità in Microsoft Teams
======================================================

Microsoft teams è basato sul cloud di livello aziendale di Office 365 Hyper-Grade, offrendo le funzionalità avanzate di sicurezza e conformità che i nostri clienti si aspettano.

Teams è conforme a livello D. Sono inclusi i seguenti standard: ISO 27001, ISO 27018, SSAE16 SOC 1 e SOC 2, HIPAA e clausole modello EU (EUMC). In Microsoft Compliance Framework Microsoft classifica le applicazioni e i servizi di Office 365 in quattro categorie. Ogni categoria è definita da specifici impegni di conformità che devono essere soddisfatti per un servizio di Office 365 o un servizio Microsoft correlato, da elencare in tale categoria.

I servizi nelle categorie di conformità C e D che hanno impegni di conformità leader del settore sono abilitati per impostazione predefinita. I servizi nelle categorie A e B sono dotati di controlli per attivare o disattivare questi servizi per un'intera organizzazione. I dettagli sono disponibili nel [Framework conformità per gli standard e](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)le normative del settore. Teams supporta anche la conformità a Cloud Security Alliance.

Teams applica anche l'autenticazione a livello di team e a livello di organizzazione a due fattori, Single Sign-on tramite Active Directory e la crittografia dei dati in transito e a riposo. I file sono archiviati in SharePoint e sono supportate dalla crittografia di SharePoint. Le note sono archiviate in OneNote e sono supportate dalla crittografia di OneNote. I dati di OneNote sono archiviati nel sito del team di SharePoint. La scheda wiki può essere usata anche per l'acquisizione di note e il contenuto viene archiviato anche nel sito del team di SharePoint.

È stato inoltre aggiunto il supporto per la ricerca nel log di controllo, eDiscovery e blocco legale per canali, chat e file, nonché per la gestione delle applicazioni per dispositivi mobili con Microsoft Intune. Per gestire queste impostazioni, accedere al centro conformità & sicurezza di Office 365. 

Per altre informazioni su Office 365 sicurezza & conformità, vedere [configurare il tenant di office 365 per aumentare la sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

## <a name="auditing-and-reporting"></a>Controllo e creazione di report

La ricerca nel log di controllo si connette direttamente al centro conformità & sicurezza di Office 365 ed espone le abilità per impostare avvisi e/o segnalare l'evento di controllo rendendo disponibile, l'esportazione di set di eventi specifici o generici per i carichi di lavoro per l'uso e l'analisi dell'amministratore, in un sequenza temporale di controllo illimitata. Tutti i dati del log di controllo sono disponibili per la configurazione di avvisi all'interno del centro conformità & sicurezza di Office 365, nonché per l'applicazione di filtri ed esportazioni per ulteriori analisi. Fare riferimento a questo [collegamento](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) per altre informazioni su come eseguire una ricerca nel log di controllo per gli eventi di Microsoft Teams nel centro conformità & sicurezza di Office 365. 

## <a name="compliance-content-search"></a>Ricerca di contenuto di conformità

La ricerca di contenuto può essere usata per cercare tutti i dati dei team attraverso ricche funzionalità di filtro ed esportati in un contenitore specifico per il supporto della conformità e del contenzioso. Questa operazione può essere eseguita con o senza un caso di eDiscovery. In questo modo gli amministratori della conformità possono raccogliere i dati dei team in tutti gli utenti, rivederli ed esportarli per ulteriori elaborazioni. Fare riferimento a questo [collegamento](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) per altre informazioni su come eseguire una ricerca di contenuto di conformità per il contenuto di Microsoft Teams nel centro conformità & sicurezza di Office 365. 

Suggerimento: il tipo Microsoft teams può essere usato per filtrare fino a Microsoft teams solo contenuto, ad esempio messaggi di chat e canali, riunioni e chiamate. 

## <a name="ediscovery"></a>eDiscovery

Electronic Discovery è l'aspetto elettronico dell'identificazione, della raccolta e della produzione di informazioni archiviate elettronicamente (ESI) in risposta a una richiesta di produzione in una causa legale o in un'inchiesta. Le funzionalità includono la gestione dei casi, la conservazione, la ricerca, l'analisi e l'esportazione di dati Team. Questo include chat, messaggistica e file, riepiloghi di riunioni e chiamate. Per le riunioni e le chiamate dei team, un riepilogo degli eventi accaduti nella riunione e nella chiamata viene creato e reso disponibile in eDiscovery. 

Per altre informazioni su come eseguire eDiscovery in Security & Compliance Center e eseguire la ricerca di contenuto di conformità per il contenuto dei team, visitare i collegamenti seguenti: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Ricerca contenuto](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

I clienti possono sfruttare eDiscovery sul posto o [Advanced eDiscovery] per i rispettivi requisiti (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4). La tabella seguente illustra le differenze tra i due:


| |EDiscovery sul posto  |EDiscovery avanzato  |
|---------|---------|---------|
|Gestione dei casi     |X        |X         |
|Controllo di accesso  |X         |X         |
|Ricerche di contenuto     |X         | X        |
|Blocco/i   |X         | X        |
|Esportazione     |X         |X         |
|Rilevamento della duplicazione     |-         |X         |
|Ricerca della pertinenza con l'apprendimento automatico    |-         |X         |
|Analisi dei dati non strutturata      |-         |X         |


## <a name="legal-hold"></a>Blocco legale

Durante un contenzioso, è spesso necessario che tutti i dati associati a un utente (custode) o a un team vengano mantenuti preservato in modo che possa essere usato come prova per il caso. Questa operazione viene eseguita inserendo un utente (cassetta postale dell'utente) o un team in attesa legale. Quando un team all'interno di teams viene messo in blocco sul posto (sottoinsieme della raccolta di siti o delle cassette postali tramite query mirate o contenuto filtrato) o blocco per controversia legale (intera cassetta postale o raccolta siti), il blocco viene inserito nella cassetta postale dei gruppi. Ciò assicura che anche se gli utenti finali eliminano o modificano i messaggi di canale che vengono ingeriti nella cassetta postale del gruppo, le copie non modificabili del contenuto vengono mantenute e disponibili nella ricerca di eDiscovery. Le esenzioni legali vengono in genere applicate nel contesto di un caso di eDiscovery. Vedere [questo](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) articolo della Guida per informazioni più dettagliate sulla conservazione e le detiene nel centro conformità & sicurezza di Office 365. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Architettura di protezione delle informazioni per Microsoft teams. 

La figura seguente indica il flusso di ingestione dei dati del team sia in Exchange che in SharePoint per i file e i messaggi del team. 

![Diagramma del flusso di lavoro dei dati di teams in Exchange e SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Nella figura seguente viene indicato il flusso di ingestione delle riunioni di team e la chiamata di dati a Exchange.

![Diagramma del flusso di lavoro delle riunioni di team e chiamata di dati a Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Per individuare il contenuto di teams, è possibile attendere fino a 24 ore di ritardo.

<a name="licensing"></a>Licensing
---------------

Per quanto riguarda le funzionalità di protezione delle informazioni, gli abbonamenti a Office 365 e le licenze autonome associate determineranno il set di caratteristiche disponibile.


| Funzionalità di protezione delle informazioni | Office 365 Business Essentials | Office 365 Business Premium | Office 365 Enterprise E1 | Office 365 Enterprise E3/E4 | Office 365 Enterprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Archivio              |               -                |              -              |            -             |             Sì             |           Sì            |
|        EDiscovery sul posto        |               -                |              -              |            -             |             Sì             |           Sì            |
|        EDiscovery avanzato        |               -                |              -              |            -             |              -              |           Sì            |
|            Blocco legale             |               -                |              -              |            -             |             Sì             |           Sì            |
|     Ricerca di contenuto di conformità     |               -                |             Sì             |           Sì            |             Sì             |           Sì            |
|      Controllo e creazione di report       |              Sì               |             Sì             |           Sì            |             Sì             |           Sì            |
|       Accesso condizionale\*        |              Sì               |             Sì             |           Sì            |             Sì             |           Sì            |

> [!NOTE]
> \*L'accesso condizionale richiede licenze aggiuntive


| |  |  |
|---------|---------|---------|
|![Icona che rappresenta un punto decisionale](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Punto decisionale         |L'organizzazione ha le licenze necessarie per soddisfare i requisiti di conformità e sicurezza aziendale?         |
|![Icona che rappresenta i passaggi successivi](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Passaggi successivi         |Esaminare le licenze correnti dell'organizzazione e verificare che soddisfi tutti i requisiti aziendali per la conformità e la sicurezza.         |

Prima di abilitare una qualsiasi di queste funzionalità, assicurati di avere accesso al centro conformità & sicurezza nell'interfaccia di amministrazione di Microsoft 365. Per impostazione predefinita, gli amministratori del tenant hanno accesso.

La ricerca di contenuto e eDiscovery non richiedono l'abilitazione nel centro conformità & sicurezza.

<a name="location-of-data-in-teams"></a>Posizione dei dati in teams
-------------------------

I dati in teams si trovano nell'area geografica associata al tenant di Office 365. Attualmente, teams supporta le aree Australia, Canada, Francia, India, Giappone, Regno Unito, Corea del sud, Sud Africa, Americhe, APAC e EMEA. 

> [!IMPORTANT]
> I team attualmente offrono la residenza dati in Australia, Canada, Francia, India, Giappone, Regno Unito, Corea del sud e Sud Africa solo per i nuovi inquilini. Un nuovo tenant viene definito come un tenant che non ha un singolo utente del tenant che accede a teams. I tenant esistenti provenienti da Australia, India, Giappone e Corea del sud continueranno ad avere i dati dei team archiviati nell'area APAC. I tenant esistenti in Canada continueranno ad avere i loro dati archiviati nelle Americhe. I tenant esistenti in Francia, Regno Unito e Sud Africa continueranno ad avere i loro dati archiviati nell'area EMEA.

Per altre informazioni su South African data Residency per Teams è possibile trovare il post di Blog di Antonio Sagar, [Microsoft teams lancia il South African data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611).

Altre informazioni sulla residenza di dati in Corea del sud per i team viene fornita per gentile concessione del post di Blog di Antonio Sagar, [Microsoft teams lancia il sud coreano data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171).

Per altre informazioni sul lancio della residenza di dati in India e Regno Unito per i team, leggere il post di Blog di anmariana, [Microsoft teams avvia l'India data Residency, altro GEOS presto disponibile](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827). 

Per altre informazioni su Canada data Residency per Teams, leggere il post di Blog di Antonio Sagar, [Microsoft teams avvia Canada data Residency, Australia e Giappone presto disponibile](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Per saperne di più sul lancio di data Residency in Australia e Giappone per i team, leggere il post di Blog di Antonio Sagar, [Microsoft teams avvia l'Australia e Japan data Residency](https://go.microsoft.com/fwlink/?linkid=867773). 

Per altre informazioni sul lancio di France data Residency per Teams, leggere il post di Blog di Antonio Sagar, [Microsoft teams lancia France data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466).

Per visualizzare l'area geografica contenente i dati per il tenant, accedere al**profilo dell'organizzazione****delle impostazioni** > dell'interfaccia di [Amministrazione](https://portal.office.com/adminportal/home) > di Microsoft 365. Scorrere verso il basso fino a **posizione dati**. 

![Screenshot della tabella della posizione dei dati, inclusi i team nell'interfaccia di amministrazione](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Come funzionano i criteri di accesso condizionale per i team?
-------------------------

Microsoft teams si basa molto su Exchange Online, SharePoint Online e Skype for business online per scenari di produttività di base, come riunioni, calendari, chat di interoperabilità e condivisione di file. I criteri di accesso condizionale impostati per queste app Cloud si applicano a Microsoft teams quando un utente accede direttamente a Microsoft teams-in qualsiasi client. 

Microsoft teams è supportato separatamente come app cloud nei criteri di accesso condizionale di Azure Active Directory. I criteri di accesso condizionale impostati per l'app cloud di Microsoft teams si applicano a Microsoft teams quando un utente accede. Tuttavia, senza i criteri corretti per altre app come Exchange Online e SharePoint Online, gli utenti potrebbero essere ancora in grado di accedere direttamente a tali risorse. Per altre informazioni sulla configurazione di criteri di accesso condizionale in Azure Portal, vedere: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

I client desktop di Microsoft teams per Windows e Mac supportano l'autenticazione moderna. L'autenticazione moderna porta l'accesso in base alla libreria di autenticazione di Azure Active Directory (ADAL) alle applicazioni client di Microsoft Office tra piattaforme.

L'applicazione desktop Microsoft teams supporta AppLocker.  Per altre informazioni sui prerequisiti di AppLocker, vedere: requisiti per l'uso di AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Privacy in teams
--------------------------

Come cliente di Office 365, si è proprietari e si controllano i dati. Microsoft non usa i dati per altro che fornire il servizio a cui si è sottoscritto. In qualità di provider di servizi non analizziamo la posta elettronica, i documenti o i team per la pubblicità o per scopi non correlati ai servizi. Microsoft non ha accesso al contenuto caricato. Come OneDrive for business e SharePoint Online, i dati dei clienti restano all'interno del tenant.

Per altre informazioni sulla nostra informazione relativa all'attendibilità e alla sicurezza, visitare il [Centro protezione Microsoft](https://microsoft.com/trustcenter). Teams segue le stesse linee guida e i principi del Centro protezione Microsoft.

<a name="related-topics"></a>Argomenti correlati
----------------------
[Collegamenti sicuri ATP di Office 365](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
