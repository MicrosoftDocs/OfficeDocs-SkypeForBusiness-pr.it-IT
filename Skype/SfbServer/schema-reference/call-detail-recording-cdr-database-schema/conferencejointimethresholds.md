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
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: "La tabella ConferenceJoinTimeThresholds contiene i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza. Il report Riepilogo temporale per la conferenza di partecipazione riepiloga il tempo necessario per consentire agli utenti di partecipare a una conferenza con successo. questi valori temporali vengono segnalati sia come media che in una delle categorie seguenti:"
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194841"
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
   

