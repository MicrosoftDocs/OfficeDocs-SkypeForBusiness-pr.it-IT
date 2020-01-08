---
title: 'Lync Server 2013: Verificare la progettazione della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe262033699e46c77897652cf48969d46b7817f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="c8061-102">Verificare la progettazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8061-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8061-103">_**Argomento Ultima modifica:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="c8061-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="c8061-104">Generatore di topologia verifica automaticamente la topologia.</span><span class="sxs-lookup"><span data-stu-id="c8061-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="c8061-105">Qualsiasi errore di topologia viene identificato come errore di convalida, indicato dall'icona di errore di convalida accanto al ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="c8061-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="c8061-106">È importante verificare anche che la topologia rappresenti correttamente la topologia della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8061-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="c8061-107">Per verificare la topologia prima della pubblicazione</span><span class="sxs-lookup"><span data-stu-id="c8061-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="c8061-108">Verificare che tutti gli URL semplici siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="c8061-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="c8061-109">Verificare che il server basato su SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologia, incluse le regole del firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="c8061-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="c8061-110">Verificare che la condivisione file sia disponibile e che siano definite le autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="c8061-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="c8061-111">Verificare che i ruoli del server corretti che soddisfano i requisiti di distribuzione siano definiti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="c8061-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="c8061-112">Verificare che i server siano presenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c8061-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="c8061-113">Ciò avverrà automaticamente se i server sono stati aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="c8061-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="c8061-114">Dopo aver verificato la topologia e non sono presenti errori di convalida, è necessario essere pronti per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="c8061-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="c8061-115">Se sono presenti errori di convalida, è necessario correggerli prima di poter pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="c8061-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="c8061-116">Per informazioni dettagliate sulla pubblicazione della topologia, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="c8061-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

