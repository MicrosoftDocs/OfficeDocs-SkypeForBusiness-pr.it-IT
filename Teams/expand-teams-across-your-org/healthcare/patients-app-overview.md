---
title: 'App Pazienti per amministratori di Teams '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informazioni sull'app Pazienti per amministratori di Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803504"
---
# <a name="patients-app-overview"></a>Panoramica dell'app Pazienti

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell'app Pazienti vengono archiviati nella cassetta postale del gruppo di Office 365 che backup il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non sono più accessibili tramite l'interfaccia utente. Gli utenti possono creare di nuovo i propri elenchi usando [l'app Elenchi.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti. Per iniziare, vedere il modello Pazienti in Elenchi. Per altre informazioni su come gestire l'app Elenchi nell'organizzazione, vedere [Gestire l'app Elenchi.](../../manage-lists-app.md)

L'applicazione Pazienti è un'app di Microsoft Teams disponibile per tutti gli utenti di Teams. L'app consente a team di salute dei pazienti composti da operatori clinici (ad esempio infermieri, medici, social worker) di curare e rivedere elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti.

L'app ha due modalità:

- Modalità di connessione EMR che si connette alle E EMR tramite FHIR. L'app modalità connessione EMR resta in anteprima privata e i clienti o gli amministratori interessati possono richiedere l'accesso all'app inviando a Microsoft un messaggio e-mail all'indirizzo [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) con informazioni sull'organizzazione di Microsoft 365.
- Modalità manuale che consente ai team sanitari di aggiungere/inserire manualmente le informazioni sui pazienti. L'applicazione è disponibile nell'App Store di Teams per il download in anteprima privata da parte degli utenti finali. L'app può essere limitata a determinate sezioni di utenti che usano criteri [di configurazione delle app](../../teams-app-setup-policies.md) in Teams. Per accedere all'app, il tenant deve far parte del programma Technology Adoption Program (TAP). Inviaci un'e-mail [all'indirizzo teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) per avviare il processo di richiesta di accesso.

## <a name="usage-example"></a>Esempio di utilizzo

Durante le sessioni di arrotondamento di ogni turno nei reparti medici, i medici si riuniscono presso la stazione di sviluppo per discutere degli aggiornamenti più recenti sullo stato di avanzamento con i pazienti nella clinica.  Evidenziano le metriche critiche chiave (non necessariamente medicali o esplicite nelle cartelle cliniche dei pazienti) e assicurano che il paziente si trova nel percorso di glide giusto per lo svertio in base alla diagnosi. Per arrotondare questi pazienti, l'infermiera responsabile configura l'app del paziente in un team in cui vengono aggiunti tutti i medici e li aggiunge a un elenco di pazienti. Durante il turno, le infermiere e gli altri operatori del settore sanitario accedono a Microsoft Teams e all'app Pazienti sui loro dispositivi mobili e aggiornano le informazioni rilevanti sui pazienti sul proprio dispositivo, in modo che tutti gli altri membri del team sanitario possano visualizzare gli aggiornamenti e le note e rimanere sincronizzati. Due volte al giorno, all'inizio e alla fine di un turno, hanno anche riunioni multi-team per passare sopra l'elenco dei pazienti e usare l'app Pazienti per macinato e condividere informazioni su ogni paziente usando l'app Pazienti su un grande schermo. Spesso, alcuni medici possono anche accedere a queste riunioni di Teams in remoto e fare ancora parte della discussione.

## <a name="configure-patients-app"></a>Configurare l'app Pazienti

Per informazioni su come preparare l'ambiente per l'uso dell'app Pazienti in modalità EMR, vedere Integrazione di record sanitari [elettronici in Microsoft Teams.](patients-app.md) Sarà anche necessario vedere Gestire i criteri [di configurazione delle app in Microsoft Teams](../../teams-app-setup-policies.md) per abilitare l'app Pazienti per l'organizzazione.

Per informazioni su come gli utenti finali possono accedere e installare l'app Pazienti in un team di loro proprietà o gestiti, vedere Introduzione ai [pazienti di Microsoft Teams.](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Domande frequenti

**Dove vengono archiviati i dati dell'app Pazienti?**

Tutti i dati immessi dagli utenti finali nell'app Pazienti, inclusi lo schema colonna/campo, i dati effettivi immessi nell'elenco e le voci di elenco (ad esempio i pazienti), vengono archiviati nell'infrastruttura sicura e conforme di Exchange Online. Tutti i dati vengono archiviati nella cassetta postale del gruppo associata al team. Questa architettura consente all'app Pazienti di soddisfare facilmente la residenza dei dati, il supporto cloud per enti pubblici (in futuro) e altre caratteristiche di protezione della conformità/informazioni come il supporto di eDiscovery. L'app Pazienti opera in un ambito del team. Sarà necessario installare un'istanza dell'app per ogni team.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Da dove è possibile acquistare l'app Pazienti?**

Se l'app Pazienti è abilitata per l'organizzazione dall'amministratore, qualsiasi utente finale può accedere all'App Store di Teams e aggiungere l'app Pazienti a un team di cui è membro. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in Microsoft Teams.](../../teams-app-setup-policies.md)

**È possibile avere più istanze dell'app Pazienti in un team perché è così che funziona la mia azienda/unità?**

Attualmente è possibile installare solo un'istanza dell'app Pazienti per un determinato team e solo nel canale generale. Tuttavia, all'interno dell'app, è possibile creare più elenchi per affrontare scenari di isolamento/separazione multicanale. Per impostazione predefinita, tutti i membri del team avranno accesso alla scheda Pazienti del canale generale. 

**È possibile esportare tutti i dati dall'app Pazienti?**
Non al momento, ma questa funzionalità sarà disponibile a breve. 

**Poiché questa app supporta phi, è in essere un controllo per impedire l'accesso non autorizzato o la conformità alle normative?**

Sì. Ogni singola azione dell'interfaccia utente eseguita da un utente di Microsoft Teams nell'app Pazienti viene verificata e disponibile nel Centro sicurezza e conformità. I dettagli sono spiegati nei [log di controllo dell'app Pazienti.](patients-audit.md)

## <a name="related-topics"></a>Argomenti correlati

[Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)
