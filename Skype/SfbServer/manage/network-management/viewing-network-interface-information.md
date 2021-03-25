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
ms.openlocfilehash: 0e72b2550413004038b110292b693dda25affaf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122420"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="9fc40-104">Visualizzazione delle informazioni sull'interfaccia di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9fc40-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="9fc40-105">È possibile visualizzare le informazioni sull'interfaccia di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkInterface.**</span><span class="sxs-lookup"><span data-stu-id="9fc40-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="9fc40-106">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fc40-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="9fc40-107">Per visualizzare informazioni sulle interfacce di rete</span><span class="sxs-lookup"><span data-stu-id="9fc40-107">To view network interface information</span></span>

  - <span data-ttu-id="9fc40-108">Per visualizzare le informazioni sull'interfaccia di rete, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9fc40-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="9fc40-109">Questo comando restituisce informazioni simili alle seguenti per ogni interfaccia di rete:</span><span class="sxs-lookup"><span data-stu-id="9fc40-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="9fc40-110">Per informazioni dettagliate, vedere [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="9fc40-110">For details, see [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).</span></span>