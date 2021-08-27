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
ms.localizationpriority: medium
description: In Skype for Business Server, è possibile assegnare più trunk a un singolo gateway PSTN. I gateway e i trunk non sono uguali e gli amministratori devono utilizzare il cmdlet Get-CsTrunk per visualizzare le informazioni su un singolo trunk SIP.
ms.openlocfilehash: 2c39a35ee0a42e2f54e87541cec857b3d90cd2c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617802"
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
