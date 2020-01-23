---
title: 'App pazienti per amministratori Teams '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: App pazienti per amministratori Teams
ms.openlocfilehash: 550a92ac638f1d83cf8bca9a89e0e29d323247e0
ms.sourcegitcommit: d7fab927e96954f294f28dfb33c0889f736b3ab5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259065"
---
# <a name="patients-app-overview"></a>Panoramica dell'app Pazienti

L'applicazione patients è un'app Store di Microsoft teams disponibile per tutti gli utenti di teams. L'app consente ai team di assistenza paziente costituiti da operatori clinici (ad esempio infermieri, medici, assistenti sociali) di curare e rivedere elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti.

L'app ha due modalità:

- La modalità connessa EMR che si connette a EMR tramite FHIR. L'app modalità connessa EMR rimane in anteprima privata e i clienti interessati o gli amministratori possono richiedere l'accesso all'app eliminando Microsoft un messaggio di posta elettronica su teamsforhealthcare@service.microsoft.com con le informazioni sul tenant di Office 365.
- La modalità manuale che consente ai team di assistenza di aggiungere/apportare manualmente le informazioni sul paziente. L'applicazione è disponibile nell'app teams Store per gli utenti finali da scaricare per impostazione predefinita ed è in anteprima pubblica. L'app può essere limitata a determinate sezioni di utenti che usano [criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md)

## <a name="usage-example"></a>Esempio di utilizzo

Durante le sessioni di arrotondamento su ogni turno in reparto medico, i clinici si radunano presso la stazione di cura per discutere gli ultimi aggiornamenti sullo stato di avanzamento dei pazienti nel reparto.  Evidenziano le metriche chiave critiche (non necessariamente mediche o che esplicitano sulle cartelle cliniche dei pazienti) e assicurano che il paziente sia sul percorso di scorrimento a destra per il discarico in base alla diagnosi. Per aggirare questi pazienti, l'infermiera di carica configura l'app paziente in un team in cui vengono aggiunti tutti i clinici e aggiunge i pazienti a un elenco di pazienti. Durante i turni, gli infermieri e gli altri responsabili della cura per il paziente accedono a Microsoft teams e l'app patients sui loro dispositivi mobili e aggiornano le informazioni pertinenti sul paziente nel dispositivo e quindi tutti gli altri membri del team di assistenza possono vedere gli aggiornamenti e le note e rimanere sincronizzati. Due volte al giorno, all'inizio e alla fine di un turno, hanno anche riunioni di team multi-disciplinari per passare all'elenco dei pazienti e usare l'app pazienti per mettere a terra se stessi e condividere informazioni su ogni paziente usando l'app pazienti in uno schermo di grandi dimensioni. Spesso, alcuni clinici possono anche accedere a queste riunioni di team in remoto ed essere ancora parte della discussione.

## <a name="configure-patients-app"></a>Configurare l'app pazienti

Per informazioni su come preparare l'ambiente per l'uso dell'app pazienti in modalità EMR, vedere [integrazione di record sanitari elettronici in Microsoft teams](patients-app.md). Dovrai anche vedere gestire i [criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md) per abilitare l'app patients per l'organizzazione.

Per informazioni su come gli utenti finali possono accedere e installare l'app patients in un team di cui sono proprietari o gestiti, vedere [Introduzione a Microsoft teams patients](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393) 

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Domande frequenti (FAQ)

**Dove sono archiviati i dati dell'app patients?**

Tutti i dati immessi dagli utenti finali nell'app patients, incluso lo schema column/field, i dati effettivi immessi nell'elenco e negli elementi di elenco (ad esempio i pazienti) vengono archiviati nell'infrastruttura di Exchange online sicura e conforme. Tutti i dati vengono archiviati nella cassetta postale del gruppo associata al team. Questa architettura consente all'app patients di realizzare facilmente la data Residency, il supporto per il cloud governativo (in futuro) e altre caratteristiche di conformità/protezione delle informazioni, come il supporto di eDiscovery. L'app patients opera in un ambito del team. Sarà necessario installare un'istanza dell'app per Team.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Da dove posso acquisire l'app pazienti?**

Se l'app pazienti è abilitata per l'organizzazione dall'amministratore, qualsiasi utente finale può accedere all'app store teams e aggiungere l'app patients a un team di cui fanno parte. Per altre informazioni, Vedi [gestire i criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md).

**È possibile avere più istanze dell'app patients in un team perché è così che funziona il reparto/unità?**

Attualmente è possibile installare un'unica istanza dell'app patients per un team specifico e solo nel canale generale. All'interno dell'app, tuttavia, è possibile creare più elenchi per affrontare scenari multicanale o di isolamento/separazione. Per impostazione predefinita, tutti i membri del team avranno accesso alla scheda pazienti nel canale generale. 

**È possibile esportare tutti i dati dall'app patients?**
Non in questo momento, ma questa funzionalità sarà disponibile a breve. 

**Dato che questa app ospita PHI, esiste un controllo per impedire l'accesso non autorizzato o la conformità alle normative?**

Sì, c'è. Tutte le singole azioni dell'interfaccia utente eseguite da Microsoft teams nell'app patients vengono controllate e disponibili nel centro sicurezza e conformità. In [questo articolo vengono](patients-audit.md) illustrati i dettagli

## <a name="related-topics"></a>Argomenti correlati

[Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)
