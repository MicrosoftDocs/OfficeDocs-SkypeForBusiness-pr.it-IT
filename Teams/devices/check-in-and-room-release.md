---
title: Check-in e rilascio sala su pannelli Microsoft Teams
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
ms.topic: reference
search.appverid: MET150
description: Questo articolo fornisce indicazioni su come abilitare il check-in e il rilascio della sala Teams dispositivi con pannelli.
ms.openlocfilehash: a1fc01b349a2189ab2f5ca09ff6b856338fbcdbb
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761278"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Check-in e rilascio sala su pannelli Microsoft Teams

Quando il check-in e il rilascio della sala sono abilitati, gli utenti archiviano Teams pannelli nella sala che hanno prenotato all'inizio della riunione. Se un utente non esegue il check-in entro un determinato periodo di tempo dopo l'ora di inizio della riunione, la sala riunioni rifiuta l'invito alla riunione, invia un messaggio di annullamento all'organizzatore della riunione e la sala diventa disponibile per la prenotazione da parte di altri utenti.  

## <a name="requirements"></a>Requisiti 

Questa funzionalità può essere usata in una distribuzione Pannello di Teams autonoma. Puoi anche associare Teams pannelli con Teams Rooms su Android con app versione 1449/1.0.96.2022011305 o successiva per altre funzionalità come le notifiche di check-in.  

## <a name="enable-check-in-and-room-release"></a>Abilitare il check-in e il rilascio della sala 

Il check-in e il rilascio della sala sono disattivati per impostazione predefinita. Per attivarla,  

1. Nel Pannello di Teams accedere con le credenziali di amministratore.  

2. Passare a **Impostazioni Impostazioni > dispositivo > Amministrazione impostazioni > Teams impostazioni di amministrazione > Riunioni**.

3. Attiva Release room se nessuno effettua l'accesso.

4. Per regolare la quantità di tempo per cui gli utenti devono effettuare il check-in prima del rilascio della sala, passare a **Rilascia dopo** : e selezionare un'opzione nell'elenco a discesa.  

Quando Teams pannelli sono associati a una sala Teams in Android, un utente può accedere alla riunione nella sala Teams.  

## <a name="turn-on-check-in-notifications"></a>Attivare le notifiche di archiviazione

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo per Teams pannelli associati a una sala Teams in Android. Il Pannello di Teams e Teams chat room devono essere connessi allo stesso account della risorsa. Per altre informazioni, vedere [Associare un Pannello di Teams a una sala Microsoft Teams in Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android).  

Le notifiche di archiviazione vengono inviate quando una riunione continua oltre la fascia oraria riservata. Una volta che un utente della riunione successiva effettua l'accesso, la notifica verrà visualizzata nella parte anteriore della visualizzazione della sala all'ora di inizio della riunione pianificata per far sapere ai partecipanti alla riunione precedente che la prenotazione è finita e che le persone stanno aspettando lo spazio.  

Per attivare le notifiche di check-in,  

1. Nel Pannello di Teams accedere con le credenziali di amministratore. 

2. Passare a **Impostazioni Impostazioni > dispositivo > Amministrazione impostazioni > Teams impostazioni di amministrazione > Riunioni**.

3. Vai a **Archiviazione** e attiva **Invia notifica di archiviazione**.

## <a name="related-topics"></a>Argomenti correlati

- [Come usare i pannelli Microsoft Teams](use-teams-panels.md)

- [Microsoft Teams pannelli](teams-panels.md)
