---
title: 'Lync Server 2013: verificare la progettazione della topologia'
description: 'Lync Server 2013: verificare la progettazione della topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560192"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="8d292-103">Verificare la progettazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d292-103">Verify the topology design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d292-104">_**Ultimo argomento modificato:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="8d292-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="8d292-105">Generatore di topologie verifica automaticamente la topologia.</span><span class="sxs-lookup"><span data-stu-id="8d292-105">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="8d292-106">Gli eventuali errori di topologia vengono identificati come errori di convalida e indicati dall'apposita icona accanto al ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="8d292-106">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="8d292-107">È inoltre importante verificare che la topologia rappresenti correttamente la topologia della propria distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8d292-107">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="8d292-108">Per verificare la topologia prima della pubblicazione</span><span class="sxs-lookup"><span data-stu-id="8d292-108">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="8d292-109">Controllare che tutti gli URL semplici siano configurati in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="8d292-109">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="8d292-110">Verificare che il server basato su SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologie, incluse le eventuali regole del firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="8d292-110">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="8d292-111">Verificare che la condivisione file sia disponibile e siano state definite le autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="8d292-111">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="8d292-112">Verificare che nella topologia siano definiti i ruoli del server corretti conformi ai requisiti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8d292-112">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="8d292-113">Verificare che i server siano presenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8d292-113">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="8d292-114">Ciò avviene automaticamente se i server sono stati aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="8d292-114">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="8d292-115">Dopo aver verificato la topologia e stabilito che non sono presenti errori di convalida, è possibile procedere con la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="8d292-115">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="8d292-116">Gli eventuali errori di convalida rilevati dovranno essere risolti prima di poter pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8d292-116">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="8d292-117">Per informazioni dettagliate sulla pubblicazione della topologia, vedere [publish the topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="8d292-117">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

