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
ms.openlocfilehash: 02028b3ed63fe8f5cd40fd118bd36c73af9d15cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="c5a32-102">Pianificazione della sicurezza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a32-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5a32-103">_**Argomento Ultima modifica:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="c5a32-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="c5a32-104">Usare questa sezione di sicurezza per valutare e gestire i rischi di sicurezza per la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5a32-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="c5a32-105">Anche se la distribuzione di Lync Server 2013 è modesta, è probabile che nella rete siano presenti componenti con una propria documentazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c5a32-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="c5a32-106">Di conseguenza, è improbabile che questa sezione copra tutti gli aspetti della sicurezza per tutti i componenti e le aree pertinenti alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c5a32-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="c5a32-107">Usare questa sezione come punto di partenza per affrontare la sicurezza della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5a32-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="c5a32-108">Fornisce linee guida e procedure consigliate generali per la valutazione e la gestione dei rischi di sicurezza più comuni.</span><span class="sxs-lookup"><span data-stu-id="c5a32-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="c5a32-109">Alla fine di ogni argomento sono elencate altre risorse di prodotto e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c5a32-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c5a32-110">La sicurezza è un argomento in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="c5a32-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="c5a32-111">Man mano che sorgono nuove minacce e soluzioni, i documenti, le soluzioni, i metodi e le procedure obsoleti devono essere sostituiti da materiale aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c5a32-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c5a32-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c5a32-112">In This Section</span></span>

  - [<span data-ttu-id="c5a32-113">Caratteristiche di sicurezza chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a32-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="c5a32-114">Minacce comuni per la sicurezza nell'informatica moderna</span><span class="sxs-lookup"><span data-stu-id="c5a32-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="c5a32-115">Esclusioni dall'analisi antivirus per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a32-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="c5a32-116">Framework di sicurezza per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a32-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="c5a32-117">Affrontare le minacce per l'infrastruttura di base per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a32-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="c5a32-118">Distribuzione di una porta e di un alias non standard di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a32-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

