---
title: Check-in e rilascio della sala sui pannelli di Microsoft Teams
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
ms.topic: reference
search.appverid: MET150
description: Questo articolo fornisce indicazioni su come abilitare i dispositivi dei pannelli teams per il check-in e il rilascio delle sale.
ms.openlocfilehash: d5998049faf1e3c8c25b3e49470291bb20f97eea
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801857"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Check-in e rilascio della sala sui pannelli di Microsoft Teams

Quando il check-in e il rilascio della sala sono abilitati, gli utenti accedono ai pannelli di Teams nella sala che hanno prenotato all'inizio della riunione. Se un utente non esegue il check-in entro un determinato periodo di tempo dopo l'ora di inizio della riunione, la sala riunioni rifiuta l'invito alla riunione, invia un messaggio di annullamento all'organizzatore della riunione e la sala diventa disponibile per la prenotazione da parte di altri utenti.  

## <a name="requirements"></a>Requisiti 

Questa funzionalità può essere usata in una distribuzione Pannello di Teams autonoma. È anche possibile associare i pannelli di Teams con Teams Rooms su Android con l'app versione 1449/1.0.96.2022011305 o successiva per altre funzionalità come le notifiche di check-in.

Per il corretto funzionamento di questa caratteristica, la cassetta postale condivisa associata al Pannello di Teams deve avere il fuso orario corretto. Per informazioni su come impostare il fuso orario per le cassette postali condivise, vedere [Impostazioni del fuso orario per le cassette postali condivise in Outlook sul web](/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting).

## <a name="enable-check-in-and-room-release"></a>Abilitare il check-in e il rilascio della sala 

Il check-in e il rilascio della sala sono disattivati per impostazione predefinita. Per attivarla,  

1. Nel Pannello di Teams accedere con le credenziali di amministratore.  

2. Passare a **Impostazioni > Impostazioni dispositivo > Amministrazione impostazioni > impostazioni di amministrazione di Teams > Riunioni**.

3. Attiva **Release room se nessuno effettua l'accesso**.

4. Per regolare la quantità di tempo per cui gli utenti devono effettuare il check-in prima del rilascio della sala, passare a **Rilascia dopo** : e selezionare un'opzione nell'elenco a discesa.  

Quando i pannelli di Teams sono associati a una sala riunioni di Teams su Android, un utente può controllare la partecipazione alla riunione nella sala riunioni di Teams.  

## <a name="turn-on-check-in-notifications"></a>Attivare le notifiche di archiviazione

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo nei pannelli di Teams associati a teams room su Android. Il Pannello di Teams e la chat room di Teams devono essere connessi allo stesso account delle risorse. Per altre informazioni, vedi [Associare un Pannello di Teams a una sala riunioni di Microsoft Teams su Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android).  

Le notifiche di archiviazione vengono inviate quando una riunione continua oltre la fascia oraria riservata. Una volta che un utente della riunione successiva effettua l'accesso, la notifica verrà visualizzata nella parte anteriore della visualizzazione della sala all'ora di inizio della riunione pianificata per far sapere ai partecipanti alla riunione precedente che la prenotazione è finita e che le persone stanno aspettando lo spazio.  

Per attivare le notifiche di check-in,  

1. Nel Pannello di Teams accedere con le credenziali di amministratore. 

2. Passare a **Impostazioni > Impostazioni dispositivo > Amministrazione impostazioni > impostazioni di amministrazione di Teams > Riunioni**.

3. Vai a **Archiviazione** e attiva **Invia notifica di archiviazione**.

## <a name="related-topics"></a>Argomenti correlati

- [Come usare i pannelli di Microsoft Teams](use-teams-panels.md)

- [Pannelli di Microsoft Teams](teams-panels.md)
