---
title: Visualizzazione delle informazioni sull'interfaccia di rete
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
description: È possibile visualizzare le informazioni sull'interfaccia di rete utilizzando Windows PowerShell e il cmdlet Get-CsNetworkInterface rete. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.
ms.openlocfilehash: 56d6abcd804a5dd525bdc1d9f7b3e5df74f756b0
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015360"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Visualizzazione delle informazioni sull'interfaccia di rete in Skype for Business Server

È possibile visualizzare le informazioni sull'interfaccia di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkInterface.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.

## <a name="to-view-network-interface-information"></a>Per visualizzare informazioni sulle interfacce di rete

Per visualizzare le informazioni sull'interfaccia di rete, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:
    
`Get-CsNetworkInterface`

Questo comando restituisce informazioni simili alle seguenti per ogni interfaccia di rete:

```console    
Identity              : dc.vdomain.com/Primary/1
ComputerFqdn          : dc.vdomain.com
IPAddress             : 0.0.0.0
IPv6Address           :
Interface             : Primary
InterfaceNumber       : 1
ConfiguredFqdn        :
ConfiguredIPAddress   :
ConfiguredIPv6Address :
```

Per informazioni dettagliate, vedere [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).
