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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="05f6b-104">Visualizzazione delle informazioni sulle interfacce di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="05f6b-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="05f6b-105">Per visualizzare le informazioni sull'interfaccia di rete, è possibile usare Windows PowerShell e il cmdlet **Get-CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="05f6b-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="05f6b-106">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05f6b-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="05f6b-107">Per visualizzare le informazioni sull'interfaccia di rete</span><span class="sxs-lookup"><span data-stu-id="05f6b-107">To view network interface information</span></span>

  - <span data-ttu-id="05f6b-108">Per visualizzare le informazioni sull'interfaccia di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="05f6b-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="05f6b-109">Questo comando restituisce informazioni simili a quelle seguenti per ogni interfaccia di rete:</span><span class="sxs-lookup"><span data-stu-id="05f6b-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="05f6b-110">Per informazioni dettagliate, vedere [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="05f6b-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


