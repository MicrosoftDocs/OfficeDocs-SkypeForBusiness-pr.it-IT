---
title: Routing inter-trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server offre una gestione delle sessioni di base tramite il supporto del routing intertrunk. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816966"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing inter-trunk in Skype for Business Server

Skype for Business Server offre una gestione delle sessioni di base tramite il supporto del routing intertrunk. Questa funzionalità consente a Skype for Business Server di specificare le funzionalità di controllo delle chiamate per i sistemi di telefonia downstream. Il routing intertrunk può interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere indirizzate alla rete PSTN e le chiamate PSTN in arrivo possano essere indirizzate a un telefono PBX. Analogamente, Skype for Business Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX. 


La figura seguente illustra Skype for Business Server che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.

![Interconnettività tra un gateway PSTN e un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

Nella figura seguente viene illustrato Skype for Business Server che connette due sistemi IP-PBX.

![Skype for Business Server che connette due sistemi IP-PGX](../../media/two-ip-pbx-systems.jpg)

