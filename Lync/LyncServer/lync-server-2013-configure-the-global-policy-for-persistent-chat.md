---
title: 'Lync Server 2013: configurare i criteri globali per la chat persistente'
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
ms.openlocfilehash: b9c4596749e1c4bf4c9f4002b33234c83afa1fd5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="92767-102">Configurare il criterio globale per la chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92767-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92767-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="92767-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="92767-104">È possibile utilizzare il criterio globale predefinito per abilitare le impostazioni di chat persistente per tutti gli utenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="92767-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="92767-105">È inoltre possibile specificare criteri aggiuntivi per i siti e gli utenti per controllare se la chat persistente è abilitata o disabilitata per utenti e siti specifici.</span><span class="sxs-lookup"><span data-stu-id="92767-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="92767-106">Non è possibile eliminare i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="92767-106">You cannot delete the global policy.</span></span> <span data-ttu-id="92767-107">Se si tenta l'eliminazione, la configurazione viene reimpostata sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="92767-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92767-108">Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="92767-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="92767-109">Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="92767-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="92767-110">Per configurare le impostazioni di configurazione del server Chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="92767-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="92767-111">Per configurare i criteri globali per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="92767-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="92767-112">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="92767-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92767-113">Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="92767-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="92767-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="92767-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="92767-115">È inoltre possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92767-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="92767-116">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="92767-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="92767-117">Nel pannello di controllo di Lync Server, fare clic su **Persistent Chat**e quindi su **criteri di chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="92767-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="92767-118">Fare clic su **Globale** nell'elenco di criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="92767-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="92767-119">In **Modifica Criteri Persistent Chat - Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="92767-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="92767-120">In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera usare il nome predefinito Globale.</span><span class="sxs-lookup"><span data-stu-id="92767-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="92767-121">In **Descrizione**fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri globali per NomeSitoCentrale ".</span><span class="sxs-lookup"><span data-stu-id="92767-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="92767-122">Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="92767-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="92767-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="92767-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

