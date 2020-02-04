---
title: 'Lync Server 2013: Installare gli strumenti di amministrazione di Lync Server'
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
ms.openlocfilehash: 5ebdcf355618c4257ceaeced5f5e4032ede40cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="d8863-102">Installare gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8863-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8863-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d8863-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d8863-104">Questo argomento descrive come installare gli strumenti di amministrazione che è necessario usare per distribuire e gestire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8863-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="d8863-105">Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server che esegue Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8863-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="d8863-106">È inoltre possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate.</span><span class="sxs-lookup"><span data-stu-id="d8863-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="d8863-107">È consigliabile installare gli strumenti di amministrazione in un computer che si trova nello stesso dominio o foresta della distribuzione di Lync Server 2013 in corso, in modo da verificare che la procedura di preparazione dei servizi di dominio Active Directory sia già presente completa, che consente di usare gli strumenti di amministrazione nel computer in un secondo momento per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d8863-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="d8863-108">Verificare che i requisiti per l'infrastruttura, il sistema operativo, il software e i diritti di amministratore vengano riesaminati prima di installare o utilizzare gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8863-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="d8863-109">Per informazioni dettagliate sui requisiti dell'infrastruttura, vedere [requisiti dell'infrastruttura per gli strumenti amministrativi in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8863-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="d8863-110">Per informazioni dettagliate sui requisiti del sistema operativo e del software per installare gli strumenti di amministrazione di Lync Server 2013, vedere [supporto dei sistemi operativi per server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md)e [supporto e requisiti aggiuntivi del server in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8863-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="d8863-111">Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per installare e usare gli strumenti, vedere [diritti di amministratore e autorizzazioni necessarie per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="d8863-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8863-112">Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa da un'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Lync Server nella finestra di dialogo Imposta.</span><span class="sxs-lookup"><span data-stu-id="d8863-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="d8863-113">Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Lync Server 2013 verrà distribuito nell'unità.</span><span class="sxs-lookup"><span data-stu-id="d8863-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="d8863-114">Per installare gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8863-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="d8863-115">Accedere come amministratore locale (requisito minimo) al computer in cui si vogliono installare gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d8863-115">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools.</span></span> <span data-ttu-id="d8863-116">Se è stato effettuato l'accesso come utente standard nei sistemi operativi Windows Vista o Windows 7 e il controllo dell'account utente è abilitato, verrà richiesto l'amministratore locale o un nome utente e una password equivalenti al dominio.</span><span class="sxs-lookup"><span data-stu-id="d8863-116">If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="d8863-117">Individuare il supporto di installazione nel computer e quindi fare doppio clic \\su Setup\\amd64\\Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="d8863-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="d8863-118">Se viene richiesto di installare Microsoft Visual C++ 2008 distribuibili, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d8863-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="d8863-119">Nella pagina **percorso di installazione di Microsoft Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8863-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="d8863-120">Cambiare il percorso in un'altra posizione o in un'altra unità se è necessario installare i file in un'altra posizione.</span><span class="sxs-lookup"><span data-stu-id="d8863-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d8863-121">Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa da un'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Lync Server 2013 nella finestra di dialogo Imposta.</span><span class="sxs-lookup"><span data-stu-id="d8863-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="d8863-122">Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Lync Server 2013 verrà distribuito in questa unità.</span><span class="sxs-lookup"><span data-stu-id="d8863-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="d8863-123">Nella pagina **contratto di licenza con l'utente finale** verificare le condizioni di licenza, fare clic su **Accetto**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8863-123">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="d8863-124">Questo passaggio è obbligatorio prima di poter continuare.</span><span class="sxs-lookup"><span data-stu-id="d8863-124">This step is required before you can continue.</span></span>

6.  <span data-ttu-id="d8863-125">Nella pagina **Microsoft Lync Server 2013-distribuzione guidata** fare clic su **installa strumenti amministratore**.</span><span class="sxs-lookup"><span data-stu-id="d8863-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="d8863-126">Dopo aver completato l'installazione, fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="d8863-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d8863-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8863-127">See Also</span></span>


[<span data-ttu-id="d8863-128">Aprire gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8863-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="d8863-129">Strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8863-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

