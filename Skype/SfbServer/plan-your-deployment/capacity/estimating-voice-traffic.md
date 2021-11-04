---
title: Stima dell'utilizzo vocale e del traffico per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: È possibile utilizzare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare tale traffico.
ms.openlocfilehash: bfc5e35b839f3accc139f3f9a02fdb8436426462
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746852"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Stima dell'utilizzo vocale e del traffico per Skype for Business Server
 
È possibile utilizzare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare tale traffico.
  
> Per un livello di **traffico leggero** (una chiamata PSTN per utente all'ora) considerare 15 utenti per porta.
> 
> Per un livello di **traffico medio** (2 chiamate PSTN per utente all'ora) considerare 10 utenti per porta.
> 
> Per un livello di **traffico pesante** (3 chiamate PSTN o più per utente all'ora) considerare 5 utenti per porta.
    
Il numero di porte determina a sua volta il numero di Mediation Server e gateway necessari. I gateway PSTN (Public Switched Telephone Network) distribuiti nella maggior parte delle organizzazioni variano in dimensione da 2 a 960 porte. Sono disponibili anche gateway più grandi, ma vengono utilizzati principalmente dai provider di servizi di telefonia.
  
Un'organizzazione con 10.000 utenti e traffico medio, ad esempio, necessiterebbe di 1000 porte. Il numero di gateway richiesti sarebbe uguale al numero totale di porte necessarie determinato in base alla capacità totale dei gateway.
  

