---
title: 'Lync Server 2013: creare i criteri di routing VoIP per gli utenti di succursale'
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
ms.openlocfilehash: 308c4ad3a7371c9a27f668b79623a512227623b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="a0c8d-102">Creare i criteri di routing VoIP per gli utenti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0c8d-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0c8d-103">_**Ultimo argomento modificato:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="a0c8d-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="a0c8d-104">È consigliabile creare un criterio VoIP (Voice Over IP) distinto per gli utenti dei siti derivati.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="a0c8d-105">Questo criterio deve contenere route per l'uscita dal gateway Survivable Branch Appliance o il gateway esterno Survivable Branch Server e le route di backup per l'uscita da un gateway nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="a0c8d-106">Indipendentemente dalla posizione in cui l'utente è registrato, sia nel registrar del Survivable Branch Appliance o Survivable Branch Server o nel cluster di registrazione di backup nel sito centrale, i criteri VoIP dell'utente sono sempre attivi.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="a0c8d-107">Per configurare i criteri di routing VoIP per gli utenti dei siti di succursale</span><span class="sxs-lookup"><span data-stu-id="a0c8d-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="a0c8d-108">Creare un dial plan a livello utente e assegnarlo agli utenti dei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="a0c8d-109">Per ulteriori informazioni, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="a0c8d-110">Assegnare regole di normalizzazione corrispondenti alle abitudini degli utenti del sito in relazione alla composizione dei numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="a0c8d-111">Se l'utente Survivable Branch Appliance o Survivable Branch Server non riesce a eseguire il failover del pool di registrazione di backup nel sito centrale, lo stesso dial plan sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="a0c8d-112">Per ulteriori informazioni, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="a0c8d-113">Configurare una route vocale che egresses dal gateway Survivable Branch Appliance o dal gateway esterno Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="a0c8d-114">Per ulteriori informazioni, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="a0c8d-115">Impostare una route di chiamata di backup nel Survivable Branch Appliance o Survivable Branch Server gateway in modo che punti al pool di registrazione di backup (collocato con Mediation Server) nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="a0c8d-116">Vedere la documentazione relativa a Survivable Branch Appliance o Survivable Branch Server vendor.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a0c8d-117">Questa configurazione del percorso di chiamata di backup consente di garantire che le chiamate in ingresso all'utente di succursale funzionino quando il Survivable Branch Appliance o il Survivable Branch Server non è disponibile, ad esempio se è inattivo per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="a0c8d-118">Se il servizio di registrazione e Mediation Server nel Survivable Branch Appliance o Survivable Branch Server non sono disponibili e l'utente è registrato con il pool di registrazione di backup nel sito centrale, le chiamate in entrata possono comunque essere instradate all'utente.</span><span class="sxs-lookup"><span data-stu-id="a0c8d-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="a0c8d-119">**Passaggio successivo**: [configurare le impostazioni di reinstradamento della segreteria telefonica in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a0c8d-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

