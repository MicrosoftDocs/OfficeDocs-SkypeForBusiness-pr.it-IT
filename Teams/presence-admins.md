---
title: Presenza dell'utente in teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Gli amministratori di informazioni devono comprendere la presenza in teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11902a5d6ef768afa6d7bb1bba2f33b64757fef1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184381"
---
# <a name="user-presence-in-teams"></a>Presenza dell'utente in teams

La presenza fa parte del profilo di un utente in Microsoft Teams (e in Office 365) e indica la disponibilità e lo stato correnti dell'utente ad altri utenti dell'organizzazione. Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano i team possono vedere, in tempi quasi reali, se gli altri sono o meno disponibili online.

## <a name="presence-states-in-teams"></a>Stati presenza in teams

Gli Stati di presenza degli utenti disponibili in teams sono:

|Configurato dall'utente|App configurata|
|:--- |:---|
| ![Contrassegno di Chek verde a tinta unita, che indica la presenza disponibile](media/Presence_Available.png) Disponibili|![Contrassegno di Chek verde a tinta unita, che indica la presenza disponibile](media/Presence_Available.png) Disponibili|
|| ![Aprire il contrassegno di Chek verde, indicando disponibile OOF](media/Presence_Available_OOF.png) Disponibile, fuori sede |
|  ![Cerchio rosso a tinta unita che indica occupato](media/Presence_Busy.png) Disponibilità |  ![Cerchio rosso a tinta unita che indica occupato](media/Presence_Busy.png) Disponibilità  |
|| ![Cerchio rosso a tinta unita, che indica occupato in una chiamata](media/Presence_Busy.png) In una chiamata|
|| ![Cerchio rosso a tinta unita, che indica occupato in una riunione](media/Presence_Busy.png) In una riunione |
|| ![Aprire il cerchio rosso, indicando OOF occupato](media/Presence_Busy_OOF.png) In una chiamata fuori sede|
|  ![Cerchio rosso con linea bianca che indica che non disturbare](media/Presence_DND.png) Non disturbare ||
|| ![Cerchio rosso con linea bianca che indica la presentazione](media/Presence_DND.png) Presentazione|
| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) Via| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) Via|
|| ![Icona dell'orologio giallo, che](media/Presence_Away.png) indica l'ora dell'ultima *volta* che è stata vista|
|![Icona dell'orologio giallo, che indica di distanza, torno subito](media/Presence_Away.png) Torno subito| |
|| ![Icona dell'orologio giallo, con indicazione di distanza, fuori lavoro](media/Presence_Away.png)  Fuori ufficio|
|| ![Cerchio grigio con x, che indica offline](media/Presence_Offline.png) Offline |
|| ![Aprire il cerchio grigio, indicando lo stato sconosciuto](media/Presence_Unknown.png) Stato sconosciuto|
||![Aprire il cerchio rosso con la linea diagonale, indicando bloccato](media/Presence_Blocked.png) Bloccati |
|| ![Cerchio viola con freccia che indica fuori sede](media/Presence_OOF.png) Fuori sede|
|||
 
Gli utenti possono impostare manualmente lo stato presenza corrente su alcune opzioni e il relativo stato viene riflesso a tutti gli altri utenti. Ulteriori dettagli sulla presenza degli utenti vengono aggiornati automaticamente in base alle attività degli utenti (ad esempio, disponibile o distante), agli Stati del calendario di Outlook (ad esempio in una riunione) o agli Stati dell'app Teams (in una chiamata, presentazione), agli Stati rientrati nell'elenco.

Esiste un timeout di 15 minuti di inattività, dopo il quale lo stato di presenza corrente degli utenti verrà reimpostato su away.

Gli utenti possono specificare chi può sfondare (contattarli eseguendo l'override di un'impostazione non disturbare). Queste impostazioni sono disponibili in-app.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Impostazioni di amministrazione in teams rispetto a Skype for business

Le seguenti impostazioni di amministratore Skype for business sono diverse in teams:

- In teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione. Privacy (decidere chi può vedere la presenza) la configurazione non è disponibile in teams.
- La condivisione della presenza con tutti (inclusi i servizi federati) è sempre abilitata per gli utenti in teams. Il relativo elenco di contatti (se ne ha uno in Skype for business) è visibile in **Chat > contatti** o in **chiamate > contatti**.
- Il client non disturbare e le caratteristiche di innovazione sono sempre abilitate per gli utenti in teams.
- Calendario (include fuori sede e altre informazioni sul calendario) l'integrazione è sempre abilitata per gli utenti in teams se integrata con Outlook.
- L'ultima volta *che* è *stata visualizzata* o disattivata (se in un ambiente duale con Skype for business) l'indicatore è sempre abilitato per gli utenti in teams.

> [!NOTE]
> La capacità di un amministratore di teams di personalizzare queste impostazioni non è attualmente supportata.

## <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for business

Vedere la coesistenza [con Skype for business](coexistence-chat-calls-presence.md) per informazioni dettagliate su come funziona la presenza di teams in caso di coesistenza con Skype for business. 
