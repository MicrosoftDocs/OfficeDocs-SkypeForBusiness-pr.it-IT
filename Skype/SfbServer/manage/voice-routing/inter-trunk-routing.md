---
title: 'Skype for Business Server: routing tra trunk'
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
description: 'Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk. '
ms.openlocfilehash: 694fc707711ae804bade0935e0fb9f34e89dbb93
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234371"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server: routing tra trunk

Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk. Questa funzionalità consente Skype for Business Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream. Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX. Analogamente, Skype for Business Server è possibile interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere effettuate e ricevute tra telefoni PBX dai diversi sistemi IP-PBX. 


Nella figura seguente viene illustrata Skype for Business Server l'interconnettività tra un gateway PSTN e un IP-PBX.

![Interconnettività tra un gateway PSTN e un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

Nella figura seguente viene illustrata Skype for Business Server due sistemi IP-PBX.

![Skype for Business Server due sistemi IP-PGX](../../media/two-ip-pbx-systems.jpg)

