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
localization_priority: Normal
description: È possibile visualizzare le informazioni sull'interfaccia di rete utilizzando Windows PowerShell e il cmdlet Get-CsNetworkInterface rete. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815136"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Visualizzazione delle informazioni sull'interfaccia di rete in Skype for Business Server

È possibile visualizzare le informazioni sull'interfaccia di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkInterface.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Per visualizzare informazioni sulle interfacce di rete

  - Per visualizzare le informazioni sull'interfaccia di rete, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:
    
        Get-CsNetworkInterface
    
    Questo comando restituisce informazioni simili alle seguenti per ogni interfaccia di rete:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Per informazioni dettagliate, vedere [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


