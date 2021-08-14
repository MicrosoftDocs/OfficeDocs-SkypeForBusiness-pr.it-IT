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
description: 'Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk. '
ms.openlocfilehash: 2c2d2dfd1062414de0d11b9e77d7f9f1993a77a14266a8d121b43bfbc12335da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351496"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing tra trunk in Skype for Business Server

Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk. Questa funzionalità consente Skype for Business Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream. Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX. Analogamente, Skype for Business Server è possibile interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere effettuate e ricevute tra telefoni PBX dai diversi sistemi IP-PBX. 


Nella figura seguente viene illustrata Skype for Business Server l'interconnettività tra un gateway PSTN e un IP-PBX.

![Interconnettività tra un gateway PSTN e un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

Nella figura seguente viene illustrata Skype for Business Server la connessione di due sistemi IP-PBX.

![Skype for Business Server due sistemi IP-PGX](../../media/two-ip-pbx-systems.jpg)

