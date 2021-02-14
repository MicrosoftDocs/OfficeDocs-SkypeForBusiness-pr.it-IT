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
description: Informazioni su come abilitare i servizi vocali di Sistema telefonico per gli utenti di Skype for Business.
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625112"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="afedd-103">Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="afedd-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="afedd-104">Skype for Business online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="afedd-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="afedd-105">Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.</span><span class="sxs-lookup"><span data-stu-id="afedd-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="afedd-106">Informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="afedd-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="afedd-107">Informazioni su come abilitare i servizi vocali di Sistema telefonico per gli utenti di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="afedd-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="afedd-108">Il passaggio finale per la distribuzione di Sistema telefonico con connettività PSTN locale consiste nell'abilitare gli utenti al sistema telefonico e alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="afedd-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="afedd-109">Per abilitare queste funzionalità, è necessario essere un utente con il ruolo amministratore globale ed essere in grado di eseguire Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afedd-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="afedd-110">È necessario seguire i passaggi descritti in questo argomento per tutti gli account utente che non VoIP aziendale abilitati per Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="afedd-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="afedd-111">Abilitare i servizi vocali di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="afedd-111">Enable Phone System voice services</span></span>

<span data-ttu-id="afedd-112">Per abilitare un utente per La voce e la segreteria telefonica del sistema telefonico, è necessario eseguire alcuni passaggi iniziali, ad esempio verificare se il connettore Skype for Business online è distribuito sui server e abilitare gli utenti per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="afedd-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="afedd-113">Per abilitare gli utenti alla segreteria telefonica e alla segreteria telefonica di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="afedd-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="afedd-114">Skype for Business Online Connector fa attualmente parte del modulo PowerShell di Teams più recente.</span><span class="sxs-lookup"><span data-stu-id="afedd-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="afedd-115">Se si usa la versione pubblica di [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)più recente, non è necessario installare il connettore Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="afedd-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="afedd-116">Prima di iniziare, verificare che il modulo PowerShell di Teams sia installato nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="afedd-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="afedd-117">In caso contrario, eseguire l'installazione usando le istruzioni in Installazione del modulo [PowerShell di Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="afedd-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="afedd-118">Avviare Windows PowerShell amministratore.</span><span class="sxs-lookup"><span data-stu-id="afedd-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="afedd-119">Digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="afedd-119">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. <span data-ttu-id="afedd-120">Digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="afedd-120">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="afedd-121">Dopo aver premuto INVIO, verrà visualizzata la Windows PowerShell di dialogo Credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="afedd-121">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="afedd-122">Digitare il nome utente e la password dell'amministratore tenant e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="afedd-122">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="afedd-123">Nella finestra di PowerShell digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="afedd-123">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="afedd-124">Importare la sessione digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="afedd-124">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="afedd-125">Quando si esegue PowerShell in Skype for Business Server, i cmdlet di Skype for Business locali sono già caricati quando si apre PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afedd-125">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="afedd-126">È necessario specificare il parametro -AllowClobber per consentire ai cmdlet online di sovrascrivere i cmdlet locali con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="afedd-126">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="afedd-127">Utilizzare il cmdlet Set-CsUser per assegnare le proprietà $EnterpriseVoiceEnabled e $HostedVoiceMail all'utente nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="afedd-127">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="afedd-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="afedd-128">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="afedd-129">È inoltre possibile specificare un utente in base all'indirizzo SIP, al nome dell'entità utente (UPN), al nome di dominio e al nome utente (dominio\nomeutente) e al nome visualizzato in Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="afedd-129">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="afedd-130">Aggiornare l'URI linea e il dial plan per gli utenti abilitati per Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="afedd-130">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="afedd-131">In questa sezione viene descritto come aggiornare l'URI linea e il dial plan per gli utenti abilitati per Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="afedd-131">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="afedd-132">Per aggiornare l'URI linea</span><span class="sxs-lookup"><span data-stu-id="afedd-132">To update the Line URI</span></span>

1. <span data-ttu-id="afedd-133">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="afedd-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="afedd-134">Usa il menu Start o il collegamento sul desktop per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="afedd-134">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="afedd-135">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="afedd-135">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="afedd-136">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="afedd-136">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="afedd-137">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="afedd-137">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="afedd-138">Nella tabella, fare clic sull'account utente Skype for Business che si desidera modificare l'URI linea.</span><span class="sxs-lookup"><span data-stu-id="afedd-138">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="afedd-139">Fare **clic su URI** linea e digitare un numero di telefono normalizzato univoco , ad esempio tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="afedd-139">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="afedd-140">Fare quindi clic su **Commit.**</span><span class="sxs-lookup"><span data-stu-id="afedd-140">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="afedd-141">Aggiornare il dial plan utilizzando i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="afedd-141">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="afedd-142">È possibile assegnare dial plan per utente con Windows PowerShell e il cmdlet [Grant-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="afedd-142">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="afedd-143">È possibile eseguire questo cmdlet da Skype for Business Server 2015 o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afedd-143">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="afedd-144">Per assegnare un dial plan per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="afedd-144">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="afedd-145">Utilizzare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per assegnare il dial plan per utente RedmondDialPlan all'utente Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="afedd-145">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="afedd-146">Per assegnare un dial plan per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="afedd-146">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="afedd-147">Il comando seguente assegna il dial plan per utente RedmondDialPlan a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="afedd-147">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="afedd-148">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="afedd-148">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="afedd-149">È possibile utilizzare dial plan globali o utente per gli utenti online.</span><span class="sxs-lookup"><span data-stu-id="afedd-149">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="afedd-150">I dial plan del sito non possono essere utilizzati in quanto si applicano solo agli utenti ospitati in locale e assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="afedd-150">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="afedd-151">Per annullare l'assegnazione di un dial plan per utente</span><span class="sxs-lookup"><span data-stu-id="afedd-151">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="afedd-152">Utilizzare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per annullare l'assegnazione di qualsiasi dial plan per utente precedentemente assegnato a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="afedd-152">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="afedd-153">Dopo l'annullamento dell'assegnazione del dial plan per utente, Ken Myer verrà gestito automaticamente utilizzando il dial plan globale o il dial plan con ambito di servizio assegnato alla funzione di registrazione o al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="afedd-153">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="afedd-154">Un dial plan con ambito di servizio ha la precedenza sul dial plan globale:</span><span class="sxs-lookup"><span data-stu-id="afedd-154">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="afedd-155">Aggiornare i criteri di routing vocale utilizzando i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="afedd-155">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="afedd-156">In questa sezione viene descritto come aggiornare i criteri di routing vocale per gli utenti abilitati per Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="afedd-156">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="afedd-157">Gli utenti di Sistema telefonico devono disporre di un criterio di routing vocale assegnato per consentire il corretto instradamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="afedd-157">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="afedd-158">Ciò è diverso dagli utenti di VoIP aziendale locale che richiedono l'assegnazione di un criterio vocale per consentire il routing corretto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="afedd-158">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="afedd-159">Il criterio di routing vocale deve contenere utilizzi PSTN che definiscono le chiamate e le route autorizzate per gli utenti di Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="afedd-159">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="afedd-160">È possibile copiare questi utilizzi PSTN dai criteri vocali esistenti ai nuovi criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="afedd-160">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="afedd-161">Per ulteriori informazioni, vedere [New-CsVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="afedd-161">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="afedd-162">A tutti gli utenti di Sistema telefonico viene assegnato lo stesso criterio vocale online denominato BusinessVoice che definisce le funzionalità di chiamata consentite; ad esempio Consenti squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="afedd-162">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="afedd-163">Per assegnare un criterio di routing vocale per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="afedd-163">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="afedd-164">Utilizzare il cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) per assegnare il criterio di routing vocale per utente RedmondVoiceRoutingPolicy all'utente Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="afedd-164">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="afedd-165">Per assegnare un criterio di routing vocale per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="afedd-165">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="afedd-166">Il comando successivo assegna il criterio di routing vocale per utente RedmondVoiceRoutingPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="afedd-166">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="afedd-167">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="afedd-167">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="afedd-168">È possibile utilizzare criteri di routing vocali globali o utente per gli utenti online.</span><span class="sxs-lookup"><span data-stu-id="afedd-168">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="afedd-169">I criteri di routing vocale del sito non possono essere utilizzati in quanto si applicano solo agli utenti ospitati in locale e assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="afedd-169">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="afedd-170">Per annullare l'assegnazione di un criterio di routing vocale per utente</span><span class="sxs-lookup"><span data-stu-id="afedd-170">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="afedd-171">Utilizzare il Grant-CsVoiceRoutingPolicy per annullare l'assegnazione di qualsiasi criterio di routing vocale per utente precedentemente assegnato a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="afedd-171">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="afedd-172">Dopo l'annullamento dell'assegnazione del criterio di routing vocale per utente, Ken Myer verrà gestito automaticamente utilizzando il criterio di routing vocale globale.</span><span class="sxs-lookup"><span data-stu-id="afedd-172">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="afedd-173">Per ulteriori informazioni, vedere [Grant-CsVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="afedd-173">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

