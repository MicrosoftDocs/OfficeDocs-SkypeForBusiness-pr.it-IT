---
title: 'Supporto per la virtualizzazione di Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: informazioni sul supporto per la virtualizzazione di Skype for Business Server 2019.'
ms.openlocfilehash: b4524b1284a85e7ab372b415d45c2005f8212887
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755810"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="178e4-103">Supporto per la virtualizzazione di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="178e4-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="178e4-104">Skype for Business Server 2019 è supportato sulla virtualizzazione.</span><span class="sxs-lookup"><span data-stu-id="178e4-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="178e4-105">Anche se la virtualizzazione è supportata, esistono alcuni punti chiave da ricordare:</span><span class="sxs-lookup"><span data-stu-id="178e4-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="178e4-106">Mantenere un rapporto di 1:1 tra CPU virtuale e CPU fisica.</span><span class="sxs-lookup"><span data-stu-id="178e4-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="178e4-107">Non spostare un server Guest mentre è in funzione.</span><span class="sxs-lookup"><span data-stu-id="178e4-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="178e4-108">La migrazione di un sistema Live e la portabilità di una macchina virtuale non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="178e4-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="178e4-109">Disabilitare la tecnologia Hyper-Threading su tutti gli host.</span><span class="sxs-lookup"><span data-stu-id="178e4-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="178e4-110">Non configurare la memoria dinamica nei server host.</span><span class="sxs-lookup"><span data-stu-id="178e4-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="178e4-111">Utilizzare dischi fissi o pass-through anziché dischi dinamici.</span><span class="sxs-lookup"><span data-stu-id="178e4-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="178e4-112">Consenti il sovraccarico del 6-10% per gli hypervisor oltre ciò che richiede l'ospite virtuale.</span><span class="sxs-lookup"><span data-stu-id="178e4-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="178e4-113">Hypervisor supportati</span><span class="sxs-lookup"><span data-stu-id="178e4-113">Supported hypervisors</span></span>

<span data-ttu-id="178e4-114">Questo server 2019 è supportato in Windows Server 2016 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="178e4-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="178e4-115">Per le hypervisor di terze parti, è necessario un hypervisor che ha superato il testing del programma SVVP (Server Virtualization Validation Program) per il sistema operativo pertinente.</span><span class="sxs-lookup"><span data-stu-id="178e4-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="178e4-116">Vedere le [versioni di Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.</span><span class="sxs-lookup"><span data-stu-id="178e4-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="178e4-117">Vedere le [versioni di Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.</span><span class="sxs-lookup"><span data-stu-id="178e4-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="178e4-118">Strumento di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="178e4-118">Stress and performance tool</span></span>

<span data-ttu-id="178e4-119">Lo strumento per lo stress e le prestazioni di Skype for Business Server 2019 include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="178e4-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="178e4-120">Lo strumento di supporto per la sollecitazione e le prestazioni di Skype for Business Server 2019 consente di:</span><span class="sxs-lookup"><span data-stu-id="178e4-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="178e4-121">Semplificare la pianificazione dell'hardware per Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="178e4-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="178e4-122">Offrire maggiori informazioni e procedure consigliate per l'ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="178e4-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="178e4-123">Misurare le prestazioni delle distribuzioni di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="178e4-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="178e4-124">È possibile scaricare lo strumento da [qui](https://www.microsoft.com/download/details.aspx?id=101447).</span><span class="sxs-lookup"><span data-stu-id="178e4-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
