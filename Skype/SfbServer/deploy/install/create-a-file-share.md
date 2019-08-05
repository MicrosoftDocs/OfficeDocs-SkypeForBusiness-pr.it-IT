---
title: Creare una condivisione file in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: "Riepilogo: informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: d6a34ad4807948a5580fc572628a4fd6333dd9f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194286"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="ee6b7-104">Creare una condivisione file in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ee6b7-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="ee6b7-105">**Riepilogo:** Informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="ee6b7-106">Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all'[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Indirizzo:.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="ee6b7-107">Skype for Business Server richiede una condivisione file in modo che i computer di tutta la topologia possano scambiare file.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="ee6b7-108">La creazione di una condivisione file è il passaggio 2 di 8 nel processo di installazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="ee6b7-109">È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="ee6b7-110">Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5 come indicato nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="ee6b7-111">Per informazioni sulla pianificazione della condivisione file, vedere [requisiti ambientali per i requisiti di Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o server [per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee6b7-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Diagramma di panoramica](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="ee6b7-113">Creare una condivisione di file di base</span><span class="sxs-lookup"><span data-stu-id="ee6b7-113">Create a basic file share</span></span>

<span data-ttu-id="ee6b7-114">Questa sezione illustra la creazione di una condivisione di file di Windows Server di base.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="ee6b7-115">È supportata una condivisione file di base di Windows Server con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="ee6b7-116">Tuttavia, non garantisce in modo esplicito una disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="ee6b7-117">Per un ambiente ad alta disponibilità, è consigliabile una condivisione file del file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="ee6b7-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="ee6b7-118">Per altre informazioni su una condivisione di file ad alta disponibilità e su DFS, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ee6b7-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ee6b7-119">Windows Server 2012 R2 ha compiuto notevoli salti nella fornitura di soluzioni di condivisione file di tipo SAN (Storage Area Network) con la piattaforma Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="ee6b7-120">Rispetto a un dispositivo tradizionale basato su SAN, una soluzione di archiviazione di Windows Server 2012 R2 può ridurre i costi a metà con un impatto molto minimo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="ee6b7-121">Per altre informazioni sulle opzioni di condivisione file in Windows Server 2012 R2, vedere lo spazio di archiviazione scaricabile white paper [Windows server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="ee6b7-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="ee6b7-122">Guardare la procedura video per **creare una condivisione file**:</span><span class="sxs-lookup"><span data-stu-id="ee6b7-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="ee6b7-123">Creare una condivisione di file di base</span><span class="sxs-lookup"><span data-stu-id="ee6b7-123">Create a basic file share</span></span>

1. <span data-ttu-id="ee6b7-124">Accedere al computer in cui verrà ospitata la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="ee6b7-125">Fare clic con il pulsante destro del mouse sulla cartella che si prevede di condividere e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="ee6b7-126">Selezionare la scheda **condivisione** e fare clic su **condivisione avanzata**.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="ee6b7-127">Fare clic su **Condividi cartella**.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="ee6b7-128">Fare clic su **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="ee6b7-129">Aggiungere il gruppo **Administrators** locale del server che ospita la condivisione file, concedere **Consenti: controllo completo, modifica e** diritti di lettura e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="ee6b7-130">Fare di nuovo clic su **OK** e prendere nota del percorso di rete.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="ee6b7-131">Fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-131">Click **Done** to close the wizard.</span></span>
    
     ![Scheda condivisione per la condivisione di una cartella.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="ee6b7-133">Se l'archivio file è ospitato in una condivisione DFS, verrà ricevuto l'avviso seguente:</span><span class="sxs-lookup"><span data-stu-id="ee6b7-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="ee6b7-134">Avviso: non è possibile accedere alle autorizzazioni di\\<domain>\<condivisione per "Condividi>".</span><span class="sxs-lookup"><span data-stu-id="ee6b7-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="ee6b7-135">Questa operazione è prevista se non si è un amministratore nel file server o se si tratta di una condivisione di file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="ee6b7-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="ee6b7-136">Se le autorizzazioni di condivisione sono già state configurate, questo avviso può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="ee6b7-137">Se si tratta di una nuova condivisione, vedere la documentazione per informazioni dettagliate sulla configurazione manuale delle autorizzazioni di condivisione.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="ee6b7-138">A causa dell'impossibilità di accedere alle autorizzazioni di condivisione per una condivisione DFS, Skype for Business Server non sarà in grado di impostare esplicitamente i gruppi sulla condivisione file.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="ee6b7-139">Per assicurarti che i componenti di Skype for Business Server possano accedere alla condivisione file con le autorizzazioni appropriate, assicurati che i gruppi RTC seguenti vengano aggiunti con le autorizzazioni di condivisione del livello di modifica oltre agli amministratori locali con autorizzazioni di condivisione controllo completo.</span><span class="sxs-lookup"><span data-stu-id="ee6b7-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>

<span data-ttu-id="ee6b7-140">RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ee6b7-140">RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins</span></span>
