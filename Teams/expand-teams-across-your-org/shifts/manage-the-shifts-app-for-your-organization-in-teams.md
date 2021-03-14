---
title: Gestire l'app Turni per l'organizzazione
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Informazioni su come configurare e gestire l’app Turni in Teams per gli operatori sul campo dell’organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909090"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app Turni per l'organizzazione in Microsoft Teams

> [!IMPORTANT]
> A partire dal 30 giugno 2020, Microsoft StaffHub è stato ritirato. Stiamo integrando le funzionalità di StaffHub in Microsoft Teams. Al momento, Teams include l’app Turni per la gestione delle pianificazioni. Altre funzionalità verranno implementate nel corso del tempo. StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020. Chiunque provi ad aprire StaffHub visualizza un messaggio che invita a scaricare Teams. Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Panoramica di Turni

L’app Turni in Microsoft Teams consente agli operatori sul campo di rimanere connessi e sincronizzati. È stata ottimizzata per i dispositivi mobili per rendere veloce ed efficace la gestione del tempo e la comunicazione dei team. Turni consente agli operatori sul campo e ai loro manager di usare i propri dispositivi mobili per gestire le pianificazioni e mantenersi in contatto.  

- I manager creano, aggiornano e gestiscono le pianificazioni dei turni per i team. Possono inviare messaggi a una persona ("c'è una perdita sul pavimento") o all'intero team ("il responsabile locale arriverà tra 20 minuti"). Possono anche inviare documenti con criteri, bollettini di notizie e video. 
- I dipendenti visualizzano i propri turni successivi, vedono quali sono gli altri colleghi pianificati per la giornata, possono richiedere o offrire un cambio di turno e richiedere un permesso. 

Turni attualmente non supporta gli utenti guest. Ciò significa che gli utenti guest in un team non possono essere aggiunti o usare la programmazione dei turni quando l’accesso guest è attivato in Teams. 

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
2. Nell'elenco delle app eseguire una delle operazioni seguenti:

    - Per disattivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi selezionare **Blocca**.
    - Per attivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi selezionare **Consenti**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Turni per utenti specifici nell'organizzazione

Per consentire o bloccare l'uso di Turni a utenti specifici dell'organizzazione, assicurarsi che Turni sia attivato per l'organizzazione nella pagina [Gestisci app](../../manage-apps.md) e quindi creare criteri di autorizzazione per l’app personalizzati da assegnare a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in Teams](../../teams-app-permission-policies.md).

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usare il criterio di configurazione dell’app per operatori sul campo per aggiungere Turni a Teams

I criteri di configurazione dell’app consentono di personalizzare Teams per evidenziare le app più importanti per gli utenti dell'organizzazione. Le app impostate in un criterio vengono aggiunte alla barra delle app&mdash;la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobile di Teams&mdash;dove gli utenti possono accedervi rapidamente e facilmente.
 
Teams include un criterio predefinito di configurazione dell’app per operatori sul campo che è possibile assegnare agli operatori sul campo dell’organizzazione. Per impostazione predefinita, il criterio include le app Attività, Turni, Chat e Chiamate. 

Per visualizzare il criterio per operatori sul campo, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Criteri di configurazione dell’app**.

![Screenshot del criterio di configurazione dell’app per operatori sul campo](../../media/firstline-worker-app-setup-policy.png "Screenshot del criterio di configurazione dell’app per operatori sul campo nell’interfaccia di amministrazione di Microsoft Teams.")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Assegnare il criterio di configurazione dell’app per operatori sul campo agli utenti

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Cercare nel log di controllo gli eventi di Turni

**(in anteprima)**

È possibile eseguire ricerche nel log di controllo per visualizzare le attività di Turni nell’organizzazione.  Per altre informazioni su come eseguire ricerche nel log di controllo e vedere un elenco delle [attività di Turni](../../audit-log-events.md#shifts-in-teams-activities) registrate nel log di controllo, vedere [Cercare nel log di controllo eventi di Teams](../../audit-log-events.md).

Prima di poter eseguire ricerche nel log di controllo, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://protection.office.com). Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="related-topics"></a>Argomenti correlati

- [Guida di Turni per gli operatori sul campo](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Assegnare criteri agli utenti in Teams](../../assign-policies.md)
