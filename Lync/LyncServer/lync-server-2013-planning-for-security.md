---
title: 'Lync Server 2013: pianificazione della sicurezza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f99fbd5e511063d7687dbb9e1b9a73fa0cb6ab6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507003"
---
# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="4fe4d-102">Pianificazione della sicurezza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe4d-102">Planning for security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fe4d-103">_**Ultimo argomento modificato:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="4fe4d-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="4fe4d-104">Utilizzare questa sezione di sicurezza per valutare e gestire i rischi per la sicurezza per la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="4fe4d-105">Anche se la distribuzione di Lync Server 2013 è modesto, è probabile che nella rete siano presenti componenti che dispongono di una documentazione relativa alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="4fe4d-106">Pertanto, è improbabile che in questa sezione vengano descritti tutti gli aspetti della sicurezza per tutti i componenti e le aree rilevanti per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="4fe4d-107">Utilizzare questa sezione come punto di partenza per risolvere la sicurezza della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="4fe4d-108">Vengono fornite linee guida generali e procedure consigliate per valutare e gestire i rischi di sicurezza più comuni.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="4fe4d-109">Alla fine di ogni argomento sono elencate altre risorse di prodotti e di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4fe4d-110">La sicurezza è un argomento in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="4fe4d-111">Quando emergono nuove minacce e soluzioni, i documenti obsoleti, le soluzioni, i metodi e le procedure devono essere sostituiti da materiale aggiornato.</span><span class="sxs-lookup"><span data-stu-id="4fe4d-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4fe4d-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="4fe4d-112">In This Section</span></span>

  - [<span data-ttu-id="4fe4d-113">Caratteristiche principali di sicurezza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe4d-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="4fe4d-114">Minacce alla sicurezza comuni nell'elaborazione di giorni moderni</span><span class="sxs-lookup"><span data-stu-id="4fe4d-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="4fe4d-115">Esclusioni di analisi antivirus per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe4d-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="4fe4d-116">Framework di sicurezza per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe4d-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="4fe4d-117">Indirizzare le minacce all'infrastruttura di base per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe4d-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="4fe4d-118">Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe4d-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

