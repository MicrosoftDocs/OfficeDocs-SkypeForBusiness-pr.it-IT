---
title: Aggiornare o aggiornare un server back-end o un server Standard Edition
description: Aggiornare o aggiornare un server back-end o un server Standard Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c529546bdcf88ada6fd82399d3b65b46b4312db0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580432"
---
# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f6d63-103">Aggiornare o aggiornare un server back-end o un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6d63-103">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6d63-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f6d63-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f6d63-105">In questo argomento viene descritto come installare un aggiornamento in un server di back-end Enterprise Edition o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f6d63-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="f6d63-106">Se un server back-end è inverso verso il basso per almeno 30 minuti mentre lo si sta aggiornando, gli utenti possono accedere alla modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="f6d63-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="f6d63-107">Al termine dell'aggiornamento e i server back-end sono di nuovo connessi con i Front End Server nel pool, gli utenti vengono restituiti alla funzionalità completa.</span><span class="sxs-lookup"><span data-stu-id="f6d63-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="f6d63-108">Se l'aggiornamento richiede meno di 30 minuti, gli utenti non saranno coinvolti.</span><span class="sxs-lookup"><span data-stu-id="f6d63-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="f6d63-109">Per aggiornare un server back-end o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f6d63-109">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="f6d63-110">Eseguire l'accesso al server da aggiornare come membro del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f6d63-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f6d63-111">Scaricare l'aggiornamento ed estrarlo nel disco rigido locale.</span><span class="sxs-lookup"><span data-stu-id="f6d63-111">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="f6d63-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f6d63-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="f6d63-113">Arrestare i servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6d63-113">Stop Lync Server services.</span></span> <span data-ttu-id="f6d63-114">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f6d63-114">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="f6d63-115">Arrestare il servizio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="f6d63-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="f6d63-116">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="f6d63-116">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="f6d63-117">Chiudere tutte le finestre di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6d63-117">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="f6d63-118">Installare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f6d63-118">Install the update.</span></span>

8.  <span data-ttu-id="f6d63-119">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f6d63-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="f6d63-120">Arrestare di nuovo i servizi di Lync Server per rilevare la Global Assembly Cache (GAC) – d Assemblies.</span><span class="sxs-lookup"><span data-stu-id="f6d63-120">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="f6d63-121">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="f6d63-121">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="f6d63-122">Riavviare il servizio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="f6d63-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="f6d63-123">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="f6d63-123">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="f6d63-124">Applicare le modifiche apportate da LyncServerUpdateInstaller.exe ai database di SQL Server eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6d63-124">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="f6d63-125">Se si tratta di un server back-end Enterprise Edition e non sono presenti database collocati nel server, ad esempio i database di archiviazione o di monitoraggio, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="f6d63-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="f6d63-126">Se si tratta di un server back-end Enterprise Edition e sono presenti database collocati nel server, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="f6d63-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="f6d63-127">Se si tratta di un server Standard Edition, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="f6d63-127">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

