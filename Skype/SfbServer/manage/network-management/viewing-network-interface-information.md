---
title: Visualizzazione delle informazioni sulle interfacce di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Per visualizzare le informazioni sull'interfaccia di rete, è possibile usare Windows PowerShell e il cmdlet Get-CsNetworkInterface. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.
ms.openlocfilehash: d4443f7ec10a0f56cc82ab495d88518f3f3aa17d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817352"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Visualizzazione delle informazioni sulle interfacce di rete in Skype for Business Server

Per visualizzare le informazioni sull'interfaccia di rete, è possibile usare Windows PowerShell e il cmdlet **Get-CsNetworkInterface** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Per visualizzare le informazioni sull'interfaccia di rete

  - Per visualizzare le informazioni sull'interfaccia di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkInterface
    
    Questo comando restituisce informazioni simili a quelle seguenti per ogni interfaccia di rete:
    
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


