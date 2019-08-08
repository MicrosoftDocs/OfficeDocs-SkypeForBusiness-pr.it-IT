---
title: Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Riepilogo: Scopri come visualizzare le informazioni sui trunk SIP in Skype for Business Server.'
ms.openlocfilehash: 3d8ad70428926c26445c6556544a5a363de12f5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240212"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="51c72-103">Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="51c72-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="51c72-104">**Riepilogo:** Scopri come visualizzare le informazioni sui trunk SIP in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="51c72-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="51c72-105">I trunk SIP vengono usati per connettere la rete telefonica Voice over IP di Skype for Business Server con la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="51c72-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="51c72-106">Nella versione precedente del prodotto Trunks veniva usato per instradare le chiamate in uscita da un Mediation Server a un gateway PSTN e ogni gateway era limitato a un singolo trunk.</span><span class="sxs-lookup"><span data-stu-id="51c72-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="51c72-107">Di conseguenza, un gateway PSTN e un trunk SIP erano essenzialmente identici.</span><span class="sxs-lookup"><span data-stu-id="51c72-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="51c72-108">Per gli amministratori, ciò significava che potevano visualizzare informazioni su un singolo trunk SIP semplicemente visualizzando le informazioni sul gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="51c72-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="51c72-109">In Skype for Business Server, tuttavia, è ora possibile assegnare più trunk a un singolo gateway PSTN. Ciò significa che i gateway e i trunk non sono più uno e lo stesso.</span><span class="sxs-lookup"><span data-stu-id="51c72-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="51c72-110">A sua volta, ciò significa che gli amministratori devono usare il nuovo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) per visualizzare informazioni su un singolo trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="51c72-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="51c72-111">Per visualizzare le informazioni per tutti i trunk SIP</span><span class="sxs-lookup"><span data-stu-id="51c72-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="51c72-112">Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="51c72-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="51c72-113">Per visualizzare le informazioni relative a un trunk SIP specifico</span><span class="sxs-lookup"><span data-stu-id="51c72-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="51c72-114">Questo comando restituisce solo le informazioni per il trunk SIP con Identity PstnGateway: 192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="51c72-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="51c72-115">Visualizzare informazioni per tutti i trunk SIP assegnati a un pool</span><span class="sxs-lookup"><span data-stu-id="51c72-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="51c72-116">In questo esempio vengono restituite le informazioni per tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="51c72-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
