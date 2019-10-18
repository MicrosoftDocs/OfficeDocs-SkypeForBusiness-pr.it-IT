---
title: Presenza dell'utente in teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informazioni per gli amministratori sulla presenza in teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573218"
---
# <a name="user-presence-in-teams"></a>Presenza dell'utente in teams

La presenza fa parte del profilo di un utente in Microsoft Teams (e in tutto Office 365) che indica la disponibilità e lo stato correnti dell'utente ad altri utenti. Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano team possono vedere (in tempi quasi reali) se sono disponibili online.

> [!IMPORTANT]
> Se si disinstalla il client Skype for business dopo aver spostato un utente in modalità **solo teams** , la presenza smette di funzionare in Outlook e in altre app di Office. La presenza funziona correttamente in teams. Soluzione alternativa: per vedere la presenza in Outlook e in altre app di Office, è necessario installare Skype for business, anche se si sta usando teams in modalità **solo teams** . Microsoft è a conoscenza del problema e sta lavorando a una correzione.

## <a name="presence-states-in-teams"></a>Stati presenza in teams

Gli Stati di presenza degli utenti disponibili in teams sono:

|Configurato dall'utente|App configurata|
|:--- |:---|
| ![Segno di spunta verde fisso, che indica la presenza disponibile](media/Presence_Available.png) Disponibili|![Segno di spunta verde fisso, che indica la presenza disponibile](media/Presence_Available.png) Disponibili|
|| ![Aprire il segno di spunta verde, indica disponibile OOF](media/Presence_Available_OOF.png) Disponibile, fuori sede |
|  ![Cerchio rosso a tinta unita, indica occupato](media/Presence_Busy.png) Disponibilità |  ![Cerchio rosso a tinta unita, indica occupato](media/Presence_Busy.png) Disponibilità  |
|| ![Cerchio rosso a tinta unita, indica occupato in una chiamata](media/Presence_Busy.png) In una chiamata|
|| ![Cerchio rosso a tinta unita, indica occupato in una riunione](media/Presence_Busy.png) In una riunione |
|| ![Aprire il cerchio rosso, indica occupato](media/Presence_Busy_OOF.png) In una chiamata fuori sede|
|  ![Cerchio rosso con linea bianca, indica non disturbare](media/Presence_DND.png) Non disturbare ||
|| ![Cerchio rosso con linea bianca, indica la presentazione](media/Presence_DND.png) Presentazione|
|| ![Cerchio rosso con linea bianca, indica lo stato di messa a fuoco](media/Presence_DND.png) Incentrato|
| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) Via| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) Via|
|| ![Icona dell'orologio giallo, che](media/Presence_Away.png) indica la data dell'ultima *ora* di visualizzazione|
|![Icona dell'orologio giallo, indica via, torno subito](media/Presence_Away.png) Torno subito| |
|| ![Icona dell'orologio giallo, indica via, fuori lavoro](media/Presence_Away.png)  Fuori ufficio|
|| ![Cerchio grigio con x, indica offline](media/Presence_Offline.png) Offline |
|| ![Apri cerchio grigio, indica lo stato sconosciuto](media/Presence_Unknown.png) Stato sconosciuto|
||![Aprire il cerchio rosso con la linea diagonale, indica il blocco](media/Presence_Blocked.png) Bloccati |
|| ![Cerchio viola con freccia, indica fuori sede](media/Presence_OOF.png) Fuori sede|
|||
 
Gli utenti possono impostare manualmente lo stato presenza corrente su alcune opzioni e il relativo stato viene riflesso a tutti gli altri utenti. Vengono aggiornati automaticamente anche altri dettagli sulla presenza dell'utente. Le modifiche sono basate su attività utente (disponibile, assente), Stati del calendario di Outlook (in una riunione) o Stati dell'app Teams (in una chiamata, presentazione), agli Stati rientrati nell'elenco.

Si verifica un timeout di 15 minuti di inattività, dopo il quale viene reimpostato uno stato presenza corrente su assente.

Gli utenti possono specificare chi può sfondare (il che significa mettersi in contatto nonostante uno stato non disturbare). Queste impostazioni sono disponibili nel client teams.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Impostazioni di amministrazione in teams rispetto a Skype for business

Le seguenti impostazioni di amministratore Skype for business sono diverse in teams:

- In teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione. La privacy (dove è possibile definire chi può vedere la presenza) la configurazione non è disponibile in teams.
- La condivisione della presenza con tutti (inclusi i servizi federati) è sempre abilitata per gli utenti in teams. Il relativo elenco di contatti (se ne ha uno in Skype for business) è visibile in **Chat > contatti** o in **chiamate > contatti**.
- Il client non disturbare e le caratteristiche di innovazione sono sempre abilitate per gli utenti in teams.
- Calendario (include fuori sede e altre informazioni sul calendario) l'integrazione è sempre abilitata per gli utenti quando i team sono integrati con Outlook.
- L'indicatore l'ultima volta *che* viene *visualizzato* o disattivo è sempre abilitato per gli utenti in teams se l'organizzazione usa anche Skype for business.

> [!NOTE]
> La capacità di un amministratore di teams di personalizzare queste impostazioni non è attualmente supportata.

## <a name="coexistence-with-skype-for-business"></a>Coesistenza con Skype for business

Vedere la [coesistenza con Skype for business](coexistence-chat-calls-presence.md) per informazioni dettagliate su come funziona la presenza di teams quando l'organizzazione usa anche Skype for business.
