---
title: Distribuire le barre di collaborazione per Microsoft Teams
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
description: Leggere questo articolo per informazioni sulla distribuzione delle barre di collaborazione per Microsoft Teams.
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962907"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Distribuire le barre di collaborazione per Microsoft Teams

La distribuzione delle barre di collaborazione per Microsoft Teams può essere suddivisa nelle seguenti fasi:

- **Conformità del sito** Verificare che le posizioni di distribuzione (sale) soddisfino i requisiti di distribuzione.
- **Conformità dei servizi** Creare account delle risorse e assegnarli ai dispositivi [(vedere Creare un account delle risorse usando l'interfaccia di amministrazione di Microsoft 365).](resource-account-ui.md) Anche se è consigliabile usare una licenza di sala dedicata, un account utente finale con regolare licenza può anche accedere alle barre di collaborazione.
- **Configurazione e distribuzione** Configurare le barre di collaborazione nelle sale riunioni e collegare i dispositivi periferiche necessari (vedere la documentazione del produttore per le barre di collaborazione).

Per gestire le barre di collaborazione, è necessario essere un amministratore globale, un amministratore del servizio Teams o un amministratore di dispositivi di Teams. Per altre informazioni sui ruoli di amministratore, vedere Usare i ruoli di amministratore [di Microsoft Teams per gestire Teams.](../using-admin-roles.md)

## <a name="site-readiness"></a>Conformità del sito

Mentre i dispositivi ordinati vengono recapitati all'organizzazione, collaborare con le risorse di rete, le strutture e i team audio-visivi per assicurarsi che i requisiti di distribuzione siano soddisfatti e che ogni sito e sala sia pronto in termini di potenza, rete e visualizzazione.

I nostri suggerimenti per i siti della barra di collaborazione sono:

- Sale con un massimo di 4 persone
- Account delle risorse dedicati
- Schermi abilitati per il tocco
- Cavi Ethernet
- Qualità del servizio (QoS) abilitata nella rete per i supporti multimediali di Microsoft Teams

Per considerazioni sull'installazione fisica, vedere la documentazione del produttore e, se disponibile, sfruttare l'esperienza del team audio-visivo prima di installare e montare gli schermi ed eseguire i cavi.

> [!TIP]
> Consultare Preparare la rete [per Teams per la](../prepare-network.md) pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.
>
> Non è consigliabile inserire server proxy tra i dispositivi di Teams e Internet. Per altre informazioni sui server proxy e Teams, vedere [Server proxy per Teams.](../proxy-servers-for-skype-for-business-online.md)

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti di conformità del sito per le barre di collaborazione per Microsoft Teams.</li><li>Verificare di avere fornito larghezza di banda sufficiente per ogni sito.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione degli strumenti di collaborazione.</li></ul>|

## <a name="service-readiness"></a>Prontezza del servizio

Prima di distribuire le barre di collaborazione, è necessario decidere se dovranno usare gli account delle risorse di Microsoft 365, gli account degli utenti finali o una combinazione di entrambi. Gli account delle risorse di Microsoft 365 sono account delle cassette postali e di Teams dedicati a risorse specifiche, ad esempio una sala, un proiettore e così via. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite dall'utente quando vengono create. A meno che una barra di collaborazione non sia dedicata a un utente specifico per il loro uso privato, è consigliabile configurare un account delle risorse di Microsoft 365.

### <a name="using-a-resource-account"></a>Uso di un account delle risorse

Se si decide di configurare un account delle risorse di Microsoft 365, è necessario acquistare una licenza per la sala riunioni. La licenza della sala riunioni include una cassetta postale delle risorse che consente agli utenti dell'organizzazione di prenotare la sala riunioni tramite Outlook o Teams. La licenza abilita anche le conferenze video e audio e la condivisione dello schermo tra i partecipanti alla riunione.

Se è necessario ricevere o effettuare chiamate da o verso un numero di telefono esterno, potrebbe essere necessaria una licenza per il Piano per chiamate o per il componente aggiuntivo Microsoft 365 Business [Voice.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business) Se nell'organizzazione è abilitato l'instradamento diretto, è necessario utilizzare solo lo SKU Sala riunioni.

Quando si crea un account delle risorse, è possibile scegliere se consentire all'account di accettare o rifiutare automaticamente le convocazioni riunione, consentire riunioni ricorrenti, specificare con quale anticipo le persone possono prenotare la risorsa e così via.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Per altre informazioni sulle barre di collaborazione per gli account delle risorse di Microsoft 365, vedere Creare un account delle risorse con l'interfaccia di amministrazione di [Microsoft 365.](resource-account-ui.md)

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se effettuare o ricevere chiamate telefoniche esterne e identificare i requisiti di licenza per gli account delle risorse.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare gli account delle risorse.</li></ul>|

## <a name="configuration-and-deployment"></a>Configurazione e distribuzione

La pianificazione della configurazione e della distribuzione riguarda le aree principali seguenti:

- Provisioning dell'account delle risorse
- Distribuzione di dispositivi
- Barre di collaborazione per l'applicazione Microsoft Teams e la configurazione dei dispositivi periferiche
-  Test
- Gestione beni

### <a name="account-provisioning"></a>Provisioning dell'account

Se si prevede di usare gli account delle risorse di Microsoft 365 per consentire agli utenti di prenotare barre di collaborazione, seguire le istruzioni in Creare un account delle risorse usando l'interfaccia di amministrazione di [Microsoft 365](resource-account-ui.md) per creare un account delle risorse di Microsoft 365 per ogni barra di collaborazione che ne richiede uno. Qui è anche necessario aggiungere una licenza sala riunioni all'account della risorsa e, se si desidera effettuare o ricevere chiamate da numeri di telefono esterni, una licenza Piano per chiamate o Voce aziendale se l'organizzazione non usa l'instradamento diretto.

Se si vogliono assegnare barre di collaborazione a singoli utenti per il loro uso privato, non è necessario configurare altri account. Gli utenti possono accedere alle barre di collaborazione usando i propri account personali.

> [!TIP]
> Usare nomi visualizzati descrittivi e facili da capire per gli account delle risorse di Microsoft 365. Questi sono i nomi che gli utenti visualizzano quando cercano e aggiungono barre di collaborazione per Microsoft Teams alle riunioni. È possibile usare una convenzione come Nome sala siti ( Capacità massima sala ), quindi ad esempio Curie, una sala riunioni con 4 persone a Londra, potrebbe avere il nome visualizzato - LON-CURIE(4).

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Stabilire la convenzione di denominazione per gli account delle risorse dedicati.</li><li>Decidere se creare singoli account o usare script di provisioning in blocco.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>|

### <a name="device-deployment"></a>Distribuzione di dispositivi

Successivamente, è necessario creare il piano per la consegna dei dispositivi e delle periferiche assegnate alle sale e quindi procedere con l'installazione e la configurazione.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno le barre di collaborazione per Microsoft Teams nel sito ed intraprendere le configurazioni e i test.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avviare il test del dispositivo.</li></ul>|

### <a name="testing"></a> Test

Dopo aver distribuito le barre di collaborazione per Microsoft Teams, è necessario testarle. Accedere al dispositivo e verificare che le funzionalità previste funzionino nel dispositivo distribuito. È consigliabile verificare che i dispositivi  siano visualizzati nella sezione Barre di collaborazione della scheda **Dispositivi** dell'interfaccia di amministrazione di Microsoft Teams. È anche importante effettuare un certo numero di chiamate e riunioni di prova per verificare qualità e prestazioni.

Nell'ambito dell'implementazione generale di Microsoft Teams, è consigliabile configurare file di creazione per Call Quality Dashboard (CQD), monitorare le tendenze qualitative e partecipare al processo di revisione della qualità dell'esperienza. Per altre informazioni, vedere la [guida alla verifica della qualità dell'esperienza.](https://aka.ms/qerguide)

### <a name="asset-management"></a>Gestione beni

Nell'ambito della distribuzione, è necessario aggiornare il registro beni con il nome della sala, l'account delle risorse connesso e le periferiche assegnate.

## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per le barre di collaborazione per Microsoft Teams usando l'interfaccia di amministrazione di Microsoft Teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
