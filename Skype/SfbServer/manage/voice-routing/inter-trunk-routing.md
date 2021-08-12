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
ms.openlocfilehash: 917f6bb1eb114202f06e1f1d2be0c7c126f42d8cf1614c2a05dcce0dde6bb9a6
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850171"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server: routing tra trunk

Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk. Questa funzionalità consente Skype for Business Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream. Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX. Analogamente, Skype for Business Server è possibile interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere effettuate e ricevute tra telefoni PBX dai diversi sistemi IP-PBX. 


Nella figura seguente viene illustrata Skype for Business Server l'interconnettività tra un gateway PSTN e un IP-PBX.

![Interconnettività tra un gateway PSTN e un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

Nella figura seguente viene illustrata Skype for Business Server due sistemi IP-PBX.

![Skype for Business Server due sistemi IP-PGX](../../media/two-ip-pbx-systems.jpg)

