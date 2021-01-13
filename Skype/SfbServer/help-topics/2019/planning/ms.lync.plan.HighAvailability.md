---
title: Disponibilità elevata (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Lo schema di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819796"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="512cd-104">Disponibilità elevata (strumento di pianificazione)</span><span class="sxs-lookup"><span data-stu-id="512cd-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="512cd-105">Lo schema di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server si basa sulla ridondanza del server tramite pool.</span><span class="sxs-lookup"><span data-stu-id="512cd-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="512cd-106">In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.</span><span class="sxs-lookup"><span data-stu-id="512cd-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="512cd-107">Skype for Business Server richiede almeno due front end server per poter abilitare la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="512cd-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="512cd-108">Lo strumento di pianificazione utilizza i seguenti criteri per determinare se verranno aggiunti altri server per supportare la disponibilità elevata:</span><span class="sxs-lookup"><span data-stu-id="512cd-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="512cd-109">Se la distribuzione contiene due o più Front End Server, lo strumento di pianificazione non aggiunge un server aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="512cd-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="512cd-110">Se la distribuzione contiene server perimetrale, viene aggiunto un altro server.</span><span class="sxs-lookup"><span data-stu-id="512cd-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="512cd-111">Se la distribuzione contiene chat persistente, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool.</span><span class="sxs-lookup"><span data-stu-id="512cd-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="512cd-112">Ad esempio, se nella distribuzione sono già presenti quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server), ma manterrà un singolo pool.</span><span class="sxs-lookup"><span data-stu-id="512cd-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="512cd-113">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="512cd-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="512cd-114">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="512cd-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="512cd-115">Per ulteriori informazioni, vedere [aggiornamento di Skype for business to Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="512cd-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="512cd-116">Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a utilizzare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="512cd-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="512cd-117">Lo strumento di pianificazione aggiunge anche un database SQL mirror per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="512cd-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="512cd-118">Ad esempio, se è presente un database front-end di SQL Server, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo e lo definirà come "database SQL front-end mirror.</span><span class="sxs-lookup"><span data-stu-id="512cd-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="512cd-119">Per ulteriori informazioni sulla preparazione dell'ambiente per la disponibilità elevata, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="512cd-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

