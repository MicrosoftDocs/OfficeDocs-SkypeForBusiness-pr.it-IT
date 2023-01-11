---
title: Creazione di uno stream in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Questo articolo illustra come creare uno stream per gli eventi di streaming di Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767991"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>Creare un evento live in Microsoft Teams

> [!IMPORTANT]
> **Cina**: attualmente, gli utenti residenti in Cina non potranno configurare o partecipare a eventi live di Microsoft Teams o Yammer o visualizzare video su richiesta senza l'aiuto dell'amministratore IT.
>
> Prima di iniziare, rivolgersi all'amministratore per verificare se è necessario configurare una VPN per connettere la rete aziendale in modo che queste app possano funzionare senza problemi nell'organizzazione.

> [!IMPORTANT]
> Quando si configura un evento live, è consigliabile configurare le autorizzazioni per video, community e utenti almeno 24 ore prima dell'evento per un'esperienza ottimale. Sono incluse impostazioni come l'aggiunta di utenti, l'aggiornamento delle autorizzazioni video e la modifica di una community da privata a pubblica. La propagazione di determinate modifiche in Microsoft Stream, Microsoft Teams e Microsoft Yammer può richiedere fino a due (2) ore. Consentire 24 ore o più può fornire tempo per il test e apportare modifiche, se necessario.

## <a name="schedule-the-live-event"></a>Pianificare l'evento live

1. Aprire il client Microsoft Teams e passare al calendario.
1. Usare l'elenco a discesa **Nuova riunione** .
1. Selezionare l'opzione **Evento live** .
1. Nella finestra popup **Nuovo evento live** immetti i dettagli dell'evento a sinistra (**Titolo**, **Luogo**, **Inizio**, **Fine**, **Fuso orario** e **Dettagli**).
1. Nella stessa pagina, a destra, **invita i relatori** ad aggiungere relatori e produttori, singolarmente o tramite gruppi.
1. Dopo aver immesso tutto, seleziona **Avanti**.
1. Selezionare **Persone e gruppi**, **a livello di organizzazione** o **Pubblico** in **Autorizzazioni evento** live per specificare chi può guardare l'evento live.
1. Seleziona **Teams Encoder (Anteprima)** in **Come potrai produrre il tuo evento live**?
1. Configurare le opzioni necessarie, ad **esempio Q&A**, **Didascalie** e altre in **Opzioni evento**.
1. Seleziona **Pianifica** per completare la pianificazione dell'evento live.

## <a name="stream-the-live-event"></a>Trasmettere in streaming l'evento live

1. Dopo aver programmato l'evento live, è possibile recuperare l'URL di inserimento e la **chiave RTMP** del **server RTMP** nella sezione **RTMP Nei dettagli** dell'invito al calendario, che è possibile usare per eseguire il push del contenuto da Encoder tramite RTMP Ingest.
1. Per configurare il codificatore, copiare l'URL di inserimento RTMP e la chiave RTMP nel codificatore per iniziare a inviare il feed del codificatore in tempo reale al team. L'uso di un codificatore per lo streaming live in Microsoft Teams contiene ulteriori informazioni.
1. Utilizzando un client Microsoft Teams, partecipa all'evento live come producer. È anche possibile trovare RTMP Nei dettagli da altre -> opzioni riunione.
1. Quando si inizia a eseguire il push del contenuto dal codificatore al punto di inserimento del server, dovrebbe essere visualizzato l'aggiornamento dell'anteprima del produttore.
1. Quando sei soddisfatto della configurazione e puoi vedere l'anteprima nell'interfaccia utente producer, seleziona il **feed RTMP** dalle origini e **invia live**.
1. Selezionare **Avvia evento** per avviare l'evento live, pubblicare i membri del pubblico che possono vedere l'evento.
1. Al termine dell'evento, seleziona **Termina evento** nell'interfaccia utente del produttore. In questo modo l'evento viene terminato e il contenuto sarà immediatamente disponibile per video su richiesta.

Per altre informazioni sullo streaming dell'evento live, vedere [Produrre un evento live usando il codificatore di Teams](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9).
