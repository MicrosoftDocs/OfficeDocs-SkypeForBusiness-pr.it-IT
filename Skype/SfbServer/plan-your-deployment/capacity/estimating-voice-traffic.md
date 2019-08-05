---
title: Stima dell'uso delle voci e del traffico per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: È possibile usare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare il traffico.
ms.openlocfilehash: 09c3e638d25225376b95afd60bdd6d3c311c1f5a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187916"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Stima dell'uso delle voci e del traffico per Skype for Business Server
 
È possibile usare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare il traffico.
  
> Per il **traffico leggero** (una chiamata PSTN per utente per ora), figura 15 utenti per ogni porta.
> 
> Per il **traffico medio** (2 chiamate PSTN per utente per ora), figura 10 utenti per ogni porta.
> 
> Per **traffico intenso** (3 o più chiamate PSTN per utente per ora), figura 5 utenti per ogni porta.
    
Il numero di porte determina a sua volta il numero di server di mediazione e gateway che saranno necessari. I gateway PSTN (Public Switched Telephone Network) che la maggior parte delle organizzazioni considerano la distribuzione di intervalli di dimensioni da 2 porte fino a un numero di porte di 960. Ci sono anche gateway più grandi, ma questi sono usati principalmente dai provider di servizi di telefonia.
  
Ad esempio, un'organizzazione con gli utenti di 10.000 e il traffico medio richiederebbe porte 1000. Il numero di gateway necessari sarebbe uguale al numero totale di porte richieste come determinato dalla capacità totale dei gateway.
  

