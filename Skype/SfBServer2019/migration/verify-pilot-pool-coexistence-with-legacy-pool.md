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
ms.openlocfilehash: f9a3fa8a9716d880b8fa2381fd5cafe88509504c2c142ebd5da5c5ab43667cf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341122"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificare la coesistenza del pool pilota con il pool legacy

 **In questo articolo**
  
[Verificare che Skype for Business Server 2019 siano stati avviati](#sectionSection0)
  
[Aprire il Pannello di controllo Skype for Business Server 2019](#sectionSection1)
  
[Non tentare di aprire la topologia nel Generatore di topologie legacy](#sectionSection2)
  
Dopo aver distribuito il pool pilota, è necessario verificare la coesistenza dei due pool utilizzando gli strumenti di amministrazione per visualizzare le informazioni dei pool. Per i Skype for Business Server 2019 e i pool legacy, è necessario utilizzare gli strumenti Skype for Business Server Pannello di controllo e Generatore di topologie di Skype for Business Server 2019. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Verificare che Skype for Business Server 2019 siano stati avviati
<a name="sectionSection0"> </a>

1. Dall'Skype for Business Server 2019 Front End Server passare all'applet Strumenti di amministrazione\Servizi.
    
2. Verificare che i servizi seguenti siano in esecuzione nel Front End Server:

    - Agente del servizio di registrazione centralizzato
    - Condivisione applicazioni
    - Servizio di test audio
    - Audio/videoconferenze
    - Parcheggio di chiamata
    - Annuncio conferenza
    - Operatore conferenza
    - Front-End
    - Conferenze di messaggistica istantanea
    - Mediation
    - Replica Replicator Agent
    - Response Group
    - Conferenze Web
    - Gateway di traduzione XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Aprire il Pannello di controllo Skype for Business Server 2019
<a name="sectionSection1"> </a>

Dal Front End Server nella distribuzione Skype for Business Server 2019, aprire il Pannello di controllo Skype for Business Server 2019 e selezionare il pool legacy. Ripetere la procedura per aprire il Skype for Business Server 2019.
  
> [!IMPORTANT]
> In Skype for Business Server 2019, è necessario aggiornare Silverlight a Silverlight versione 5 prima di utilizzare il Pannello Skype for Business Server controllo. 
  
Questa topologia ora include ruoli del server legacy Skype for Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Non tentare di aprire la topologia nel Generatore di topologie legacy
<a name="sectionSection2"> </a>

La topologia può essere visualizzata solo Skype for Business Server Generatore di topologie 2019. È Skype for Business Server generatore di topologie 2019 per creare pool sia per Skype for Business Server 2019 che per l'installazione legacy.

  

