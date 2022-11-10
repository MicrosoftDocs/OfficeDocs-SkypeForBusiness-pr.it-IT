---
title: Panoramica della certificazione delle app da parte di Microsoft
description: Informazioni sul programma di conformità dell’app Microsoft 365 per la sicurezza, la conformità e la privacy delle app di terze parti.
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 09/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b0f01942dcee0ed5f2696c7e6ab5b31d67a98856
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912875"
---
# <a name="find-teams-apps-that-undergo-microsoft-365-app-compliance-program-for-security-compliance-and-privacy"></a>Trovare le app di Teams soggette al programma di conformità delle app di Microsoft 365 per la sicurezza, la conformità e la privacy

Il programma di conformità Microsoft controlla e verifica un'app in base ai controlli derivati dai framework leader del settore. Il certificato dimostra che vengono implementate procedure di sicurezza e conformità complesse per proteggere i dati dei clienti quando l'app viene attivata in un'organizzazione. Il programma prevede le fasi seguenti:

* [Verifica dell'autore](#publisher-verification).
* [Attestazione dell'autore](#publisher-attestation).
* [Certificazione Microsoft 365](#microsoft-365-certification).

## <a name="publisher-verification"></a>Verifica autore

Prima che uno sviluppatore di app possa inviare la propria app a Microsoft, lo sviluppatore deve sottoporsi a una verifica. Uno sviluppatore verifica la propria identità usando l'account Microsoft Partner Network (MPN) e associa questo account MPN alla registrazione dell'app. La verifica dell'autore consente agli amministratori e agli utenti finali di comprendere l'autenticità degli sviluppatori di applicazioni. La verifica dell'autore offre i vantaggi seguenti:

* Maggiore trasparenza e riduzione dei rischi per i clienti: questa funzionalità consente ai clienti di comprendere quali app usate nelle organizzazioni vengono pubblicate dagli sviluppatori di cui si fidano.
* Personalizzazione migliorata: viene visualizzato un `verified` badge nella richiesta di consenso di Azure Active Directory, nella pagina App aziendali e in altre interfacce utente usate da utenti finali e amministratori.
* Adozione aziendale più fluida: gli amministratori possono configurare i criteri di consenso degli utenti, con lo stato di verifica degli editori come criterio primario dei criteri.

## <a name="publisher-attestation"></a>Attestazione dell'editore

L'attestazione dell'autore è il livello successivo del programma di conformità delle app. Le app con attestazione dell’autore offrono agli amministratori maggiore sicurezza sulle misure di conformità e sicurezza di un'app e riducono il tempo necessario per rivederle in un'app. L'attestazione rifletterà le procedure di sicurezza, gestione dei dati e conformità di un'app rispetto a più di 80 fattori di rischio identificati da [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security). Il processo di attestazione dell'autore può essere avviato prima del completamento della verifica del server di pubblicazione.

Agli sviluppatori di app viene chiesto di completare un'autovalutazione che include le domande frequenti poste dai clienti e dagli amministratori IT per valutare la sicurezza e la conformità di un'app. Microsoft pubblica quindi queste informazioni per una valutazione più semplice e tempestiva. Per saperne di più, vedere [Guida all'attestazione](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

Gli amministratori possono controllare rapidamente le app con attestazione dell’autore in tre modi diversi.

* Per ottenere ulteriori informazioni su un'app, consultare i dettagli di un'app specifica al relativo link su [Sicurezza e conformità delle app di Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps). In alternativa, selezionare il `Publisher attestation`link nell’[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/).

  :::image type="content" source="media/attested-app-tac3.png" alt-text="Nell'interfaccia di amministrazione di Teams, quando si controllano i dettagli di un'app dalla pagina Gestisci app, si vede l'icona dell'editore attestato sul banner nella pagina dei dettagli dell'app.":::

* Nell’interfaccia di amministrazione di Teams, quando si controllano i dettagli di un'app dalla pagina **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**, si vede l'icona dell'editore attestato sul banner nella pagina dei dettagli dell'app.

  :::image type="content" source="media/attested-app-tac1.png" alt-text="Nell’interfaccia di amministrazione di Teams, l'icona dell’autore attestato viene visualizzata in tutte le app con attestazione.":::

* Nell'interfaccia di amministrazione di Teams, prima di [concedere le autorizzazioni per l'app](app-permissions-admin-center.md), un segno di spunta blu davanti al nome dell'app indica che si tratta di un'app con attestazione dell'editore. Tutte le app di Microsoft 365 passano anche attraverso l'attestazione dell'editore, quindi viene visualizzato un segno di spunta blu anche per le app di Microsoft 365.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Nell’interfaccia di amministrazione di Teams, nella finestra di dialogo per concedere le autorizzazioni, gli amministratori possono controllare il segno di spunta blu per essere certi che l'app abbia un autore attestato.":::

Nella pagina dei dettagli dell'attestazione per un'app attestata o certificata sono elencati i dettagli seguenti.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Informazioni dettagliate fornite per le app attestate.":::

## <a name="microsoft-365-certification"></a>Certificazione Microsoft 365

La certificazione dell'app viene ottenuta tramite:

* Revisione di un analista qualificato.
* Approvazione di una valutazione completa incentrata sui framework, i processi e le procedure di sicurezza e conformità di un'app.

Controlliamo l'app in base a una serie di controlli di sicurezza derivati dai framework standard leader del settore.

Il certificato dimostra le solide pratiche di sicurezza e conformità messe in atto per proteggere i dati dei clienti quando l'app viene utilizzata in un'organizzazione. Ulteriori informazioni su come gli amministratori e gli utenti finali possono beneficiare della certificazione sono disponibili su [Panoramica del programma di conformità delle app di Microsoft 365](/microsoft-365-app-certification/docs/enterprise-app-certification-guide).

Gli amministratori possono verificare rapidamente la presenza delle app certificate Microsoft 365 nei modi seguenti.

* Quando si raccolgono ulteriori informazioni su un'applicazione sul web, vedere l'icona dello scudo nella [documentazione Microsoft sull'applicazione](/microsoft-365-app-certification/teams/teams-apps).

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="Visualizzare le informazioni sulla certificazione di Microsoft 365 nell'articolo dettagliato della guida sulla sicurezza e la conformità di un'app.":::

* Quando si controlla un'applicazione nell’[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/policies/manage-apps), ordinare l'elenco delle applicazioni utilizzando la colonna Certificazione. Visualizzare l'icona e, facoltativamente, selezionare il collegamento per accedere alla pagina specifica dell'app menzionata in precedenza.

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Visualizzare lo stato della certificazione Microsoft 365 di un'app nell'interfaccia di amministrazione di Teams." lightbox="media/m365cert-apps-list2.png":::

* Quando si visualizzano i dettagli di un'app, vedere l'icona del certificato Microsoft 365 nel banner dell'app.

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Visualizzare le informazioni sulla certificazione Microsoft 365 nel banner dell'app quando si gestisce un'app specifica nell’interfaccia di amministrazione di Teams":::

* Nell'interfaccia di amministrazione di Teams, prima di [concedere le autorizzazioni per l'app](app-permissions-admin-center.md), un segno di spunta blu davanti al nome dell'app indica che si tratta di un'app con attestazione dell'editore. Tutte le app di Microsoft 365 passano anche attraverso l'attestazione dell'editore, quindi viene visualizzato un segno di spunta blu anche per le app di Microsoft 365.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Nell'interfaccia di amministrazione di Teams, nella finestra di dialogo per concedere le autorizzazioni, gli amministratori possono controllare il segno di spunta blu per essere certi che l'app sia certificata Microsoft 365.":::

## <a name="view-security-compliance-and-privacy-information"></a>Visualizzare le informazioni su sicurezza, conformità e privacy

È possibile trovare informazioni su sicurezza, privacy, conformità e comportamenti per un'app attestata o certificata nella [documentazione Microsoft](/microsoft-365-app-certification/teams/teams-apps) e nell'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/policies/manage-apps).

### <a name="microsoft-documentation"></a>Documentazione Microsoft

Sono elencati i dettagli su sicurezza, privacy, conformità e altro ancora di ogni app negli articoli della guida specifici dell'app collegati relativi alla [sicurezza e conformità delle app di Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Argomenti su cui vengono fornite informazioni dettagliate per le app sottoposte al programma di conformità Microsoft.":::

### <a name="teams-admin-center"></a>Interfaccia di amministrazione di Teams

Quando si valuta un'applicazione, è possibile utilizzare Cloud Access Security Brokers (CASB) indipendenti, come Microsoft Cloud App Security (MCAS), per trovare informazioni sulla sicurezza e sui comportamenti di un'applicazione. L'interfaccia di amministrazione di Teams include le informazioni sulla sicurezza e sulla conformità fornite da MCAS per le app certificate Microsoft 365. Controllare queste informazioni nella pagina dei dettagli dell'applicazione, per verificare se l'applicazione soddisfa le vostre esigenze di sicurezza.

> [!NOTE]
> Questa funzionalità è disponibile per tutti gli amministratori, indipendentemente dal fatto che l'organizzazione disponga o meno di una licenza che supporta MCAS.

Per accedere alle informazioni MCAS per un'app:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Selezionare **Certificazione** per ordinare le app ed eseguire il push di tutte le app certificate Microsoft 365 all'inizio della tabella.

1. Scegliere un'app certificata per Microsoft 365.

1. Selezionare la scheda **Sicurezza e conformità**.

   :::image type="content" source="media/mcas.png" alt-text="Screenshot della scheda Sicurezza e conformità dell'interfaccia di amministrazione di Teams":::

   Per altri dettagli sulle funzionalità supportate per l'app, selezionare l'elenco a discesa per ogni categoria.

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>Visualizzare l'informativa sulla privacy e le condizioni per l'utilizzo di un'app

Nell’interfaccia di amministrazione di Teams, ogni pagina dell'app contiene un collegamento all'informativa sulla privacy e alle condizioni per l'utilizzo dell'app.

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="Dall’interfaccia di amministrazione di Teams, gli amministratori possono accedere al collegamento all'informativa sulla privacy e alle condizioni per l'utilizzo per ogni app." lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>Articoli correlati

* [Visualizzare le autorizzazioni per le app e concedere il consenso dell'amministratore](app-permissions-admin-center.md).
