---
title: Check-in e rilascio sala Microsoft Teams pannelli
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: Questo articolo fornisce indicazioni su come abilitare il check-in e il rilascio della sala Teams dispositivi.
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689101"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Check-in e rilascio sala Microsoft Teams pannelli

Quando il check-in e il rilascio della sala sono abilitati, gli utenti archiviano i Teams nella sala che hanno prenotato all'inizio della riunione. Se un utente non archivia entro un periodo di tempo impostato dopo l'ora di inizio della riunione, la sala riunioni rifiuta l'invito alla riunione, invia un messaggio di annullamento all'organizzatore della riunione e la sala diventa disponibile per la prenotazione da parte di altri utenti.  

## <a name="requirements"></a>Requisiti 

Questa caratteristica può essere usata in una distribuzione autonoma Teams pannello comandi. È anche possibile associare Teams pannelli con Teams Rooms in Android con la versione 1449/1.0.96.2022011305 o successiva per altre funzionalità come le notifiche di archiviazione.  

## <a name="enable-check-in-and-room-release"></a>Abilitare il check-in e il rilascio delle chat room 

Il check-in e il rilascio della sala sono disattivati per impostazione predefinita. Per attivarlo,  

1. Nel riquadro Teams accedere usando le credenziali di amministratore.  

2. Passare **all'Impostazioni > dispositivo Impostazioni >'app Impostazioni > pannello Impostazioni > riunioni**.

3. Attivare release room se nessuno esegue l'accesso.

4. Per modificare la quantità di tempo in cui gli utenti devono archiviare prima che la chat room venga rilasciata, passare a **Rilascio dopo e** selezionare un'opzione nell'elenco a discesa.  

Quando Teams pannelli sono associati a una Teams room su Android, un utente può eseguire il check-in partecipando alla riunione nella Teams room.  

## <a name="turn-on-check-in-notifications"></a>Attivare le notifiche di archiviazione

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo nei Teams che sono associati a una Teams room in Android. Il Teams e la Teams deve essere connessi allo stesso account della risorsa. Per [altre informazioni, vedere Associare un Teams di lavoro con Microsoft Teams room su Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android).  

Le notifiche di archiviazione vengono inviate quando una riunione continua oltre l'intervallo di tempo riservato. Quando un utente della riunione successiva esegue l'archiviazione, la notifica viene visualizzata nella parte anteriore della sala all'ora di inizio della riunione pianificata per far sapere ai partecipanti alla riunione precedente che la prenotazione è finita e che le persone sono in attesa dello spazio.  

Per attivare le notifiche di archiviazione,  

1. Nel riquadro Teams accedere usando le credenziali di amministratore. 

2. Passare **all'Impostazioni > dispositivo Impostazioni >'app Impostazioni > pannello Impostazioni > riunioni**.

3. Passare a **Archiviazione e** attivare Invia notifica **di archiviazione**.

## <a name="related-topics"></a>Argomenti correlati

- [Come usare i Microsoft Teams di lavoro](use-teams-panels.md)

- [Microsoft Teams di lavoro](teams-panels.md)