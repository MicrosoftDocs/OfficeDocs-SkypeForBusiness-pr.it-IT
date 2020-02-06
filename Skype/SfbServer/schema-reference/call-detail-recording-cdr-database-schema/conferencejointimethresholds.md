---
title: Tabella ConferenceJoinTimeThresholds in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: "La tabella ConferenceJoinTimeThresholds contiene i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza. Il report Riepilogo temporale per la conferenza di partecipazione riepiloga il tempo necessario per consentire agli utenti di partecipare a una conferenza con successo. questi valori temporali vengono segnalati sia come media che in una delle categorie seguenti:"
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815394"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabella ConferenceJoinTimeThresholds in Skype for Business Server 2015
 
La tabella ConferenceJoinTimeThresholds contiene i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza. Il report Riepilogo temporale per la conferenza di partecipazione riepiloga il tempo necessario per consentire agli utenti di partecipare a una conferenza con successo. questi valori temporali vengono segnalati sia come media che in una delle categorie seguenti:
  
- Meno di 2 secondi.
    
- Tra 2 secondi e 5 secondi.
    
- Tra 5 secondi e 10 secondi.
    
- Più di 10 secondi.
    
La tabella ConferenceJoinTimeThresholds contiene i valori di classificazione 2 secondi, 5 secondi e 10 secondi.
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per la classificazione.  <br/> |
|**ThresholdValue:** <br/> |int  <br/> || Limite superiore per la classificazione. I valori consentiti sono: <br/>  2 <br/>  5 <br/>  10 <br/> |
   

