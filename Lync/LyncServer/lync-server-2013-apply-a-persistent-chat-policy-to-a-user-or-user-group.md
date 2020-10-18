---
title: 'Lync Server 2013: applicazione di un criterio di chat persistente a un utente o a un gruppo di utenti'
description: 'Lync Server 2013: applicare un criterio di chat persistente a un utente o a un gruppo di utenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 168fa795303bbcf3f3eef4bfc817aa98d763d1ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573482"
---
# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="e0913-103">Applicare un criterio di chat persistente a un utente o a un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0913-103">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0913-104">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e0913-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e0913-105">Se un utente è stato abilitato per Lync Server 2013, è possibile applicare criteri adeguati a utenti specifici per abilitarli o disabilitarli per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e0913-105">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0913-106">Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="e0913-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="e0913-107">Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e0913-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e0913-108">Per configurare le impostazioni di configurazione del server Chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e0913-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e0913-109">Utilizzare la procedura descritta in questo argomento per applicare un criterio utente di chat persistente creato in precedenza a uno o più account utente o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="e0913-109">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="e0913-110">Per applicare un criterio utente di chat persistente a un account utente</span><span class="sxs-lookup"><span data-stu-id="e0913-110">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="e0913-111">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e0913-111">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e0913-112">Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="e0913-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="e0913-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e0913-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e0913-114">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="e0913-114">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="e0913-115">Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e0913-115">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e0913-116">In **modifica utente di Lync Server** in **criteri di Persistent Chat**Selezionare il criterio utente di chat persistente che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="e0913-116">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0913-117">Le impostazioni <STRONG> &lt; automatiche &gt; </STRONG> applicano il criterio effettivo predefinito.</span><span class="sxs-lookup"><span data-stu-id="e0913-117">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="e0913-118">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="e0913-118">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="e0913-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e0913-119">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

