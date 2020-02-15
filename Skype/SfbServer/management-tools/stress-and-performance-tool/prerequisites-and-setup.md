---
title: Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Requisiti o prerequisiti per lo strumento di sollecito e prestazioni di Skype for Business Server 2015. Informazioni su come installare o configurare lo strumento di stress e prestazioni.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005981"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="850bc-104">Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines</span><span class="sxs-lookup"><span data-stu-id="850bc-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="850bc-105">Requisiti o prerequisiti per lo strumento di sollecito e prestazioni di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="850bc-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="850bc-106">Informazioni su come installare o configurare lo strumento di stress e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="850bc-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="850bc-107">Sono disponibili le seguenti sezioni dei requisiti hardware, software e di configurazione del sistema di cui è necessario tenere conto prima di eseguire lo strumento stress and performance:</span><span class="sxs-lookup"><span data-stu-id="850bc-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="850bc-108">Requisiti hardware client</span><span class="sxs-lookup"><span data-stu-id="850bc-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="850bc-109">Requisiti software client</span><span class="sxs-lookup"><span data-stu-id="850bc-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="850bc-110">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="850bc-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="850bc-111">Inoltre, è presente una sezione per [l'installazione dello strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="850bc-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="850bc-112">Requisiti hardware client</span><span class="sxs-lookup"><span data-stu-id="850bc-112">Client hardware requirements</span></span>
<span data-ttu-id="850bc-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="850bc-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="850bc-114">Quando si esegue lo strumento di stress e prestazioni per la distribuzione di Skype for Business Server 2015, è necessario soddisfare almeno i requisiti hardware per ogni 4500 utenti del test:</span><span class="sxs-lookup"><span data-stu-id="850bc-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="850bc-115">1 scheda di rete Gigabit</span><span class="sxs-lookup"><span data-stu-id="850bc-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="850bc-116">8 GB di RAM</span><span class="sxs-lookup"><span data-stu-id="850bc-116">8 GB RAM</span></span>
    
- <span data-ttu-id="850bc-117">2 CPU dual core</span><span class="sxs-lookup"><span data-stu-id="850bc-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="850bc-118">Requisiti software client</span><span class="sxs-lookup"><span data-stu-id="850bc-118">Client software requirements</span></span>
<span data-ttu-id="850bc-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="850bc-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="850bc-120">I sistemi operativi supportati per lo strumento stress and performance sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="850bc-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="850bc-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="850bc-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="850bc-122">Windows Server 2008 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="850bc-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="850bc-123">Inoltre, i computer devono soddisfare i requisiti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="850bc-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="850bc-124">È necessario che sia installato Microsoft .NET 4,5 Framework.</span><span class="sxs-lookup"><span data-stu-id="850bc-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="850bc-125">Scaricare .NET 4,5 Framework qui.</span><span class="sxs-lookup"><span data-stu-id="850bc-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="850bc-126">È necessaria la funzionalità esperienza desktop abilitata in Windows.</span><span class="sxs-lookup"><span data-stu-id="850bc-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="850bc-127">È necessario che Microsoft Visual C++ 2013 (x64) sia installato.</span><span class="sxs-lookup"><span data-stu-id="850bc-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="850bc-128">Scaricare Visual C++ 2013 qui</span><span class="sxs-lookup"><span data-stu-id="850bc-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="850bc-129">Sarà necessario che Skype for Business Server 2015 sia stato distribuito correttamente.</span><span class="sxs-lookup"><span data-stu-id="850bc-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="850bc-130">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="850bc-130">Configuration requirements</span></span>
<span data-ttu-id="850bc-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="850bc-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="850bc-132">Per eseguire correttamente lo strumento stress and performance, sono necessarie ulteriori configurazioni:</span><span class="sxs-lookup"><span data-stu-id="850bc-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="850bc-133">È necessario eseguire l'accesso al server come membro del gruppo del dominio o dell'amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="850bc-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="850bc-134">Non è possibile installare lo strumento di creazione degli utenti di Skype for Business Server 2015 (UserProvisioningTool. exe) su un server front end server o Standard Edition in cui si trovano gli account utente.</span><span class="sxs-lookup"><span data-stu-id="850bc-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="850bc-135">Quando lo strumento per la creazione dell'utente viene eseguito più volte, ogni utente abilitato per le comunicazioni unificate di Microsoft deve disporre di un numero di telefono univoco.</span><span class="sxs-lookup"><span data-stu-id="850bc-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="850bc-136">Le dimensioni del file di paging devono essere gestite da sistemi oppure devono essere almeno 1,5 volte la quantità di RAM nel computer.</span><span class="sxs-lookup"><span data-stu-id="850bc-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="850bc-137">Installazione dello strumento di sollecito e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="850bc-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="850bc-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="850bc-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="850bc-139">L'installazione non può essere più semplice.</span><span class="sxs-lookup"><span data-stu-id="850bc-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="850bc-140">È necessario eseguire il file di Windows Installer, **CapacityPlanningTool. msi**, in ogni computer client che si intende utilizzare per simulare il traffico degli utenti e in un front end server in ogni pool in cui verranno creati utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="850bc-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="850bc-141">Per scaricare il. msi, insieme agli script di esempio menzionati negli altri articoli, passare al collegamento Centro download: [Skype for Business Server 2015, strumento di stress e prestazioni](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="850bc-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

