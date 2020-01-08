---
title: 'Lync Server 2013: aprire gli strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="67b81-102">Aprire gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67b81-102">Open Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67b81-103">_**Argomento Ultima modifica:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="67b81-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="67b81-104">È possibile usare le procedure descritte in questo argomento per aprire gli strumenti di amministrazione per distribuire, configurare o risolvere i problemi della topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67b81-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="67b81-105">Distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="67b81-105">Deployment Wizard</span></span>

  - <span data-ttu-id="67b81-106">Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="67b81-106">Topology Builder</span></span>

  - <span data-ttu-id="67b81-107">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="67b81-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="67b81-108">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="67b81-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="67b81-109">Distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="67b81-109">Deployment Wizard</span></span>

<span data-ttu-id="67b81-110">Usare la procedura seguente per avviare la distribuzione guidata localmente per aggiungere o rimuovere file di componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67b81-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="67b81-111">Per avviare la distribuzione guidata di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67b81-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="67b81-112">Accedere al computer in cui è installata la distribuzione guidata di Lync Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="67b81-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="67b81-113">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **distribuzione guidata Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="67b81-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="67b81-114">Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="67b81-114">Topology Builder</span></span>

<span data-ttu-id="67b81-115">Usare la procedura seguente per aprire il generatore di topologia per definire i server che si desidera distribuire nella topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67b81-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="67b81-116">Per aprire il generatore di topologia di Lync Server 2013 per progettare la topologia</span><span class="sxs-lookup"><span data-stu-id="67b81-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="67b81-117">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="67b81-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67b81-118">È possibile definire una topologia usando un account che è un membro del gruppo utenti locali, ma per leggere, pubblicare o abilitare una topologia, necessaria per installare Lync Server 2013 in un server, è necessario usare un account membro del gruppo Domain Admins e RTCUniv gruppo ersalServerAdmins, con autorizzazioni controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione file che si vuole usare per l'archiviazione dei file archiviati in modo che generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto (DACL), o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="67b81-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="67b81-119">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="67b81-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="67b81-120">Pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67b81-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="67b81-121">Usare una delle procedure seguenti per aprire il pannello di controllo di Lync Server 2013 per gestire la configurazione di server, utenti, client e dispositivi nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="67b81-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67b81-122">È possibile usare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67b81-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="67b81-123">È possibile usare altri ruoli per accedere al pannello di controllo di Lync Server 2013 per eseguire attività di amministrazione specifiche, in base all'attività che occorre eseguire.</span><span class="sxs-lookup"><span data-stu-id="67b81-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="67b81-124">Ad esempio, puoi usare CSArchivingAdministrator per amministrare l'archiviazione nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67b81-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="67b81-125">Per informazioni dettagliate sui ruoli, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="67b81-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="67b81-126">Per informazioni dettagliate sui ruoli che è possibile usare per eseguire un'attività specifica, vedere la documentazione relativa all'attività.</span><span class="sxs-lookup"><span data-stu-id="67b81-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="67b81-127">Per aprire il pannello di controllo di Lync Server 2013 da qualsiasi computer all'interno del firewall dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="67b81-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="67b81-128">Da un account utente assegnato al ruolo CsAdministrator o da un altro ruolo che disponga dei diritti utente appropriati e delle autorizzazioni per l'attività da eseguire, accedere a qualsiasi computer della distribuzione interna con una risoluzione minima dello schermo di 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="67b81-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="67b81-129">Se è stato configurato un semplice URL (Uniform Resource Locator) di amministrazione, è possibile accedere al pannello di controllo di Lync Server 2013 da un browser Internet in uso in qualsiasi computer all'interno del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="67b81-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="67b81-130">Per informazioni dettagliate sulla configurazione dell'URL semplice di amministrazione, vedere <A href="lync-server-2013-planning-for-simple-urls.md">pianificazione di URL semplici in Lync server 2013</A> nella documentazione di pianificazione e <A href="lync-server-2013-edit-or-configure-simple-urls.md">modifica o configurazione di URL semplici in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="67b81-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="67b81-131">Aprire una finestra del browser e quindi immettere l'URL di amministratore configurato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="67b81-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="67b81-132">Per aprire il pannello di controllo di Lync Server 2013 in un computer che gestisce Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67b81-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="67b81-133">Da un account utente che fa parte del ruolo CsAdministrator o di un altro ruolo che disponga dei diritti utente e delle autorizzazioni appropriate per l'attività, accedere a un computer in cui è installato Lync Server 2013 o, almeno, Lync Server 2013 amministrazione strumenti Ive.</span><span class="sxs-lookup"><span data-stu-id="67b81-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="67b81-134">Per configurare le impostazioni, il computer deve avere una risoluzione minima dello schermo di 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="67b81-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="67b81-135">Avviare il pannello di controllo di Lync Server 2013: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**, scegliere **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server 2013 pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="67b81-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="67b81-136">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="67b81-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="67b81-137">Usare la procedura seguente per aprire Lync Server 2013 Management Shell per amministrare server, utenti, client e dispositivi nell'ambiente tramite la riga di comando.</span><span class="sxs-lookup"><span data-stu-id="67b81-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67b81-138">Puoi usare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività in Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="67b81-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="67b81-139">È possibile accedere con altri ruoli per eseguire attività di amministrazione specifiche, a seconda dell'attività che occorre eseguire.</span><span class="sxs-lookup"><span data-stu-id="67b81-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="67b81-140">Ad esempio, puoi usare CSArchivingAdministrator per eseguire i cmdlet correlati all'amministrazione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="67b81-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="67b81-141">Per informazioni dettagliate sui ruoli, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="67b81-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="67b81-142">Per informazioni dettagliate sui ruoli che è possibile usare per eseguire un cmdlet specifico, vedere la documentazione relativa al cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67b81-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="67b81-143">Puoi anche eseguire determinati cmdlet usando un account utente nei gruppi RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, a seconda del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67b81-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="67b81-144">Per aprire Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="67b81-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="67b81-145">Se si apre una finestra di Windows PowerShell anziché Lync Server 2013 Management Shell, per impostazione predefinita non è possibile eseguire i cmdlet di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67b81-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="67b81-146">Per eseguire i cmdlet di Lync Server 2013 da Windows PowerShell, digitare quanto segue al prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67b81-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="67b81-147">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="67b81-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67b81-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67b81-148">See Also</span></span>


[<span data-ttu-id="67b81-149">Installare gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67b81-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="67b81-150">Strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67b81-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

