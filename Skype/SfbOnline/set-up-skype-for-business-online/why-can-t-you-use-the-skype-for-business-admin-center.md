---
title: "Perché non è possibile utilizzare il Skype Business Online interfaccia di amministrazione di direttamente?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: "Informazioni su informazioni che è possibile utilizzare in Skype per l'interfaccia di amministrazione di Business e altre caratteristiche quando il servizio viene eseguita la migrazione a un'altra data center di Microsoft. "
ms.openlocfilehash: e9d0f2b56ebe11ef95b59ff125434dcf3dd4574d
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="319e6-103">Perché non è possibile utilizzare il Skype Business Online interfaccia di amministrazione di direttamente?</span><span class="sxs-lookup"><span data-stu-id="319e6-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="319e6-104">È possibile sapere che è frustrante quando non è possibile ottenere il proprio lavoro, in modo che verranno esaminati viene descritto ciò che accade e sui motivi per cui sarà possibile più il tempo di attesa.</span><span class="sxs-lookup"><span data-stu-id="319e6-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="319e6-105">Per prima cosa, ecco la spiegazione tecnica:</span><span class="sxs-lookup"><span data-stu-id="319e6-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="319e6-106">È stiamo migrazione il Skype per servizio di Business in linea (ovvero gli utenti e le impostazioni dell'organizzazione) a un'altra data center Microsoft che è più vicino all'utente.</span><span class="sxs-lookup"><span data-stu-id="319e6-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="319e6-107">Per migliorare il servizio e ridurre la latenza.</span><span class="sxs-lookup"><span data-stu-id="319e6-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="319e6-108">Per ulteriori informazioni tecniche, vedere [durante e dopo la migrazione dei dati]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="319e6-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="319e6-109">Naturalmente, in modo che cosa?</span><span class="sxs-lookup"><span data-stu-id="319e6-109">OK, so what does that mean?</span></span>

<span data-ttu-id="319e6-110">Per prima cosa, possiamo suddividere alcuni termini.</span><span class="sxs-lookup"><span data-stu-id="319e6-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="319e6-111">**Centro dati** Questo è il percorso fisico in cui sono memorizzate le informazioni dall'organizzazione Office 365, ad esempio il file e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="319e6-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="319e6-112">Se si desidera realmente approfondire la conoscenza di che cosa sono i centri dati di Office 365, consultare[questo articolo](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="319e6-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="319e6-113">**Eseguire la migrazione** Ciò è molto simile a quella "spostamento".</span><span class="sxs-lookup"><span data-stu-id="319e6-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="319e6-114">In questo caso, significa che passiamo ora il Skype per utenti Business Online e le impostazioni di un datacenter a un altro più vicina per migliorare il servizio.</span><span class="sxs-lookup"><span data-stu-id="319e6-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="319e6-115">**Latenza** Si tratta di quantità di tempo necessario per accedere all'interfaccia di amministrazione di Office 365, effettuare delle impostazioni modificare e quindi salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="319e6-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="319e6-116">**ID correlazione** Si potrebbe essere visualizzato che questo indicato nel messaggio da che appena proviene.</span><span class="sxs-lookup"><span data-stu-id="319e6-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="319e6-117">Queste informazioni vengono utilizzate dal personale del supporto tecnico Microsoft per risolvere un errore.</span><span class="sxs-lookup"><span data-stu-id="319e6-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="319e6-118">Se si contatta il supporto Microsoft, potrebbe essere richiesto per l'ID correlazione.</span><span class="sxs-lookup"><span data-stu-id="319e6-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="319e6-119">In modo che cos'è questo indica che tutti si è il processo di spostamento di tutti i Skype per gli utenti aziendali Online e impostazioni in un'altra posizione più vicina al servizio.</span><span class="sxs-lookup"><span data-stu-id="319e6-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="319e6-120">Più il migliore.</span><span class="sxs-lookup"><span data-stu-id="319e6-120">The closer the better.</span></span> <span data-ttu-id="319e6-121">La buona notizia è che dopo questo breve periodo di tempo, migliorerà le Skype per il servizio di Business in linea.</span><span class="sxs-lookup"><span data-stu-id="319e6-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Servizio di migrazione in Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="319e6-123">Che cosa Skype per la funzionalità di Business Online continuerà a funzionare?</span><span class="sxs-lookup"><span data-stu-id="319e6-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="319e6-124">Sebbene non sarà in grado di accedere Skype per interfaccia di amministrazione di Business in linea, Skype seguenti per la funzionalità di Business Online continuerà a funzionare durante la migrazione:</span><span class="sxs-lookup"><span data-stu-id="319e6-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="319e6-125">Riunioni in linea</span><span class="sxs-lookup"><span data-stu-id="319e6-125">Online meetings</span></span>
    
- <span data-ttu-id="319e6-126">Informazioni sulla presenza</span><span class="sxs-lookup"><span data-stu-id="319e6-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="319e6-127">È possibile ottenere altre operazioni?</span><span class="sxs-lookup"><span data-stu-id="319e6-127">Can I get other work done?</span></span>

<span data-ttu-id="319e6-128">Verificare.</span><span class="sxs-lookup"><span data-stu-id="319e6-128">Sure.</span></span> <span data-ttu-id="319e6-129">Mentre è stiamo migrazione il Skype per il servizio di Business in linea, è comunque possibile utilizzare altre interfacce di amministrazione di Office 365 (ad esempio, l'Office 365 ed Exchange admin Center).</span><span class="sxs-lookup"><span data-stu-id="319e6-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="319e6-130">Insieme Skype per interfaccia di amministrazione di Business in linea, tuttavia, non sarà in grado di utilizzare il Skype per i cmdlet di PowerShell remoto Online Business durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="319e6-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="319e6-131">See also</span><span class="sxs-lookup"><span data-stu-id="319e6-131">Related topics</span></span>
[<span data-ttu-id="319e6-132">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="319e6-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="319e6-133">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="319e6-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a><span data-ttu-id="319e6-134">Commenti e suggerimenti?</span><span class="sxs-lookup"><span data-stu-id="319e6-134">Feedback?</span></span>
<span data-ttu-id="319e6-135">Per inviare commenti e suggerimenti prodotto o per consentire us sapere come ci si limita, vedere [Skype per commenti e suggerimenti Business](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="319e6-135">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>