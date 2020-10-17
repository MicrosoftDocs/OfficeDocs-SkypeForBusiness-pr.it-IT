---
title: 'Lync Server 2013: creare un criterio utente per la chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dba93ca943c16caa6ee4982533e59c958e60ffc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501843"
---
# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="47b48-102">Creare un criterio utente per la chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47b48-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47b48-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="47b48-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="47b48-104">Nel pannello di controllo di Lync Server, è possibile definire i criteri utente che possono essere assegnati agli utenti in **utenti**.</span><span class="sxs-lookup"><span data-stu-id="47b48-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="47b48-105">I criteri utente hanno la precedenza sui criteri globali e di sito, ma solo per gli utenti specifici a cui tali criteri utente sono assegnati.</span><span class="sxs-lookup"><span data-stu-id="47b48-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47b48-106">Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="47b48-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="47b48-107">Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="47b48-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="47b48-108">Per configurare le impostazioni di configurazione del server Chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="47b48-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="47b48-109">Per creare un criterio utente per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="47b48-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="47b48-110">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="47b48-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="47b48-111">Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="47b48-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="47b48-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="47b48-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="47b48-113">È inoltre possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47b48-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="47b48-114">Vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="47b48-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="47b48-115">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="47b48-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="47b48-116">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="47b48-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="47b48-117">In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47b48-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="47b48-118">In **Nome** specificare un nome per il nuovo criterio utente.</span><span class="sxs-lookup"><span data-stu-id="47b48-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="47b48-119">In **Descrizione**fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri di chat persistente per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="47b48-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="47b48-120">Per controllare la chat persistente per tutti gli utenti non controllati in modo specifico tramite criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="47b48-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="47b48-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="47b48-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

