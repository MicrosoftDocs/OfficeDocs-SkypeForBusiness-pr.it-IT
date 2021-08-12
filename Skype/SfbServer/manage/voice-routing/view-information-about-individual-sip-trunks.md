---
title: Skype for Business Server - Visualizzare informazioni sui singoli trunk SIP
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
description: In Skype for Business Server, è possibile assegnare più trunk a un singolo gateway PSTN. I gateway e i trunk non sono uguali e gli amministratori devono utilizzare il cmdlet Get-CsTrunk per visualizzare le informazioni su un singolo trunk SIP.
ms.openlocfilehash: f78aad8aa55202cdd59107be8f5e66dc2f83e1d336dc2f66c4982b7f534c88cc
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848391"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype for Business Server - Visualizzare informazioni sui singoli trunk SIP

In Skype for Business Server, è possibile assegnare più trunk a un singolo gateway PSTN. ciò significa che i gateway e i trunk non sono uguali e che gli amministratori devono utilizzare il cmdlet [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) per visualizzare le informazioni su un singolo trunk SIP.

Il cmdlet Get-CsTrunk può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.

**Per visualizzare le informazioni per tutti i trunk SIP**

Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:

`Get-CsTrunk`

**Per visualizzare le informazioni per un trunk SIP specifico**

Questo comando restituisce informazioni solo sul trunk SIP con l'identità (Identity) PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Visualizzazione delle informazioni relative a tutti i trunk SIP assegnati a un pool**

In questo esempio vengono restituite le informazioni su tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
