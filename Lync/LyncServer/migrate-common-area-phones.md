---
title: Migrare i telefoni delle aree comuni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138068c73264ded3483d8d9f0902d403833a306d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="5d455-102">Migrare i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="5d455-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d455-103">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="5d455-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="5d455-104">I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione.</span><span class="sxs-lookup"><span data-stu-id="5d455-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="5d455-105">Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire la funzionalità UC di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d455-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="5d455-106">Dopo aver eseguito la migrazione di una distribuzione di Lync Server 2010 a Lync Server 2013, è necessario eseguire la migrazione anche degli oggetti contatto associati al telefono delle aree comuni legacy.</span><span class="sxs-lookup"><span data-stu-id="5d455-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="5d455-107">Utilizzando Lync Server Management Shell, è necessario recuperare tutti gli oggetti contatto associati ai telefoni delle aree comuni di Lync Server 2010 e quindi spostare tali oggetti nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d455-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="5d455-108">**Eseguire la migrazione dei telefoni di aree comuni**</span><span class="sxs-lookup"><span data-stu-id="5d455-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="5d455-109">Dal front end server Lync Server 2013 aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5d455-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="5d455-110">Dalla riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5d455-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="5d455-111">Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013, dal tipo Lync Server Management Shell, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d455-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="5d455-112">Verificare che tutti gli oggetti contatto siano ora associati al pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d455-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

