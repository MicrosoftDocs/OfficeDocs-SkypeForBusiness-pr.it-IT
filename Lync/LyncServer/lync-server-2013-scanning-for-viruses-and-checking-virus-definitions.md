---
title: 'Lync Server 2013: ricerca di virus e controllo delle definizioni di virus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 357c2c2053aca6b7b18a966756ece2768a8e71c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="1e84a-102">Ricerca di virus e controllo delle definizioni di virus in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e84a-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e84a-103">_**Argomento Ultima modifica:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="1e84a-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="1e84a-104">Ti consigliamo vivamente di installare un prodotto antivirus a livello di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="1e84a-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="1e84a-105">La messaggistica istantanea è una fonte ben nota per diffondere rapidamente sia il virus che il software maligno in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1e84a-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="1e84a-106">Microsoft Forefront® Security per Lync Server offre la ricerca di più motori con virus, software malevolo, protezione dei filtri di file e parole chiave e integrazione perfetta con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="1e84a-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="1e84a-107">Oltre a Forefront Security per Lync Server, consigliamo vivamente di installare una soluzione antivirus a livello di file per proteggere il file System del server.</span><span class="sxs-lookup"><span data-stu-id="1e84a-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="1e84a-108">È molto importante mantenere aggiornati i motori dello scanner e le definizioni di virus.</span><span class="sxs-lookup"><span data-stu-id="1e84a-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="1e84a-109">La configurazione e il monitoraggio dello stato degli aggiornamenti garantisce che le informazioni di analisi più aggiornate vengano usate per proteggere sia Office Communications Server che il file System.</span><span class="sxs-lookup"><span data-stu-id="1e84a-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e84a-110">Quando si usa un software antivirus a livello di file di terze parti su un server che esegue Lync Server 2013 e Forefront Security per Lync Server, verificare che le cartelle in cui sono installati Forefront Security per Lync Server e Lync Server non vengano digitalizzate, per evitare il loro danneggiamento.</span><span class="sxs-lookup"><span data-stu-id="1e84a-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="1e84a-111">Per l'elenco completo delle esclusioni, vedere <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span><span class="sxs-lookup"><span data-stu-id="1e84a-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

