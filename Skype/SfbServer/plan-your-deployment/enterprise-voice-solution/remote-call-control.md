---
title: Pianificare il controllo delle chiamate remote in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Il controllo delle chiamate remote è una funzionalità delle versioni precedenti di Lync Server che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server questa funzionalità è stata sostituita da chiamata tramite lavoro. Nelle versioni client per Skype for Business Server 2015 e in corso forward, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'uso.
ms.openlocfilehash: e98bcbd7e1feb91b31994d2ece2770c911547882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187574"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Pianificare il controllo delle chiamate remote in Skype for business
 
Il controllo delle chiamate remote è una funzionalità delle versioni precedenti di Lync Server che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server questa funzionalità è stata sostituita da chiamata tramite lavoro.  *Nelle versioni client per Skype for Business Server 2015 e in corso forward, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'uso.* 
  
 Gli utenti del controllo delle chiamate remote dell'organizzazione ospitati nei server front-end che eseguono Lync Server possono continuare a usare il controllo delle chiamate remote, anche se usano un client Skype for business. Tuttavia, per gli utenti residenti in Skype for Business Server, il controllo delle chiamate remote non è supportato. Vedere la tabella seguente per le combinazioni server/client e se può supportare il controllo delle chiamate remote o la chiamata tramite lavoro.
  
||**Client Skype for business con interfaccia utente Skype abilitata**|**Client Skype for business con interfaccia utente di Lync abilitata**|**Client di 2016 per Skype for business**|**Client Lync 2013**|**Lync 2010 Client**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Chiamata tramite lavoro  <br/> |1 <br/> |Chiamata tramite lavoro  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |1 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |
| Lync Server 2010 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |1 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |
   
1. Nessuna caratteristica è supportata.
  
Per altre informazioni, vedere [controllo delle chiamate remote](https://go.microsoft.com/fwlink/p/?LinkId=530208) nella documentazione di Lync Server 2013.
  
## <a name="see-also"></a>Vedere anche

[Pianificare la chiamata tramite il lavoro in Skype for Business Server](call-via-work.md)
  
[Confronto tra funzionalità client desktop per Skype for business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Effettuare una chiamata Skype for business, ma usare il telefono da tavolo PBX per l'audio](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

