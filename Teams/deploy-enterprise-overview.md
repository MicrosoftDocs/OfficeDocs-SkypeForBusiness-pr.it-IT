---
title: Panoramica della distribuzione aziendale di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Informazioni su come distribuire le caratteristiche aziendali di Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: fae55eb230c3c0a450a95eb00e50861888bbe3f1
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045575"
---
# <a name="teams-enterprise-deployment-overview"></a>Panoramica della distribuzione aziendale di Teams

Per le aziende di medie e grandi dimensioni, è necessario determinare come verrà distribuito il servizio agli utenti, come distribuire il client Microsoft Teams agli utenti, in che modo la progettazione della rete potrebbe influire sulla qualità delle comunicazioni in tempo reale e così via. Consultare le sezioni seguenti per riferimenti ad articoli utili alla pianificazione di Teams all’interno dell’organizzazione.

> [!NOTE]
> Se non si è già stato fatto, è consigliabile iniziare la distribuzione di Teams attraverso una distribuzione pilota. La distribuzione pilota consentirà all’utente e agli early adopter di acquisire familiarità con Teams e le relative funzionalità prima della pianificazione e della distribuzione finale. Per altre informazioni su come avviare la distribuzione pilota, vedere [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md).

Quando si sono lette le sezioni seguenti e ci si appresta a distribuire Teams nell'organizzazione, vedere [Configurare Microsoft Teams nell'organizzazione](deploy-enterprise-setup.md).

## <a name="architecture"></a>Architettura

Teams è strettamente integrato in Microsoft 365 e usa molte caratteristiche per incrementare chat, condivisione di file, riunioni, telefonia, streaming video e altro ancora. Prima di implementare Teams [, vedere i poster di soluzioni di telefonia e architettura IT di Microsoft Teams](teams-architecture-solutions-posters.md) per acquisire familiarità con il funzionamento di Teams con il resto di Microsoft 365 per creare un'esperienza di collaborazione completa per gli utenti.

## <a name="workloads"></a>Carichi di lavoro

Teams ha tre carichi di lavoro che possono essere distribuiti in modo indipendente l'uno dall'altro:**chat, team e canali**; **riunioni e conferenze** e **sistema telefonico e connettività PSTN (Public Switched Telephone Network)**. Ogni carico di lavoro ha una propria sezione nella documentazione per semplificare l'individuazione di informazioni sul carico di lavoro specifico. Sono incluse informazioni sulla pianificazione della distribuzione.

Per informazioni sulla pianificazione della distribuzione per il carico di lavoro che si vuole distribuire, vedere gli articoli seguenti:

- [Chat, team e canali](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Riunioni e conferenze](deploy-meetings-microsoft-teams-landing-page.md)
- [Sistema telefonico e connettività PSTN](cloud-voice-landing-page.md)

## <a name="network-planner"></a>Network Planner

La pianificazione della rete per Teams è estremamente importante in caso di un numero elevato di utenti, reti complesse o entrambi. Teams supporta le chiamate vocali e le videoconferenze, che si basano sulle comunicazioni in tempo reale per offrire l'esperienza migliore possibile agli utenti. Le reti devono:

- avere una capacità di larghezza di banda sufficiente per contenere il numero di chiamate vocali, videoconferenze, riunioni, condivisione dello schermo simultanei e così via.
- Avere hardware di rete che supporta protocolli di comunicazione in tempo reale.
- Consentire le porte di rete necessarie tra i dispositivi delle reti, i servizi Microsoft 365 e gli utenti esterni.

Vedere gli articoli seguenti per informazioni sui requisiti di rete di Teams:

- [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md)
- [Server proxy per Teams o Skype for Business Online](proxy-servers-for-skype-for-business-online.md)

Per facilitare la pianificazione, Teams include il Network Planner. Il Network Planner pone domande sul numero e sui tipi di utenti disponibili, sul numero di siti dell'organizzazione, sulla capacità di larghezza di banda dei collegamenti di rete e altro ancora. Usando queste informazioni, il Network Planner crea un report che mostra i requisiti di larghezza di banda per ogni attività, insieme ai consigli.

 > [!div class="nextstepaction"]
> [Passare a Network Planner](https://admin.teams.microsoft.com/networkplanner/organization)

(È necessario essere un [amministratore globale Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) per aprire il Network Planner.)

Per informazioni dettagliate sul funzionamento di Network Planner, vedere [Usare Network Planner per Microsoft Teams](network-planner.md).

Per un esempio di come Network Planner può pianificare la rete, vedere [Uso di Network Planner, scenario di esempio](tutorial-network-planner-example.yml).

## <a name="teams-advisor"></a>Assistente per Teams

L'assistente per Teams è una soluzione all'interno di Teams che riunisce team, canali, condivisione di file e Planner per creare un progetto di distribuzione per l'organizzazione. L'assistente di Teams crea un piano di progetto specifico del carico di lavoro selezionato (ad esempio chat, team e canali), che include le attività consigliate da eseguire durante la distribuzione. Ogni attività contiene istruzioni, suggerimenti e collegamenti ad articoli pertinenti, che guidano l'utente nelle fasi del processo. È possibile assegnare facilmente attività a una o più persone e specificare le date di inizio e di fine per ogni attività.

> [!TIP]
> Per informazioni su come usare l'Assistente per Teams per pianificare la distribuzione, completare il modulo di Microsoft Learn [Implementare Teams con l'Assistente per Teams](/learn/modules/m365-teams-rollout-using-advisor/).

> [!div class="nextstepaction"]
> [Passare a Assistente per Teams](https://admin.teams.microsoft.com/teams-deployment)

(È necessario essere un [amministratore globale Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) per aprire l’assistente per Teams.)

Per informazioni dettagliate sul funzionamento dell'Assistente per Teams, vedere [Usare Assistente per Teams per distribuire Microsoft Teams](use-advisor-teams-roll-out.md).

## <a name="lifecycle-and-governance-planning"></a>Pianificazione di ciclo di vita e governance

Quando si pianifica la distribuzione di Teams, è necessario considerare il ciclo di vita di team, canali, file e così via nell'organizzazione. È consigliabile anche scegliere quali tipi di informazioni verranno archiviati in essi. I team possono essere creati per un progetto specifico, per un reparto, oppure possono essere usati come risorsa centrale per l'intera organizzazione. Ognuno di questi usi ha requisiti diversi, che sono alla base di domande come le seguenti:

- Per quanto tempo i team resteranno attivi?
- Chi deve essere il proprietario e il gestore dei team e dei relativi canali?
- Alcuni requisiti di conformità si applicano ad alcuni team, ma non ad altri?
- È necessario un criterio di denominazione per aiutare gli utenti a identificare il team giusto?

La creazione di criteri e linee guida come parte della distribuzione iniziale consente di garantire agli utenti di trovare le informazioni necessarie. Inoltre, i criteri appropriati aiutano a proteggere l'organizzazione dalla perdita di informazioni, a conformarsi ai requisiti normativi e a conservare le informazioni in base alle esigenze ai fini dell'archiviazione.

Per altre informazioni sulla gestione del ciclo di vita e la governance in Teams, vedere:

- [Pianificare la gestione del ciclo di vita in Teams](plan-teams-lifecycle.md)
- [Pianificare la governance in Teams](plan-teams-governance.md)

## <a name="adoption"></a>Adozione

Per fare in modo che l'organizzazione e gli utenti possano ottenere il massimo da Teams, è necessario un programma di adozione. Un programma di adozione efficace può mobilitare gli early adopter che possono:

- articolare i vantaggi dei team con i colleghi e con i responsabili aziendali o di gruppo.
- Aumentare l'entusiasmo per gli altri utenti che vedono in che modo Teams migliora la collaborazione e semplifica la connessione tra loro.
- Aiuta a valutare gli attuali processi aziendali e a formulare suggerimenti su come integrare Teams al loro interno.
- Segnalare al team di distribuzione i successi e le difficoltà che possono contribuire a migliorare il processo di adozione.

Per informazioni dettagliate sulla configurazione di un programma di adozione, vedere [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md).