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
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565955"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="9e3e2-103">Supporto per la virtualizzazione di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9e3e2-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="9e3e2-104">Skype for Business Server 2019 è supportato sulla virtualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="9e3e2-105">Anche se la virtualizzazione è supportata, esistono alcuni punti chiave da ricordare:</span><span class="sxs-lookup"><span data-stu-id="9e3e2-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="9e3e2-106">Mantenere un rapporto di 1:1 tra CPU virtuale e CPU fisica.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="9e3e2-107">Non spostare un server Guest mentre è in funzione.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="9e3e2-108">La migrazione di un sistema Live e la portabilità di una macchina virtuale non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="9e3e2-109">Disabilitare la tecnologia Hyper-Threading su tutti gli host.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="9e3e2-110">Non configurare la memoria dinamica nei server host.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="9e3e2-111">Utilizzare dischi fissi o pass-through anziché dischi dinamici.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="9e3e2-112">Consenti il sovraccarico del 6-10% per gli hypervisor oltre ciò che richiede l'ospite virtuale.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="9e3e2-113">Hypervisor supportati</span><span class="sxs-lookup"><span data-stu-id="9e3e2-113">Supported hypervisors</span></span>

<span data-ttu-id="9e3e2-114">Questo server 2019 è supportato in Windows Server 2016 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="9e3e2-115">Per le hypervisor di terze parti, è necessario un hypervisor che ha superato il testing del programma SVVP (Server Virtualization Validation Program) per il sistema operativo pertinente.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="9e3e2-116">Vedere le [versioni di Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="9e3e2-117">Vedere le [versioni di Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.</span><span class="sxs-lookup"><span data-stu-id="9e3e2-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
