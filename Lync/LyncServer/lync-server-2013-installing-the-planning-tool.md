---
title: 'Lync Server 2013: installazione dello strumento di pianificazione'
description: 'Lync Server 2013: installazione dello strumento di pianificazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11836e2c86cb01d6f911670a9eeafef0c31c0af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575062"
---
# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="7b9f7-103">Installazione dello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b9f7-103">Installing the Planning Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b9f7-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="7b9f7-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7b9f7-105">Prima di iniziare la progettazione e la pianificazione dell'infrastruttura Lync Server 2013 utilizzando Microsoft Lync Server 2013, strumento di pianificazione, è necessario innanzitutto installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-105">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="7b9f7-106">Non è necessario distribuire lo strumento di pianificazione su una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-106">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="7b9f7-107">Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'utilizzo dello strumento.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-107">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="7b9f7-108">Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-108">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7b9f7-109">Lo strumento di pianificazione richiede l'installazione da parte di un utente con autorizzazioni e diritti di amministratore nel computer in cui deve essere installato lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-109">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="7b9f7-110">I sistemi operativi supportati per l'installazione e l'esecuzione dello strumento di pianificazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b9f7-110">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="7b9f7-111">Windows 8</span><span class="sxs-lookup"><span data-stu-id="7b9f7-111">Windows 8</span></span>

  - <span data-ttu-id="7b9f7-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7b9f7-112">Windows 8.1</span></span>

  - <span data-ttu-id="7b9f7-113">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="7b9f7-113">Windows Server 2012</span></span>

  - <span data-ttu-id="7b9f7-114">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7b9f7-114">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="7b9f7-115">Windows 7, edizione a 32 bit</span><span class="sxs-lookup"><span data-stu-id="7b9f7-115">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="7b9f7-116">Windows 7, edizione a 64 bit con Windows on Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="7b9f7-116">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="7b9f7-117">Windows Server 2008 R2, con WOW</span><span class="sxs-lookup"><span data-stu-id="7b9f7-117">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="7b9f7-118">Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-118">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="7b9f7-119">Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-119">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="7b9f7-120">Per installare lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="7b9f7-120">To install the Planning Tool</span></span>

1.  <span data-ttu-id="7b9f7-121">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-121">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="7b9f7-122">Se si utilizza Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-122">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="7b9f7-123">Individuare il LyncPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-123">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="7b9f7-124">In Esplora risorse fare doppio clic sul file.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-124">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="7b9f7-125">Nella finestra di comando, digitare il nome del file e quindi premere **invio** per eseguire il file.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-125">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="7b9f7-126">Nella pagina iniziale dell' **installazione guidata dello strumento di pianificazione di Microsoft Lync Server 2013**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-126">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="7b9f7-127">Leggere il **Contratto di Licenza con l'utente finale**, selezionare **Accetto i termini del Contratto di Licenza** se si sceglie di accettare le condizioni per l'utilizzo riportate nel contratto e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-127">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="7b9f7-128">Scegliere dove installare i file dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-128">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="7b9f7-129">Il percorso predefinito è C: \\ Program Files (x86) \\ Microsoft Lync Server 2013 \\ Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-129">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="7b9f7-130">Se si desidera cambiarlo, fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-130">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="7b9f7-131">In **Modifica cartella di destinazione**, individuare o digitare il percorso in cui installare i file, fare clic su **OK** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-131">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="7b9f7-132">Il programma di installazione è ora pronto per installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-132">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="7b9f7-133">Fare clic su **Installa** per avviare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-133">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="7b9f7-134">L'installazione verrà avviata e verrà visualizzato il relativo stato.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-134">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="7b9f7-135">Al termine dell'installazione, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-135">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="7b9f7-136">Lo strumento di pianificazione è pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="7b9f7-136">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7b9f7-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b9f7-137">See Also</span></span>


[<span data-ttu-id="7b9f7-138">Installazione di software facoltativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b9f7-138">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

