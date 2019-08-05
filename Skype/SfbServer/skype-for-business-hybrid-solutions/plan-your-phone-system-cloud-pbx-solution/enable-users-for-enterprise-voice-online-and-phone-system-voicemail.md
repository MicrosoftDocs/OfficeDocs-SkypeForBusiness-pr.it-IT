---
title: Abilitare gli utenti per Enterprise Voice online e il sistema telefonico in Office 365 Voicemail
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Informazioni su come abilitare il sistema telefonico in Office 365 Voice Services per gli utenti di Skype for business.
ms.openlocfilehash: 1305f4045d4de86a65e0286938d22490f577507c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190838"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="2f329-103">Abilitare gli utenti per Enterprise Voice online e il sistema telefonico in Office 365 Voicemail</span><span class="sxs-lookup"><span data-stu-id="2f329-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="2f329-104">Informazioni su come abilitare il sistema telefonico in Office 365 Voice Services per gli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2f329-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="2f329-105">Il passaggio finale nella distribuzione di sistemi telefonici in Office 365 con connettività PSTN locale consiste nell'abilitare gli utenti per il sistema telefonico in Office 365 e la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="2f329-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="2f329-106">Per abilitare queste funzionalità, è necessario essere un utente con il ruolo di amministratore globale di Office 365 ed essere in grado di eseguire Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f329-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="2f329-107">È necessario seguire la procedura descritta in questo argomento per tutti gli account utente che non dispongono già di VoIP aziendale abilitato per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="2f329-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="2f329-108">Abilitare il sistema telefonico in Office 365 Voice Services</span><span class="sxs-lookup"><span data-stu-id="2f329-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="2f329-109">Per abilitare un utente per il sistema telefonico in Office 365 Voice and voicemail, è necessario eseguire alcuni passaggi iniziali, ad esempio verificare se il connettore di Skype for business online è distribuito nei server e abilitare gli utenti per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="2f329-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="2f329-110">Per abilitare gli utenti per il sistema telefonico in Office 365 Voice and voicemail</span><span class="sxs-lookup"><span data-stu-id="2f329-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="2f329-111">Prima di iniziare, verificare che il connettore Skype for business online (modulo Windows PowerShell) sia distribuito nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="2f329-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="2f329-112">In caso contrario, è possibile scaricarlo dall' [area download](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="2f329-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="2f329-113">Per altre informazioni sull'uso di questo modulo, vedere [configurare il computer per la gestione di Skype for business online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2f329-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="2f329-114">Avviare Windows PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="2f329-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="2f329-115">Digitare il codice seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="2f329-115">Type the following and press Enter:</span></span>
    
   ```
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="2f329-116">Digitare il codice seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="2f329-116">Type the following and press Enter:</span></span>
    
   ```
   $cred = Get-Credential
   ```

    <span data-ttu-id="2f329-117">Dopo aver premuto INVIO, dovrebbe essere visualizzata la finestra di dialogo credenziali di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f329-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="2f329-118">Digitare il nome utente e la password dell'amministratore del tenant e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f329-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="2f329-119">Nella finestra di PowerShell digitare il codice seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="2f329-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="2f329-120">Importare la sessione digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2f329-120">Import the session by typing the following cmdlet:</span></span>
    
   ```
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="2f329-121">Quando si esegue PowerShell in un server Skype for business, i cmdlet di Skype for business locali sono già caricati quando si apre PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f329-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="2f329-122">Devi specificare il parametro-AllowClobber per consentire ai cmdlet online di sovrascrivere i cmdlet locali con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2f329-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="2f329-123">Usa il cmdlet Set-CsUser per assegnare le proprietà $EnterpriseVoiceEnabled e $HostedVoiceMail all'utente come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2f329-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="2f329-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f329-124">For example:</span></span>
    
   ```
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="2f329-125">È anche possibile specificare un utente per l'indirizzo SIP, il nome dell'entità utente (UPN), il nome di dominio e il nomeutente (dominio\nomeutente) e il nome visualizzato in Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="2f329-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="2f329-126">Aggiornare l'URI di linea e il dial plan per gli utenti abilitati per il sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="2f329-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="2f329-127">Questa sezione descrive come aggiornare l'URI di linea e il dial plan per gli utenti abilitati per il sistema telefonico in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f329-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="2f329-128">Per aggiornare l'URI di linea</span><span class="sxs-lookup"><span data-stu-id="2f329-128">To update the Line URI</span></span>

1. <span data-ttu-id="2f329-129">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2f329-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2f329-130">Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f329-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2f329-131">È anche possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f329-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="2f329-132">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="2f329-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2f329-133">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **Trovare**.</span><span class="sxs-lookup"><span data-stu-id="2f329-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="2f329-134">Nella tabella fare clic sull'account utente di Skype for business che si desidera modificare URI di linea.</span><span class="sxs-lookup"><span data-stu-id="2f329-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="2f329-135">Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="2f329-135">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="2f329-136">Quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="2f329-136">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="2f329-137">Aggiornare il dial plan con i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="2f329-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2f329-138">È possibile assegnare piani di dial per utente con Windows PowerShell e il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2f329-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="2f329-139">Questo cmdlet può essere eseguito da Skype for Business Server 2015 o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f329-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="2f329-140">Per assegnare un dial plan per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="2f329-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="2f329-141">Usare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per assegnare il dial plan per utente "RedmondDialPlan" all'utente Ken REQUESTO:</span><span class="sxs-lookup"><span data-stu-id="2f329-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="2f329-142">Per assegnare un dial plan per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="2f329-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="2f329-143">Con il comando seguente viene assegnato il dial plan per utente "RedmondDialPlan" a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="2f329-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="2f329-144">Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="2f329-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="2f329-145">Per gli utenti online è possibile usare piani di Dial globale o utenti.</span><span class="sxs-lookup"><span data-stu-id="2f329-145">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="2f329-146">I piani di accesso al sito non possono essere usati perché si applicano solo agli utenti ospitati in locale e assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="2f329-146">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="2f329-147">Per annullare l'assegnazione di un dial plan per utente</span><span class="sxs-lookup"><span data-stu-id="2f329-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="2f329-148">Usare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per annullare l'assegnazione di un dial plan per utente assegnato in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="2f329-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="2f329-149">Dopo che il dial plan per utente non è stato assegnato, Ken è gestito automaticamente tramite il dial plan globale o con il dial plan per l'ambito dei servizi assegnato al proprio registrar o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="2f329-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="2f329-150">Un dial plan per l'ambito dei servizi ha la precedenza sul dial plan globale:</span><span class="sxs-lookup"><span data-stu-id="2f329-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="2f329-151">Aggiornare i criteri di routing vocale usando i cmdlet di Windows PowerShell locali</span><span class="sxs-lookup"><span data-stu-id="2f329-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2f329-152">Questa sezione descrive come aggiornare i criteri di routing vocale per gli utenti abilitati per il sistema telefonico in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f329-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="2f329-153">Sistema telefonico in Office 365 gli utenti devono disporre di un criterio di routing vocale assegnato alle chiamate per l'instradamento corretto.</span><span class="sxs-lookup"><span data-stu-id="2f329-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="2f329-154">Ciò si differenzia dagli utenti di VoIP aziendale locali che richiedono l'assegnazione di un criterio vocale per consentire alle chiamate di instradarsi correttamente.</span><span class="sxs-lookup"><span data-stu-id="2f329-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="2f329-155">Il criterio di routing vocale deve contenere gli usi PSTN che definiscono le chiamate e le route autorizzate per il sistema telefonico negli utenti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f329-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="2f329-156">È possibile copiare questi usi PSTN dai criteri vocali esistenti ai nuovi criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="2f329-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="2f329-157">Per altre informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2f329-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f329-158">Tutti i sistemi telefonici in Office 365 agli utenti viene assegnato lo stesso criterio vocale online denominato BusinessVoice, che definisce le funzionalità di chiamata consentite; ad esempio, Consenti squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="2f329-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="2f329-159">Per assegnare un criterio di routing vocale per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="2f329-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="2f329-160">Usare il cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) per assegnare il criterio di routing vocale per utente RedmondVoiceRoutingPolicy all'utente Ken request:</span><span class="sxs-lookup"><span data-stu-id="2f329-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="2f329-161">Per assegnare criteri di routing vocale per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="2f329-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="2f329-162">Il comando successivo assegna il criterio di routing vocale per utente RedmondVoiceRoutingPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="2f329-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="2f329-163">Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2f329-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="2f329-164">È possibile usare i criteri di routing vocale globale o utente per gli utenti online.</span><span class="sxs-lookup"><span data-stu-id="2f329-164">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="2f329-165">I criteri di routing vocale del sito non possono essere usati perché si applicano solo agli utenti ospitati in locale e assegnati a un sito locale.</span><span class="sxs-lookup"><span data-stu-id="2f329-165">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="2f329-166">Per annullare l'assegnazione di un criterio di routing vocale per utente</span><span class="sxs-lookup"><span data-stu-id="2f329-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="2f329-167">Usare Grant-CsVoiceRoutingPolicy per annullare l'assegnazione di criteri di routing vocale per utente assegnati in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="2f329-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="2f329-168">Dopo che i criteri di routing vocale per utente non sono assegnati, Ken è gestito automaticamente tramite il criterio di routing vocale globale.</span><span class="sxs-lookup"><span data-stu-id="2f329-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="2f329-169">Per altre informazioni, vedere [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2f329-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

