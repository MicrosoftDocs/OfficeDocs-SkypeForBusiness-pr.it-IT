---
title: Pianificare il controllo delle chiamate remote in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Il controllo delle chiamate remote era una funzionalità nelle versioni precedenti di Lync Server, che consentiva agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita da chiamata tramite lavoro. Nelle versioni client per Skype for Business Server 2015 e in futuro, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'utilizzo.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982801"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Pianificare il controllo delle chiamate remote in Skype for business
 
Il controllo delle chiamate remote era una funzionalità nelle versioni precedenti di Lync Server, che consentiva agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita da chiamata tramite lavoro.  *Nelle versioni client per Skype for Business Server 2015 e in futuro, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'utilizzo.* 
  
 Gli utenti del controllo delle chiamate remote nell'organizzazione ospitati nei front end server che eseguono Lync Server possono continuare a utilizzare il controllo delle chiamate remote, anche se utilizzano un client Skype for business. Tuttavia, per tutti gli utenti ospitati su Skype for Business Server, il controllo delle chiamate remote non è supportato. Vedere la tabella seguente per le combinazioni di server/client e se è in grado di supportare il controllo delle chiamate remote o la chiamata tramite lavoro.
  
||**Client Skype for business con interfaccia utente Skype abilitata**|**Client Skype for business con Lync UI abilitata**|**Client Skype for business 2016**|**Client Lync 2013**|**Lync 2010 Client**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Chiamata tramite lavoro  <br/> |1  <br/> |Chiamata tramite lavoro  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |1  <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |
| Lync Server 2010 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |1  <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |
   
1. Nessuna caratteristica è supportata.
  
Per ulteriori informazioni, vedere [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) nella documentazione di Lync Server 2013.
  
## <a name="see-also"></a>Vedere anche

[Pianificare la chiamata tramite il lavoro in Skype for Business Server](call-via-work.md)
  
[Confronto delle funzionalità dei client desktop per Skype for business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Effettuare una chiamata Skype for business, ma utilizzare il telefono da tavolo PBX per l'audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

