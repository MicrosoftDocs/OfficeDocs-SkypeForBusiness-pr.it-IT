---
title: Disponibilità elevata (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.
ms.openlocfilehash: 36869cedb2443d13774e8646b72a51a039683f16
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36196001"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="8785b-104">Disponibilità elevata (strumento di pianificazione)</span><span class="sxs-lookup"><span data-stu-id="8785b-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="8785b-105">Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pooling.</span><span class="sxs-lookup"><span data-stu-id="8785b-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="8785b-106">Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.</span><span class="sxs-lookup"><span data-stu-id="8785b-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="8785b-107">Skype for Business Server richiede almeno due server front-end per consentire l'elevata disponibilità.</span><span class="sxs-lookup"><span data-stu-id="8785b-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="8785b-108">Lo strumento di pianificazione usa i criteri seguenti per determinare se verranno aggiunti server aggiuntivi per supportare la disponibilità elevata:</span><span class="sxs-lookup"><span data-stu-id="8785b-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="8785b-109">Se la distribuzione contiene due o più server front-end, lo strumento di pianificazione non aggiunge un server aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="8785b-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="8785b-110">Se la distribuzione contiene Edge Server, viene aggiunto un altro server.</span><span class="sxs-lookup"><span data-stu-id="8785b-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="8785b-111">Se la distribuzione contiene una chat persistente, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool.</span><span class="sxs-lookup"><span data-stu-id="8785b-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="8785b-112">Ad esempio, se la distribuzione contiene già quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server), ma manterrà un singolo pool.</span><span class="sxs-lookup"><span data-stu-id="8785b-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="8785b-113">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8785b-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8785b-114">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="8785b-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="8785b-115">Per altre informazioni, Vedi [aggiornamento di Skype for business a Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="8785b-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="8785b-116">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8785b-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="8785b-117">Lo strumento di pianificazione aggiunge anche un database SQL mirror per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="8785b-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="8785b-118">Ad esempio, se c'è un database di SQL Server front-end, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo nome e lo definirà come "database SQL front-end mirror".</span><span class="sxs-lookup"><span data-stu-id="8785b-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="8785b-119">Per altre informazioni su come preparare l'ambiente per una disponibilità elevata, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8785b-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

