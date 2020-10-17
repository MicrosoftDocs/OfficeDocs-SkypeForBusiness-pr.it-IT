---
title: 'Lync Server 2013: creare i criteri di routing VoIP per gli utenti di succursale'
description: 'Lync Server 2013: creare i criteri di routing VoIP per gli utenti di succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c39cff86d9ede957fa99e7955d8a87172380f963
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551082"
---
# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="671a5-103">Creare i criteri di routing VoIP per gli utenti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671a5-103">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="671a5-104">_**Ultimo argomento modificato:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="671a5-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="671a5-105">È consigliabile creare un criterio VoIP (Voice Over IP) distinto per gli utenti dei siti derivati.</span><span class="sxs-lookup"><span data-stu-id="671a5-105">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="671a5-106">Questo criterio deve contenere route per l'uscita dal gateway Survivable Branch Appliance o il gateway esterno Survivable Branch Server e le route di backup per l'uscita da un gateway nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="671a5-106">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="671a5-107">Indipendentemente dalla posizione in cui l'utente è registrato, sia nel registrar del Survivable Branch Appliance o Survivable Branch Server o nel cluster di registrazione di backup nel sito centrale, i criteri VoIP dell'utente sono sempre attivi.</span><span class="sxs-lookup"><span data-stu-id="671a5-107">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="671a5-108">Per configurare i criteri di routing VoIP per gli utenti dei siti di succursale</span><span class="sxs-lookup"><span data-stu-id="671a5-108">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="671a5-109">Creare un dial plan a livello utente e assegnarlo agli utenti dei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="671a5-109">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="671a5-110">Per ulteriori informazioni, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="671a5-110">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="671a5-111">Assegnare regole di normalizzazione corrispondenti alle abitudini degli utenti del sito in relazione alla composizione dei numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="671a5-111">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="671a5-112">Se l'utente Survivable Branch Appliance o Survivable Branch Server non riesce a eseguire il failover del pool di registrazione di backup nel sito centrale, lo stesso dial plan sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="671a5-112">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="671a5-113">Per ulteriori informazioni, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="671a5-113">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="671a5-114">Configurare una route vocale che egresses dal gateway Survivable Branch Appliance o dal gateway esterno Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="671a5-114">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="671a5-115">Per ulteriori informazioni, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="671a5-115">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="671a5-116">Impostare una route di chiamata di backup nel Survivable Branch Appliance o Survivable Branch Server gateway in modo che punti al pool di registrazione di backup (collocato con Mediation Server) nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="671a5-116">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="671a5-117">Vedere la documentazione relativa a Survivable Branch Appliance o Survivable Branch Server vendor.</span><span class="sxs-lookup"><span data-stu-id="671a5-117">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="671a5-118">Questa configurazione del percorso di chiamata di backup consente di garantire che le chiamate in ingresso all'utente di succursale funzionino quando il Survivable Branch Appliance o il Survivable Branch Server non è disponibile, ad esempio se è inattivo per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="671a5-118">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="671a5-119">Se il servizio di registrazione e Mediation Server nel Survivable Branch Appliance o Survivable Branch Server non sono disponibili e l'utente è registrato con il pool di registrazione di backup nel sito centrale, le chiamate in entrata possono comunque essere instradate all'utente.</span><span class="sxs-lookup"><span data-stu-id="671a5-119">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="671a5-120">**Passaggio successivo**: [configurare le impostazioni di reinstradamento della segreteria telefonica in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="671a5-120">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

