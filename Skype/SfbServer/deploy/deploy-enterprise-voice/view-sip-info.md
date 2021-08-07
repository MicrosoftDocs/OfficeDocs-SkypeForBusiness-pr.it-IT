---
title: Visualizzare le informazioni sul trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Riepilogo: informazioni su come visualizzare informazioni sui trunk SIP in Skype for Business Server.'
ms.openlocfilehash: 2f4cc3a7435577d6c9d635a7dc910873b21f9981
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772797"
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
