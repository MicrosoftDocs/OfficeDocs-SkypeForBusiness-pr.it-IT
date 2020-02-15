---
title: Creare una condivisione file in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: "Riepilogo: informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028297"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="6c3b7-104">Creare una condivisione file in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6c3b7-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="6c3b7-105">**Riepilogo:** Informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="6c3b7-106">Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Indirizzo:.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="6c3b7-107">Skype for Business Server richiede una condivisione file in modo che i computer della topologia possano scambiare file.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="6c3b7-108">La creazione di una condivisione file è il passaggio 2 di 8 del processo di installazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="6c3b7-109">È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="6c3b7-110">Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5 come indicato nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="6c3b7-111">Per informazioni sulla pianificazione della condivisione file, vedere Requisiti per l' [ambiente per](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) i requisiti server e Skype for business per Skype for [Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c3b7-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Diagramma Panoramica](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="6c3b7-113">Creare una condivisione file di base</span><span class="sxs-lookup"><span data-stu-id="6c3b7-113">Create a basic file share</span></span>

<span data-ttu-id="6c3b7-114">In questa sezione viene illustrata la creazione di una condivisione di file di Windows Server di base.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="6c3b7-115">Una condivisione di file di Windows Server di base è supportata con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="6c3b7-116">Tuttavia, la disponibilità elevata non viene fornita in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="6c3b7-117">Per un ambiente a disponibilità elevata, è consigliata una condivisione file del file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="6c3b7-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="6c3b7-118">Per ulteriori informazioni su una condivisione file e un DFS a disponibilità elevata, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="6c3b7-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c3b7-119">Windows Server 2012 R2 ha compiuto importanti balzi in quanto fornisce soluzioni di condivisione file come la rete di archiviazione (SAN) utilizzando la piattaforma Windows Server.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="6c3b7-120">Rispetto a un dispositivo tradizionale basato su SAN, una soluzione di archiviazione Windows Server 2012 R2 può ridurre i costi a metà con un impatto minimo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="6c3b7-121">Per ulteriori informazioni sulle opzioni di condivisione file in Windows Server 2012 R2, vedere il white paper scaricabile [Windows server 2012 R2 storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="6c3b7-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="6c3b7-122">Guardare i passaggi video per **creare una condivisione file**:</span><span class="sxs-lookup"><span data-stu-id="6c3b7-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="6c3b7-123">Creare una condivisione file di base</span><span class="sxs-lookup"><span data-stu-id="6c3b7-123">Create a basic file share</span></span>

1. <span data-ttu-id="6c3b7-124">Accedere al computer in cui verrà ospitata la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="6c3b7-125">Fare clic con il pulsante destro del mouse sulla cartella che si intende condividere e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="6c3b7-126">Selezionare la scheda **condivisione** e fare clic su **condivisione avanzata**.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="6c3b7-127">Fare clic su **Condividi questa cartella**.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="6c3b7-128">Fare clic su **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="6c3b7-129">Aggiungere il gruppo **Administrators** locale del server che ospita la condivisione file, concedere **Consenti: controllo completo, modifica e** diritti di lettura e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="6c3b7-130">Fare di nuovo clic su **OK** e prendere nota del percorso di rete.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="6c3b7-131">Fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-131">Click **Done** to close the wizard.</span></span>
    
     ![Scheda condivisione per la condivisione di una cartella.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="6c3b7-133">Se l'archivio file è ospitato in una condivisione DFS, verrà visualizzato l'avviso seguente:</span><span class="sxs-lookup"><span data-stu-id="6c3b7-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="6c3b7-134">Avviso: Impossibile accedere alle autorizzazioni di condivisione per\\<domain>\<"Share>".</span><span class="sxs-lookup"><span data-stu-id="6c3b7-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="6c3b7-135">Questo è previsto se non si è un amministratore nel file server oppure se si tratta di una condivisione di file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="6c3b7-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="6c3b7-136">Se le autorizzazioni di condivisione sono già state configurate, è possibile ignorare questo avviso.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="6c3b7-137">Se si tratta di una nuova condivisione, fare riferimento alla documentazione per informazioni dettagliate sulla configurazione manuale delle autorizzazioni di condivisione.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="6c3b7-138">A causa dell'impossibilità di accedere alle autorizzazioni di condivisione su una condivisione DFS, Skype for Business Server non sarà in grado di impostare in modo esplicito i gruppi nella condivisione file.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="6c3b7-139">Per assicurarsi che i componenti di Skype for Business Server possano accedere alla condivisione file con le autorizzazioni appropriate, verificare che i seguenti gruppi RTC siano stati aggiunti con autorizzazioni di condivisione a livello di lettura e modifica, oltre agli amministratori locali con condivisione di controllo completa autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6c3b7-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="6c3b7-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="6c3b7-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="6c3b7-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="6c3b7-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="6c3b7-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6c3b7-142">RTCUniversalServerAdmins</span></span>
