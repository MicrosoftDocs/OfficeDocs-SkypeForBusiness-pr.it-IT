---
title: Configurare i criteri utente di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Riepilogo: leggere questo argomento per informazioni su come creare criteri utente iniziali per il server di chat persistente in Skype for Business Server 2015. I criteri utente della chat persistente determinano se gli utenti sono autorizzati ad accedere alle chat room.'
ms.openlocfilehash: 83d6b49372f695be1a4db516eda6c7be357beed3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239757"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="013b5-104">Configurare i criteri utente di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="013b5-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="013b5-105">**Riepilogo:** Leggere questo argomento per informazioni su come creare criteri utente iniziali per il server di chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="013b5-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="013b5-106">I criteri utente della chat persistente determinano se gli utenti sono autorizzati ad accedere alle chat room.</span><span class="sxs-lookup"><span data-stu-id="013b5-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="013b5-107">È possibile gestire i criteri degli utenti del server di chat persistente ai livelli seguenti: globale, sito o utente.</span><span class="sxs-lookup"><span data-stu-id="013b5-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="013b5-108">Inizialmente, configuri il criterio globale per abilitare le impostazioni della chat persistente per tutti gli utenti della distribuzione e quindi crei altri criteri per l'utente e il sito per controllare se la chat persistente è attivata per utenti e siti specifici.</span><span class="sxs-lookup"><span data-stu-id="013b5-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="013b5-109">Questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="013b5-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="013b5-110">Configurare il criterio globale</span><span class="sxs-lookup"><span data-stu-id="013b5-110">Configure the global policy</span></span>
    
- <span data-ttu-id="013b5-111">Creare un criterio per il sito</span><span class="sxs-lookup"><span data-stu-id="013b5-111">Create a site policy</span></span>
    
- <span data-ttu-id="013b5-112">Creare un criterio utente</span><span class="sxs-lookup"><span data-stu-id="013b5-112">Create a user policy</span></span>
    
- <span data-ttu-id="013b5-113">Applicare un criterio a un utente o a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="013b5-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="013b5-114">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="013b5-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="013b5-115">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="013b5-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="013b5-116">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="013b5-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="013b5-117">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="013b5-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="013b5-118">Configurare il criterio globale</span><span class="sxs-lookup"><span data-stu-id="013b5-118">Configure the global policy</span></span>

<span data-ttu-id="013b5-119">Per configurare il criterio globale:</span><span class="sxs-lookup"><span data-stu-id="013b5-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="013b5-120">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="013b5-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="013b5-121">Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="013b5-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="013b5-122">Nel pannello di controllo di Skype for Business Server fare clic su **chat persistente**e quindi su **criteri di chat permanenti**.</span><span class="sxs-lookup"><span data-stu-id="013b5-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="013b5-123">Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="013b5-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="013b5-124">In **Modifica Criteri Chat persistente- Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="013b5-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="013b5-125">In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera utilizzare il nome predefinito Globale.</span><span class="sxs-lookup"><span data-stu-id="013b5-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="013b5-126">In **Descrizione**specificare i dettagli relativi al criterio utente (ad esempio, criteri globali per _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="013b5-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="013b5-127">Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="013b5-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="013b5-128">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="013b5-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="013b5-129">Creare un criterio per il sito</span><span class="sxs-lookup"><span data-stu-id="013b5-129">Create a site policy</span></span>

<span data-ttu-id="013b5-130">Per ogni sito distribuito, è possibile creare un criterio di chat persistente specifico del sito.</span><span class="sxs-lookup"><span data-stu-id="013b5-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="013b5-131">La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono.</span><span class="sxs-lookup"><span data-stu-id="013b5-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="013b5-132">Per creare un criterio per il sito:</span><span class="sxs-lookup"><span data-stu-id="013b5-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="013b5-133">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="013b5-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="013b5-134">Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="013b5-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="013b5-135">Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Criteri di Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="013b5-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="013b5-136">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="013b5-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="013b5-137">In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="013b5-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="013b5-138">In **Nuovi criteri Chat persistente** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="013b5-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="013b5-139">In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.</span><span class="sxs-lookup"><span data-stu-id="013b5-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="013b5-140">In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".</span><span class="sxs-lookup"><span data-stu-id="013b5-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="013b5-141">Per controllare Chat persistente per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="013b5-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="013b5-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="013b5-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="013b5-143">Creare un criterio utente</span><span class="sxs-lookup"><span data-stu-id="013b5-143">Create a user policy</span></span>

<span data-ttu-id="013b5-144">Puoi creare criteri specifici dell'utente che eseguono l'override dei criteri globali e di tutti i criteri del sito a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="013b5-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="013b5-145">Per creare un criterio utente:</span><span class="sxs-lookup"><span data-stu-id="013b5-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="013b5-146">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="013b5-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="013b5-147">Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="013b5-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="013b5-148">Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Criteri di Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="013b5-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="013b5-149">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="013b5-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="013b5-150">In **Nuovi criteri Chat persistente** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="013b5-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="013b5-151">In **Nome** specificare un nome per il nuovo criterio utente.</span><span class="sxs-lookup"><span data-stu-id="013b5-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="013b5-152">In **Descrizione**, fornisci i dettagli sui criteri degli utenti, ad esempio i criteri di chat persistenti per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="013b5-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="013b5-153">Per controllare la chat persistente per tutti gli utenti che non sono specificamente controllati tramite un criterio utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="013b5-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="013b5-154">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="013b5-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="013b5-155">Applicare un criterio a un account utente</span><span class="sxs-lookup"><span data-stu-id="013b5-155">Apply a policy to a user account</span></span>

<span data-ttu-id="013b5-156">Dopo aver creato i criteri, è possibile applicarli a un account utente come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="013b5-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="013b5-157">Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="013b5-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="013b5-158">Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="013b5-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="013b5-159">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="013b5-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="013b5-160">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="013b5-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="013b5-161">In **modifica utenti di Skype for Business Server** in **criteri di chat persistenti**Selezionare il criterio utente per la chat persistente che si vuole applicare.</span><span class="sxs-lookup"><span data-stu-id="013b5-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="013b5-162">Le \*\* \<impostazioni\> automatiche\*\* applicano i criteri effettivi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="013b5-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="013b5-163">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="013b5-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="013b5-164">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="013b5-164">Click **Commit**.</span></span>
    

