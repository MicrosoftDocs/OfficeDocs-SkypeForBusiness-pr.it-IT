---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Processo per verificare la coesistenza del pool pilota con il pool legacy.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751658"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificare la coesistenza del pool pilota con il pool legacy

 **In questo articolo**
  
[Verificare che i servizi di Skype for Business Server 2019 siano stati avviati](#sectionSection0)
  
[Aprire il Pannello di controllo di Skype for Business Server 2019](#sectionSection1)
  
[Non tentare di aprire la topologia nel Generatore di topologie legacy](#sectionSection2)
  
Dopo aver distribuito il pool pilota, è necessario verificare la coesistenza dei due pool utilizzando gli strumenti di amministrazione per visualizzare le informazioni dei pool. Per i pool di Skype for Business Server 2019 e i pool legacy, è necessario utilizzare il Pannello di controllo di Skype for Business Server 2019 e gli strumenti di Generatore di topologie. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Verificare che i servizi di Skype for Business Server 2019 siano stati avviati
<a name="sectionSection0"> </a>

1. Dal Front End Server di Skype for Business Server 2019, accedere all'applet Strumenti di amministrazione\Servizi.
    
2. Verificare che i servizi seguenti siano in esecuzione nel Front End Server:

    - Agente del servizio di registrazione centralizzato
    - Condivisione applicazioni
    - Servizio test audio
    - Audio/videoconferenze
    - Parcheggio di chiamata
    - Annuncio conferenza
    - Operatore Conferenza
    - Front-End
    - Servizi di conferenza di messaggistica istantanea
    - Mediation
    - Agente Replicator
    - Response Group
    - Conferenze Web
    - Gateway di conversione XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Aprire il Pannello di controllo di Skype for Business Server 2019
<a name="sectionSection1"> </a>

Dal Front End Server nella distribuzione di Skype for Business Server 2019, aprire il Pannello di controllo di Skype for Business Server 2019 e selezionare il pool legacy. Ripetere la procedura per aprire il pool di Skype for Business Server 2019.
  
> [!IMPORTANT]
> In Skype for Business Server 2019, è necessario aggiornare Silverlight a Silverlight versione 5 prima di usare il Pannello di controllo di Skype for Business Server. 
  
Questa topologia ora include i ruoli del server Legacy e Skype for Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Non tentare di aprire la topologia nel Generatore di topologie legacy
<a name="sectionSection2"> </a>

La topologia può essere visualizzata solo tramite Generatore di topologie di Skype for Business Server 2019. Il Generatore di topologie di Skype for Business Server 2019 deve essere utilizzato per creare pool sia per Skype for Business Server 2019 che per l'installazione legacy.

  

