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
ms.openlocfilehash: ff5a13d6b31527138b71d2ad3b2387f827933eda
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616950"
---
# <a name="user-presence-in-teams"></a>Presenza utente in Teams

La presenza fa parte del profilo di un utente in Microsoft Teams (e in Microsoft 365 o Office 365). La presenza indica la disponibilità e lo stato correnti dell'utente ad altri utenti. Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online. La presenza viene aggiornata in tempo reale sulle versioni Web e desktop quando si aggiorna la pagina in un dispositivo mobile.

 > [!Note]
 > Per informazioni dettagliate sui profili utente di Team su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="presence-states-in-teams"></a>Stati di presenza in Teams

|Utente configurato|App configurata|
|:--- |:---|
| ![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) Disponibile|![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) Disponibile|
|| ![Segno di spunta verde trasparente, indica la disponibilità fuori sede](media/Presence_Available_OOF.png) Disponibile, fuori sede. Nota: fuori sede viene impostato automaticamente per i periodi di tempo in cui l'utente imposta "risposte automatiche". Se l'utente usa l'app durante questi periodi di tempo, potrebbe essere visualizzata una doppia presenza, ad esempio "fuori sede, disponibile". |
|  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) Non disponibile |  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) Non disponibile  |
|| ![Cerchio rosso pieno, indica Non disponibile, al telefono](media/Presence_Busy.png) In una chiamata|
|| ![Cerchio rosso pieno, indica Non disponibile, in riunione](media/Presence_Busy.png) In riunione |
|| ![Cerchio rosso trasparente, indica Non disponibile](media/Presence_Busy_OOF.png) Chiamata in corso, fuori sede|
|  ![Cerchio rosso con linea bianca, indica Non disturbare](media/Presence_DND.png) Non disturbare ||
|| ![Cerchio rosso con linea bianca, indica Presentazione in corso](media/Presence_DND.png) Presentazione in corso|
|| ![Cerchio rosso con linea bianca, indica Occupato](media/Presence_DND.png) Incentrato. Lo stato di attivazione si verifica quando gli utenti pianificano l'ora di attivazione in analisi/approfondimenti nei propri calendari.|
| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente|
|| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente, ultimo accesso *orario*|
|![Icona orologio giallo, indica Assente, torno subito](media/Presence_Away.png) Torno subito| |
|![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) Visualizzazione offline|![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) Offline.  Quando gli utenti non accedono a nessuno dei loro dispositivi per alcuni minuti, vengono visualizzati offline. | |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) Stato sconosciuto|
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) Fuori sede. Fuori sede viene usato quando viene impostata una risposta automatica. (Disponibile solo in Outlook) |
|||

Gli stati di presenza configurati dall'app si basano sulle attività utente (Disponibile, Assente), gli stati del calendario di Outlook (In riunione) o gli stati dell'app Teams (Chiamata in corso, Presentazione in corso). Quando si è in modalità Focus in base al **Calendario, lo** stato attivo verrà visualizzato in teams. La modalità di attivazione verrà visualizzata come **non disturbare** in altri prodotti.

Quando si blocca il computer o quando il computer entra in modalità Idle o Sleep, lo stato di presenza corrente cambia in via. In un dispositivo mobile, lo stato presenza viene modificato in via ogni volta che l'app teams è in background.

Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza. Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online. Se uno stato utente è impostato su non disturbare, l'utente riceverà comunque i messaggi di chat, ma le notifiche banner non vengono visualizzate.

Gli utenti ricevono le chiamate con qualsiasi stato di presenza tranne Non disturbare, in cui le chiamate in arrivo vengono inoltrate alla segreteria telefonica. Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.

Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams. Le persone con accesso prioritario possono contattare l'utente anche quando lo stato dell'utente è impostato su non disturbare.

### <a name="dual-presence"></a>Presenza doppia

  Il modo in cui la presenza funziona per la maggior parte degli utenti è motivato dagli eventi del calendario o degli eventi del dispositivo, ad esempio una chiamata. L'utente può eseguire l'override di questo stato nell'interfaccia utente impostando manualmente gli Stati, che hanno una certa data di scadenza.

## <a name="user-configured-states-expiration"></a>Scadenza degli stati configurati dall'utente

Quando un utente seleziona uno stato di presenza specifico, prevale su qualsiasi aggiornamento delle attività dell'app. Ad esempio, se un utente si imposta come non disturbare, la sua presenza rimarrà come non disturbare, anche se partecipa a una riunione o risponde a una chiamata.

Gli stati configurati dall'utente hanno impostazioni di scadenza predefinite in teams per evitare che gli utenti visualizzino uno stato che potrebbe non essere pertinente dopo un determinato periodo di tempo.

|Stato configurato dall'utente|Scadenza predefinita|
|:--- |:---|
| Non disponibile|1 giorno|
| Non disturbare|1 giorno|
| Altri|7 giorni|
|||

> [!NOTE]
> Un utente può anche configurare manualmente una durata per la sua presenza. Ad esempio, un utente può impostarsi come visualizzato offline fino a domani mattina.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Confronto tra le impostazioni di amministrazione di Teams e Skype for Business

Le seguenti impostazioni di amministrazione di Skype for Business sono diverse da quelle di Teams:

- In Teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione. La privacy (in cui Definisci chi può vedere la presenza) la configurazione non è disponibile in teams.
- La condivisione della presenza con tutti, inclusi i servizi federati, è sempre abilitata per gli utenti di Teams. L'elenco contatti, se presente in Skype for Business, è visibile in **Chat > Contatti** o in **Chiamate > Contatti**.
- Le funzionalità client Non disturbare e Contatti sempre ammessi sono sempre abilitate per gli utenti di Teams.
- L'integrazione del calendario, incluse le informazioni fuori sede e degli altri calendario, è sempre abilitata per gli utenti se Teams è integrato con Outlook.
- L'indicatore *Ultimo accesso* o *Assente dalle* è sempre abilitato per gli utenti di Teams se l'organizzazione utilizza anche Skype for Business.

> [!NOTE]
> La personalizzazione di queste impostazioni da parte di un amministratore di Teams non è supportata al momento.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Impostazioni di amministrazione in teams rispetto a Microsoft Outlook

La presenza di team in Outlook è supportata nell'app desktop di Outlook 2013 e in seguito per i contatti della stessa organizzazione.

Se il criterio modalità di aggiornamento dell'account utente è impostato su TeamsOnly, Outlook comunica ai team per ottenere la presenza. Se l'account utente non è impostato su TeamsOnly, Outlook comunica con Skype for business.

## <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

Vedere la [coesistenza con Skype for business](coexistence-chat-calls-presence.md) per informazioni dettagliate su come funziona la presenza di teams quando l'organizzazione usa anche Skype for business.
