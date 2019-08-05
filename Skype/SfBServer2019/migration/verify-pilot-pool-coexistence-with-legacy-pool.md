---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processo per verificare la coesistenza del pool pilota con il pool legacy.
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2019
ms.locfileid: "36196041"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificare la coesistenza del pool pilota con il pool legacy

 **In questo articolo**
  
[Verificare che i servizi di Skype for Business Server 2019 siano stati avviati](#sectionSection0)
  
[Aprire il pannello di controllo di Skype for Business Server 2019](#sectionSection1)
  
[Non provare ad aprire la topologia nel generatore di topologia legacy](#sectionSection2)
  
Dopo la distribuzione del pool pilota, è necessario verificare la coesistenza dei due pool usando gli strumenti di amministrazione per visualizzare le informazioni sul pool. Per i pool di 2019 e i pool legacy di Skype for Business Server, è necessario usare gli strumenti pannello di controllo e generatore di topologia di Skype for Business Server 2019. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Verificare che i servizi di Skype for Business Server 2019 siano stati avviati
<a name="sectionSection0"> </a>

1. Dal server front-end di Skype for Business Server 2019 passare all'applet Tools\Services amministrativa.
    
2. Verificare che i servizi seguenti siano in uso nel server front-end:

    - Agente del servizio di registrazione centralizzato
    - Condivisione applicazioni
    - Servizio test audio
    - Conferenze audio/video
    - Parcheggio di chiamata
    - Annuncio conferenza
    - Assistente conferenza
    - Front-end
    - Conferenza di messaggistica istantanea
    - Pubblicitari
    - Agente Replicator replica
    - Response Group
    - Web Conferencing
    - Gateway di traduzione XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Aprire il pannello di controllo di Skype for Business Server 2019
<a name="sectionSection1"> </a>

Dal server front-end della distribuzione di Skype for Business Server 2019 aprire il pannello di controllo di Skype for Business Server 2019 e selezionare il pool legacy. Ripetere la procedura per aprire il pool di Skype for Business Server 2019.
  
> [!IMPORTANT]
> In Skype for Business Server 2019 è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di usare il pannello di controllo di Skype for Business Server. 
  
Questa topologia include ora i ruoli server legacy e Skype for Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Non provare ad aprire la topologia nel generatore di topologia legacy
<a name="sectionSection2"> </a>

La topologia può essere visualizzata solo con il generatore di topologia di Skype for Business Server 2019. Il generatore di topologia di Skype for Business Server 2019 deve essere usato per creare pool sia per Skype for Business Server 2019 che per l'installazione legacy.

  

