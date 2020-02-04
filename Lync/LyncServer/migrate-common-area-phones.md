---
title: Eseguire la migrazione dei telefoni di aree comuni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="66277-102">Eseguire la migrazione dei telefoni di aree comuni</span><span class="sxs-lookup"><span data-stu-id="66277-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66277-103">_**Argomento Ultima modifica:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="66277-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="66277-104">I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica.</span><span class="sxs-lookup"><span data-stu-id="66277-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="66277-105">I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66277-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="66277-106">Dopo la migrazione di una distribuzione di Lync Server 2010 a Lync Server 2013, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy.</span><span class="sxs-lookup"><span data-stu-id="66277-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="66277-107">Usando Lync Server Management Shell si recupereranno prima tutti gli oggetti contatto associati ai telefoni delle aree comuni di Lync Server 2010 e quindi li sposteremo nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66277-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="66277-108">**Eseguire la migrazione dei telefoni di aree comuni**</span><span class="sxs-lookup"><span data-stu-id="66277-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="66277-109">Dal server front-end di Lync Server 2013 aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="66277-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="66277-110">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="66277-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="66277-111">Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013, in Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="66277-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="66277-112">Verificare che tutti gli oggetti contatto siano ora associati al pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66277-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

