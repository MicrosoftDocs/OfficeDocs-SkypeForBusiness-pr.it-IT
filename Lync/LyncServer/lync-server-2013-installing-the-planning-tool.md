---
title: 'Lync Server 2013: Installazione dello strumento di pianificazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e528062d5fd04e1a11df934cbc01b2dc8c92aa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="14070-102">Installazione dello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14070-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14070-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="14070-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="14070-104">Prima di iniziare a progettare e pianificare l'infrastruttura di Lync Server 2013 utilizzando Microsoft Lync Server 2013, strumento di pianificazione, è necessario prima di tutto installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="14070-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="14070-105">Lo strumento di pianificazione non deve essere distribuito in una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14070-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="14070-106">Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'uso dello strumento.</span><span class="sxs-lookup"><span data-stu-id="14070-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="14070-107">Alcune delle informazioni contenute nel file Leggimi vengono duplicate qui per chiarezza.</span><span class="sxs-lookup"><span data-stu-id="14070-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14070-108">Lo strumento di pianificazione richiede l'installazione da parte di un utente con diritti e autorizzazioni di amministratore nel computer in cui deve essere installato lo strumento.</span><span class="sxs-lookup"><span data-stu-id="14070-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="14070-109">I sistemi operativi supportati per l'installazione e il funzionamento dello strumento di pianificazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="14070-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="14070-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="14070-110">Windows 8</span></span>

  - <span data-ttu-id="14070-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="14070-111">Windows 8.1</span></span>

  - <span data-ttu-id="14070-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="14070-112">Windows Server 2012</span></span>

  - <span data-ttu-id="14070-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="14070-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="14070-114">Windows 7, 32 bit Edition</span><span class="sxs-lookup"><span data-stu-id="14070-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="14070-115">Windows 7, 64 bit Edition con Windows su Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="14070-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="14070-116">Windows Server 2008 R2 con WOW</span><span class="sxs-lookup"><span data-stu-id="14070-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="14070-117">Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="14070-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="14070-118">Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="14070-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="14070-119">Per installare lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="14070-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="14070-120">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="14070-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="14070-121">Usando Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="14070-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="14070-122">Individuare il file LyncPlanningTool. msi.</span><span class="sxs-lookup"><span data-stu-id="14070-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="14070-123">In Esplora risorse fare doppio clic sul file.</span><span class="sxs-lookup"><span data-stu-id="14070-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="14070-124">Nella finestra di comando digitare il nome del file e quindi premere **invio** per eseguire il file.</span><span class="sxs-lookup"><span data-stu-id="14070-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="14070-125">Nella pagina di benvenuto di **Microsoft Lync Server 2013, configurazione guidata strumento di pianificazione**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="14070-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="14070-126">Esaminare il **contratto di licenza con l'utente finale**, selezionare **Accetto i termini del contratto di licenza** se si sceglie di accettare le condizioni per l'uso nel contratto di licenza e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="14070-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="14070-127">Scegliere la posizione in cui installare i file dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="14070-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="14070-128">Il percorso predefinito è C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="14070-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="14070-129">Se si vuole modificare il percorso di installazione, fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="14070-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="14070-130">In **modifica cartella di destinazione**selezionare o digitare la posizione in cui installare i file, fare clic su **OK**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="14070-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="14070-131">Il programma di installazione è ora pronto per l'installazione dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="14070-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="14070-132">Fare clic su **Installa** per avviare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="14070-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="14070-133">L'installazione verrà avviata e verrà visualizzato lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="14070-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="14070-134">Dopo aver completato l'installazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="14070-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="14070-135">Lo strumento di pianificazione è pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="14070-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14070-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14070-136">See Also</span></span>


[<span data-ttu-id="14070-137">Installazione di software facoltativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14070-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

