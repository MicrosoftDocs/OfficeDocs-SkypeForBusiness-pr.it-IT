---
title: Routing tra trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tra trunk. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814126"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing tra trunk in Skype for Business Server

Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tra trunk. Questa funzionalità consente a Skype for Business Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream. Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX. Analogamente, Skype for Business Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX. 


Nella figura seguente viene illustrato Skype for Business Server che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.

![Interconnettività tra un gateway PSTN e un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

Nella figura seguente viene illustrato Skype for Business Server che collega due sistemi IP-PBX.

![Skype for Business Server che collega due sistemi IP-PGX](../../media/two-ip-pbx-systems.jpg)

