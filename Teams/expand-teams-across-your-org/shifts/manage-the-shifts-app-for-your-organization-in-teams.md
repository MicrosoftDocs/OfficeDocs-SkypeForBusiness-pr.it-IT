---
title: Gestire l'app Turni per l'organizzazione
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Informazioni su come configurare e gestire l'app Turni in Teams per i lavoratori in prima linea nell'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fa274c8aa068d7b17ce35d17525b58152677de07
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288374"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app Turni per l'organizzazione in Microsoft Teams

## <a name="overview-of-shifts"></a>Panoramica di Turni

L'app Turni in Microsoft Teams mantiene i dipendenti in prima linea connessi e sincronizzati. È progettato per la gestione e la comunicazione del tempo per i team in modo rapido ed efficace. I turni consentono ai dipendenti in prima linea e ai loro manager di usare i dispositivi mobili per gestire le pianificazioni e tenersi in contatto.

- I manager creano, aggiornano e gestiscono le pianificazioni dei turni per i team. Possono inviare messaggi a una persona ("c'è una perdita sul pavimento") o all'intero team ("il responsabile locale arriverà tra 20 minuti"). Possono anche inviare documenti con criteri, bollettini di notizie e video.
- I dipendenti visualizzano i propri turni successivi, vedono quali sono gli altri colleghi pianificati per la giornata, possono richiedere o offrire un cambio di turno e richiedere un permesso.

È importante sapere che i turni attualmente non supportano gli ospiti. Ciò significa che gli utenti guest in un team non possono essere aggiunti o usare la programmazione dei turni quando l’accesso guest è attivato in Teams.

> [!Note]
> Per informazioni dettagliate sulle funzionalità di Turni su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilità di Turni

Turni è disponibile in tutte le SKU Enterprise dove Teams è disponibile.

## <a name="location-of-shifts-data"></a>Posizione dei dati di Turni

I dati di Turni sono attualmente archiviati in Azure nei data center in America del Nord, Europa occidentale e Asia Pacifico. Per altre informazioni sulla posizione di archiviazione dei dati, vedere [Dove sono i dati?](http://o365datacentermap.azurewebsites.net/)

## <a name="set-up-shifts"></a>Configurare Turni

### <a name="enable-or-disable-shifts-in-your-organization"></a>Abilitare o disabilitare Turni nell'organizzazione

Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams nell’organizzazione. È possibile disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Nell'elenco delle app cercare l'app Turni, selezionarla e quindi impostare l'interruttore Stato su **Bloccato** o **Consentito**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Turni per utenti specifici nell'organizzazione

Per consentire o impedire a utenti specifici dell'organizzazione di usare Turni, verificare che l'opzione Turni sia attivata per l'organizzazione nella [pagina Gestisci](../../manage-apps.md) app. Creare quindi criteri di autorizzazione dell'app personalizzati e assegnarli a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](../../teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Usare i criteri di configurazione dell'app per aggiungere Turni Teams

I criteri di configurazione delle app consentono di personalizzare Teams per evidenziare le app più importanti per gli utenti dell'organizzazione. Le app impostate in un criterio vengono aggiunte alla barra delle app&mdash;la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobile di Teams&mdash;dove gli utenti possono accedervi rapidamente e facilmente.

È possibile creare criteri [di configurazione dell'app personalizzati](../../teams-app-setup-policies.md) aggiungendo l'app Turni e quindi [assegnando il criterio](../../assign-policies-users-and-groups.md) agli utenti. In caso contrario, è possibile usare i criteri di configurazione dell'app che fanno parte dei pacchetti di criteri Frontline Worker e Frontline Manager.

Un [pacchetto di](../../manage-policy-packages.md) criteri in Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione. Il set di criteri nei pacchetti di criteri Frontline Worker e Frontline Manager include un criterio di configurazione dell'app che aggiunge l'app Turns e altre app che supportano le attività di comunicazione e collaborazione per quel ruolo.

È consigliabile usare i pacchetti di criteri Frontline Worker e Frontline Manager per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per la forza lavoro in prima linea.

## <a name="search-the-audit-log-for-shifts-events"></a>Cercare nel log di controllo gli eventi di Turni

**(in anteprima)**

È possibile eseguire ricerche nel log di controllo per visualizzare le attività di Turni nell’organizzazione.  Per altre informazioni su come eseguire ricerche nel log di controllo e vedere un elenco delle [attività di Turni](../../audit-log-events.md#shifts-in-teams-activities) registrate nel log di controllo, vedere [Cercare nel log di controllo eventi di Teams](../../audit-log-events.md).

Prima di poter eseguire ricerche nel log di controllo, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://protection.office.com). Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="related-topics"></a>Argomenti correlati

- [Guida di Turni per i lavoratori in prima linea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Assegnare i criteri agli utenti in Teams](../../policy-assignment-overview.md)
- [Turni connettori](shifts-connectors.md)
