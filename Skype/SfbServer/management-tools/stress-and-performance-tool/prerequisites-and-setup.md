---
title: Prerequisiti e configurazione dello strumento Skype for Busines Stress and Performance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisiti o prerequisiti per lo strumento Skype for Business Server 2015 Stress and Performance. Come installare o configurare lo strumento Stress and Performance.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814956"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="f7b80-104">Prerequisiti e configurazione dello strumento Skype for Busines Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="f7b80-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="f7b80-105">Requisiti o prerequisiti per lo strumento Skype for Business Server 2015 Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="f7b80-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="f7b80-106">Come installare o configurare lo strumento Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="f7b80-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="f7b80-107">Sono disponibili le sezioni seguenti dei requisiti hardware, software e di configurazione del sistema di cui è necessario essere a conoscenza prima di eseguire lo strumento Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="f7b80-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="f7b80-108">Requisiti hardware client</span><span class="sxs-lookup"><span data-stu-id="f7b80-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="f7b80-109">Requisiti software client</span><span class="sxs-lookup"><span data-stu-id="f7b80-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="f7b80-110">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="f7b80-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="f7b80-111">Inoltre, di seguito è disponibile una sezione per l'installazione dello strumento [Skype for Business Server 2015 Stress and Performance](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="f7b80-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="f7b80-112">Requisiti hardware client</span><span class="sxs-lookup"><span data-stu-id="f7b80-112">Client hardware requirements</span></span>
<span data-ttu-id="f7b80-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="f7b80-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="f7b80-114">Quando si esegue lo strumento Stress and Performance sulla distribuzione di Skype for Business Server 2015, è necessario soddisfare almeno questi requisiti hardware ogni 4500 utenti nel test:</span><span class="sxs-lookup"><span data-stu-id="f7b80-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="f7b80-115">Scheda di rete a 1 gigabit</span><span class="sxs-lookup"><span data-stu-id="f7b80-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="f7b80-116">8 GB di RAM</span><span class="sxs-lookup"><span data-stu-id="f7b80-116">8 GB RAM</span></span>
    
- <span data-ttu-id="f7b80-117">2 CPU dual core</span><span class="sxs-lookup"><span data-stu-id="f7b80-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="f7b80-118">Requisiti software client</span><span class="sxs-lookup"><span data-stu-id="f7b80-118">Client software requirements</span></span>
<span data-ttu-id="f7b80-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="f7b80-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="f7b80-120">I sistemi operativi supportati per lo strumento Stress and Performance Sono:</span><span class="sxs-lookup"><span data-stu-id="f7b80-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="f7b80-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f7b80-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="f7b80-122">Windows Server 2008 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="f7b80-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="f7b80-123">Inoltre, i computer devono soddisfare i requisiti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7b80-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="f7b80-124">È necessario che sia installato Microsoft .NET 4.5 Framework.</span><span class="sxs-lookup"><span data-stu-id="f7b80-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="f7b80-125">Scaricare .Net 4.5 Framework qui.</span><span class="sxs-lookup"><span data-stu-id="f7b80-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="f7b80-126">È necessario che la funzionalità Esperienza desktop sia abilitata in Windows.</span><span class="sxs-lookup"><span data-stu-id="f7b80-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="f7b80-127">È necessario che sia installato Microsoft Visual C++ 2013 (x64).</span><span class="sxs-lookup"><span data-stu-id="f7b80-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="f7b80-128">Scarica Visual C++ 2013 qui</span><span class="sxs-lookup"><span data-stu-id="f7b80-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="f7b80-129">You're going to need Skype for Business Server 2015 successfully deployed.</span><span class="sxs-lookup"><span data-stu-id="f7b80-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="f7b80-130">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="f7b80-130">Configuration requirements</span></span>
<span data-ttu-id="f7b80-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="f7b80-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="f7b80-132">Per eseguire correttamente lo strumento Stress and Performance, sono necessarie queste configurazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="f7b80-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="f7b80-133">È necessario accedere al server come membro del gruppo Domain o Local Administrator.</span><span class="sxs-lookup"><span data-stu-id="f7b80-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="f7b80-134">Non è possibile installare lo strumento di creazione utenti di Skype for Business Server 2015 (UserProvisioningTool.exe) in alcun Front End Server o server Standard Edition in cui risiederanno gli account utente.</span><span class="sxs-lookup"><span data-stu-id="f7b80-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="f7b80-135">Quando lo strumento creazione utenti viene eseguito più volte, ogni utente abilitato per le comunicazioni unificate Microsoft deve disporre di un numero di telefono univoco.</span><span class="sxs-lookup"><span data-stu-id="f7b80-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="f7b80-136">Le dimensioni del file di pagina devono essere gestite dal sistema o in altro modo devono essere almeno 1,5 volte la quantità di RAM nel sistema del computer.</span><span class="sxs-lookup"><span data-stu-id="f7b80-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="f7b80-137">Installazione dello strumento Skype for Business Server 2015 Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="f7b80-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="f7b80-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="f7b80-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="f7b80-139">L'installazione non può essere più semplice.</span><span class="sxs-lookup"><span data-stu-id="f7b80-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="f7b80-140">È necessario eseguire il file di Windows **Installer,CapacityPlanningTool.msi,** in ogni computer client che si userà per simulare il traffico degli utenti e in un Front End Server in ogni pool in cui verranno creati utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="f7b80-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="f7b80-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="f7b80-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

