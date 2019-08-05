---
title: Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype for Business Server è possibile assegnare più trunk a un singolo gateway PSTN. Ciò significa che i gateway e i trunk non sono uno e gli stessi e gli amministratori devono usare il cmdlet Get-CsTrunk per visualizzare informazioni su un singolo trunk SIP.
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186998"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server

In Skype for Business Server è possibile assegnare più trunk a un singolo gateway PSTN. Ciò significa che i gateway e i trunk non sono uguali e che gli amministratori devono usare il cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) per visualizzare informazioni su un singolo trunk SIP.

Il cmdlet Get-CsTrunk può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.

**Per visualizzare le informazioni per tutti i trunk SIP**

Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:

`Get-CsTrunk`

**Per visualizzare le informazioni relative a un trunk SIP specifico**

Questo comando restituisce solo le informazioni per il trunk SIP con Identity PstnGateway: 192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Visualizzazione di informazioni per tutti i trunk SIP assegnati a un pool**

In questo esempio vengono restituite le informazioni per tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
