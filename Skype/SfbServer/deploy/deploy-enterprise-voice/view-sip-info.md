---
title: Visualizzare le informazioni sul trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Riepilogo: informazioni su come visualizzare informazioni sui trunk SIP in Skype for Business Server.'
ms.openlocfilehash: b2e2471d47dd40747c1e090936ed585f32208ef6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771484"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>Skype for Business Server: visualizzare informazioni sui singoli trunk SIP 
 
**Riepilogo:** Informazioni su come visualizzare informazioni sui trunk SIP in Skype for Business Server.
  
I trunk SIP vengono utilizzati per Skype for Business Server rete telefonica Voice over IP con la rete PSTN (Public Switched Telephone Network). Nella versione precedente del prodotto i trunk vengono utilizzati per instradare le chiamate in uscita da un Mediation Server a un gateway PSTN e ogni gateway è limitato a un singolo trunk. Un gateway PSTN e un trunk SIP in questo caso pertanto sono essenzialmente identici. Per gli amministratori, questo significa che possono visualizzare le informazioni relative a un trunk SIP semplicemente visualizzando le informazioni relative al gateway PSTN associato.
  
In Skype for Business Server, tuttavia, ora è possibile assegnare più trunk a un singolo gateway PSTN. ciò significa che i gateway e i trunk non sono più uguali. Questo di conseguenza significa che gli amministratori devono utilizzare il nuovo cmdlet [Get-CsTrunk](/powershell/module/skype/get-cstrunk) per visualizzare le informazioni relative a un singolo trunk SIP.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Per visualizzare le informazioni per tutti i trunk SIP

- Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Per visualizzare le informazioni per un trunk SIP specifico

- Questo comando restituisce informazioni solo sul trunk SIP con l'identità (Identity) PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Visualizzare le informazioni per tutti i trunk SIP assegnati a un pool

- In questo esempio vengono restituite le informazioni su tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
