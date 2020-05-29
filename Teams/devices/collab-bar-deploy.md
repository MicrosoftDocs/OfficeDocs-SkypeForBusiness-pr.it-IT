---
title: Distribuire barre di collaborazione per Microsoft Teams
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leggere questo articolo per informazioni sulla distribuzione di barre di collaborazione per Microsoft teams.
ms.openlocfilehash: 71f9482dd5f42ddeb56b32c1a92db033d1f179f7
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410451"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Distribuire barre di collaborazione per Microsoft Teams

La distribuzione di barre di collaborazione per Microsoft teams può essere suddivisa nelle fasi seguenti:

- **Disponibilità del sito** Verificare che i percorsi di distribuzione (sale) soddisfino i requisiti di distribuzione.
- **Disponibilità del servizio** Creare account di risorse e assegnarli ai dispositivi ([vedere creare un account di risorse tramite l'interfaccia di amministrazione di Microsoft 365](resource-account-ui.md)). Mentre ti consigliamo di usare una licenza per la sala dedicata, un account utente finale con licenza appropriata può accedere anche alle barre di collaborazione.
- **Configurazione e distribuzione** Configurare le barre di collaborazione nelle sale e connettere i dispositivi periferici necessari (vedere la documentazione del produttore per le barre di collaborazione).

## <a name="site-readiness"></a>Disponibilità del sito

Mentre i dispositivi ordinati vengono recapitati all'organizzazione, collaborare con i team di networking, servizi e audio-visivi per verificare che i requisiti di distribuzione vengano soddisfatti e che ogni sito e spazio sia pronto in termini di potenza, networking e visualizzazione.

Le nostre raccomandazioni per i siti della barra di collaborazione sono:

- Sale fino a 4 persone in dimensioni
- Account di risorse dedicati
- Schermi abilitati per il tocco
- Cablaggio Ethernet
- Qualità del servizio (QoS) abilitato nella rete per Microsoft teams media

Per considerazioni sull'installazione fisica, vedere la documentazione del produttore e, se disponibile, sfruttare l'esperienza del team di audio-visivo prima di installare e montare schermi ed eseguire i cavi.

> [!TIP]
> Assicurarsi di verificare [preparare la rete per i team](../prepare-network.md) per la pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.
>
> Non è consigliabile collocare i server proxy tra i dispositivi teams e Internet. Per altre informazioni su server e team proxy, vedere [server proxy per Teams](../proxy-servers-for-skype-for-business-online.md).

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti di conformità del sito per le barre di collaborazione per Microsoft teams.</li><li>Verificare di avere fornito larghezza di banda sufficiente per ogni sito.</li></ul>|
| ![Icona che descrive i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione della barra di collaborazione.</li></ul>|

## <a name="service-readiness"></a>Disponibilità del servizio

Prima di distribuire le barre di collaborazione, è necessario decidere se usare gli account delle risorse di Microsoft 365, gli account degli utenti finali o una combinazione di entrambi. Gli account delle risorse di Microsoft 365 sono account di cassette postali e team dedicati a risorse specifiche, ad esempio una sala, un proiettore e così via. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite durante la creazione. A meno che una barra di collaborazione non sia dedicata a un utente specifico per l'uso privato, è consigliabile configurare un account di risorse Microsoft 365.

### <a name="using-a-resource-account"></a>Uso di un account delle risorse

Se si decide di configurare un account Microsoft 365 Resource, è necessario acquistare una licenza per la sala riunioni. La licenza della sala riunioni include una cassetta postale per le risorse che consente alle persone dell'organizzazione di prenotare la sala riunioni tramite Outlook o teams. La licenza consente inoltre la condivisione di video e audio e lo schermo tra i partecipanti alla riunione.

Se è necessario ricevere o effettuare chiamate da o verso un numero di telefono esterno, potrebbe essere necessario un piano di chiamata o una licenza per [il componente aggiuntivo](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)Voice business per Microsoft 365. Se si ha un routing diretto abilitato nell'organizzazione, è necessaria solo la SKU della sala riunioni.

Quando si crea un account di risorse, è possibile scegliere se consentire all'account di accettare o rifiutare automaticamente le convocazioni di riunione, concedere riunioni ricorrenti, specificare la quantità di persone in anticipo che possono prenotare la risorsa e così via.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Per altre informazioni sulle barre di collaborazione per gli account delle risorse di Microsoft 365, vedere [creare un account risorse con l'interfaccia di amministrazione di microsoft 365](resource-account-ui.md).

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se si desidera effettuare o ricevere chiamate telefoniche esterne e identificare i requisiti di licenza per gli account delle risorse.</li></ul>|
| ![Icona che descrive i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare gli account delle risorse.</li></ul>|

## <a name="configuration-and-deployment"></a>Configurazione e distribuzione

La pianificazione della configurazione e della distribuzione comprende le aree principali seguenti:

- Provisioning degli account risorse
- Distribuzione di dispositivi
- Barre di collaborazione per la configurazione di applicazioni e periferiche Microsoft Teams
-  Test
- Asset Management

### <a name="account-provisioning"></a>Provisioning degli account

Se si prevede di usare gli account delle risorse di Microsoft 365 per consentire agli utenti di prenotare le barre di collaborazione, seguire le istruzioni in [creare un account risorse usando l'](resource-account-ui.md) interfaccia di amministrazione di Microsoft 365 per creare un account di risorse di Microsoft 365 per ogni barra di collaborazione che ne ha bisogno. Anche in questo caso è necessario aggiungere una licenza per la sala riunioni all'account delle risorse e, se si vogliono effettuare o ricevere chiamate da o verso numeri di telefono esterni, un piano di chiamata o una licenza vocale aziendale se l'organizzazione non usa il routing diretto.

Se si vogliono assegnare barre di collaborazione a singoli utenti per l'uso privato, non è necessario configurare altri account. Gli utenti possono accedere alle barre di collaborazione usando gli account personali.

> [!TIP]
> Impostare i nomi visualizzati per gli account delle risorse di Microsoft 365 descrittivi e di facile comprensione. Questi sono i nomi che gli utenti vedranno durante la ricerca e l'aggiunta di barre di collaborazione per Microsoft teams alle riunioni. È possibile usare una convenzione come *Site* - il*nome della sala*del sito (*capacità massima della sala*), quindi, ad esempio, Curie, una sala riunioni di 4 persone a Londra, potrebbe avere il nome visualizzato Lon-Curie (4).

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione per gli account delle risorse dedicati.</li><li>Decidere se creare singoli account o usare gli script di provisioning in blocco.</li></ul>|
| ![Icona che descrive i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>|

### <a name="device-deployment"></a>Distribuzione di dispositivi

È quindi necessario creare il piano per consegnare i dispositivi e i dispositivi periferici assegnati alle camere e quindi procedere con l'installazione e la configurazione.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno le barre di collaborazione per Microsoft teams sul sito e intraprendere la configurazione e i test.</li></ul>|
| ![Icona che descrive i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avviare il test del dispositivo.</li></ul>|

### <a name="testing"></a> Test

Dopo la distribuzione delle barre di collaborazione per Microsoft teams, è consigliabile testarle. Accedere al dispositivo e verificare che le funzionalità previste funzionino nel dispositivo distribuito. Ti consigliamo vivamente di verificare che i dispositivi vengano visualizzati nella sezione barre di **collaborazione** nella scheda **dispositivi** dell'interfaccia di amministrazione di Microsoft teams. È anche importante effettuare numerose chiamate di test e riunioni per verificare la qualità e le prestazioni.

Come parte dell'implementazione generale di Microsoft teams, è consigliabile configurare i file di costruzione per il dashboard di qualità delle chiamate (Call Quality Dashboard), monitorare le tendenze della qualità e avviare il processo di revisione della qualità dell'esperienza. Per altre informazioni, vedi la [Guida alla revisione della qualità della prova](https://aka.ms/qerguide).

### <a name="asset-management"></a>Asset Management

Come parte della distribuzione, è necessario aggiornare il registro asset con il nome della sala, l'account delle risorse con accesso e i dispositivi periferici assegnati.

## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per le barre di collaborazione per Microsoft teams usando l'interfaccia di amministrazione di Microsoft Teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
