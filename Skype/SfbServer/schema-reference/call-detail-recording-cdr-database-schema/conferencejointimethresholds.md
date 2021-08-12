---
title: Tabella ConferenceJoinTimeThresholds Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabella ConferenceJoinTimeThresholds include i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza. Questo rapporto riepiloga la quantità di tempo richiesto agli utenti per partecipare a una conferenza. I valori temporali vengono riportati come media e in una delle categorie seguenti:'
ms.openlocfilehash: 9ce7e8e92921e0cccd8987d6f270a205c5c94de457571ebf959da703cc4bf2ca
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341751"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabella ConferenceJoinTimeThresholds Skype for Business Server 2015
 
La tabella ConferenceJoinTimeThresholds include i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza. Questo rapporto riepiloga la quantità di tempo richiesto agli utenti per partecipare a una conferenza. I valori temporali vengono riportati come media e in una delle categorie seguenti:
  
- Meno di 2 secondi.
    
- Tra 2 e 5 secondi.
    
- Tra 5 e 10 secondi.
    
- Più di 10 secondi.
    
La tabella ConferenceJoinTimeThresholds include i valori di classificazione 2 secondi, 5 secondi e 10 secondi.
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco della classificazione.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite superiore per la classificazione. I valori consentiti sono: <br/>  2 <br/>  5  <br/>  10  <br/> |
   

