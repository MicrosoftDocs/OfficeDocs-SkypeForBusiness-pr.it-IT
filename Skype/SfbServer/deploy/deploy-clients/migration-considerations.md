---
title: Considerazioni sulla migrazione di Skype room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più versioni di Skype for Business Server e Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805786"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="33c67-103">Considerazioni sulla migrazione di Skype room System</span><span class="sxs-lookup"><span data-stu-id="33c67-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="33c67-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più versioni di Skype for Business Server e Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33c67-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="33c67-105">Considerazioni sulla migrazione</span><span class="sxs-lookup"><span data-stu-id="33c67-105">Migration considerations</span></span>

<span data-ttu-id="33c67-106">In questa sezione vengono fornite indicazioni per la distribuzione di Skype room System in un ambiente multi-pool che include diverse versioni di Skype for Business Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33c67-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="33c67-107">Il componente User Replicator (UR) in Lync Server Ottiene gli oggetti utente da Active Directory e li inserisce nel database di SQL Server back-end di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33c67-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="33c67-108">Solo l'UR in Lync Server 2013 è a conoscenza degli oggetti del sistema in sala Skype.</span><span class="sxs-lookup"><span data-stu-id="33c67-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="33c67-109">L'UR nelle versioni precedenti di Lync Server e Office Communications Server non rileva gli attributi di Active Directory che designano gli oggetti di LRS e pertanto non li ha informati.</span><span class="sxs-lookup"><span data-stu-id="33c67-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="33c67-110">Se un account di sistema di Skype room cerca di accedere a Lync e esegue l'individuazione automatica in base al record SRV o a un record DNS, e se tali account puntano a una versione precedente di Lync Server o Office Communications Server, LRS riceverà una risposta di 404 non trovata dal pool legacy.</span><span class="sxs-lookup"><span data-stu-id="33c67-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="33c67-111">Il pool legacy non sarà in grado di reindirizzare Skype room System al relativo pool Lync Server 2013 Home.</span><span class="sxs-lookup"><span data-stu-id="33c67-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="33c67-112">È possibile risolvere il problema con le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33c67-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="33c67-113">Posizionare il record SRV di individuazione automatica (_sipinternaltls. _tcp. contoso. com) nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33c67-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="33c67-114">Se la prima opzione non è possibile, è necessario configurare manualmente LRS e fornire l'indirizzo del pool di Lync Server 2013 direttamente configurarlo nell'applicazione console del sistema Skype room.</span><span class="sxs-lookup"><span data-stu-id="33c67-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="33c67-115">Se il sistema di Skype Room è distribuito all'esterno della rete aziendale e un server perimetrale di Lync è stato distribuito e configurato in modo da puntare a un pool o a un Director legacy, è necessario un sito server perimetrale secondario, che punta al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33c67-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="33c67-116">Per ulteriori informazioni sulla distribuzione di un server perimetrale secondario, vedere la documentazione relativa alla distribuzione di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="33c67-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="33c67-117">Interoperabilità dei sistemi Skype room con un pool Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="33c67-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="33c67-118">Durante la migrazione, se un utente che si trova in un pool di Lync Server 2010 pianifica una riunione e invita l'account del sistema di chat room Skype, il client del sistema della sala Skype avrà una funzionalità limitata durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="33c67-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="33c67-119">Quando il client del sistema Skype room si unisce a una conferenza telefonica pianificata che è stata organizzata da un utente ospitato in Lync Server 2010, Skype room System ha le seguenti limitazioni in-meeting:</span><span class="sxs-lookup"><span data-stu-id="33c67-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="33c67-120">Skype room System non è in grado di visualizzare la raccolta video multi-view.</span><span class="sxs-lookup"><span data-stu-id="33c67-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="33c67-121">Se il client del sistema Skype Room è il relatore, non è in grado di applicare il blocco video ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="33c67-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="33c67-122">Skype room System non è in grado di visualizzare la risoluzione video 1080p (in ingresso o in uscita), anche se i criteri di conferenza di Lync Server 2013 lo consentono, a causa delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33c67-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="33c67-123">Lync Server 2010 non supporta la risoluzione 1080p.</span><span class="sxs-lookup"><span data-stu-id="33c67-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="33c67-124">Skype room System è sempre limitato dai criteri di conferenza dell'organizzatore per la risoluzione video.</span><span class="sxs-lookup"><span data-stu-id="33c67-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="33c67-125">Pertanto, anche se il pool Lync 2010 supporta la risoluzione 720p, Skype room System non sarà in grado di trarre vantaggio dalla risoluzione 720p, purché il criterio dell'organizzatore non lo supporti.</span><span class="sxs-lookup"><span data-stu-id="33c67-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="33c67-126">I client Lync 2013 rilevano la presenza di LRS nella sala riunioni e si disattivano automaticamente per evitare l'eco nella sala riunioni fisica.</span><span class="sxs-lookup"><span data-stu-id="33c67-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="33c67-127">Questa funzionalità non funziona nelle riunioni ospitate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="33c67-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="33c67-128">Sono presenti limitazioni sulle prestazioni di condivisione del desktop per le riunioni ospitate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="33c67-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="33c67-129">Gli utenti non saranno in grado di partecipare a riunioni private (limitate) ospitate su Lync 2010 con Skype room System.</span><span class="sxs-lookup"><span data-stu-id="33c67-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

