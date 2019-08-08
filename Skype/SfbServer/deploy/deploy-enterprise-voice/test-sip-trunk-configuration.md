---
title: Verificare le impostazioni di configurazione del trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Riepilogo: informazioni su come verificare le impostazioni di configurazione del trunk SIP tramite Skype for Business Server Management Shell.'
ms.openlocfilehash: 1ef034f0b1de187e472fc3049573e9453e5a9505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240305"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Verificare le impostazioni di configurazione del trunk SIP in Skype for Business Server
 
**Riepilogo:** Informazioni su come verificare le impostazioni di configurazione del trunk SIP tramite Skype for Business Server Management Shell.
  
Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch eXchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:
  
- Se il bypass multimediale deve essere abilitato nei trunk.
    
- Condizioni in cui vengono inviati i pacchetti RTCP (Realtime Transport Control Protocol).
    
- Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk.
    
Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN). Gli amministratori possono anche usare il cmdlet Test-CsTrunkConfiguration per verificare che un trunk sia in grado di convertire un numero come composto da un utente in un numero che può essere gestito dal gateway.
  
Le impostazioni di configurazione trunk possono essere testate solo usando Windows PowerShell e il cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) . Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Skype for Business Server Management Shell.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Per testare le impostazioni di configurazione del trunk SIP

- Questo comando verifica che le impostazioni di configurazione del trunk per il sito Redmond possano convertire correttamente il numero composto da 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


