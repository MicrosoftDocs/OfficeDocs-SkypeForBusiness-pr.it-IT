---
title: Perché non è possibile usare l'interfaccia di amministrazione di Skype for business online in questo momento?
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
description: "Informazioni su cosa è possibile e non si può usare nell'interfaccia di amministrazione di Skype for business e altre funzionalità quando il servizio viene migrato in un altro centro dati Microsoft. "
ms.openlocfilehash: 7258467929663c42bfb6088202511a04613db383
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164495"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="0b660-103">Perché non è possibile usare l'interfaccia di amministrazione di Skype for business online in questo momento?</span><span class="sxs-lookup"><span data-stu-id="0b660-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="0b660-104">Sappiamo che è frustrante quando non è possibile eseguire il lavoro, quindi spiegheremo cosa sta succedendo e perché varrà l'attesa.</span><span class="sxs-lookup"><span data-stu-id="0b660-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="0b660-105">Prima di tutto, ecco la spiegazione tecnica:</span><span class="sxs-lookup"><span data-stu-id="0b660-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="0b660-106">Stiamo migrando il servizio Skype for business online (ovvero gli utenti e le impostazioni dell'organizzazione) in un altro centro dati Microsoft più vicino.</span><span class="sxs-lookup"><span data-stu-id="0b660-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="0b660-107">Questo migliorerà il servizio e ridurrà la latenza.</span><span class="sxs-lookup"><span data-stu-id="0b660-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="0b660-108">Per altri dettagli tecnici, vedere [durante e dopo lo stato di trasferimento dei dati]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="0b660-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="0b660-109">OK, cosa significa?</span><span class="sxs-lookup"><span data-stu-id="0b660-109">OK, so what does that mean?</span></span>

<span data-ttu-id="0b660-110">Per prima cosa, analizziamo alcuni termini.</span><span class="sxs-lookup"><span data-stu-id="0b660-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="0b660-111">**Data Center** Questa è la posizione fisica in cui sono archiviate le informazioni di Microsoft 365 o Office 365, ad esempio i file e i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0b660-111">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="0b660-112">Se si vuole veramente analizzare i dati di Microsoft 365 e Office 365, vedere[questo articolo](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="0b660-112">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="0b660-113">**Migrazione** Questo è più o meno uguale a "spostamento".</span><span class="sxs-lookup"><span data-stu-id="0b660-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="0b660-114">In questo caso, significa che stiamo spostando gli utenti e le impostazioni di Skype for business online da un centro dati a un altro più vicino a te per migliorare il servizio.</span><span class="sxs-lookup"><span data-stu-id="0b660-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="0b660-115">**Latenza** Questa è la quantità di tempo necessaria per accedere all'interfaccia di amministrazione di Microsoft 365, apportare modifiche alle impostazioni e quindi salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0b660-115">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="0b660-116">**ID correlazione** Potrebbe essere visualizzato questo elenco nel messaggio appena uscito.</span><span class="sxs-lookup"><span data-stu-id="0b660-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="0b660-117">Queste informazioni vengono usate dagli ingegneri del supporto Microsoft per aiutarti a risolvere un errore.</span><span class="sxs-lookup"><span data-stu-id="0b660-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="0b660-118">Se si contatta il supporto Microsoft, è possibile che venga richiesto l'ID di correlazione.</span><span class="sxs-lookup"><span data-stu-id="0b660-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="0b660-119">Questo significa che stiamo spostando tutti gli utenti e le impostazioni di servizio di Skype for business online in un'altra posizione più vicina a te.</span><span class="sxs-lookup"><span data-stu-id="0b660-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="0b660-120">Maggiore è il miglioramento.</span><span class="sxs-lookup"><span data-stu-id="0b660-120">The closer the better.</span></span> <span data-ttu-id="0b660-121">La buona notizia è che dopo questo breve periodo di tempo, il servizio Skype for business online migliorerà.</span><span class="sxs-lookup"><span data-stu-id="0b660-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Migrazione del servizio in Microsoft 365 o Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="0b660-123">Quali funzionalità di Skype for business online funzionano ancora?</span><span class="sxs-lookup"><span data-stu-id="0b660-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="0b660-124">Anche se non è possibile accedere all'interfaccia di amministrazione di Skype for business online, le caratteristiche seguenti di Skype for business online continueranno a funzionare durante la migrazione:</span><span class="sxs-lookup"><span data-stu-id="0b660-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="0b660-125">Riunioni online</span><span class="sxs-lookup"><span data-stu-id="0b660-125">Online meetings</span></span>
    
- <span data-ttu-id="0b660-126">Informazioni sulla presenza</span><span class="sxs-lookup"><span data-stu-id="0b660-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="0b660-127">È possibile eseguire altre operazioni?</span><span class="sxs-lookup"><span data-stu-id="0b660-127">Can I get other work done?</span></span>

<span data-ttu-id="0b660-128">Sicuro.</span><span class="sxs-lookup"><span data-stu-id="0b660-128">Sure.</span></span> <span data-ttu-id="0b660-129">Mentre si sta migrando il servizio Skype for business online, è comunque possibile usare gli altri centri di amministrazione di Microsoft 365, ad esempio Microsoft 365 ed Exchange Admin Centers.</span><span class="sxs-lookup"><span data-stu-id="0b660-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="0b660-130">Tuttavia, insieme all'interfaccia di amministrazione di Skype for business online, non potrai usare i cmdlet di PowerShell remoto di Skype for business online durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="0b660-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="0b660-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0b660-131">Related topics</span></span>
[<span data-ttu-id="0b660-132">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="0b660-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0b660-133">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="0b660-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
