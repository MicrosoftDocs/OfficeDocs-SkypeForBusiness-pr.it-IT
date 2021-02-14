---
title: 'Supporto della virtualizzazione per Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: informazioni sul supporto della virtualizzazione per Skype for Business Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509033"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="3955a-103">Supporto della virtualizzazione per Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3955a-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="3955a-104">Skype for Business Server 2019 è supportato nella virtualizzazione.</span><span class="sxs-lookup"><span data-stu-id="3955a-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="3955a-105">Anche se la virtualizzazione è supportata, esistono alcuni punti chiave da ricordare:</span><span class="sxs-lookup"><span data-stu-id="3955a-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="3955a-106">Mantenere un rapporto di 1:1 tra CPU virtuale e CPU fisica.</span><span class="sxs-lookup"><span data-stu-id="3955a-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="3955a-107">Non spostare un server guest mentre è in funzione.</span><span class="sxs-lookup"><span data-stu-id="3955a-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="3955a-108">La migrazione di un sistema in tempo reale e la portabilità di una macchina virtuale non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="3955a-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="3955a-109">Disabilitare l'hyperthreading in tutti gli host.</span><span class="sxs-lookup"><span data-stu-id="3955a-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="3955a-110">Non configurare la memoria dinamica nei server host.</span><span class="sxs-lookup"><span data-stu-id="3955a-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="3955a-111">Utilizzare dischi fissi o pass-through anziché dischi dinamici.</span><span class="sxs-lookup"><span data-stu-id="3955a-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="3955a-112">Consentire un sovraccarico del 6-10% per gli hypervisor oltre a quello richiesto dal guest virtuale.</span><span class="sxs-lookup"><span data-stu-id="3955a-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="3955a-113">Hypervisor supportati</span><span class="sxs-lookup"><span data-stu-id="3955a-113">Supported hypervisors</span></span>

<span data-ttu-id="3955a-114">SfB Server 2019 è supportato in Windows Server 2016 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3955a-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="3955a-115">Per gli hypervisor di terze parti, è necessario un hypervisor che abbia superato il test SVVP (Server Virtualization Validation Program) per il sistema operativo pertinente.</span><span class="sxs-lookup"><span data-stu-id="3955a-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="3955a-116">Vedi le [versioni di Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.</span><span class="sxs-lookup"><span data-stu-id="3955a-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="3955a-117">Vedi le [versioni di Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.</span><span class="sxs-lookup"><span data-stu-id="3955a-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="3955a-118">Strumento stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="3955a-118">Stress and performance tool</span></span>

<span data-ttu-id="3955a-119">Lo strumento Skype for Business Server 2019 Stress and Performance include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3955a-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="3955a-120">Lo strumento Skype for Business Server 2019 Stress and Performance consente di:</span><span class="sxs-lookup"><span data-stu-id="3955a-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="3955a-121">Semplificare la pianificazione dell'hardware per Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3955a-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="3955a-122">Fornire maggiori conoscenze e procedure consigliate per l'ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="3955a-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="3955a-123">Misurare le prestazioni delle distribuzioni di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3955a-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="3955a-124">Puoi scaricare lo strumento da [qui.](https://www.microsoft.com/download/details.aspx?id=101447)</span><span class="sxs-lookup"><span data-stu-id="3955a-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
