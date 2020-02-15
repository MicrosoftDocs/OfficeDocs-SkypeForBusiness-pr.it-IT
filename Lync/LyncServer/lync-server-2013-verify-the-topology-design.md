---
title: 'Lync Server 2013: verificare la progettazione della topologia'
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
ms.openlocfilehash: c6968dfca2072ca9a6c0e5008528e27a14f01447
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="9bc25-102">Verificare la progettazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bc25-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bc25-103">_**Ultimo argomento modificato:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="9bc25-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="9bc25-104">Generatore di topologie verifica automaticamente la topologia.</span><span class="sxs-lookup"><span data-stu-id="9bc25-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="9bc25-105">Gli eventuali errori di topologia vengono identificati come errori di convalida e indicati dall'apposita icona accanto al ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="9bc25-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="9bc25-106">È inoltre importante verificare che la topologia rappresenti correttamente la topologia della propria distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9bc25-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="9bc25-107">Per verificare la topologia prima della pubblicazione</span><span class="sxs-lookup"><span data-stu-id="9bc25-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="9bc25-108">Controllare che tutti gli URL semplici siano configurati in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="9bc25-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="9bc25-109">Verificare che il server basato su SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologie, incluse le eventuali regole del firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="9bc25-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="9bc25-110">Verificare che la condivisione file sia disponibile e siano state definite le autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="9bc25-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="9bc25-111">Verificare che nella topologia siano definiti i ruoli del server corretti conformi ai requisiti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9bc25-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="9bc25-112">Verificare che i server siano presenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9bc25-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="9bc25-113">Ciò avviene automaticamente se i server sono stati aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="9bc25-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="9bc25-114">Dopo aver verificato la topologia e stabilito che non sono presenti errori di convalida, è possibile procedere con la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="9bc25-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="9bc25-115">Gli eventuali errori di convalida rilevati dovranno essere risolti prima di poter pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9bc25-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="9bc25-116">Per informazioni dettagliate sulla pubblicazione della topologia, vedere [publish the topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="9bc25-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

