---
title: Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Riepilogo: informazioni su come visualizzare informazioni sui trunk SIP in Skype for Business Server.'
ms.openlocfilehash: 989f9fea44bfcce67eba71b9f0b495b924f9e3a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103232"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="c3265-103">Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c3265-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="c3265-104">**Riepilogo:** Informazioni su come visualizzare informazioni sui trunk SIP in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3265-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="c3265-105">I trunk SIP vengono utilizzati per connettere Skype for Business Server Voice over IP Phone Network alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="c3265-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="c3265-106">Nella versione precedente del prodotto i trunk vengono utilizzati per instradare le chiamate in uscita da un Mediation Server a un gateway PSTN e ogni gateway è limitato a un singolo trunk.</span><span class="sxs-lookup"><span data-stu-id="c3265-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="c3265-107">Un gateway PSTN e un trunk SIP in questo caso pertanto sono essenzialmente identici.</span><span class="sxs-lookup"><span data-stu-id="c3265-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="c3265-108">Per gli amministratori, questo significa che possono visualizzare le informazioni relative a un trunk SIP semplicemente visualizzando le informazioni relative al gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="c3265-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="c3265-109">In Skype for Business Server, tuttavia, ora è possibile assegnare più trunk a un singolo gateway PSTN. ciò significa che i gateway e i trunk non sono più uguali.</span><span class="sxs-lookup"><span data-stu-id="c3265-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="c3265-110">Questo di conseguenza significa che gli amministratori devono utilizzare il nuovo cmdlet [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) per visualizzare le informazioni relative a un singolo trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="c3265-110">In turn, that means that administrators must use the new [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="c3265-111">Per visualizzare le informazioni per tutti i trunk SIP</span><span class="sxs-lookup"><span data-stu-id="c3265-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="c3265-112">Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="c3265-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="c3265-113">Per visualizzare le informazioni per un trunk SIP specifico</span><span class="sxs-lookup"><span data-stu-id="c3265-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="c3265-114">Questo comando restituisce informazioni solo sul trunk SIP con l'identità (Identity) PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="c3265-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="c3265-115">Visualizzare le informazioni per tutti i trunk SIP assegnati a un pool</span><span class="sxs-lookup"><span data-stu-id="c3265-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="c3265-116">In questo esempio vengono restituite le informazioni su tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="c3265-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```