---
title: 'Skype for Business Server: testare le impostazioni di configurazione dei trunk SIP'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Riepilogo: informazioni su come testare le impostazioni di configurazione dei trunk SIP tramite Skype for Business Server Management Shell.'
---

# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype for Business Server: testare le impostazioni di configurazione dei trunk SIP
 
**Riepilogo:** Informazioni su come testare le impostazioni di configurazione dei trunk SIP tramite Skype for Business Server Management Shell.
  
Le impostazioni di configurazione dei trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (Branch eXchange) di IP-Public o un session border controller (SBC) presso il provider di servizi. Queste impostazioni consentono di specificare quanto segue:
  
- Se il bypass multimediale deve essere abilitato nei trunk
    
- Condizioni in cui vengono inviati pacchetti RTCP (Realtime Transport Control Protocol)
    
- Se è necessaria la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk
    
Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione trunk SIP. Inoltre, gli amministratori possono creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN). Gli amministratori possono inoltre utilizzare il cmdlet Test-CsTrunkConfiguration per verificare che un trunk sia in grado di convertire un numero composto da un utente in un numero che il gateway può gestire.
  
Le impostazioni di configurazione dei trunk possono essere verificate solo utilizzando Windows PowerShell e il cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration). Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Skype for Business Server Management Shell.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Per testare le impostazioni di configurazione dei trunk SIP

- Il comando seguente verifica che le impostazioni di configurazione dei trunk per il sito Redmond siano in grado di convertire correttamente il numero composto 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
