---
title: Perché non è possibile usare l'interfaccia di amministrazione di Skype for Business Online in questo momento?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.TenantInMigration
description: "Informazioni su cosa è possibile e non si può usare nell'interfaccia di amministrazione di Skype for Business e su altre funzionalità durante la migrazione del servizio a un altro data center Microsoft. "
ms.openlocfilehash: 725a60be96a2d61bcec6367e1a0a33f2bc5dcee6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238917"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="25b62-103">Perché non è possibile usare l'interfaccia di amministrazione di Skype for Business Online in questo momento?</span><span class="sxs-lookup"><span data-stu-id="25b62-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="25b62-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span><span class="sxs-lookup"><span data-stu-id="25b62-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span></span>

<span data-ttu-id="25b62-105">Sappiamo che è frustrante quando non è possibile eseguire il lavoro, quindi spiegheremo cosa succede qui e perché vale la pena aspettare.</span><span class="sxs-lookup"><span data-stu-id="25b62-105">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="25b62-106">Prima di tutto, ecco la spiegazione tecnica:</span><span class="sxs-lookup"><span data-stu-id="25b62-106">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="25b62-107">Stiamo eseguendo la migrazione del servizio Skype for Business Online (ovvero gli utenti e le impostazioni dell'organizzazione) a un altro data center Microsoft più vicino all'utente.</span><span class="sxs-lookup"><span data-stu-id="25b62-107">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="25b62-108">In questo modo si migliorerà il servizio e si ridurrà la latenza.</span><span class="sxs-lookup"><span data-stu-id="25b62-108">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="25b62-109">Per altre informazioni tecniche, vedere [Durante e dopo lo spostamento dei dati.]( https://go.microsoft.com/fwlink/?LinkId=526418)</span><span class="sxs-lookup"><span data-stu-id="25b62-109">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="25b62-110">Ok, quindi cosa significa?</span><span class="sxs-lookup"><span data-stu-id="25b62-110">OK, so what does that mean?</span></span>

<span data-ttu-id="25b62-111">Prima di tutto, diamo un'interruzione di alcuni termini.</span><span class="sxs-lookup"><span data-stu-id="25b62-111">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="25b62-112">**Data center** Si tratta della posizione fisica in cui sono archiviate le informazioni Microsoft 365 o Office 365, ad esempio i file e i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="25b62-112">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="25b62-113">Se si vuole davvero scoprire quali sono i Microsoft 365 e Office 365 data center, vedere[questo articolo.](https://www.microsoft.com/online/legal/v2/?docid=25)</span><span class="sxs-lookup"><span data-stu-id="25b62-113">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="25b62-114">**Migrazione** Questo è più o meno lo stesso di "spostamento".</span><span class="sxs-lookup"><span data-stu-id="25b62-114">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="25b62-115">In questo caso, significa che stiamo spostando gli utenti e le impostazioni di Skype for Business Online da un data center a un altro più vicino all'utente per migliorare il servizio.</span><span class="sxs-lookup"><span data-stu-id="25b62-115">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="25b62-116">**Latenza** Questo è il tempo necessario per accedere all'interfaccia Microsoft 365 di amministrazione, apportare una modifica alle impostazioni e quindi salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="25b62-116">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="25b62-117">**ID correlazione** È possibile che sia stato visualizzato nell'elenco del messaggio da cui si è appena arrivati.</span><span class="sxs-lookup"><span data-stu-id="25b62-117">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="25b62-118">Queste informazioni vengono usate dai tecnici del supporto tecnico Microsoft per facilitare la risoluzione di un errore.</span><span class="sxs-lookup"><span data-stu-id="25b62-118">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="25b62-119">Se si contatta il supporto Tecnico Microsoft, potrebbe essere richiesto l'ID di correlazione.</span><span class="sxs-lookup"><span data-stu-id="25b62-119">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="25b62-120">Questo significa che stiamo spostando tutti gli utenti e le impostazioni dei servizi di Skype for Business Online in un'altra posizione più vicina a te.</span><span class="sxs-lookup"><span data-stu-id="25b62-120">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="25b62-121">Quanto più vicino è meglio è.</span><span class="sxs-lookup"><span data-stu-id="25b62-121">The closer the better.</span></span> <span data-ttu-id="25b62-122">La buona notizia è che dopo questo breve periodo di tempo, il servizio Skype for Business Online migliorerà.</span><span class="sxs-lookup"><span data-stu-id="25b62-122">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Migrazione dei servizi in Microsoft 365 o Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="25b62-124">Quali Skype for Business funzionalità online saranno ancora disponibili?</span><span class="sxs-lookup"><span data-stu-id="25b62-124">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="25b62-125">Anche se non sarà possibile accedere all'interfaccia di amministrazione di Skype for Business Online, le funzionalità di Skype for Business Online seguenti funzionano ancora durante la migrazione:</span><span class="sxs-lookup"><span data-stu-id="25b62-125">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="25b62-126">Riunioni online</span><span class="sxs-lookup"><span data-stu-id="25b62-126">Online meetings</span></span>
    
- <span data-ttu-id="25b62-127">Informazioni sulla presenza</span><span class="sxs-lookup"><span data-stu-id="25b62-127">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="25b62-128">È possibile eseguire altre operazioni?</span><span class="sxs-lookup"><span data-stu-id="25b62-128">Can I get other work done?</span></span>

<span data-ttu-id="25b62-129">Certo.</span><span class="sxs-lookup"><span data-stu-id="25b62-129">Sure.</span></span> <span data-ttu-id="25b62-130">Durante la migrazione del servizio Skype for Business Online, è comunque possibile usare le altre interfaccia di amministrazione in Microsoft 365, ad esempio le Microsoft 365 e le Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="25b62-130">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="25b62-131">Tuttavia, insieme all'interfaccia di amministrazione di Skype for Business Online, non sarà possibile usare i cmdlet remoti di PowerShell di Skype for Business Online durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="25b62-131">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="25b62-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="25b62-132">Related topics</span></span>
[<span data-ttu-id="25b62-133">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="25b62-133">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="25b62-134">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="25b62-134">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
