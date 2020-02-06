---
title: Routing inter-trunk in Skype for Business Server
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Informazioni su come Skype for Business Server VoIP aziendale supporta il routing tra trunk.
ms.openlocfilehash: 85a77fea8fb414a90b556e5862c42e2c59046dec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802856"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing inter-trunk in Skype for Business Server
 
Informazioni su come Skype for Business Server VoIP aziendale supporta il routing tra trunk.
  
Skype for Business Server offre una gestione delle sessioni di base tramite il supporto del routing intertrunk. In questo modo Skype for Business Server offre funzionalità per il controllo delle chiamate ai sistemi di telefonia downstream. Il routing intertrunk può interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere indirizzate alla rete PSTN e le chiamate PSTN in arrivo possano essere indirizzate a un telefono PBX. Analogamente, Skype for Business Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX. 
  
La figura seguente illustra Skype for Business Server che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.
  
![Diagramma delle connessioni tra Lync Server e gateway PSTN/IP-PBX](../../media/inter_trunk01.jpg)
  
Nella figura seguente viene illustrato Skype for Business Server che connette due sistemi IP-PBX.
  
![Diagramma delle interconnessioni tra Lync Server e sistemi IP-PAX](../../media/inter_trunk02.jpg)
  

