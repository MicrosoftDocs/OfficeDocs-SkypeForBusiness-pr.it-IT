---
title: Panoramica della convalida delle app e dei test delle app da parte di Microsoft
ms.reviewer: ''
description: Informazioni sui controlli di qualità e sulla convalida delle app eseguite per le app di Teams.
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
ms.openlocfilehash: fa6a03c5408afcd7cce1d3e48b78b3b1ddb3675a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2022
ms.locfileid: "64756992"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Convalida eseguita da Microsoft per tutte le app di Teams

Microsoft richiede a tutte le app di superare una convalida obbligatoria prima di essere elencata nello Store per gli usi finali. Si applica a tutte le app (ad eccezione delle app personalizzate) pubblicate nell'App Store di Teams. Inoltre, Microsoft incoraggia vivamente gli sviluppatori di app a partecipare a una certificazione facoltativa delle app che indica controlli avanzati di conformità, sicurezza e privacy.

Tutte le app sono obbligatoriamente necessarie per rispettare i criteri di certificazione delle app Microsoft. Il team di Teams Store esegue oltre 400 test per garantire che le app siano utilizzabili e siano conformi a standard elevati di privacy e sicurezza.

Per conoscere le linee guida dettagliate sulla convalida a cui aderiscono gli sviluppatori di app, vedi [Linee guida per la convalida per gli sviluppatori](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). Le linee guida si basano sui [criteri di certificazione per le app Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> La convalida e i controlli di Microsoft non sono disponibili per un'app personalizzata in quanto sviluppata all'interno dell'organizzazione ed è disponibile solo per i membri dell'organizzazione.

## <a name="app-validation-and-testing"></a>Convalida e test delle app

Eseguiamo più di 400 test case per ogni app prima che venga resa disponibile in Teams Store. I test garantiscono funzionalità, esperienza utente e sicurezza appropriate e assicurano che tutte le app siano conformi ai criteri CMO elencati pubblicamente. Di seguito sono riportati alcuni dei test eseguiti dal team di convalida delle app Microsoft per ogni app prima della pubblicazione:

* Assicurarsi che le autorizzazioni graph richieste dall'app siano effettivamente quelle necessarie per la funzionalità dell'app e non le autorizzazioni aggiuntive. Le autorizzazioni graph per le app esistenti vengono controllate regolarmente per assicurarsi che non siano richieste autorizzazioni aggiuntive da un'app.
* Le app che richiedono agli utenti di accedere hanno un'opzione di disconnessione.
* Tutti gli autori di app vengono sottoposti a un processo di verifica dettagliato su Microsoft Partner Center. La verifica include la verifica tramite posta elettronica, la verifica aziendale e altro ancora. Per altre informazioni sulla pubblicazione di app, vedi [In che modo gli sviluppatori creano un account del Centro per i partner](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Guida per l'invio per gli sviluppatori](/office/dev/store/add-in-submission-guide) e [Modalità di pubblicazione delle app da parte degli sviluppatori](https://aka.ms/PublishToTeamsStore).
* Solo le app degli autori verificati possono cercare le autorizzazioni Graph dagli utenti finali.
* Nessuna app può scaricare un file eseguibile.
* Le app vengono testate per non contenere annunci, promozione per altre app
* Le app vengono testate per funzionare in modo appropriato senza linguaggio offensivo, bot di attacco informatico, posta indesiderata o contenuti di phishing.
* Tutti i collegamenti in un'app sono funzionali e correlati solo all'offerta dell'app.
* Testiamo e valutiamo regolarmente tutte le app Teams pubblicate nell'ambito dei controlli di integrità dell'App Store.
* L'informativa sulla privacy e le Condizioni per l'utilizzo che coprono Teams app sono pubblicate dall'ISV
* I dettagli di contatto dell'ISV sono disponibili nella presentazione dello Store e nelle rispettive [pagine di attestazione dell'Editore](/microsoft-365-app-certification/teams/teams-apps).

Inoltre, Microsoft incoraggia gli sviluppatori di app a partecipare al programma di conformità che è un approccio rigoroso a due livelli per garantire la qualità, la sicurezza e la conformità delle app. Teams Store include centinaia di app che vanno oltre il rispetto delle linee guida di convalida già dettagliate e la conformità a questi programmi.

## <a name="publisher-verification"></a>Verifica autore

Prima che uno sviluppatore di app possa inviare la propria app a Microsoft, lo sviluppatore deve sottoporsi a una verifica. Un autore verifica la propria identità usando l'account Microsoft Partner Network (MPN) e associa questo account MPN alla registrazione dell'app. La verifica dell'autore consente agli amministratori e agli utenti finali di comprendere l'autenticità degli sviluppatori di applicazioni che si integrano con Microsoft Identity Platform. La verifica dell'autore offre i vantaggi seguenti:

* Maggiore trasparenza e riduzione dei rischi per i clienti: questa funzionalità consente ai clienti di comprendere quali app usate nelle organizzazioni vengono pubblicate dagli sviluppatori di cui si fidano.
* Personalizzazione migliorata: viene visualizzato un `verified` badge nella richiesta di consenso di Azure Active Directory, nella pagina App aziendali e in altre interfacce utente usate da utenti finali e amministratori.
* Adozione aziendale più fluida: gli amministratori possono configurare i criteri di consenso degli utenti, con lo stato di verifica degli editori come criterio primario dei criteri.

## <a name="see-also"></a>Vedere anche

* [Panoramica per amministratori di Microsoft 365 programma di conformità delle app](overview-of-app-certification.md)
