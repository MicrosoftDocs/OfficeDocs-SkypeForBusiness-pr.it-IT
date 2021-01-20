---
title: Gestire l'app turni per l'organizzazione
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
description: Informazioni su come configurare e gestire l'app turni in teams per i lavoratori Frontline nell'organizzazione.
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
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909090"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app turni per l'organizzazione in Microsoft Teams

> [!IMPORTANT]
> Efficace il 30 giugno 2020, Microsoft StaffHub è stato ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020. Chiunque tenti di aprire StaffHub viene visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Panoramica dei turni

L'app turni in Microsoft teams mantiene i lavoratori in prima linea connessi e sincronizzati. È stato costruito per la prima volta per la gestione e la comunicazione del tempo veloce ed efficace per i team. Turni consente agli operatori di Frontline e ai loro manager di usare i loro dispositivi mobili per gestire le pianificazioni e tenersi in contatto.

- I manager creano, aggiornano e gestiscono le pianificazioni di turno per i team. Possono inviare messaggi a una sola persona ("c'è una fuoriuscita sul pavimento") o all'intero team ("il GM regionale arriva in 20 minuti"). Possono anche inviare documenti di policy, notiziari e video. 
- I dipendenti visualizzano i turni imminenti, vedere chi altro è programmato per il giorno, richiedere di scambiare o offrire un turno e richiedere un permesso. 

È importante sapere che i turni attualmente non supportano gli utenti guest. Ciò significa che gli ospiti di un team non possono essere aggiunti o usare le pianificazioni di turni quando l'accesso Guest è attivato in teams. 

> [!Note]
> Per informazioni dettagliate sulle funzionalità di spostamento su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilità di turni

Turni è disponibile in tutti gli SKU aziendali in cui è disponibile teams.

## <a name="location-of-shifts-data"></a>Posizione dei dati di turni

Turni i dati sono attualmente archiviati in Azure nei data center in Nord America, Europa occidentale e Asia Pacifico. Per altre informazioni sulla posizione di archiviazione dei dati, vedere [dove sono i dati](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurare turni

### <a name="enable-or-disable-shifts-in-your-organization"></a>Abilitare o disabilitare i turni nell'organizzazione

Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams dell'organizzazione. Puoi disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.
2. Nell'elenco delle app eseguire una delle operazioni seguenti:

    - Per disattivare i turni per l'organizzazione, cercare l'app turni, selezionarla e quindi selezionare **blocca**.
    - Per attivare i turni per l'organizzazione, cercare l'app turni, selezionarla e quindi selezionare **Consenti**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Abilitare o disabilitare turni per utenti specifici dell'organizzazione

Per consentire o bloccare gli utenti specifici dell'organizzazione dall'uso di turni, verificare che i turni siano attivati per l'organizzazione nella pagina [Gestisci app](../../manage-apps.md) e quindi creare un criterio di autorizzazione per le app personalizzate e assegnarlo a tali utenti. Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](../../teams-app-permission-policies.md).

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usare i criteri di configurazione dell'app FrontlineWorker per aggiungere i turni ai team

I criteri di configurazione delle app consentono di personalizzare i team per evidenziare le app più importanti per gli utenti dell'organizzazione. Le app impostate in un criterio sono bloccate alla barra dell'app &mdash; la barra sul lato del client desktop teams e nella parte inferiore dei client per dispositivi mobili in &mdash; cui gli utenti possono accedervi in modo rapido e semplice.
 
Teams include un criterio di configurazione dell'app FrontlineWorker predefinito che puoi assegnare a operatori Frontline nell'organizzazione. Per impostazione predefinita, il criterio include le app attività, turni, chat e chiamate. 

Per visualizzare i criteri di FrontlineWorker, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di configurazione dell'app **Teams app**  >  .

![Screenshot dei criteri di configurazione dell'app FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Screenshot dei criteri di configurazione dell'app FrontlineWorker nell'interfaccia di amministrazione di Microsoft Teams")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Assegnare i criteri di configurazione dell'app FrontlineWorker agli utenti

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Eseguire ricerche nel log di controllo per gli eventi turni

**(in anteprima)**

È possibile eseguire una ricerca nel log di controllo per visualizzare le attività di turni nell'organizzazione.  Per altre informazioni su come eseguire una ricerca nel log di controllo e visualizzare un elenco di [attività di turni](../../audit-log-events.md#shifts-in-teams-activities) registrate nel log di controllo, vedere [eseguire la ricerca nel log di controllo per gli eventi in teams](../../audit-log-events.md).

Prima di eseguire una ricerca nel log di controllo, è necessario attivare prima di tutto il controllo nel [centro conformità & sicurezza](https://protection.office.com). Per altre informazioni, vedere [attivare o disattivare la ricerca nel log di controllo](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tieni presente che i dati di controllo sono disponibili solo dal momento in cui hai attivato il controllo.

## <a name="related-topics"></a>Argomenti correlati

- [Sposta la guida per i lavoratori Frontline](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Assegnare i criteri agli utenti in Teams](../../assign-policies.md)
