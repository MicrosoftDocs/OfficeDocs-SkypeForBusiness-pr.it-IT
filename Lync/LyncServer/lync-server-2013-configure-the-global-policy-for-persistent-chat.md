---
title: 'Lync Server 2013: Configurare i criteri globali per Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49fb5f329851436e503a9e3e42e144353b70017f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="e298b-102">Configurare i criteri globali per Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e298b-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e298b-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e298b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e298b-104">È possibile usare i criteri globali predefiniti per abilitare le impostazioni della chat persistente per tutti gli utenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e298b-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="e298b-105">È anche possibile specificare criteri aggiuntivi per i siti e gli utenti per controllare se la chat persistente è abilitata o disabilitata per utenti e siti specifici.</span><span class="sxs-lookup"><span data-stu-id="e298b-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="e298b-106">Non è possibile eliminare il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="e298b-106">You cannot delete the global policy.</span></span> <span data-ttu-id="e298b-107">Se si tenta di eliminarlo, la configurazione viene reimpostata sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e298b-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e298b-108">Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="e298b-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="e298b-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e298b-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e298b-110">Per configurare le impostazioni di configurazione del server di chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server di chat permanenti globalmente o per il pool di server di chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="e298b-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="e298b-111">Per configurare il criterio globale per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="e298b-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="e298b-112">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e298b-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e298b-113">Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="e298b-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="e298b-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="e298b-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e298b-115">È anche possibile usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e298b-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e298b-116">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente con i cmdlet di Windows PowerShell</A> nella documentazione di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e298b-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="e298b-117">Nel pannello di controllo di Lync Server fare clic su **chat persistente**e quindi su **criteri di chat permanenti**.</span><span class="sxs-lookup"><span data-stu-id="e298b-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="e298b-118">Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e298b-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e298b-119">In **Modifica Criteri Chat persistente- Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e298b-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="e298b-120">In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera utilizzare il nome predefinito Globale.</span><span class="sxs-lookup"><span data-stu-id="e298b-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="e298b-121">In **Descrizione**specificare i dettagli relativi al criterio utente (ad esempio, criteri globali per centralSiteName).</span><span class="sxs-lookup"><span data-stu-id="e298b-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="e298b-122">Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="e298b-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="e298b-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e298b-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

