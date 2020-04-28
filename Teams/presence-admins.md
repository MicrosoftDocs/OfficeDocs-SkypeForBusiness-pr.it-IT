---
title: Presenza utente in Teams
author: lolajacobsen
ms.author: lolaj
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
ms.openlocfilehash: 6432bac9dbbfe65cf3e139ecae00b02cd5ae8651
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905768"
---
# <a name="user-presence-in-teams"></a>Presenza utente in Teams

La presenza è inclusa nel profilo degli utenti di Microsoft Teams (e ovunque in Office 365) e indica la disponibilità e lo stato correnti dell'utente. Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online.

La presenza di Teams in Outlook è supportata nell'app desktop Outlook 2013 e versioni successive.

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
|| ![Icona orologio giallo, indica Assente, non al lavoro](media/Presence_Away.png)  Non al lavoro|
|| ![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) Offline |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) Stato sconosciuto|
||![Cerchio rosso trasparente con linea diagonale, indica Bloccato](media/Presence_Blocked.png) Bloccato |
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) Fuori sede|
|||

Gli stati di presenza configurati dall'app si basano sulle attività utente (Disponibile, Assente), gli stati del calendario di Outlook (In riunione) o gli stati dell'app Teams (Chiamata in corso, Presentazione in corso).

Lo stato di presenza corrente cambia in Assente quando si blocca il computer o quando si attiva la modalità di sospensione. In un dispositivo mobile, lo stato di presenza viene impostato su Assente quando l'app Teams è in background.

Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza. Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online. Se un utente è in stato Non disturbare, riceverà comunque i messaggi delle chat, ma le notifiche del banner non verranno mostrate.

Gli utenti ricevono le chiamate con qualsiasi stato di presenza tranne Non disturbare, in cui le chiamate in arrivo vengono inoltrate alla segreteria telefonica. Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.

Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams. Le persone con accesso prioritario possono contattare l'utente anche se è in stato Non disturbare.

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
