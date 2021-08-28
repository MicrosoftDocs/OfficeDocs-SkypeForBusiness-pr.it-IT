---
title: Pianificare il controllo delle chiamate remote in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Il controllo delle chiamate remote era una funzionalità delle versioni precedenti di Lync Server che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita con Chiama tramite lavoro. Nelle versioni client di Skype for Business Server 2015 e successive, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'utilizzo.
ms.openlocfilehash: bbe98c5aa6a490276f1f317ed208d936920b0c65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604735"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Pianificare il controllo delle chiamate remote in Skype for Business
 
Il controllo delle chiamate remote era una funzionalità delle versioni precedenti di Lync Server che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita con Chiama tramite lavoro.  *Nelle versioni client di Skype for Business Server 2015 e successive, il controllo delle chiamate remote non è più disponibile per la configurazione nel client ed è stato rimosso per l'utilizzo.* 
  
 Gli utenti del controllo delle chiamate remote nell'organizzazione ospitati nei Front End Server che eseguono Lync Server possono continuare a utilizzare il controllo delle chiamate remote, anche se utilizzano un client Skype for Business remoto. Tuttavia, per tutti gli utenti ospitati in Skype for Business Server, il controllo delle chiamate remote non è supportato. Vedere la tabella seguente per le combinazioni server/client e se sono in grado di supportare il controllo delle chiamate remote o chiamata tramite lavoro.
  
||**Skype for Business Client con interfaccia Skype abilitata**|**Skype for Business Client con interfaccia utente di Lync abilitata**|**Skype for Business 2016 Client**|**Lync 2013 Client**|**Lync 2010 Client**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Chiamata tramite lavoro  <br/> |1  <br/> |Chiamata tramite lavoro  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |1  <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |
| Lync Server 2010 <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |1  <br/> |Controllo delle chiamate remote  <br/> |Controllo delle chiamate remote  <br/> |
   
1. Nessuna delle due funzionalità è supportata.
  
Per ulteriori informazioni, vedere [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) nella documentazione di Lync Server 2013.
  
## <a name="see-also"></a>Vedere anche

[Pianificare la chiamata tramite lavoro in Skype for Business Server](call-via-work.md)
  
[Confronto delle funzionalità client desktop per Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Effettuare una Skype for Business chiamata, ma usare il telefono da tavolo PBX per l'audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)