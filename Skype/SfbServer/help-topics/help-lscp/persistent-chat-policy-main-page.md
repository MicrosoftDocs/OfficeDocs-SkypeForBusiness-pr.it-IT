---
title: Pagina principale Criteri Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: È possibile utilizzare la pagina Criteri di Persistent Chat del gruppo di Persistent Chat per gestire i criteri a livello globale, di pool, di sito o di utente, inclusa la configurazione del criterio globale predefinito e la creazione di uno o più criteri utente e sito aggiuntivi per la distribuzione. Se un utente è abilitato per il server Chat persistente in base ai criteri, l'ambiente del server Chat persistente verrà visualizzato nel client.
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819306"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="dc5b7-104">Pagina principale dei criteri di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="dc5b7-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="dc5b7-105">È possibile utilizzare la pagina Criteri di **Persistent Chat** del gruppo di **Persistent Chat** per gestire i criteri a livello globale, di pool, di sito o di utente, inclusa la configurazione del criterio globale predefinito e la creazione di uno o più criteri utente e sito aggiuntivi per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="dc5b7-106">Se un utente è abilitato per il server Chat persistente in base ai criteri, l'ambiente del server Chat persistente verrà visualizzato nel client.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc5b7-107">Nella topologia, i criteri del sito del server Chat persistente si applicano a livello globale, per pool di utenti, per sito dell'utente o per utente.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="dc5b7-108">Il criterio globale viene creato automaticamente quando si distribuisce il server Chat persistente e può essere configurato, ma non eliminato.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="dc5b7-109">Poiché il criterio globale si applica a tutti gli utenti, non è necessario impostarlo per utente.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="dc5b7-110">È possibile creare e configurare più criteri sito e utente che, insieme al criterio globale, abilitano gli utenti per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="dc5b7-111">I criteri del server Chat persistente del pool e del sito sostituiscono i criteri globali del server Chat persistente, ma solo per gli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="dc5b7-112">I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc5b7-113">Per configurare e utilizzare il server Chat persistente, è innanzitutto necessario utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="dc5b7-114">Per informazioni dettagliate, vedere [Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="dc5b7-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="dc5b7-115">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="dc5b7-115">Tasks that you can perform</span></span>

<span data-ttu-id="dc5b7-116">Nella pagina Criteri chat **persistente** è possibile eseguire le attività seguenti: abilitare e gestire i criteri del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="dc5b7-117">Per configurare i criteri globali per Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="dc5b7-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="dc5b7-118">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dc5b7-119">Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="dc5b7-120">Nel Pannello di controllo di Skype for Business Server fare clic su **Chat persistente** e quindi su **Criteri chat persistente.**</span><span class="sxs-lookup"><span data-stu-id="dc5b7-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="dc5b7-121">Fare clic su **Globale** nell'elenco di criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="dc5b7-122">In **Modifica Criteri Persistent Chat - Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc5b7-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="dc5b7-123">In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera usare il nome predefinito Globale.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="dc5b7-124">In **Descrizione** specificare i dettagli relativi ai criteri utente, ad esempio Criteri globali per _centralSiteName._</span><span class="sxs-lookup"><span data-stu-id="dc5b7-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="dc5b7-125">Per controllare Persistent Chat per tutti i siti e gli utenti non controllati in modo specifico tramite criteri sito o utente, selezionare o deselezionare la casella di controllo Abilita **Persistent Chat.**</span><span class="sxs-lookup"><span data-stu-id="dc5b7-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="dc5b7-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="dc5b7-127">Per creare criteri di Persistent Chat per un sito</span><span class="sxs-lookup"><span data-stu-id="dc5b7-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="dc5b7-128">Per ogni sito distribuito, è possibile creare criteri di Persistent Chat specifici del sito.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="dc5b7-129">La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="dc5b7-130">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dc5b7-131">Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="dc5b7-132">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="dc5b7-133">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="dc5b7-134">In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="dc5b7-135">In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc5b7-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="dc5b7-136">In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="dc5b7-137">In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".</span><span class="sxs-lookup"><span data-stu-id="dc5b7-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="dc5b7-138">Per controllare Persistent Chat per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="dc5b7-139">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="dc5b7-140">Per creare criteri utente per Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="dc5b7-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="dc5b7-141">Nel Pannello di controllo di Skype for Business Server definisci i criteri utente che possono essere assegnati agli utenti in **Utenti.**</span><span class="sxs-lookup"><span data-stu-id="dc5b7-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="dc5b7-142">I criteri utente hanno la precedenza sui criteri globali e di sito, ma solo per gli utenti specifici a cui tali criteri utente sono assegnati.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="dc5b7-143">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dc5b7-144">Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="dc5b7-145">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="dc5b7-146">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="dc5b7-147">In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc5b7-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="dc5b7-148">In **Nome** specificare un nome per il nuovo criterio utente.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="dc5b7-149">In **Descrizione** fornire informazioni dettagliate sui criteri utente, ad esempio i criteri di Persistent Chat per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="dc5b7-150">Per controllare Persistent Chat per tutti gli utenti non controllati in modo specifico tramite un criterio utente, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat.**</span><span class="sxs-lookup"><span data-stu-id="dc5b7-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="dc5b7-151">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="dc5b7-152">Per applicare un criterio utente di Persistent Chat a un account utente</span><span class="sxs-lookup"><span data-stu-id="dc5b7-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="dc5b7-153">Se un utente è stato abilitato per Skype for Business, è possibile applicare i criteri appropriati a utenti specifici per abilitarli o disabilitarli per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="dc5b7-154">Utilizzare la procedura descritta in questo argomento per applicare un criterio utente di Persistent Chat creato in precedenza a uno o più account utente o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="dc5b7-155">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dc5b7-156">Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="dc5b7-157">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="dc5b7-158">Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="dc5b7-159">In **Modifica utente di Lync Server** in Criteri di Chat **persistente** selezionare il criterio utente di Persistent Chat che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc5b7-160">Le **\<Automatic\>** impostazioni applicano il criterio effettivo predefinito.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="dc5b7-161">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="dc5b7-162">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dc5b7-162">Click **Commit**.</span></span>
    

