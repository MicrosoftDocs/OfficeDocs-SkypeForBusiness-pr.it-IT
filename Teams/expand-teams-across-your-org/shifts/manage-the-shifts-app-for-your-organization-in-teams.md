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
description: Informazioni su come configurare e gestire l'app Turni in Teams per gli operatori in prima linea nell'organizzazione.
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
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app Turni per l'organizzazione in Microsoft Teams

> [!IMPORTANT]
> Microsoft StaffHub è stato ritirato il 30 giugno 2020. Stiamo creando funzionalità di StaffHub in Microsoft Teams. Oggi, Teams include l'app Turni per la gestione della pianificazione e altre funzionalità verranno implementazioni nel tempo. StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020. Chiunque tenti di aprire StaffHub viene visualizzato un messaggio che li indirizza a scaricare Teams. Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview-of-shifts"></a>Panoramica di Turni

L'app Turni in Microsoft Teams mantiene i dipendenti in prima linea connessi e sincronizzati. È progettato per primo per la gestione del tempo e la comunicazione per i team in modo rapido ed efficace. Turni consente ai dipendenti in prima linea e ai loro manager di usare i propri dispositivi mobili per gestire le pianificazioni e restare in contatto.

- I responsabili creano, aggiornano e gestiscono le pianificazioni dei turni per i team. Possono inviare messaggi a una persona ("c'è una perdita sul pavimento") o all'intero team ("il responsabile locale arriva tra 20 minuti"). Possono anche inviare documenti di criteri, bollettini di notizie e video. 
- I dipendenti visualizzano i turni programmati, vedono chi altro è pianificato per la giornata, richiedono uno scambio o un'offerta di turno e richiedono un periodo di riposo. 

È importante sapere che Attualmente Turni non supporta gli utenti guest. Questo significa che i guest di un team non possono essere aggiunti o utilizzare le pianificazioni dei turni quando l'accesso guest è attivato in Teams. 

> [!Note]
> Per informazioni dettagliate sulle funzionalità di Turni su piattaforme diverse, vedi le [funzionalità di Teams per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>Disponibilità di Turni

Turni è disponibile in tutti gli SKU Enterprise in cui Teams è disponibile.

## <a name="location-of-shifts-data"></a>Posizione dei dati di Turni

I dati di Turni sono attualmente archiviati in Azure in data center in America del Nord, Europa occidentale e Asia Pacifico. Per altre informazioni sulla posizione di archiviazione dei dati, vedere [Dove sono i dati?](http://o365datacentermap.azurewebsites.net/)

## <a name="set-up-shifts"></a>Configurare Turni

### <a name="enable-or-disable-shifts-in-your-organization"></a>Abilitare o disabilitare Turni nell'organizzazione

Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams nell'organizzazione. È possibile disattivare o attivare l'app a livello di organizzazione nella pagina Gestisci [app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.
2. Nell'elenco delle app eseguire una delle operazioni seguenti:

    - Per disattivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi scegliere **Blocca.**
    - Per attivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi scegliere **Consenti.**

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Turni per utenti specifici dell'organizzazione

Per consentire o impedire a utenti specifici dell'organizzazione di usare Turni, [](../../manage-apps.md) assicurarsi che l'opzione Turni sia attivata per l'organizzazione nella pagina Gestisci app, quindi creare criteri di autorizzazione per le app personalizzati e assegnarli a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione per le app in Teams.](../../teams-app-permission-policies.md)

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usare i criteri di configurazione dell'app FrontlineWorker per aggiungere Turni a Teams

I criteri di configurazione delle app consentono di personalizzare Teams per evidenziare le app più importanti per gli utenti dell'organizzazione. Le app impostate in un criterio vengono aggiunte alla barra dell'app sulla barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams in cui gli utenti possono accedervi rapidamente e &mdash; &mdash; facilmente.
 
Teams include un criterio di configurazione predefinito dell'app FrontlineWorker che è possibile assegnare agli operatori sul campo nell'organizzazione. Per impostazione predefinita, il criterio include le app Attività, Turni, Chat e Chiamate. 

Per visualizzare i criteri di FrontlineWorker, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di configurazione **dell'app Teams.**  >  

![Screenshot dei criteri di configurazione dell'app FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Screenshot del criterio di configurazione dell'app FrontlineWorker nell'interfaccia di amministrazione di Microsoft Teams")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Assegnare i criteri di configurazione dell'app FrontlineWorker agli utenti

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Cercare gli eventi di Turni nel log di controllo

**(in anteprima)**

È possibile eseguire ricerche nel log di controllo per visualizzare le attività di Turni nell'organizzazione.  Per altre informazioni su come eseguire ricerche nel [](../../audit-log-events.md#shifts-in-teams-activities) log di controllo e per visualizzare un elenco delle attività di Turni registrate nel log di controllo, vedere Cercare gli eventi [nel log di controllo in Teams.](../../audit-log-events.md)

Prima di eseguire ricerche nel log di controllo, è necessario attivare il controllo nel Centro [& conformità.](https://protection.office.com) Per altre informazioni, vedere Attivare o disattivare [la ricerca nel log di controllo.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="related-topics"></a>Argomenti correlati

- [Guida turni per i dipendenti in prima linea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Assegnare i criteri agli utenti in Teams](../../assign-policies.md)
