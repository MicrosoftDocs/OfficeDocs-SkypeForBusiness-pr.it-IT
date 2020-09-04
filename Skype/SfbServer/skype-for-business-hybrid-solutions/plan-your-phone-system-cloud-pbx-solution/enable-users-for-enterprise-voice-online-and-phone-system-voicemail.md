---
title: Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Informazioni su come abilitare i servizi vocali del sistema telefonico per gli utenti di Skype for business.
ms.openlocfilehash: ed5e571976a032facc70b2e602d4b0ea7fd01afc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359182"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="6fbb3-103">Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="6fbb3-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="6fbb3-104">Skype for business online si ritirerà il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="6fbb3-105">Inoltre, la connettività PSTN tra l'ambiente locale e Skype for Business Server o il Cloud Connector Edition e Skype for business online non sarà più supportato.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="6fbb3-106">Informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="6fbb3-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="6fbb3-107">Informazioni su come abilitare i servizi vocali del sistema telefonico per gli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="6fbb3-108">L'ultimo passaggio per la distribuzione del sistema telefonico con connettività PSTN locale consiste nell'abilitare gli utenti per il sistema telefonico e la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="6fbb3-109">Per abilitare queste funzionalità, è necessario essere un utente con il ruolo di amministratore globale ed essere in grado di eseguire Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="6fbb3-110">È necessario seguire la procedura descritta in questo argomento per tutti gli account utente che non dispongono già di VoIP aziendale abilitato per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="6fbb3-111">Abilitazione dei servizi vocali del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="6fbb3-111">Enable Phone System voice services</span></span>

<span data-ttu-id="6fbb3-112">Per abilitare un utente per la segreteria telefonica del sistema telefonico, è necessario eseguire alcuni passaggi iniziali, ad esempio controllare se il connettore di Skype for business online è distribuito sui server e abilitare gli utenti per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="6fbb3-113">Per abilitare gli utenti per la segreteria telefonica e vocale del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="6fbb3-113">To enable your users for Phone System voice and voicemail</span></span>

1. <span data-ttu-id="6fbb3-114">Prima di iniziare, verificare che il connettore di Skype for business online (modulo di Windows PowerShell) sia distribuito nei server front end.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-114">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="6fbb3-115">In caso contrario, è possibile scaricarlo dall' [area download](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="6fbb3-115">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="6fbb3-116">Per ulteriori informazioni sull'utilizzo di questo modulo, vedere [configurazione del computer per la gestione di Skype for business online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6fbb3-116">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="6fbb3-117">Avviare Windows PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-117">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="6fbb3-118">Digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-118">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="6fbb3-119">Digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-119">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="6fbb3-120">Dopo aver premuto INVIO, verrà visualizzata la finestra di dialogo credenziali di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-120">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="6fbb3-121">Digitare il nome utente e la password dell'amministratore del tenant e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-121">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="6fbb3-122">Nella finestra di PowerShell, digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-122">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="6fbb3-123">Importare la sessione digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-123">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="6fbb3-124">Quando si esegue PowerShell su un server Skype for business, i cmdlet locali di Skype for business sono già caricati all'apertura di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-124">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="6fbb3-125">È necessario specificare il parametro-AllowClobber per consentire ai cmdlet online di sovrascrivere i cmdlet locali con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-125">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="6fbb3-126">Utilizzare il cmdlet Set-CsUser per assegnare le proprietà $EnterpriseVoiceEnabled e $HostedVoiceMail all'utente come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-126">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="6fbb3-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-127">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="6fbb3-128">È inoltre possibile specificare un utente per l'indirizzo SIP, il nome dell'entità utente (UPN), il nome di dominio e il nome utente (dominio\nomeutente) e il nome visualizzato in Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="6fbb3-128">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="6fbb3-129">Aggiornamento dell'URI di linea e del dial plan per gli utenti abilitati per il sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="6fbb3-129">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="6fbb3-130">In questa sezione viene descritto come aggiornare l'URI di linea e il dial plan per gli utenti abilitati per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-130">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="6fbb3-131">Per aggiornare l'URI di linea</span><span class="sxs-lookup"><span data-stu-id="6fbb3-131">To update the Line URI</span></span>

1. <span data-ttu-id="6fbb3-132">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6fbb3-133">Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-133">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6fbb3-134">È inoltre possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-134">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="6fbb3-135">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-135">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6fbb3-136">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-136">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="6fbb3-137">Nella tabella fare clic sull'account utente di Skype for business che si desidera modificare l'URI di linea.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-137">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="6fbb3-138">Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-138">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="6fbb3-139">Quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-139">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="6fbb3-140">Aggiornare il dial plan con i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="6fbb3-140">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="6fbb3-141">È possibile assegnare dial plan per utente con Windows PowerShell e il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="6fbb3-141">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="6fbb3-142">È possibile eseguire questo cmdlet sia da Skype for Business Server 2015 o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-142">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="6fbb3-143">Per assegnare un dial plan per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-143">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="6fbb3-144">Utilizzare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per assegnare il dial plan per utente RedmondDialPlan all'utente Ken referir:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-144">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="6fbb3-145">Per assegnare un dial plan per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="6fbb3-145">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="6fbb3-146">Il comando seguente assegna il dial plan per utente RedmondDialPlan a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-146">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="6fbb3-147">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="6fbb3-147">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="6fbb3-148">È possibile utilizzare piani di chiamata globale o utente per gli utenti online.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-148">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="6fbb3-149">Non è possibile utilizzare i dial plan dei siti perché sono validi solo per gli utenti ospitati in locale e vengono assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-149">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="6fbb3-150">Per annullare l'assegnazione di un dial plan per utente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-150">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="6fbb3-151">Utilizzare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per annullare l'assegnazione di un dial plan per utente precedentemente assegnato a Ken remario.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-151">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="6fbb3-152">Dopo che il dial plan per utente non è stato assegnato, Ken è gestito automaticamente utilizzando il dial plan globale o il dial plan di servizio-scope assegnato al proprio registrar o al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-152">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="6fbb3-153">Un dial plan di ambito di servizio ha la precedenza sul dial plan globale:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-153">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="6fbb3-154">Aggiornare i criteri di routing vocale utilizzando i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="6fbb3-154">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="6fbb3-155">In questa sezione viene descritto come aggiornare i criteri di routing vocale per gli utenti abilitati per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-155">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="6fbb3-156">Gli utenti di sistema telefonico devono disporre di un criterio di routing vocale ad essi assegnato per le chiamate da instradare correttamente.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-156">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="6fbb3-157">Questa impostazione è diversa da quella degli utenti di VoIP aziendale locali che richiedono l'assegnazione di un criterio vocale per consentire alle chiamate di instradare correttamente.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-157">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="6fbb3-158">Il criterio di routing vocale deve contenere gli utilizzi PSTN che definiscono le chiamate e le route autorizzate per gli utenti del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-158">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="6fbb3-159">È possibile copiare questi utilizzi PSTN dai criteri vocali esistenti ai nuovi criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-159">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="6fbb3-160">Per ulteriori informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6fbb3-160">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6fbb3-161">A tutti gli utenti di sistema telefonico sono assegnati gli stessi criteri vocali online denominati BusinessVoice, che definisce le funzionalità di chiamata consentite; ad esempio, Consenti squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-161">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="6fbb3-162">Per assegnare un criterio di routing vocale per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-162">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="6fbb3-163">Utilizzare il cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) per assegnare il criterio di routing vocale per utente RedmondVoiceRoutingPolicy all'utente Ken:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-163">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="6fbb3-164">Per assegnare un criterio di routing vocale per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="6fbb3-164">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="6fbb3-165">Il comando seguente assegna il criterio di routing vocale per utente RedmondVoiceRoutingPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-165">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="6fbb3-166">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6fbb3-166">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="6fbb3-167">È possibile utilizzare i criteri di routing vocale globale o utente per gli utenti online.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-167">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="6fbb3-168">I criteri di routing vocale del sito non possono essere utilizzati perché si applicano solo agli utenti ospitati in locale e vengono assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-168">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="6fbb3-169">Per annullare l'assegnazione di un criterio di routing vocale per utente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-169">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="6fbb3-170">Utilizzare il Grant-CsVoiceRoutingPolicy per annullare l'assegnazione di qualsiasi criterio di routing vocale per utente precedentemente assegnato a Ken.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-170">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="6fbb3-171">Dopo che il criterio di routing vocale per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio di routing vocale globale.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-171">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="6fbb3-172">Per ulteriori informazioni, vedere [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6fbb3-172">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

