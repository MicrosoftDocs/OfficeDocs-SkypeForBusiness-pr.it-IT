---
title: 'Lync Server 2013: Creare criteri sito per chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4feb77aa99e1fe3018a469e61e9688a87cf81760
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="691d2-102">Creare criteri sito per chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="691d2-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="691d2-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="691d2-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="691d2-104">Per ogni sito distribuito, è possibile creare un criterio di chat persistente specifico del sito.</span><span class="sxs-lookup"><span data-stu-id="691d2-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="691d2-105">La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono.</span><span class="sxs-lookup"><span data-stu-id="691d2-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="691d2-106">Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="691d2-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="691d2-107">Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="691d2-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="691d2-108">Per configurare le impostazioni di configurazione del server di chat persistente, vedere <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurare le opzioni del server di chat permanenti globalmente o per il pool di server di chat persistente in Lync server 2013</A> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="691d2-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="691d2-109">Per creare criteri di chat persistenti per un sito</span><span class="sxs-lookup"><span data-stu-id="691d2-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="691d2-110">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="691d2-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="691d2-111">Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="691d2-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="691d2-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="691d2-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="691d2-113">Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Criteri di Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="691d2-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="691d2-114">È anche possibile usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="691d2-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="691d2-115">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="691d2-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="691d2-116">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="691d2-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="691d2-117">In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="691d2-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="691d2-118">In **Nuovi criteri Chat persistente** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="691d2-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="691d2-119">In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.</span><span class="sxs-lookup"><span data-stu-id="691d2-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="691d2-120">In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".</span><span class="sxs-lookup"><span data-stu-id="691d2-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="691d2-121">Per controllare Chat persistente per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="691d2-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="691d2-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="691d2-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

