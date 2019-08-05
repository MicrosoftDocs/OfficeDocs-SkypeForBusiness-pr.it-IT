---
title: Visualizzazione delle informazioni sulle interfacce di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Per visualizzare le informazioni sull'interfaccia di rete, è possibile usare Windows PowerShell e il cmdlet Get-CsNetworkInterface. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188525"
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


