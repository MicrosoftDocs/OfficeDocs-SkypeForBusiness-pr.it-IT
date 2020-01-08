---
title: 'Lync Server 2013: Abilitare i criteri del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="8d4c4-102">Abilitare i criteri del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d4c4-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d4c4-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8d4c4-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8d4c4-104">Nel pannello di controllo di Lync Server 2013 è possibile usare la pagina dei **criteri di chat persistente** del gruppo di **chat persistente** per gestire i criteri a livello globale, di pool, di sito o utente, tra cui la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri aggiuntivi per l'utente e il sito per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="8d4c4-105">Se un utente è abilitato per i criteri per il server di chat persistente, l'ambiente del server di chat persistente viene visualizzato nel client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d4c4-106">Nella topologia i criteri del sito del server di chat persistenti si applicano globalmente, per il pool di utenti o per il sito per utente o per utente.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="8d4c4-107">Il criterio globale viene creato automaticamente quando si distribuisce il server di chat persistente e può essere configurato, ma non eliminato.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="8d4c4-108">Poiché il criterio globale si applica a tutti gli utenti, non è necessario configurarlo per utente.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="8d4c4-109">È possibile creare e configurare più criteri per il sito e gli utenti che, insieme al criterio globale, consentono agli utenti di usare il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="8d4c4-110">I criteri per i server di chat persistenti per pool e siti eseguono l'override del criterio server globale di chat persistente, ma solo per gli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="8d4c4-111">I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d4c4-112">Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="8d4c4-113">Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8d4c4-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8d4c4-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8d4c4-114">In This Section</span></span>

  - [<span data-ttu-id="8d4c4-115">Configurare i criteri globali per Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d4c4-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8d4c4-116">Creare criteri sito per chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d4c4-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8d4c4-117">Creare criteri utente per Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d4c4-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8d4c4-118">Applicare i criteri di Chat persistente a un utente o un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d4c4-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

