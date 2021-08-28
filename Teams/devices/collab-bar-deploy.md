---
title: Distribuire Microsoft Teams Rooms in Android
ms.author: mitressl
author: flinchbot
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
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leggere questo articolo per informazioni sulla distribuzione di Microsoft Teams Rooms su Android.
ms.openlocfilehash: 38d8ce263e3a9628dde45d22729f1a9ce4f944a3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632560"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Distribuire Microsoft Teams Rooms in Android

La distribuzione Microsoft Teams Rooms in Android può essere suddivisa nelle fasi seguenti:

- **Conformità del sito** Verificare che le posizioni di distribuzione (sale) soddisfino i requisiti di distribuzione.
- **Conformità del servizio** Creare account delle risorse e assegnarli ai dispositivi ([vedere Creare un account delle risorse usando](resource-account-ui.md)il interfaccia di amministrazione di Microsoft 365 ). Anche se è consigliabile usare una licenza di chat room dedicata, un account utente finale con licenza appropriata può anche accedere a Teams Rooms su Android.
- **Configurazione e distribuzione** Configurare Teams Rooms e collegare i dispositivi periferici necessari (vedere la documentazione del produttore per informazioni dettagliate).

Per gestire Teams Rooms, è necessario essere un amministratore globale, un amministratore Teams Service o un amministratore Teams dispositivo. Per altre informazioni sui ruoli di amministratore, vedere Usare [Microsoft Teams di amministratore per gestire Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Conformità del sito

Mentre i dispositivi ordinati vengono recapitati all'organizzazione, collaborare con le reti, le strutture e i team audio-visivi per assicurarsi che i requisiti di distribuzione siano soddisfatti e che ogni sito e sala sia pronto in termini di potenza, rete e visualizzazione.

I nostri consigli per i siti delle barre di collaborazione sono:

- Sale con un massimo di 5 persone
- Account delle risorse dedicate
- Schermi abilitati per il tocco
- Cablaggio Ethernet
- Qualità del servizio (QoS) abilitata nella rete per Microsoft Teams multimediali

Per considerazioni sull'installazione fisica, vedere la documentazione del produttore e, se disponibile, sfruttare l'esperienza del team audio-visivo prima di installare e montare gli schermi ed eseguire il cablaggio.

> [!TIP]
> Assicurarsi di consultare Preparare la rete [per la](../prepare-network.md) Teams pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.
>
> Non è consigliabile inserire server proxy tra Teams e Internet. Per altre informazioni sui server proxy e sui Teams, vedere [Server proxy per](../proxy-servers-for-skype-for-business-online.md)Teams .

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti di conformità del sito per le barre di collaborazione per Microsoft Teams.</li><li>Verificare di aver fornito larghezza di banda sufficiente per ogni sito.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione della barra di collaborazione.</li></ul>|

## <a name="service-readiness"></a>Prontezza del servizio

Prima di distribuire Teams Rooms, è necessario decidere se useranno gli account delle risorse Microsoft 365, gli account degli utenti finali o una combinazione di entrambi. Microsoft 365 account delle risorse sono account Teams cassette postali e di posta elettronica dedicati a risorse specifiche, ad esempio una sala, un proiettore e così via. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite al momento della creazione. A meno Teams Rooms non sia dedicato a un utente specifico per l'uso privato, è consigliabile configurare un account Microsoft 365 di risorse.

### <a name="using-a-resource-account"></a>Uso di un account delle risorse

Se si decide di configurare un account Microsoft 365 risorsa, è necessario acquistare una licenza Sala riunioni per l'account. La licenza Sala riunioni include una cassetta postale delle risorse che consente agli utenti dell'organizzazione di prenotare la sala riunioni tramite Outlook o Teams. La licenza consente anche videoconferenze e audioconferenza e condivisione dello schermo tra i partecipanti alla riunione.

Se è necessario ricevere o effettuare chiamate da o verso un numero di telefono esterno, potrebbe essere necessario un piano per le chiamate o una licenza per Microsoft 365 Business Voice [componente aggiuntivo](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Se nell'organizzazione è abilitato il routing diretto, è necessario solo lo SKU Sala riunioni distribuzione.

Quando si crea un account delle risorse, è possibile scegliere se consentire all'account di accettare o rifiutare automaticamente le convocazioni di riunione, consentire riunioni ricorrenti, specificare con quale anticipo gli utenti possono prenotare la risorsa e così via.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Per altre informazioni sugli account Microsoft 365 risorse, vedere [Creare un account delle risorse usando il](resource-account-ui.md)interfaccia di amministrazione di Microsoft 365 .

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se effettuare o ricevere chiamate telefoniche esterne e identificare i requisiti di licenza per gli account delle risorse.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare gli account delle risorse.</li></ul>|

## <a name="configuration-and-deployment"></a>Configurazione e distribuzione

La pianificazione della configurazione e della distribuzione riguarda le aree chiave seguenti:

- Provisioning dell'account delle risorse
- Distribuzione di dispositivi
- Teams Rooms delle applicazioni e dei dispositivi periferici
-  Test
- Gestione delle risorse

### <a name="account-provisioning"></a>Provisioning dell'account

Se si prevede di usare gli account delle risorse di Microsoft 365 per consentire agli utenti di prenotare barre di collaborazione, seguire le istruzioni in Creare un account delle risorse usando il [interfaccia di amministrazione di Microsoft 365](resource-account-ui.md) per creare un account delle risorse di Microsoft 365 per ogni barra di collaborazione che ne ha bisogno. Qui è anche necessario aggiungere una licenza Sala riunioni all'account della risorsa e, se si vogliono effettuare o ricevere chiamate da o verso numeri di telefono esterni, una licenza Piano per chiamate o Voce aziendale se l'organizzazione non usa Il routing diretto.

Se si vuole assegnare Teams Rooms a singoli utenti per l'uso privato, non è necessario configurare altri account. Gli utenti possono accedere alle barre di collaborazione usando gli account personali.

> [!TIP]
> Rendere descrittivi e facili da comprendere i nomi visualizzati Microsoft 365 account delle risorse. Questi sono i nomi che gli utenti visualizzano quando cercano e aggiungono Teams Rooms alle riunioni. È possibile usare una convenzione come Site Room Name ( Max Room Capacity ), quindi ad esempio Curie, una sala riunioni di 4 persone a Londra, potrebbe avere il nome visualizzato - LON-CURIE(4).

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione per gli account delle risorse dedicati.</li><li>Decidere se creare singoli account o usare script di provisioning in blocco.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>|

### <a name="device-deployment"></a>Distribuzione di dispositivi

Successivamente, è necessario creare il piano per distribuire i dispositivi e i dispositivi periferici assegnati alle chat room e quindi procedere con l'installazione e la configurazione.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno Teams Rooms sul sito e intraprendere la configurazione e il test.</li></ul>|
| ![Icona che illustra i passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avviare il test del dispositivo.</li></ul>|

### <a name="testing"></a> Test

Dopo aver distribuito i Teams Rooms, è consigliabile testarli. Accedere a Teams Rooms e verificare che le funzionalità previste funzionino. È consigliabile verificare che siano visualizzati  nella sezione  Barre di collaborazione nella scheda Dispositivi dell'interfaccia Microsoft Teams di amministrazione. È anche importante effettuare una serie di chiamate e riunioni di prova per verificare la qualità e le prestazioni.

Nell'ambito dell'implementazione generale di Microsoft Teams, è consigliabile configurare i file di creazione per Call Quality Dashboard (CQD), monitorare le tendenze qualitative e partecipare al processo di revisione della qualità dell'esperienza. Per altre informazioni, vedere la [Guida alla revisione della qualità dell'esperienza.](../quality-of-experience-review-guide.md)

### <a name="asset-management"></a>Gestione delle risorse

Nell'ambito della distribuzione, è necessario aggiornare il registro beni con il nome della chat room, l'account della risorsa di accesso e i dispositivi periferici assegnati.

## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per Microsoft Teams Rooms l'interfaccia Microsoft Teams di amministrazione](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->