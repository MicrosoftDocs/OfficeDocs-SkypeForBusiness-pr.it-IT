---
title: 'Lync Server 2013: abilitare i criteri del server Chat persistente'
description: 'Lync Server 2013: abilitare i criteri del server Chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58da577679795f00492af72b43ca72106d40f4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547882"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="349e6-103">Abilitare i criteri del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349e6-103">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="349e6-104">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="349e6-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="349e6-105">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **criteri di chat persistente** del gruppo di **chat persistente** per gestire i criteri a livello globale, di pool, di sito o di utente, inclusa la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri di sito e utente aggiuntivi per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="349e6-105">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="349e6-106">Se un utente è abilitato per il server Chat persistente in base ai criteri, l'ambiente del server Chat persistente viene visualizzato nel client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="349e6-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="349e6-107">Nella topologia, i criteri sito del server Chat persistente si applicano a livello globale, per pool di utenti o per sito utente o per utente.</span><span class="sxs-lookup"><span data-stu-id="349e6-107">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="349e6-108">Il criterio globale viene creato automaticamente quando si distribuisce il server Chat persistente ed è possibile configurarlo, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="349e6-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="349e6-109">Poiché il criterio globale si applica a tutti gli utenti, non è necessario configurarlo per utente.</span><span class="sxs-lookup"><span data-stu-id="349e6-109">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="349e6-110">È possibile creare e configurare più criteri di sito e utente che, insieme ai criteri globali, consentono agli utenti di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="349e6-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="349e6-111">I criteri del server Chat persistente per i pool e i siti eseguono l'override del criterio del server Chat persistente globale, ma solo per gli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="349e6-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="349e6-112">I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="349e6-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="349e6-113">Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="349e6-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="349e6-114">Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="349e6-114">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="349e6-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="349e6-115">In This Section</span></span>

  - [<span data-ttu-id="349e6-116">Configurare il criterio globale per la chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349e6-116">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="349e6-117">Creare criteri sito per chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349e6-117">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="349e6-118">Creare un criterio utente per la chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349e6-118">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="349e6-119">Applicare un criterio di chat persistente a un utente o a un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349e6-119">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

