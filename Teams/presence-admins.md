---
title: Presenza utente in Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informazioni sugli stati di presenza in teams e sulle impostazioni amministrative per la funzionalità presenza.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369211"
---
# <a name="user-presence-in-teams"></a>Presenza utente in Teams

La presenza fa parte del profilo di un utente in Microsoft Teams (e in Microsoft 365 o Office 365) che indica la disponibilità e lo stato correnti dell'utente ad altri utenti. Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online.

La presenza di Teams in Outlook è supportata nell'app desktop Outlook 2013 e versioni successive.

 > [!Note]
 > Per informazioni dettagliate sui profili utente di Team su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="presence-states-in-teams"></a>Stati di presenza in Teams

|Utente configurato|App configurata|
|:--- |:---|
| ![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) Disponibile|![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) Disponibile|
|| ![Segno di spunta verde trasparente, indica la disponibilità fuori sede](media/Presence_Available_OOF.png) Disponibile, fuori sede |
|  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) Non disponibile |  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) Non disponibile  |
|| ![Cerchio rosso pieno, indica Non disponibile, al telefono](media/Presence_Busy.png) Chiamata in corso|
|| ![Cerchio rosso pieno, indica Non disponibile, in riunione](media/Presence_Busy.png) In riunione |
|| ![Cerchio rosso trasparente, indica Non disponibile](media/Presence_Busy_OOF.png) Chiamata in corso, fuori sede|
|  ![Cerchio rosso con linea bianca, indica Non disturbare](media/Presence_DND.png) Non disturbare ||
|| ![Cerchio rosso con linea bianca, indica Presentazione in corso](media/Presence_DND.png) Presentazione in corso|
|| ![Cerchio rosso con linea bianca, indica Occupato](media/Presence_DND.png) Occupato|
| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente|
|| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente, ultimo accesso *orario*|
|![Icona orologio giallo, indica Assente, torno subito](media/Presence_Away.png) Torno subito| |
|![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) Visualizzazione offline | ![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) Offline| |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) Stato sconosciuto|
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) Fuori sede|
|||

Gli stati di presenza configurati dall'app si basano sulle attività utente (Disponibile, Assente), gli stati del calendario di Outlook (In riunione) o gli stati dell'app Teams (Chiamata in corso, Presentazione in corso). Tieni presente che quando sei in modalità Focus in base al calendario, lo stato attivo verrà visualizzato in teams, ma verrà visualizzato come non disturbare in altri prodotti.

Quando si blocca il computer o quando il computer entra in modalità Idle o Sleep, lo stato di presenza corrente cambia in via. In un dispositivo mobile, lo stato presenza viene modificato in via ogni volta che l'app teams è in background.

Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza. Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online. Se uno stato utente è impostato su non disturbare, l'utente riceverà comunque i messaggi di chat, ma le notifiche banner non vengono visualizzate.

Gli utenti ricevono le chiamate con qualsiasi stato di presenza tranne Non disturbare, in cui le chiamate in arrivo vengono inoltrate alla segreteria telefonica. Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.

Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams. Le persone con accesso prioritario possono contattare l'utente anche quando lo stato dell'utente è impostato su non disturbare.

## <a name="user-configured-states-expiration"></a>Scadenza degli stati configurati dall'utente
Quando un utente seleziona uno stato di presenza specifico, prevale su qualsiasi aggiornamento delle attività dell'app. Ad esempio, se un utente si imposta come non disturbare, la sua presenza rimarrà come non disturbare, anche se partecipa a una riunione o risponde a una chiamata.

Gli stati configurati dall'utente hanno impostazioni di scadenza predefinite in teams per evitare che gli utenti visualizzino uno stato che potrebbe non essere pertinente dopo un determinato periodo di tempo.

|Stato configurato dall'utente|Scadenza predefinita|
|:--- |:---|
| Non disponibile|1 giorno|
| Non disturbare|1 giorno|
| Altri|7 giorni|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Confronto tra le impostazioni di amministrazione di Teams e Skype for Business

Le seguenti impostazioni di amministrazione di Skype for Business sono diverse da quelle di Teams:

- In Teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione. La configurazione della privacy, grazie alla quale è possibile stabilire chi può visualizzare la presenza, non è disponibile in Teams.
- La condivisione della presenza con tutti, inclusi i servizi federati, è sempre abilitata per gli utenti di Teams. L'elenco contatti, se presente in Skype for Business, è visibile in **Chat > Contatti** o in **Chiamate > Contatti**.
- Le funzionalità client Non disturbare e Contatti sempre ammessi sono sempre abilitate per gli utenti di Teams.
- L'integrazione del calendario, incluse le informazioni fuori sede e degli altri calendario, è sempre abilitata per gli utenti se Teams è integrato con Outlook.
- L'indicatore *Ultimo accesso* o *Assente dalle* è sempre abilitato per gli utenti di Teams se l'organizzazione utilizza anche Skype for Business.

> [!NOTE]
> La personalizzazione di queste impostazioni da parte di un amministratore di Teams non è supportata al momento.

## <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

Vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) per i dettagli sul funzionamento della presenza di Teams quando l'organizzazione utilizza anche Skype for Business.
