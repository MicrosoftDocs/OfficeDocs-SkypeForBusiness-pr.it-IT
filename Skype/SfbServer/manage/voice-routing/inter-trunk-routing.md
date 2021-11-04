---
title: 'Skype for Business Server: routing tra trunk'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk. '
ms.openlocfilehash: ea21bf8e3697dc4b06b562f709d88903666cf3c5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774746"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server: routing tra trunk

Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk. Questa funzionalità consente Skype for Business Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream. Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX. Analogamente, Skype for Business Server è possibile interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere effettuate e ricevute tra telefoni PBX dai diversi sistemi IP-PBX. 


Nella figura seguente viene illustrata Skype for Business Server l'interconnettività tra un gateway PSTN e un IP-PBX.

![Interconnettività tra un gateway PSTN e un IP-PBX.](../../media/pstn-gateway-ip-pbx.jpg)

Nella figura seguente viene illustrata Skype for Business Server due sistemi IP-PBX.

![Skype for Business Server due sistemi IP-PGX.](../../media/two-ip-pbx-systems.jpg)

