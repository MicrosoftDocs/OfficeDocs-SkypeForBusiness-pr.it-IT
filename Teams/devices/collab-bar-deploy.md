---
title: Distribuire Microsoft Teams Rooms in Android
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leggere questo articolo per informazioni sulla distribuzione di Microsoft Teams Rooms in Android.
ms.openlocfilehash: f5f49a7e461153d24837d28d7160a475e4992eba
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267811"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Distribuire Microsoft Teams Rooms in Android

La distribuzione di Microsoft Teams Rooms su Android può essere suddivisa nelle fasi seguenti:

- **Preparazione del sito** Verificare che le posizioni di distribuzione (sale) soddisfino i requisiti di distribuzione.
- **Conformità del servizio** Creare account delle risorse e assegnarli ai dispositivi ([vedere Creare un account delle risorse usando la interfaccia di amministrazione di Microsoft 365](resource-account-ui.md)). Anche se è consigliabile usare una licenza dedicata per le sale, un account utente finale con licenza appropriata può anche accedere a Teams Rooms su Android.
- **Configurazione e distribuzione** Configura Teams Rooms e collega le periferiche necessarie (vedi la documentazione del produttore per i dettagli).

Per gestire Teams Rooms, è necessario essere un amministratore globale, un amministratore del servizio teams o un amministratore di dispositivi di Teams. Per altre informazioni sui ruoli di amministratore, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Preparazione del sito

Mentre i dispositivi ordinati vengono distribuiti all'organizzazione, collaborare con la rete, le strutture e i team audio visivi per assicurarsi che i requisiti di distribuzione siano soddisfatti e che ogni sito e sala sia pronto in termini di alimentazione, rete e visualizzazione.

I nostri suggerimenti per i siti della barra di collaborazione sono:

- Camere con dimensioni fino a 5 persone
- Account delle risorse dedicati
- Schermi abilitati per il tocco
- Cavi Ethernet
- Qualità del servizio (QoS) abilitata nella rete per i file multimediali di Microsoft Teams

Per considerazioni relative all'installazione fisica, vedere la documentazione del produttore e, se disponibile, sfruttare l'esperienza del team audio prima di installare e montare schermi ed eseguire il cavi.

> [!TIP]
> Assicurarsi di consultare [Preparare la rete per Teams per](../prepare-network.md) la pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.
>
> Non è consigliabile posizionare server proxy tra i dispositivi Teams e Internet. Per altre informazioni sui server proxy e Teams, vedere [Server proxy per Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icona che descrive i punti decisionali.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti di conformità del sito per le barre di collaborazione per Microsoft Teams.</li><li>Verificare di aver fornito larghezza di banda sufficiente per ogni sito.</li></ul>|
| ![Icona che illustra i passaggi successivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione della barra di collaborazione.</li></ul>|

## <a name="service-readiness"></a>Prontezza del servizio

Prima di distribuire Teams Rooms, è necessario decidere se dovranno usare gli account delle risorse di Microsoft 365, gli account utente finali o una combinazione di entrambi. Gli account delle risorse di Microsoft 365 sono cassette postali e account di Teams dedicati a risorse specifiche, ad esempio una sala, un proiettore e così via. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite al momento della creazione. A meno che Teams Rooms non sia dedicato a una persona specifica per uso privato, è consigliabile configurare un account delle risorse di Microsoft 365.

### <a name="using-a-resource-account"></a>Uso di un account di risorsa

Se si decide di configurare un account di risorse di Microsoft 365, è necessario acquistare una licenza per la sala riunioni. La licenza sala riunioni include una cassetta postale delle risorse che consente agli utenti dell'organizzazione di prenotare la sala riunioni tramite Outlook o Teams. La licenza consente inoltre la condivisione di video e audioconferenze e schermo tra i partecipanti alla riunione.

Se è necessario ricevere o effettuare chiamate da o verso un numero di telefono esterno, potrebbe essere necessario un Piano per chiamate o una licenza per Microsoft 365 Business Voice [componente aggiuntivo](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Se nell'organizzazione è abilitata l'opzione Routing diretto, è necessario solo lo SKU sala riunioni.

Quando si crea un account della risorsa, è possibile scegliere se consentire all'account di accettare o rifiutare automaticamente le convocazioni riunione, consentire riunioni ricorrenti, specificare con quale anticipo le persone possono prenotare la risorsa e così via.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Per altre informazioni sugli account delle risorse di Microsoft 365, vedere [Creare un account di risorsa usando il interfaccia di amministrazione di Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icona che descrive i punti decisionali.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se effettuare o ricevere telefonate esterne e identificare i requisiti di licenza per gli account delle risorse.</li></ul>|
| ![Icona che illustra i passaggi successivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare gli account delle risorse.</li></ul>|

## <a name="configuration-and-deployment"></a>Configurazione e distribuzione

La pianificazione della configurazione e dell'implementazione riguarda le seguenti aree principali:

- Provisioning dell'account delle risorse
- Distribuzione di dispositivi
- Teams Rooms configurazione di applicazioni e periferiche
-  Test
- Gestione asset

### <a name="account-provisioning"></a>Provisioning dell'account

Se si prevede di usare gli account delle risorse di Microsoft 365 per consentire agli utenti di prenotare barre di collaborazione, seguire le istruzioni in [Creare un account di risorsa usando la interfaccia di amministrazione di Microsoft 365](resource-account-ui.md) per creare un account di risorse di Microsoft 365 per ogni barra di collaborazione che ne richiede una. È anche qui che è necessario aggiungere una licenza per la sala riunioni all'account della risorsa e, se si desidera effettuare o ricevere chiamate da o verso numeri di telefono esterni, una licenza Piano per chiamate o Business Voice se l'organizzazione non usa l'instradamento diretto.

Se si vuole assegnare Teams Rooms a singoli utenti per uso privato, non è necessario configurare altri account. Gli utenti possono accedere alle barre di collaborazione usando i propri account personali.

> [!TIP]
> Creare nomi visualizzati descrittivi e di facile comprensione per gli account delle risorse di Microsoft 365. Questi sono i nomi che gli utenti vedranno quando cercano e aggiungono Teams Rooms alle riunioni. È possibile usare una convenzione come *Site*-*Room Name*(*Max Room Capacity*), quindi, ad esempio, Curie, una sala riunioni di 4 persone a Londra, potrebbe avere il nome visualizzato LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icona che descrive i punti decisionali.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione per gli account delle risorse dedicati.</li><li>Decidere se creare singoli account o usare script di provisioning in blocco.</li></ul>|
| ![Icona che illustra i passaggi successivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>|

### <a name="device-deployment"></a>Distribuzione di dispositivi

Successivamente, è necessario creare il piano per consegnare i dispositivi e le periferiche assegnate alle stanze, quindi procedere con l'installazione e la configurazione.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icona che descrive i punti decisionali.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno Teams Rooms sul sito e effettueranno la configurazione e i test.</li></ul>|
| ![Icona che illustra i passaggi successivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avvia il test del dispositivo.</li></ul>|

### <a name="testing"></a> Test

Dopo aver distribuito Teams Rooms, è consigliabile testarli. Accedi a Teams Rooms e verifica che le funzionalità previste funzionino. È consigliabile verificare che vengano visualizzate nella sezione **Barre di collaborazione** nella scheda **Dispositivi di Teams** dell'interfaccia di amministrazione di Microsoft Teams. È anche importante effettuare una serie di chiamate e riunioni di test per controllare la qualità e le prestazioni.

Nell'ambito dell'implementazione generale di Microsoft Teams, è consigliabile configurare la creazione di file per Call Quality Dashboard (CQD), monitorare le tendenze della qualità e partecipare al processo di verifica della qualità dell'esperienza. Per altre informazioni, vedere la [Guida alla revisione della qualità dell'esperienza](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Gestione asset

Nell'ambito della distribuzione, è consigliabile aggiornare il registro risorse con il nome della chat room, l'account delle risorse connesso e i dispositivi periferici assegnati.

## <a name="related-topics"></a>Argomenti correlati

[Creare account di risorse per sale e dispositivi teams condivisi](../rooms/with-office-365.md)