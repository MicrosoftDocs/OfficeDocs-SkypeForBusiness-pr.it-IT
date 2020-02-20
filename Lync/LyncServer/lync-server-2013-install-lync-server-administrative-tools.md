---
title: 'Lync Server 2013: installare gli strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f7d1b29ce4bad3b5a50c59d0da6911964f9e108
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="856b2-102">Installare gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856b2-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="856b2-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="856b2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="856b2-104">In questo argomento viene descritto come installare gli strumenti di amministrazione necessari per la distribuzione e la gestione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="856b2-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="856b2-105">Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server che esegue Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="856b2-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="856b2-106">Inoltre, è possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate.</span><span class="sxs-lookup"><span data-stu-id="856b2-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="856b2-107">È consigliabile installare gli strumenti di amministrazione in un computer che si trova nello stesso dominio o foresta della distribuzione di Lync Server 2013 che si sta creando, perché in questo modo si verifica che i passaggi di preparazione di Active Directory Domain Services siano già disponibili completata, che consente di utilizzare gli strumenti di amministrazione di quel computer in un secondo momento per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="856b2-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="856b2-108">Prima di installare o utilizzare gli strumenti di amministrazione di Lync Server 2013, verificare che vengano esaminati i requisiti relativi ai diritti dell'infrastruttura, del sistema operativo, del software e di amministratore.</span><span class="sxs-lookup"><span data-stu-id="856b2-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="856b2-109">Per informazioni dettagliate sui requisiti dell'infrastruttura, vedere [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856b2-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="856b2-110">Per informazioni dettagliate sui requisiti software e del sistema operativo per l'installazione degli strumenti di amministrazione di Lync Server 2013, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856b2-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="856b2-111">Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per l'installazione e l'utilizzo degli strumenti, vedere [autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="856b2-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="856b2-112">Se l'organizzazione richiede che Internet Information Services (IIS) e tutti i servizi Web si trovino in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione per i file di Lync Server nella finestra di dialogo del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="856b2-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="856b2-113">Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, anche gli altri file di Lync Server 2013 verranno distribuiti nell'unità.</span><span class="sxs-lookup"><span data-stu-id="856b2-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="856b2-114">Per installare gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856b2-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="856b2-p104">Eseguire l'accesso come amministratore locale (requisito minimo) al computer in cui si desidera installare gli strumenti di amministrazione. Se si è connessi come utente standard al sistema operativo Windows Vista o Windows 7 e il controllo dell'account utente è abilitato, verrà richiesto di specificare nome utente e password di amministratore locale o di un account di dominio equivalente.</span><span class="sxs-lookup"><span data-stu-id="856b2-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="856b2-117">Individuare il supporto di installazione nel computer in uso e quindi fare doppio \\clic\\su\\Setup amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="856b2-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="856b2-118">Se viene chiesto di installare Microsoft Visual C++ 2008 Distributable, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="856b2-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="856b2-119">Nella pagina **percorso di installazione di Microsoft Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="856b2-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="856b2-120">Sostituire il percorso indicato con un altro percorso o un'altra unità se è necessario installare i file in una diversa posizione.</span><span class="sxs-lookup"><span data-stu-id="856b2-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="856b2-121">Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Lync Server 2013 nella finestra di dialogo Imposta.</span><span class="sxs-lookup"><span data-stu-id="856b2-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="856b2-122">Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, anche gli altri file di Lync Server 2013 verranno distribuiti nell'unità.</span><span class="sxs-lookup"><span data-stu-id="856b2-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="856b2-p107">Nella pagina **Contratto di licenza con l'utente finale** leggere le condizioni di licenza, fare clic su **Accetto** e quindi su **OK**. Questo passaggio è obbligatorio per poter continuare.</span><span class="sxs-lookup"><span data-stu-id="856b2-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="856b2-125">Nella pagina **Microsoft Lync Server 2013-Deployment Wizard** fare clic su **installa strumenti di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="856b2-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="856b2-126">Al termine dell'installazione fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="856b2-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="856b2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="856b2-127">See Also</span></span>


[<span data-ttu-id="856b2-128">Aprire gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856b2-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="856b2-129">Strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856b2-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

