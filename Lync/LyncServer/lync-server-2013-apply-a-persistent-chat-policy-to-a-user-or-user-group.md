---
title: 'Lync Server 2013: Applicare i criteri di Chat persistente a un utente o un gruppo di utenti'
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
ms.openlocfilehash: 726fe9a5fa20a52f770cd5bab475de5731562989
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="da423-102">Applicare i criteri di Chat persistente a un utente o un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da423-102">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da423-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="da423-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="da423-104">Se un utente è stato abilitato per Lync Server 2013, è possibile applicare criteri appropriati a utenti specifici per abilitarli o disabilitarli per il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="da423-104">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da423-105">Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="da423-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="da423-106">Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="da423-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="da423-107">Per configurare le impostazioni di configurazione del server di chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server di chat permanenti globalmente o per il pool di server di chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="da423-107">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="da423-108">Usare la procedura descritta in questo argomento per applicare un criterio utente di chat persistente creato in precedenza a uno o più account utente o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="da423-108">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="da423-109">Per applicare un criterio utente di chat persistente a un account utente</span><span class="sxs-lookup"><span data-stu-id="da423-109">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="da423-110">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="da423-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="da423-111">Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="da423-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="da423-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="da423-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="da423-113">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="da423-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="da423-114">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="da423-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="da423-115">In **modifica utenti di Lync Server** in **criteri di chat persistenti**Selezionare i criteri utente per la chat persistente che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="da423-115">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da423-116">Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano i criteri effettivi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="da423-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="da423-117">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="da423-117">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="da423-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="da423-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

