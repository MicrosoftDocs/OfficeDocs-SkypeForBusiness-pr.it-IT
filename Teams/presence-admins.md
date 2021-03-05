---
title: Presenza utente in Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informazioni sugli stati presenza in Teams e sulle impostazioni amministrative per la caratteristica presenza.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5263880e049eb779c01f95ea58c6866bc1f3aa3c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460556"
---
# <a name="user-presence-in-teams"></a>Presenza utente in Teams

La presenza fa parte del profilo utente in Microsoft Teams (e in tutto Microsoft 365 o Office 365). La presenza indica la disponibilità e lo stato correnti dell'utente ad altri utenti. Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online. La presenza viene aggiornata in tempo reale sul Web e sulle versioni desktop quando si aggiorna la pagina in un dispositivo mobile.

 > [!Note]
 > Per informazioni dettagliate sui profili utente di Teams su diverse piattaforme, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="presence-states-in-teams"></a>Stati di presenza in Teams

|Utente configurato|App configurata|
|:--- |:---|
| ![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) Disponibile|![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) Disponibile|
|| ![Segno di spunta verde trasparente, indica la disponibilità fuori sede](media/Presence_Available_OOF.png) Disponibile, Fuori sede. Nota: Fuori sede viene impostato automaticamente per il periodo di tempo in cui l'utente imposta le "risposte automatiche". Se l'utente usa l'app durante questo periodo di tempo, è possibile che venga visualizzata una doppia presenza, ad esempio "Fuori sede, disponibile". |
|  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) Non disponibile |  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) Non disponibile  |
|| ![Cerchio rosso pieno, indica Non disponibile, al telefono](media/Presence_Busy.png) Al telefono|
|| ![Cerchio rosso pieno, indica Non disponibile, in riunione](media/Presence_Busy.png) In riunione |
|| ![Cerchio rosso trasparente, indica Non disponibile](media/Presence_Busy_OOF.png) Chiamata in corso, fuori sede|
|  ![Cerchio rosso con linea bianca, indica Non disturbare](media/Presence_DND.png) Non disturbare ||
|| ![Cerchio rosso con linea bianca, indica Presentazione in corso](media/Presence_DND.png) Presentazione in corso|
|| ![Cerchio rosso con linea bianca, indica Occupato](media/Presence_DND.png) Occupato. Lo stato attivo si verifica quando gli utenti pianificano il tempo produttivo in MyAnalytics/Insights nei propri calendari.|
| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente|
|| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente, ultimo accesso *orario*|
|![Icona orologio giallo, indica Assente, torno subito](media/Presence_Away.png) Torno subito| |
|![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) Invisibile|![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) Offline.  Se gli utenti non effettuano l'accesso ad alcun dispositivo per alcuni minuti, risultano invisibili. | |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) Stato sconosciuto|
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) Fuori sede. Fuori sede viene usato quando è impostata una risposta automatica. (Disponibile solo in Outlook). |
|||
 > [!Note]
 > Per gli utenti ospitati nella cassetta postale si prevede ritardi di presenza con un massimo di un'ora.
Gli stati di presenza configurati dall'app si basano sulle attività utente (Disponibile, Assente), gli stati del calendario di Outlook (In riunione) o gli stati dell'app Teams (Chiamata in corso, Presentazione in corso). Quando ci si trova in modalità focus in base al calendario, **Occupato** sarà lo stato che le persone visualizzeranno in Teams. La modalità focus viene visualizzata come **Non disturbare** in altri prodotti.

Lo stato di presenza corrente cambia in Assente quando si blocca il computer o quando si attiva la modalità di sospensione. In un dispositivo mobile, lo stato di presenza viene impostato su Assente quando l'app Teams è in background.

Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza. Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online. Se un utente è in stato Non disturbare, riceverà comunque i messaggi delle chat, ma le notifiche del banner non verranno mostrate.

Gli utenti ricevono le chiamate con qualsiasi stato di presenza tranne Non disturbare, in cui le chiamate in arrivo vengono inoltrate alla segreteria telefonica. Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.

Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams. Le persone con accesso prioritario possono contattare l'utente anche se lo stato dell'utente è impostato su Non disturbare.

### <a name="dual-presence"></a>Doppia presenza

  Il modo in cui la presenza funziona per la maggior parte degli utenti è motivata dagli eventi nel calendario o dagli eventi del dispositivo, ad esempio una chiamata. L'utente può ignorare questo stato nell'interfaccia utente impostando manualmente gli stati, che hanno una determinata scadenza.

## <a name="user-configured-states-expiration"></a>Scadenza degli stati configurati dall'utente

Se un utente seleziona uno stato di presenza specifico, questo ha la precedenza rispetto a qualsiasi aggiornamento delle attività dell'app. Se, ad esempio, un utente imposta il proprio stato su Non disturbare, la sua presenza rimarrà Non disturbare anche se partecipa a una riunione o risponde a una chiamata.

Per impedire agli utenti di visualizzare uno stato che potrebbe non essere pertinente dopo un determinato periodo di tempo, gli stati configurati dall'utente hanno impostazioni di scadenza predefinite in Teams.

|Stato configurato dall'utente|Scadenza predefinita|
|:--- |:---|
| Occupato|1 giorno|
| Non disturbare|1 giorno|
| Altri|7 giorni|
|||

> [!NOTE]
> Un utente può anche configurare manualmente una durata per la propria presenza. Ad esempio, un utente può impostare il proprio stato su Invisibile fino a domani mattina.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Confronto tra le impostazioni di amministrazione di Teams e Skype for Business

Le seguenti impostazioni di amministrazione di Skype for Business sono diverse da quelle di Teams:

- In Teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione. La configurazione della privacy, grazie alla quale è possibile stabilire chi può visualizzare la presenza, non è disponibile in Teams.
- La condivisione della presenza con tutti, inclusi i servizi federati, è sempre abilitata per gli utenti di Teams. L'elenco contatti, se presente in Skype for Business, è visibile in **Chat > Contatti** o in **Chiamate > Contatti**.
- Le funzionalità client Non disturbare e Contatti sempre ammessi sono sempre abilitate per gli utenti di Teams.
- L'integrazione del calendario, incluse le informazioni fuori sede e degli altri calendario, è sempre abilitata per gli utenti se Teams è integrato con Outlook.
- L'indicatore *Ultimo accesso* o *Assente dalle* è sempre abilitato per gli utenti di Teams se l'organizzazione utilizza anche Skype for Business.

> [!NOTE]
> La personalizzazione di queste impostazioni da parte di un amministratore di Teams non è supportata al momento.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Confronto tra le impostazioni di amministrazione di Teams e Microsoft Outlook

La presenza di Teams in Outlook è supportata nell'app desktop Outlook 2013 e versioni successive per i contatti nella stessa organizzazione.

Se il criterio di modalità di aggiornamento dell'account utente è impostato su TeamsOnly, Outlook comunica con Teams per ottenere la presenza. Se l'account utente non è impostato su TeamsOnly, Outlook comunica con Skype for Business.

## <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for Business

Vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) per i dettagli sul funzionamento della presenza di Teams quando l'organizzazione utilizza anche Skype for Business.
