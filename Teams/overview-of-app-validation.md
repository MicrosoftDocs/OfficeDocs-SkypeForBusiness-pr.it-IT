---
title: Panoramica della convalida delle app e dei test delle app da parte di Microsoft
ms.reviewer: ''
description: Informazioni sui controlli di qualità, la convalida delle app e i programmi di certificazione per le app Teams.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 384a57abb724ee29feb5f93fa171d0bc5ec96f3d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686493"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Controlli e convalida eseguiti da Microsoft sulle app Teams

Microsoft richiede a tutte le app di superare una convalida obbligatoria prima di essere elencata nello Store per gli usi finali. Si applica a tutte le app (ad eccezione delle app personalizzate) pubblicate nel Teams App Store. Inoltre, Microsoft invita gli sviluppatori di app a partecipare a una certificazione facoltativa di app che indica controlli avanzati di conformità, sicurezza e privacy.

Tutte le app sono obbligatoriamente necessarie per aderire ai criteri di certificazione delle app Microsoft. Il team Teams Store esegue oltre 400 test per garantire che le app siano utilizzabili e rispettino standard elevati di privacy e sicurezza.

Per conoscere le linee guida dettagliate sulla convalida a cui aderiscono gli sviluppatori di app, vedi [Linee guida per la convalida per gli sviluppatori](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). Le linee guida si basano sui [criteri di certificazione per le app Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> La convalida e i controlli di Microsoft non sono disponibili per un'app personalizzata in quanto sviluppata all'interno dell'organizzazione ed è disponibile solo per i membri dell'organizzazione.

## <a name="app-validation-and-testing"></a>Convalida e test delle app

Eseguiamo oltre 400 test case per ogni app prima che venga resa disponibile in Teams Store. I test garantiscono la funzionalità, l'esperienza utente e la sicurezza appropriate e assicurano che tutte le app siano conformi ai criteri cmo elencati pubblicamente. Ecco alcuni test eseguiti dal team di convalida app Microsoft per ogni app prima della pubblicazione:

* Assicurarsi che Graph autorizzazioni richieste dall'app siano effettivamente quelle necessarie alla funzionalità dell'app e non eventuali autorizzazioni aggiuntive. Graph le autorizzazioni per le app esistenti vengono regolarmente controllate per assicurarsi che un'app non richieda autorizzazioni aggiuntive.
* Per le app che richiedono agli utenti di accedere e/o disconnettersi è necessaria un'opzione di log/disconnessione.
* Tutti gli autori di app vengono sottoposti a un processo di verifica dettagliato nel Centro per i partner Microsoft. La verifica include la verifica tramite posta elettronica, la verifica aziendale e altro ancora. Per altre informazioni sulla pubblicazione di app, vedi [In che modo gli sviluppatori creano un account del Centro per i partner](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Guida per l'invio per gli sviluppatori](/office/dev/store/add-in-submission-guide) e Modalità di pubblicazione delle app da parte [degli sviluppatori](https://aka.ms/PublishToTeamsStore).
* Solo le app degli autori verificati possono cercare Graph autorizzazioni da parte degli utenti finali.
* Nessuna app può scaricare un file eseguibile.
* Le app sono testate per non contenere annunci, promozione per altre app
* Le app sono testate per funzionare correttamente senza linguaggio offensivo, bot per attacchi informatici, posta indesiderata o contenuti di phishing.
* Tutti i collegamenti in un'app sono funzionali e correlati solo all'offerta dell'app.
* Testiamo e valutiamo regolarmente tutte le app Teams pubblicate nell'ambito dei controlli di integrità dell'App Store.
* L'informativa sulla privacy e le Condizioni per l'utilizzo che coprono Teams app sono pubblicate dall'ISV
* I dettagli di contatto dell'ISV sono disponibili nella presentazione dello Store e nelle rispettive [pagine di attestazione Publisher](/microsoft-365-app-certification/teams/teams-apps).

## <a name="publisher-verification"></a>verifica Publisher

Publisher verifica aiuta gli amministratori e gli utenti finali a comprendere l'autenticità degli sviluppatori di applicazioni integrandoli con il Microsoft Identity Platform. Avere un autore verificato significa che l'autore ha verificato la propria identità usando l'account Microsoft Partner Network (MPN) e ha associato questo account MPN alla registrazione dell'app.

Publisher verifica offre i seguenti vantaggi:

* Maggiore trasparenza e riduzione dei rischi per i clienti: questa funzionalità aiuta i clienti a capire quali app vengono usate nelle loro organizzazioni vengono pubblicate dagli sviluppatori di cui si fidano.
* Personalizzazione migliorata: viene visualizzato un `verified` badge nella richiesta di consenso di Azure Active Directory, nella pagina app Enterprise e in altre interfacce utente usate da utenti finali e amministratori.
* Adozione aziendale più fluida: gli amministratori possono configurare i criteri di consenso degli utenti, con lo stato di verifica degli editori come criterio primario dei criteri.

Inoltre, Microsoft invita gli sviluppatori di app a partecipare al programma di conformità, un approccio rigoroso a due livelli per garantire la qualità, la sicurezza e la conformità dell'app. Teams store ha centinaia di app che vanno oltre l'assolvimento delle linee guida di convalida già dettagliate e sono conformi a questi programmi.

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365 programma per la conformità delle app

Il programma di conformità Microsoft dimostra che un'app viene controllata rispetto ai controlli derivati dai framework standard leader del settore e che sono in atto procedure di sicurezza e conformità complesse per proteggere i dati dei clienti. Il programma ha due fasi:

* Publisher attestazione.
* Microsoft 365 certificazione.

### <a name="publisher-attestation"></a>attestazione Publisher

Lo sviluppatore di app deve completare una valutazione automatica che includa le domande poste di frequente dai clienti o dagli amministratori IT quando valutano la sicurezza e la conformità di un'app. Microsoft pubblica quindi queste informazioni per una valutazione più semplice e tempestiva. Le informazioni includono dettagli sulla gestione dei dati, la sicurezza, la conformità e la privacy quando un'app viene attivata in un'organizzazione.

Per altre informazioni, vedere la [guida pubblicare l'attestazione](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

### <a name="microsoft-365-certification"></a>Certificazione Microsoft 365

La certificazione dell'app viene ottenuta tramite la revisione e l'approvazione da parte di un analista qualificato di una valutazione completa incentrata sui framework, i processi e le procedure di sicurezza e conformità di un'app. L'app viene verificata in base a una serie di controlli di sicurezza derivati dai framework standard leader del settore. Il certificato dimostra che esistono procedure di sicurezza e conformità complesse per proteggere i dati dei clienti quando l'app viene attivata in un'organizzazione.

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
