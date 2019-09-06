---
title: Considerazioni sulla migrazione di Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente che include più versioni di Skype for Business Server e Lync Server.
ms.openlocfilehash: 6524a7312644ec306185b952caf17818d29344af
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774674"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="056dd-103">Considerazioni sulla migrazione di Skype room System</span><span class="sxs-lookup"><span data-stu-id="056dd-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="056dd-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente che include più versioni di Skype for Business Server e Lync Server.</span><span class="sxs-lookup"><span data-stu-id="056dd-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="056dd-105">Considerazioni sulla migrazione</span><span class="sxs-lookup"><span data-stu-id="056dd-105">Migration considerations</span></span>

<span data-ttu-id="056dd-106">Questa sezione fornisce indicazioni per la distribuzione di Skype room System in un ambiente con più pool che include versioni diverse di Skype for Business Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="056dd-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="056dd-107">Il componente User Replicator (UR) in Lync Server Ottiene gli oggetti utente da Active Directory e li inserisce nel database di SQL Server back-end di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="056dd-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="056dd-108">Solo l'UR in Lync Server 2013 è a conoscenza degli oggetti di sistema room Skype.</span><span class="sxs-lookup"><span data-stu-id="056dd-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="056dd-109">L'UR nelle versioni precedenti di Lync Server e Office Communications Server non rileva gli attributi di Active Directory che designano gli oggetti LRS e quindi non ne erano a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="056dd-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="056dd-110">Se un account di sistema per Skype room cerca di accedere a Lync e esegue l'individuazione automatica in base al record SRV o al DNS un record Cerca e se questi account puntano a una versione precedente di Lync Server o Office Communications Server, LRS riceverà una risposta di 404 non trovata da  il pool legacy.</span><span class="sxs-lookup"><span data-stu-id="056dd-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="056dd-111">Il pool legacy non sarà in grado di reindirizzare Skype room System al proprio pool di Lync Server 2013 Home.</span><span class="sxs-lookup"><span data-stu-id="056dd-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="056dd-112">Per risolvere il problema, è possibile usare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="056dd-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="056dd-113">Posizionare il record SRV di individuazione automatica (_sipinternaltls. _tcp. contoso. com) nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="056dd-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="056dd-114">Se la prima opzione non è possibile, è necessario configurare manualmente LRS e specificare l'indirizzo del pool di Lync Server 2013, configurando direttamente l'applicazione console di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="056dd-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="056dd-115">Se il sistema room Skype è distribuito all'esterno della rete aziendale e un Edge Server Lync è stato distribuito e configurato in modo che punti a un pool o a un amministratore legacy, è necessario un sito Edge Server secondario, che punta al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="056dd-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="056dd-116">Per altre informazioni sulla distribuzione di un server perimetrale secondario, vedere la documentazione sulla distribuzione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="056dd-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="056dd-117">Interoperabilità del sistema Skype room con un pool di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="056dd-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="056dd-118">Durante la migrazione, se un utente che si trova in un pool di Lync Server 2010 pianifica una riunione e invita l'account di sistema room Skype, il client di sistema room Skype avrà funzionalità limitate durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="056dd-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="056dd-119">Quando il client della sala di Skype room si unisce a una conferenza telefonica pianificata organizzata da un utente ospitato in Lync Server 2010, Skype room System ha le seguenti limitazioni per le riunioni:</span><span class="sxs-lookup"><span data-stu-id="056dd-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="056dd-120">Skype room System non è in grado di visualizzare la raccolta di video con visualizzazione multipla.</span><span class="sxs-lookup"><span data-stu-id="056dd-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="056dd-121">Se il client del sistema di chat room Skype è il relatore, non può applicare il blocco video ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="056dd-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="056dd-122">Skype room System non può visualizzare la risoluzione video 1080p (in ingresso o in uscita), anche se il criterio di conferenza di Lync Server 2013 lo consente, a causa delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="056dd-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="056dd-123">Lync Server 2010 non supporta la risoluzione 1080p.</span><span class="sxs-lookup"><span data-stu-id="056dd-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="056dd-124">Skype room System è sempre limitato dai criteri di conferenza dell'organizzatore per la risoluzione video.</span><span class="sxs-lookup"><span data-stu-id="056dd-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="056dd-125">Pertanto, anche se il pool di Lync 2010 supporta la risoluzione 720p, Skype room System non sarà in grado di sfruttare la risoluzione 720p purché il criterio dell'organizzatore non lo supporti.</span><span class="sxs-lookup"><span data-stu-id="056dd-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="056dd-126">I client Lync 2013 rilevano la presenza di LRS nella sala riunioni e si riattivano automaticamente per evitare l'eco nella sala riunioni fisica.</span><span class="sxs-lookup"><span data-stu-id="056dd-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="056dd-127">Questa caratteristica non funziona nelle riunioni ospitate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="056dd-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="056dd-128">Esistono limitazioni sulle prestazioni di condivisione desktop per le riunioni ospitate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="056dd-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="056dd-129">Gli utenti non potranno partecipare a riunioni private (con restrizioni) ospitate in Lync 2010 con Skype room System.</span><span class="sxs-lookup"><span data-stu-id="056dd-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

