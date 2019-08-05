---
title: Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Riepilogo: Scopri come visualizzare le informazioni sui trunk SIP in Skype for Business Server.'
ms.openlocfilehash: a8cb5559b1431987adeef7c50b7810b7e9b4adc7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195204"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server
 
**Riepilogo:** Scopri come visualizzare le informazioni sui trunk SIP in Skype for Business Server.
  
I trunk SIP vengono usati per connettere la rete telefonica Voice over IP di Skype for Business Server con la rete PSTN (Public Switched Telephone Network). Nella versione precedente del prodotto Trunks veniva usato per instradare le chiamate in uscita da un Mediation Server a un gateway PSTN e ogni gateway era limitato a un singolo trunk. Di conseguenza, un gateway PSTN e un trunk SIP erano essenzialmente identici. Per gli amministratori, ciò significava che potevano visualizzare informazioni su un singolo trunk SIP semplicemente visualizzando le informazioni sul gateway PSTN associato.
  
In Skype for Business Server, tuttavia, è ora possibile assegnare più trunk a un singolo gateway PSTN. Ciò significa che i gateway e i trunk non sono più uno e lo stesso. A sua volta, ciò significa che gli amministratori devono usare il nuovo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) per visualizzare informazioni su un singolo trunk SIP.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Per visualizzare le informazioni per tutti i trunk SIP

- Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Per visualizzare le informazioni relative a un trunk SIP specifico

- Questo comando restituisce solo le informazioni per il trunk SIP con Identity PstnGateway: 192.168.0.240:
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Visualizzare informazioni per tutti i trunk SIP assegnati a un pool

- In questo esempio vengono restituite le informazioni per tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
