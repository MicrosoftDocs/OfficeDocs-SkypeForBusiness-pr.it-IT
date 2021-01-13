---
title: Criteri Persistent Chat
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
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: È possibile utilizzare la pagina Criteri di chat persistente del gruppo di chat persistente per gestire i criteri a livello globale, del pool, del sito o dell'utente, inclusa la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri aggiuntivi per l'utente e il sito per la distribuzione. Se il server Chat persistente è abilitato per un utente in base ai criteri, l'ambiente del server Chat persistente viene visualizzato nel client.
ms.openlocfilehash: e7148530f571a46937ee8d8a3bf44315ac692eb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819296"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="8e3c1-104">Criteri Chat persistente</span><span class="sxs-lookup"><span data-stu-id="8e3c1-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="8e3c1-105">È possibile utilizzare la pagina **criteri di chat persistente** del gruppo di **chat persistente** per gestire i criteri a livello globale, del pool, del sito o dell'utente, inclusa la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri aggiuntivi per l'utente e il sito per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="8e3c1-106">Se il server Chat persistente è abilitato per un utente in base ai criteri, l'ambiente del server Chat persistente viene visualizzato nel client.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="8e3c1-107">Il criterio globale viene creato automaticamente quando si distribuisce il server Chat persistente ed è possibile configurarlo, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="8e3c1-108">Poiché il criterio globale si applica a tutti gli utenti, non è necessario impostarlo per utente.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="8e3c1-109">È possibile creare e configurare più criteri di sito e utente che, insieme ai criteri globali, consentono agli utenti di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="8e3c1-110">I criteri del server Chat persistente per i pool e i siti eseguono l'override del criterio del server Chat persistente globale, ma solo per gli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="8e3c1-111">I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e3c1-112">Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="8e3c1-113">Per ulteriori informazioni, vedere [aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="8e3c1-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="8e3c1-114">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="8e3c1-114">Tasks that you can perform</span></span>

<span data-ttu-id="8e3c1-115">Nella pagina **criteri di chat persistente** è possibile eseguire le attività seguenti: attivazione dei criteri del server Chat persistente. gestire i criteri del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="8e3c1-116">Per configurare i criteri globali per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="8e3c1-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="8e3c1-117">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8e3c1-118">Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8e3c1-119">Nel pannello di controllo di Skype for Business Server, fare clic su **Persistent Chat** e quindi su **criteri di chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="8e3c1-120">Fare clic su **Globale** nell'elenco di criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8e3c1-121">In **Modifica Criteri Persistent Chat - Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e3c1-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="8e3c1-122">In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera usare il nome predefinito Globale.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="8e3c1-123">In **Descrizione** fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri globali per  _NomeSitoCentrale "_.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="8e3c1-124">Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="8e3c1-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="8e3c1-125">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="8e3c1-126">Per creare un criterio di chat persistente per un sito</span><span class="sxs-lookup"><span data-stu-id="8e3c1-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="8e3c1-127">Per ogni sito distribuito, è possibile creare un criterio di chat persistente specifico del sito.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="8e3c1-128">La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="8e3c1-129">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8e3c1-130">Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8e3c1-131">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="8e3c1-132">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="8e3c1-133">In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="8e3c1-134">In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e3c1-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="8e3c1-135">In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="8e3c1-136">In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".</span><span class="sxs-lookup"><span data-stu-id="8e3c1-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="8e3c1-137">Per controllare Persistent Chat per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="8e3c1-138">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="8e3c1-139">Per creare un criterio utente per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="8e3c1-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="8e3c1-140">Nel pannello di controllo di Skype for Business Server, è possibile definire i criteri utente che possono essere assegnati agli utenti in **utenti**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="8e3c1-141">I criteri utente hanno la precedenza sui criteri globali e di sito, ma solo per gli utenti specifici a cui tali criteri utente sono assegnati.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="8e3c1-142">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8e3c1-143">Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8e3c1-144">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="8e3c1-145">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="8e3c1-146">In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e3c1-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="8e3c1-147">In **Nome** specificare un nome per il nuovo criterio utente.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="8e3c1-148">In **Descrizione** fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri di chat persistente per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="8e3c1-149">Per controllare la chat persistente per tutti gli utenti non controllati in modo specifico tramite criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="8e3c1-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="8e3c1-150">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="8e3c1-151">Per applicare un criterio utente di chat persistente a un account utente</span><span class="sxs-lookup"><span data-stu-id="8e3c1-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="8e3c1-152">Se un utente è stato abilitato per Skype for Business Server, è possibile applicare criteri adeguati a utenti specifici per abilitarli o disabilitarli per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="8e3c1-153">Utilizzare la procedura descritta in questo argomento per applicare un criterio utente di chat persistente creato in precedenza a uno o più account utente o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="8e3c1-154">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8e3c1-155">Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8e3c1-156">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="8e3c1-157">Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8e3c1-158">In **modifica utente di Lync Server** in **criteri di Persistent Chat** Selezionare il criterio utente di chat persistente che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e3c1-159">Le **\<Automatic\>** impostazioni applicano il criterio effettivo predefinito.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="8e3c1-160">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="8e3c1-161">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-161">Click **Commit**.</span></span>
    

