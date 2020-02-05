---
title: Aggiungere un criterio di posizione a un sito di rete in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Assegnare i criteri di posizione E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768279"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="85c1a-103">Aggiungere un criterio di posizione a un sito di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="85c1a-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="85c1a-104">Assegnare i criteri di posizione E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="85c1a-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="85c1a-105">Gli esempi seguenti illustrano come aggiungere i criteri di posizione di **Redmond** definiti in [creare criteri di posizione in Skype for Business Server](create-location-policies.md) in un sito di rete esistente e come creare un nuovo sito di rete che usa il criterio di posizione **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="85c1a-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="85c1a-106">Per informazioni dettagliate sull'uso dei siti di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="85c1a-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="85c1a-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="85c1a-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="85c1a-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="85c1a-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="85c1a-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="85c1a-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="85c1a-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="85c1a-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="85c1a-111">Per assegnare un criterio di posizione a un sito di rete esistente</span><span class="sxs-lookup"><span data-stu-id="85c1a-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="85c1a-112">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="85c1a-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="85c1a-113">Eseguire i cmdlet seguenti per modificare un sito di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="85c1a-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="85c1a-114">Assegnare i criteri di posizione Tagged **Redmond** a un sito di rete esistente denominato **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="85c1a-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="85c1a-115">Per assegnare un criterio di posizione a un nuovo sito di rete</span><span class="sxs-lookup"><span data-stu-id="85c1a-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="85c1a-116">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="85c1a-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="85c1a-117">Eseguire il cmdlet seguente per creare un nuovo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="85c1a-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="85c1a-118">Creare un nuovo sito di rete nell'area di rete e assegnare il criterio di posizione Tagged **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="85c1a-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


