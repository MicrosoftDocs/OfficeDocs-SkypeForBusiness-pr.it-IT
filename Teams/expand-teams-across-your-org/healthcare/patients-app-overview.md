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
description: Informazioni sull’app Pazienti per amministratori di Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803504"
---
# <a name="patients-app-overview"></a>Panoramica dell'app Pazienti

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente. Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti. Estrai il modello Coordinamento pazienti in Elenchi per iniziare. Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).

L'applicazione Pazienti è un'app dello Store di Microsoft Teams disponibile per tutti gli utenti di Teams. L'app consente ai team sanitari dei pazienti costituiti da operatori clinici (ad esempio infermieri, medici, assistenti sociali) di curare e rivedere gli elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti.

L’app ha due modalità:

- La modalità EMR Connected che si connette a EMR tramite FHIR. L'app in modalità EMR Connected rimane in anteprima privata e i clienti o gli amministratori interessati possono richiedere l'accesso all'app inviando una e-mail a Microsoft all'indirizzo [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) con informazioni sulla loro organizzazione Microsoft 365.
- La modalità manuale che consente ai team sanitari di aggiungere / importare manualmente le informazioni sul paziente. L'applicazione è disponibile nell'App Store di Teams per consentire agli utenti finali di scaricarla in anteprima privata. L'app può essere limitata a determinate sezioni di utenti che utilizzano [criteri di configurazione delle app](../../teams-app-setup-policies.md) in Teams. Per accedere all'app, il tuo tenant deve far parte del Technology Adoption Program (TAP). Inviaci una e-mail a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) per avviare il processo di richiesta di accesso.

## <a name="usage-example"></a>Esempio di utilizzo

Durante i giri visite ad ogni turno nei reparti medici, i medici si riuniscono in infermeria per discutere gli ultimi aggiornamenti sui progressi dei pazienti del reparto.  Evidenziano le metriche critiche chiave (non necessariamente mediche o esplicite nelle cartelle cliniche dei pazienti) e si assicurano che il paziente sia sulla giusta rotta verso la dimissione in base alla diagnosi. Per tenere sotto controllo i pazienti, l'infermiera caposala imposta l'app Pazienti in un team in cui vengono aggiunti tutti i medici e aggiunge i pazienti a un elenco. Durante i giri visite, gli infermieri e gli altri operatori sanitari accedono a Microsoft Teams e all'app Pazienti sui propri dispositivi mobili e aggiornano le informazioni rilevanti sui pazienti dal proprio dispositivo; di conseguenza, tutti gli altri membri del team sanitario possono vedere tali aggiornamenti e note e rimanere aggiornati. Due volte al giorno, all'inizio e alla fine di un turno, partecipano anche a riunioni di team multidisciplinari per esaminare l'elenco dei pazienti e utilizzare l'app Pazienti per impratichirsi e condividere informazioni su ciascun paziente utilizzando l'app Pazienti su un ampio display. Spesso, alcuni medici possono anche connettersi a queste riunioni dei team da remoto e continuare a far parte della discussione.

## <a name="configure-patients-app"></a>Configurare app Pazienti

Per informazioni su come preparare l'ambiente per utilizzare l'app Pazienti in modalità EMR, vedere [Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md). Vedi anche [Gestire i criteri di configurazione delle app in Microsoft Teams](../../teams-app-setup-policies.md) per abilitare l'app Pazienti per la tua organizzazione.

Per informazioni su come gli utenti finali possono accedere e installare l’app Pazienti in un team di cui sono proprietari o coordinatori, vedere [Introduzione a Microsoft Teams Pazienti](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Domande frequenti (FAQ)

**Dove vengono archiviati i dati dell'app Pazienti?**

Tutti i dati inseriti dagli utenti finali nell'app Pazienti, inclusi lo schema di colonne / campi, i dati effettivi inseriti nell'elenco e gli elementi dell'elenco (ad esempio i pazienti), vengono archiviati nell'infrastruttura sicura e conforme di Exchange Online. Tutti i dati vengono archiviati nella casella postale del gruppo associata al team. Questa architettura consente all'app Pazienti di soddisfare facilmente la residenza dei dati, il supporto cloud governativo (disponibile in futuro) e altre funzionalità di protezione delle informazioni / conformità come il supporto eDiscovery. L'app Pazienti opera nell'ambito di un team. Dovrai installare un'istanza dell'app per team.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Dove posso acquistare l'app Pazienti?**

Se l'app Pazienti è abilitata per la propria organizzazione dall'amministratore, qualsiasi utente finale può accedere all'app store di Teams e aggiungere l'app Pazienti a un team di cui fa parte. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in Microsoft Teams](../../teams-app-setup-policies.md).

**Posso avere più istanze dell'app Pazienti in un team perché è così che opera il mio reparto / unità?**

Al momento, puoi installare solo un'istanza dell'app Pazienti per un determinato team e solo nel canale generale. Tuttavia, all'interno dell'app, è possibile creare più elenchi per affrontare scenari multicanale o di isolamento / separazione. Per impostazione predefinita, tutti i membri del team avranno accesso alla scheda Pazienti nel canale generale. 

**Posso esportare tutti i dati dall'app Pazienti?**
Non adesso, ma questa funzione sarà presto disponibile. 

**Poiché questa app supporta PHI, è previsto un controllo per impedire l'accesso non autorizzato o il rispetto delle normative?**

Sì. Ogni singola azione dell'interfaccia utente eseguita da un utente di Microsoft Teams sull'app Pazienti viene controllata e resa disponibile nel centro sicurezza e conformità. I dettagli sono spiegati in [Log di controllo per l'app Pazienti](patients-audit.md).

## <a name="related-topics"></a>Argomenti correlati

[Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)
