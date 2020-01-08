---
title: 'Lync Server 2013: ripristino di un server membro di Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="dd284-102">Ripristino di un server membro di Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd284-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd284-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="dd284-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="dd284-104">Se un server che esegue uno dei ruoli del server seguenti non riesce, seguire la procedura descritta in questo argomento per ripristinare il server.</span><span class="sxs-lookup"><span data-stu-id="dd284-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="dd284-105">Se più server non riescono in modo indipendente, seguire la procedura per ogni server.</span><span class="sxs-lookup"><span data-stu-id="dd284-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="dd284-106">Server front-end</span><span class="sxs-lookup"><span data-stu-id="dd284-106">Front End Server</span></span>

  - <span data-ttu-id="dd284-107">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="dd284-107">Mediation Server</span></span>

  - <span data-ttu-id="dd284-108">Director</span><span class="sxs-lookup"><span data-stu-id="dd284-108">Director</span></span>

  - <span data-ttu-id="dd284-109">Server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="dd284-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="dd284-110">Edge Server</span><span class="sxs-lookup"><span data-stu-id="dd284-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="dd284-111">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="dd284-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="dd284-112">È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="dd284-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="dd284-113">Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="dd284-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="dd284-114">Per ripristinare un server membro</span><span class="sxs-lookup"><span data-stu-id="dd284-114">To restore a member server</span></span>

1.  <span data-ttu-id="dd284-115">Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del server non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="dd284-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd284-116">Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd284-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="dd284-117">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="dd284-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="dd284-118">Passare alla cartella di installazione o al supporto di Lync Server e avviare la distribuzione guidata di Lync Server \\in\\Setup\\amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="dd284-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="dd284-119">Seguire la distribuzione guidata per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd284-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="dd284-120">Eseguire il **passaggio 1: installare l'archivio configurazione locale** per installare i file di configurazione locali.</span><span class="sxs-lookup"><span data-stu-id="dd284-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="dd284-121">Eseguire il **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare il ruolo del server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd284-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="dd284-122">Eseguire il **passaggio 3: richiedere, installare o assegnare certificati** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="dd284-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="dd284-123">Eseguire il **passaggio 4: avviare i servizi** per avviare i servizi nel server.</span><span class="sxs-lookup"><span data-stu-id="dd284-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="dd284-124">Per informazioni dettagliate sull'eseguire la distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="dd284-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

