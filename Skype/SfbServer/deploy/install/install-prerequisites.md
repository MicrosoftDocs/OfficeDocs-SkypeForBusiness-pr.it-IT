---
title: Installare i prerequisiti per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: "Riepilogo: informazioni sui server e sui ruoli del server che è necessario configurare prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801716"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="a824e-104">Installare i prerequisiti per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a824e-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="a824e-105">**Riepilogo:** Informazioni sui server e sui ruoli del server che è necessario configurare prima di installare Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a824e-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="a824e-106">Scaricare una versione di valutazione gratuita di Skype for Business Server dal [Centro di valutazione Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="a824e-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a824e-107">L'installazione dei prerequisiti consiste nella configurazione di Windows Server mediante l'installazione dei ruoli e delle funzionalità necessari in ognuno dei server della topologia.</span><span class="sxs-lookup"><span data-stu-id="a824e-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="a824e-108">I requisiti si basano sul ruolo che il server adempirà nella topologia.</span><span class="sxs-lookup"><span data-stu-id="a824e-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="a824e-109">È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="a824e-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="a824e-110">È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="a824e-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="a824e-111">L'installazione dei prerequisiti è il passaggio 1 di 8.</span><span class="sxs-lookup"><span data-stu-id="a824e-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagramma di panoramica - Prerequisiti per l'installazione.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="a824e-113">Installazione di Windows Server</span><span class="sxs-lookup"><span data-stu-id="a824e-113">Setup Windows Server</span></span>

<span data-ttu-id="a824e-114">Skype for Business Server richiede il sistema operativo Windows Server e alcuni prerequisiti prima di poter essere installato.</span><span class="sxs-lookup"><span data-stu-id="a824e-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="a824e-115">Per informazioni dettagliate sulla pianificazione dei prerequisiti, vedere [Requisiti server per Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="a824e-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="a824e-116">Questa procedura utilizza Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="a824e-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="a824e-117">Se si utilizza una versione diversa di Windows Server, la procedura potrebbe essere leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="a824e-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a824e-118">Prima di iniziare, assicurati che Windows Server sia aggiornato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a824e-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server aggiornato.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="a824e-120">Guardare i passaggi video per **installare i prerequisiti:**</span><span class="sxs-lookup"><span data-stu-id="a824e-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="a824e-121">Installare i ruoli e le funzionalità necessari per i server front-end</span><span class="sxs-lookup"><span data-stu-id="a824e-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="a824e-122">È possibile installare i ruoli e le funzionalità necessari utilizzando Server Manager.</span><span class="sxs-lookup"><span data-stu-id="a824e-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="a824e-123">Installare le funzionalità software prerequisiti elencate in [Requisiti server per Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="a824e-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="a824e-124">Il software necessario deve essere nel server che eseguirà Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a824e-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a824e-125">Windows Server 2012 R2 non installa tutti i file di origine per le funzionalità necessarie per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a824e-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="a824e-126">Se il server non è connesso a Internet, sarà necessario inserire il supporto di  Windows Server 2012 R2 e selezionare Specificare un percorso di origine alternativo per installare le funzionalità necessarie.</span><span class="sxs-lookup"><span data-stu-id="a824e-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="a824e-127">I file di origine si trovano nella directory sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="a824e-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="a824e-128">Ad esempio, se il supporto di Windows Server 2012 R2 si trova nell'unità D, è necessario impostare il percorso su `d:\sources\sxs` .</span><span class="sxs-lookup"><span data-stu-id="a824e-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="a824e-129">È importante disporre degli aggiornamenti più recenti di Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a824e-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="a824e-130">Se non si è connessi a Internet, sarà necessario installare manualmente tutti gli aggiornamenti rilevanti e tutti i prerequisiti per gli aggiornamenti necessari.</span><span class="sxs-lookup"><span data-stu-id="a824e-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="a824e-131">Quando la finestra di dialogo indica che l'installazione è stata completata, sarà necessario riavviare il server per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="a824e-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="a824e-132">Eseguire **di nuovo Windows Update** per verificare se sono presenti aggiornamenti dei ruoli e dei servizi installati.</span><span class="sxs-lookup"><span data-stu-id="a824e-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="a824e-133">Se si utilizza il Pannello di controllo di Skype for Business Server su questo server, è necessario installare anche Silverlight.</span><span class="sxs-lookup"><span data-stu-id="a824e-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="a824e-134">Per installare Silverlight, vedere [Microsoft Silverlight.](https://www.microsoft.com/silverlight/)</span><span class="sxs-lookup"><span data-stu-id="a824e-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a824e-135">I prerequisiti per i server che eseguono ruoli diversi dal server front-end, ad esempio il ruolo di Director, Persistent Chat o Edge, hanno i propri prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="a824e-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="a824e-136">Per informazioni dettagliate sui prerequisiti esatti richiesti da ogni tipo di server, vedere [Requisiti del server per Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="a824e-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

