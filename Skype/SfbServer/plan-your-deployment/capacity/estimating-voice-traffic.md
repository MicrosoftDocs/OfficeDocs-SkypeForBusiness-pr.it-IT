---
title: Stima dell'utilizzo vocale e del traffico per Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
  

