---
title: Installare gli strumenti di amministrazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: "Riepilogo: informazioni su come installare gli strumenti di amministrazione necessari per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812106"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="6bc78-104">Installare gli strumenti di amministrazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6bc78-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="6bc78-105">**Riepilogo:** Informazioni su come installare gli strumenti di amministrazione necessari per un'installazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="6bc78-106">Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .</span><span class="sxs-lookup"><span data-stu-id="6bc78-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="6bc78-107">Gli strumenti di amministrazione includono generatore di topologie e il pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="6bc78-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="6bc78-108">Gli strumenti di amministrazione devono essere installati in almeno un server nella topologia o in una workstation di gestione a 64 bit che esegue una versione del sistema operativo Windows supportata per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="6bc78-109">È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="6bc78-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="6bc78-110">Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come indicato nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="6bc78-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="6bc78-111">L'installazione degli strumenti di amministrazione è il passaggio 3 di 8.</span><span class="sxs-lookup"><span data-stu-id="6bc78-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagramma Panoramica](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="6bc78-113">Installare gli strumenti di amministrazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6bc78-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="6bc78-114">Il supporto di installazione per Skype for Business Server offre un'esperienza flessibile.</span><span class="sxs-lookup"><span data-stu-id="6bc78-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="6bc78-115">La prima volta che si esegue Setup.exe, gli unici strumenti installati sono la distribuzione guidata di Skype for Business Server e Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6bc78-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="6bc78-116">Utilizzando questi due strumenti, noti come componenti di base, è possibile continuare con il processo di installazione, ma non forniscono funzionalità primarie per l'ambiente globale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="6bc78-117">La distribuzione guidata viene avviata automaticamente dopo l'installazione dei componenti di base.</span><span class="sxs-lookup"><span data-stu-id="6bc78-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="6bc78-118">La sezione della distribuzione guidata intitolata **Install Administrative Tools** installa il generatore di topologie di Skype for Business Server e il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6bc78-119">Ogni ambiente di Skype for Business Server deve disporre di almeno un server con gli strumenti di amministrazione installati.</span><span class="sxs-lookup"><span data-stu-id="6bc78-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="6bc78-120">Guardare i passaggi video per l' **installazione degli strumenti di amministrazione**:</span><span class="sxs-lookup"><span data-stu-id="6bc78-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="6bc78-121">Installare gli strumenti di amministrazione di Skype for Business Server dalla distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="6bc78-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="6bc78-122">Inserire il supporto di installazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="6bc78-123">Se l'installazione non viene avviata automaticamente, fare doppio clic su **Setup**.</span><span class="sxs-lookup"><span data-stu-id="6bc78-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="6bc78-124">Il supporto di installazione richiede l'esecuzione di Microsoft Visual C++.</span><span class="sxs-lookup"><span data-stu-id="6bc78-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="6bc78-125">Verrà visualizzata una finestra di dialogo in cui viene chiesto se si desidera installarlo.</span><span class="sxs-lookup"><span data-stu-id="6bc78-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="6bc78-126">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6bc78-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="6bc78-127">Usando Smart Setup, una nuova funzionalità in Skype for Business Server, è possibile connettersi a Internet per verificare la disponibilità di aggiornamenti durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="6bc78-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="6bc78-128">In questo modo è possibile ottenere un'esperienza migliore assicurandosi di avere gli aggiornamenti più recenti del prodotto durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="6bc78-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="6bc78-129">Fare clic su **Installa** per avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="6bc78-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="6bc78-130">Esaminare attentamente il contratto di licenza e, se si è d'accordo, selezionare **Accetto i termini del contratto di licenza** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6bc78-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="6bc78-131">I componenti di base di Skype for Business Server verranno installati nel server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="6bc78-132">I componenti di base sono costituiti dai seguenti elementi, come illustrato nella figura.</span><span class="sxs-lookup"><span data-stu-id="6bc78-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Componenti di base nella schermata Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="6bc78-134">**Distribuzione guidata di Skype for Business Server** Un programma di distribuzione che fornisce una piattaforma di avvio per l'installazione dei diversi componenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="6bc78-135">**Skype for Business Server Management Shell** Programma di PowerShell preconfigurato che consente l'amministrazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bc78-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="6bc78-136">Dopo aver completato l'installazione dei componenti di base, la distribuzione guidata di Skype for Business Server verrà avviata automaticamente, come mostrato nella figura.</span><span class="sxs-lookup"><span data-stu-id="6bc78-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Distribuzione guidata di Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="6bc78-138">Oltre ai componenti di base, è necessario installare anche il generatore di topologie di Skype for Business Server e il pannello di controllo di Skype for Business Server in almeno un server nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="6bc78-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="6bc78-139">Fare clic su **installa strumenti di amministrazione** nella distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="6bc78-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="6bc78-140">Fare clic su **Avanti** per iniziare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="6bc78-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="6bc78-141">Dopo aver completato l'installazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="6bc78-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="6bc78-142">Gli strumenti di amministrazione sono ora aggiunti al server, come mostrato nella figura.</span><span class="sxs-lookup"><span data-stu-id="6bc78-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Strumenti di amministrazione di Skype for Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="6bc78-144">**Generatore di topologie di Skype for Business Server** Programma utilizzato per la creazione, la distribuzione e la gestione di topologie.</span><span class="sxs-lookup"><span data-stu-id="6bc78-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="6bc78-145">**Pannello di controllo di Skype for Business Server** Programma utilizzato per amministrare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="6bc78-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

