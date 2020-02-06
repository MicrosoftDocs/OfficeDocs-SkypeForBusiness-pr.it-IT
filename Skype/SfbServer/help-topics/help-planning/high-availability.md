---
title: Disponibilità elevata (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
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
description: Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.
ms.openlocfilehash: 1d82174e8dc1314deaf81708c70054a4d602085b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821438"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="d15b7-104">Disponibilità elevata (strumento di pianificazione)</span><span class="sxs-lookup"><span data-stu-id="d15b7-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="d15b7-105">Il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Skype for Business Server 2015 si basa sulla ridondanza del server tramite pooling.</span><span class="sxs-lookup"><span data-stu-id="d15b7-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="d15b7-106">Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.</span><span class="sxs-lookup"><span data-stu-id="d15b7-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="d15b7-107">Skype for Business Server 2015 richiede almeno due server front-end per consentire l'elevata disponibilità.</span><span class="sxs-lookup"><span data-stu-id="d15b7-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="d15b7-108">Lo strumento di pianificazione usa i criteri seguenti per determinare se verranno aggiunti server aggiuntivi per supportare la disponibilità elevata:</span><span class="sxs-lookup"><span data-stu-id="d15b7-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="d15b7-109">Se la distribuzione contiene due o più server front-end, lo strumento di pianificazione non aggiunge un server aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="d15b7-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="d15b7-110">Se la distribuzione contiene Edge Server, viene aggiunto un altro server.</span><span class="sxs-lookup"><span data-stu-id="d15b7-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="d15b7-111">Se la distribuzione contiene una chat persistente, lo strumento di pianificazione aggiungerà un server aggiuntivo, ma non aumenterà il numero del pool.</span><span class="sxs-lookup"><span data-stu-id="d15b7-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="d15b7-112">Ad esempio, se la distribuzione contiene già quattro server, lo strumento di pianificazione suggerirà di aggiungere un altro server (per un totale di cinque server), ma manterrà un singolo pool.</span><span class="sxs-lookup"><span data-stu-id="d15b7-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="d15b7-113">Lo strumento di pianificazione aggiunge anche un database SQL mirror per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="d15b7-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="d15b7-114">Ad esempio, se c'è un database di SQL Server front-end, lo strumento di pianificazione aggiungerà l'altro database come database mirror per questo nome e lo definirà come "database SQL front-end mirror".</span><span class="sxs-lookup"><span data-stu-id="d15b7-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="d15b7-115">Per altre informazioni su come preparare l'ambiente per una disponibilità elevata, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d15b7-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

