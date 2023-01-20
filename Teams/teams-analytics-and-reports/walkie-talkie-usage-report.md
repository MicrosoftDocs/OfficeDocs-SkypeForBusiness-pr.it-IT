---
title: Report sull'utilizzo e le prestazioni di Walkie-talkie
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: Informazioni su come usare il report sull'utilizzo e sulle prestazioni di Walkie-talkie nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica dell'attività di utilizzo di Walkie-talkie nell'organizzazione.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846051"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>Report sull'utilizzo e le prestazioni di Walkie-talkie

Il report sull'utilizzo e sulle prestazioni di Walkie-talkie nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica delle attività di [Walkie-talkie](../walkie-talkie.md) nell'organizzazione. Il report fornisce informazioni come il numero di trasmissioni push-to-talk (PTT) effettuate e ricevute, l'attività del canale, la durata della trasmissione e i dettagli sul dispositivo e sui partecipanti.

Usare questo report per ottenere informazioni approfondite sulle tendenze e le prestazioni di utilizzo di Walkie Talkie nell'organizzazione. Per accedere al report, è necessario essere un amministratore globale, un amministratore di Teams, un lettore globale o un lettore di report.

## <a name="download-and-view-the-report"></a>Scaricare e visualizzare il report

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams scegliere **Analytics & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, seleziona **Walkie-talkie usage**.
1. In **Intervallo di date** selezionare un intervallo di date di 7 o 30 giorni. Quindi, scegliere **Esegui report**.
1. Selezionare **Genera report**.
1. Nella scheda **Download** , in **Stato**, scegliere **Scarica** per scaricare il report in formato CSV.

## <a name="interpret-the-report"></a>Interpretare il report

Il report fornisce una suddivisione di ogni trasmissione effettuata durante l'intervallo di date selezionato. Ecco le informazioni incluse nel report.

|Nome colonna |Descrizione |
|---------|---------|
|TenantId|ID tenant.|
|Userid|ID utente.|
|Deviceid|ID dispositivo.|
|ChannelId|Il canale Walkie-talkie in cui avviene la comunicazione.|
|clientCallStatus | Indica se il dispositivo è stato in grado di ricevere la trasmissione senza problemi.|
|ConversationId|ID di ogni trasmissione PTT.|
|TeamId|ID del team che corrisponde al canale Walkie-talkie a cui l'utente si connette.|
|UnreachableParticipantsCount|Numero di partecipanti contrassegnati come irraggiungibili e nascosti dall'elenco perché non erano in grado di ricevere le ultime cinque trasmissioni.|
|TransmissionDuration|Durata del tempo (in millisecondi) tra il momento in cui il servizio riceve la notifica che un partecipante sta per avviare una trasmissione al momento in cui il servizio recapita l'ultimo pacchetto di tale trasmissione.|
|TotalParticipantsCount|Numero totale di partecipanti connessi al canale Walkie-talkie.|
|PacketCount|Numero di pacchetti utilizzati per inviare la trasmissione audio.|
|Partecipanti notificati|I partecipanti a cui viene inviata una notifica push all'avvio di una trasmissione. Negli scenari in cui la connessione tra il dispositivo e il servizio viene persa, al dispositivo viene inviata una notifica per ristabilire la connessione il più presto possibile a causa dell'arrivo di una trasmissione.|
|AudioDurationMilliseconds|Durata della trasmissione in millisecondi.|
|Id connessione|ID di ogni connessione a un canale Walkie-talkie stabilito dal dispositivo.|
|TransmissionStartTime |Data e ora in cui il servizio riceve il primo pacchetto audio.
|TransmissionEndTime|Data e ora in cui il servizio riceve l'ultimo pacchetto audio.|
|ParticipantList|Elenco delimitato da punti e virgola di ID dei dispositivi connessi al canale al momento dell'invio della trasmissione.|
|CallTimedOut|Se la trasmissione ha superato il limite di durata. Questo è un valore booleano.|
|Piattaforma|Sistema operativo del dispositivo.|
|ParticipantType|Se il partecipante era il trasmittente o un ricevitore della trasmissione.|
|Web SocketState|Se lo stato della connessione tra il dispositivo e il servizio è già stato stabilito all'inizio della trasmissione.|
|AppVersion|Versione dell'app Teams installata nel dispositivo.|

## <a name="related-articles"></a>Articoli correlati

- [App Walkie-talkie in Teams](../walkie-talkie.md)
- [Introduzione a Walkie-talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)