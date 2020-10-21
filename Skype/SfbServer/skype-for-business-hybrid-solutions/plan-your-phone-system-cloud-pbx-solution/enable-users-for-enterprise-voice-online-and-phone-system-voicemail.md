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
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625112"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="93515-103">Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="93515-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="93515-104">Skype for business online si ritirerà il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="93515-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="93515-105">Inoltre, la connettività PSTN tra l'ambiente locale e Skype for Business Server o il Cloud Connector Edition e Skype for business online non sarà più supportato.</span><span class="sxs-lookup"><span data-stu-id="93515-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="93515-106">Informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="93515-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="93515-107">Informazioni su come abilitare i servizi vocali del sistema telefonico per gli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="93515-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="93515-108">L'ultimo passaggio per la distribuzione del sistema telefonico con connettività PSTN locale consiste nell'abilitare gli utenti per il sistema telefonico e la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="93515-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="93515-109">Per abilitare queste funzionalità, è necessario essere un utente con il ruolo di amministratore globale ed essere in grado di eseguire Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93515-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="93515-110">È necessario seguire la procedura descritta in questo argomento per tutti gli account utente che non dispongono già di VoIP aziendale abilitato per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="93515-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="93515-111">Abilitazione dei servizi vocali del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="93515-111">Enable Phone System voice services</span></span>

<span data-ttu-id="93515-112">Per abilitare un utente per la segreteria telefonica del sistema telefonico, è necessario eseguire alcuni passaggi iniziali, ad esempio controllare se il connettore di Skype for business online è distribuito sui server e abilitare gli utenti per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="93515-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="93515-113">Per abilitare gli utenti per la segreteria telefonica e vocale del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="93515-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="93515-114">Skype for Business Online Connector è attualmente parte del modulo di PowerShell Teams più recente.</span><span class="sxs-lookup"><span data-stu-id="93515-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="93515-115">Se si utilizza la [versione pubblica di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)per i team più recenti, non è necessario installare il connettore di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="93515-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="93515-116">Prima di iniziare, verificare che il modulo teams PowerShell sia installato nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="93515-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="93515-117">In caso contrario, installare l'applicazione seguendo le istruzioni riportate in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="93515-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="93515-118">Avviare Windows PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="93515-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="93515-119">Digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="93515-119">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. <span data-ttu-id="93515-120">Digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="93515-120">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="93515-121">Dopo aver premuto INVIO, verrà visualizzata la finestra di dialogo credenziali di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93515-121">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="93515-122">Digitare il nome utente e la password dell'amministratore del tenant e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="93515-122">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="93515-123">Nella finestra di PowerShell, digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="93515-123">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="93515-124">Importare la sessione digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="93515-124">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="93515-125">Quando si esegue PowerShell su un server Skype for business, i cmdlet locali di Skype for business sono già caricati all'apertura di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93515-125">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="93515-126">È necessario specificare il parametro-AllowClobber per consentire ai cmdlet online di sovrascrivere i cmdlet locali con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="93515-126">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="93515-127">Utilizzare il cmdlet Set-CsUser per assegnare le proprietà $EnterpriseVoiceEnabled e $HostedVoiceMail all'utente, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="93515-127">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="93515-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93515-128">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="93515-129">È inoltre possibile specificare un utente per l'indirizzo SIP, il nome dell'entità utente (UPN), il nome di dominio e il nome utente (dominio\nomeutente) e il nome visualizzato in Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="93515-129">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="93515-130">Aggiornamento dell'URI di linea e del dial plan per gli utenti abilitati per il sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="93515-130">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="93515-131">In questa sezione viene descritto come aggiornare l'URI di linea e il dial plan per gli utenti abilitati per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="93515-131">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="93515-132">Per aggiornare l'URI di linea</span><span class="sxs-lookup"><span data-stu-id="93515-132">To update the Line URI</span></span>

1. <span data-ttu-id="93515-133">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="93515-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="93515-134">Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="93515-134">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="93515-135">È inoltre possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="93515-135">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="93515-136">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="93515-136">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="93515-137">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="93515-137">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="93515-138">Nella tabella fare clic sull'account utente di Skype for business che si desidera modificare l'URI di linea.</span><span class="sxs-lookup"><span data-stu-id="93515-138">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="93515-139">Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="93515-139">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="93515-140">Quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="93515-140">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="93515-141">Aggiornare il dial plan con i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="93515-141">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="93515-142">È possibile assegnare dial plan per utente con Windows PowerShell e il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="93515-142">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="93515-143">È possibile eseguire questo cmdlet sia da Skype for Business Server 2015 o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93515-143">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="93515-144">Per assegnare un dial plan per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="93515-144">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="93515-145">Utilizzare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per assegnare il dial plan per utente RedmondDialPlan all'utente Ken referir:</span><span class="sxs-lookup"><span data-stu-id="93515-145">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="93515-146">Per assegnare un dial plan per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="93515-146">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="93515-147">Il comando seguente assegna il dial plan per utente RedmondDialPlan a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="93515-147">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="93515-148">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="93515-148">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="93515-149">È possibile utilizzare piani di chiamata globale o utente per gli utenti online.</span><span class="sxs-lookup"><span data-stu-id="93515-149">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="93515-150">Non è possibile utilizzare i dial plan dei siti perché sono validi solo per gli utenti ospitati in locale e vengono assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="93515-150">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="93515-151">Per annullare l'assegnazione di un dial plan per utente</span><span class="sxs-lookup"><span data-stu-id="93515-151">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="93515-152">Utilizzare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per annullare l'assegnazione di un dial plan per utente precedentemente assegnato a Ken remario.</span><span class="sxs-lookup"><span data-stu-id="93515-152">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="93515-153">Dopo che il dial plan per utente non è stato assegnato, Ken è gestito automaticamente utilizzando il dial plan globale o il dial plan di servizio-scope assegnato al proprio registrar o al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="93515-153">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="93515-154">Un dial plan di ambito di servizio ha la precedenza sul dial plan globale:</span><span class="sxs-lookup"><span data-stu-id="93515-154">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="93515-155">Aggiornare i criteri di routing vocale utilizzando i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="93515-155">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="93515-156">In questa sezione viene descritto come aggiornare i criteri di routing vocale per gli utenti abilitati per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="93515-156">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="93515-157">Gli utenti di sistema telefonico devono disporre di un criterio di routing vocale ad essi assegnato per le chiamate da instradare correttamente.</span><span class="sxs-lookup"><span data-stu-id="93515-157">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="93515-158">Questa impostazione è diversa da quella degli utenti di VoIP aziendale locali che richiedono l'assegnazione di un criterio vocale per consentire alle chiamate di instradare correttamente.</span><span class="sxs-lookup"><span data-stu-id="93515-158">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="93515-159">Il criterio di routing vocale deve contenere gli utilizzi PSTN che definiscono le chiamate e le route autorizzate per gli utenti del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="93515-159">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="93515-160">È possibile copiare questi utilizzi PSTN dai criteri vocali esistenti ai nuovi criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="93515-160">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="93515-161">Per ulteriori informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="93515-161">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="93515-162">A tutti gli utenti di sistema telefonico sono assegnati gli stessi criteri vocali online denominati BusinessVoice, che definisce le funzionalità di chiamata consentite; ad esempio, Consenti squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="93515-162">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="93515-163">Per assegnare un criterio di routing vocale per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="93515-163">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="93515-164">Utilizzare il cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) per assegnare il criterio di routing vocale per utente RedmondVoiceRoutingPolicy all'utente Ken:</span><span class="sxs-lookup"><span data-stu-id="93515-164">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="93515-165">Per assegnare un criterio di routing vocale per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="93515-165">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="93515-166">Il comando seguente assegna il criterio di routing vocale per utente RedmondVoiceRoutingPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="93515-166">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="93515-167">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="93515-167">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="93515-168">È possibile utilizzare i criteri di routing vocale globale o utente per gli utenti online.</span><span class="sxs-lookup"><span data-stu-id="93515-168">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="93515-169">I criteri di routing vocale del sito non possono essere utilizzati perché si applicano solo agli utenti ospitati in locale e vengono assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="93515-169">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="93515-170">Per annullare l'assegnazione di un criterio di routing vocale per utente</span><span class="sxs-lookup"><span data-stu-id="93515-170">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="93515-171">Utilizzare l'Grant-CsVoiceRoutingPolicy per annullare l'assegnazione di qualsiasi criterio di routing vocale per utente precedentemente assegnato a Ken remario.</span><span class="sxs-lookup"><span data-stu-id="93515-171">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="93515-172">Dopo che il criterio di routing vocale per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio di routing vocale globale.</span><span class="sxs-lookup"><span data-stu-id="93515-172">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="93515-173">Per ulteriori informazioni, vedere [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="93515-173">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

