---
title: Passaggio tra le interfacce utente del client Skype for Business e del client Lync
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: ded1fbf0825fd03645aa2862cc4f51cc10374fbc
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="f9945-103">Passaggio tra le interfacce utente del client Skype for Business e del client Lync</span><span class="sxs-lookup"><span data-stu-id="f9945-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="f9945-104">[] Nelle organizzazioni che dispongono di Skype for Business online, puoi utilizzare una sessione remota di PowerShell in Office 365 per abilitare gli utenti Skype for Business a utilizzare l'interfaccia utente del client Skype for Business o quella del client Skype for Business (Lync).</span><span class="sxs-lookup"><span data-stu-id="f9945-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="f9945-105">L'impostazione predefinita prevede che gli utenti utilizzino l'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="f9945-106">Se si preferisce utilizzare l'esperienza con client Lync, è possibile gestire il comportamento dei client avvia primo per visualizzare l'interfaccia utente di Lync seguendo i passaggi descritti più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f9945-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9945-p102">L'esperienza client Lync 2013 non è prevista per le versioni client di Skype for Business 2016. Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="f9945-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f9945-109">Se si desidera cambiare facilmente interfaccia utente senza necessità di eseguire procedure manuali, visitare l'[Area download Microsoft](https://go.microsoft.com/fwlink/?LinkId=532431) per trovare un script di PowerShell che renderà più semplice l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f9945-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center ](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="f9945-110">Cambio dell'interfaccia utente di Skype for Business per gli utenti</span><span class="sxs-lookup"><span data-stu-id="f9945-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="f9945-p103">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione remota di Windows PowerShell che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688) Per altre informazioni, vedi[Configurazione del computer per la gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=534539).</span><span class="sxs-lookup"><span data-stu-id="f9945-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f9945-p104">L'impostazione del criterio  _Global_ per il cambio dell'interfaccia utente non verrà applicata a un utente che ha già un criterio personalizzato applicato. Per consentire il cambio dell'interfaccia utente, sarà necessario eseguire il seguente comando per ciascun utente che ha un criterio personalizzato applicato:</span><span class="sxs-lookup"><span data-stu-id="f9945-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="f9945-116">Il criterio  _ClientPolicyEnableSkypeUI_ sostituirà l'impostazione del criterio personalizzato esistente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f9945-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="f9945-117">Per abilitare tutti gli utenti dell'organizzazione a utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="f9945-118">Se si imposta correttamente il criterio, verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="f9945-120">Per abilitare tutti gli utenti dell'organizzazione a utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="f9945-121">Se si imposta correttamente il criterio, verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="f9945-123">Per consentire a un singolo utente dell'organizzazione di utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="f9945-124">Se si imposta correttamente il criterio, verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-124">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - Abilitare l'interfaccia utente](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="f9945-126">Per consentire a un singolo utente dell'organizzazione di utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="f9945-127">Se si imposta correttamente il criterio, verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-127">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - Interfaccia utente disabilitata](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="f9945-129">Per consentire a più utenti dell'organizzazione di utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="f9945-130">Per consentire a più utenti dell'organizzazione di utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="f9945-131">Per consentire a un gruppo di utenti dell'organizzazione di utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="f9945-132">Per consentire a un gruppo di utenti dell'organizzazione di utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9945-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="f9945-p105">Il nome dell'utente è il nome account dell'utente al quale dovrebbe essere assegnato il criterio. Il nome account dell'utente può essere immesso in uno dei formati seguenti:>  Indirizzo SIP dell'utente>  Nome dell'entità utente (UPN) dell'utente>  Dominio\\nome utente dell'utente>  Nome visualizzato Active Directory dell'utente</span><span class="sxs-lookup"><span data-stu-id="f9945-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="f9945-135">Uso di Windows PowerShell per gestire Lync Online</span><span class="sxs-lookup"><span data-stu-id="f9945-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="f9945-136">Impostazioni del criterio di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f9945-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="f9945-137">Questa tabella mostra l'esperienza utente quando il criterio viene applicato per la prima volta agli utenti:</span><span class="sxs-lookup"><span data-stu-id="f9945-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="f9945-138">**Impostazione del criterio da parte dell'amministratore**</span><span class="sxs-lookup"><span data-stu-id="f9945-138">**Admin policy setting**</span></span>|<span data-ttu-id="f9945-139">**Interfaccia utente visualizzata**</span><span class="sxs-lookup"><span data-stu-id="f9945-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9945-140">Il criterio non è impostato.</span><span class="sxs-lookup"><span data-stu-id="f9945-140">The policy isn't set.</span></span> |<span data-ttu-id="f9945-141">L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-141">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|<span data-ttu-id="f9945-142">L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-142">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|<span data-ttu-id="f9945-p106">All'utente verrà richiesto di passare all'interfaccia utente del client Skype for Business (Lync). Gli utenti possono cambiare interfaccia in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f9945-p106">The user will be asked to switch to the Skype for Business (Lync) client user interface. They can switch later.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|<span data-ttu-id="f9945-145">L'utente utilizzerà l'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-145">The user will be using the Skype for Business client user interface.</span></span> |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|<span data-ttu-id="f9945-146">L'utente verrà richiesto di passare a Skype per l'interfaccia utente client Business (Lync).</span><span class="sxs-lookup"><span data-stu-id="f9945-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="f9945-147">L'amministratore potrà in futuro modificare l'impostazione che consentirà agli utenti di passare all'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="f9945-148">Questa tabella mostra l'esperienza utente quando il criterio viene modificato:</span><span class="sxs-lookup"><span data-stu-id="f9945-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="f9945-149">**Impostazione del criterio da parte dell'amministratore**</span><span class="sxs-lookup"><span data-stu-id="f9945-149">**Admin policy setting**</span></span>|<span data-ttu-id="f9945-150">**Interfaccia utente di Skype for Business (Lync)**</span><span class="sxs-lookup"><span data-stu-id="f9945-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="f9945-151">**Interfaccia utente di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="f9945-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|<span data-ttu-id="f9945-152">All'utente verrà richiesto di passare all'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="f9945-153">L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|<span data-ttu-id="f9945-154">L'utente continua a utilizzare il Skype per l'interfaccia Business (Lync).</span><span class="sxs-lookup"><span data-stu-id="f9945-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="f9945-155">L'utente verrà richiesto di passare a Skype per l'interfaccia utente client Business (Lync).</span><span class="sxs-lookup"><span data-stu-id="f9945-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="f9945-156">Il criterio non è impostato.</span><span class="sxs-lookup"><span data-stu-id="f9945-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="f9945-157">Se il criterio non è impostato, gli utenti non visualizzeranno mai Skype per l'interfaccia utente client Business (Lync).</span><span class="sxs-lookup"><span data-stu-id="f9945-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="f9945-158">Gli utenti utilizzeranno sempre l'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="f9945-159">L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="f9945-p109">Questa tabella visualizza tutti i criteri personalizzati online disponibili. Sono stati creati nuovi criteri per dare agli amministratori la flessibilità di mantenere il vecchio criterio personalizzato durante il passaggio da un flag EnableSkypeUI all'altro. Utilizza i cmdlet indicati in precedenza per concedere agli utenti uno dei seguenti criteri.</span><span class="sxs-lookup"><span data-stu-id="f9945-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="f9945-163">**Nome del criterio**</span><span class="sxs-lookup"><span data-stu-id="f9945-163">**Policy name**</span></span>|<span data-ttu-id="f9945-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="f9945-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
```ClientPolicyDefaultPhoto```||
```ClientPolicyDefaultPhotoDisableSkypeUI``` |<span data-ttu-id="f9945-165">Falso</span><span class="sxs-lookup"><span data-stu-id="f9945-165">False</span></span>|
```ClientPolicyNoIMURL```||
```ClientPolicyNoIMURLDisableSkypeUI``` |<span data-ttu-id="f9945-166">Falso</span><span class="sxs-lookup"><span data-stu-id="f9945-166">False</span></span>|
```ClientPolicyNoIMURLPhoto```||
```ClientPolicyNoIMURLPhotoDisableSkypeUI``` |<span data-ttu-id="f9945-167">Falso</span><span class="sxs-lookup"><span data-stu-id="f9945-167">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingI```||
```ClientPolicyNoSaveIMNoArchivingDisableSkypeUI``` |<span data-ttu-id="f9945-168">Falso</span><span class="sxs-lookup"><span data-stu-id="f9945-168">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURL```||
```ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI``` |<span data-ttu-id="f9945-169">Falso</span><span class="sxs-lookup"><span data-stu-id="f9945-169">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto``` ||
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI```|<span data-ttu-id="f9945-170">Falso</span><span class="sxs-lookup"><span data-stu-id="f9945-170">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingPhoto```||
```ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI``` |<span data-ttu-id="f9945-171">Falso</span><span class="sxs-lookup"><span data-stu-id="f9945-171">False</span></span>|

   
<span data-ttu-id="f9945-172">Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="f9945-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="f9945-173">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="f9945-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="f9945-174">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9945-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="f9945-175">Comportamenti del client al primo avvio</span><span class="sxs-lookup"><span data-stu-id="f9945-175">First launch client behaviors</span></span>

<span data-ttu-id="f9945-176">Per impostazione predefinita, quando gli utenti Skype per le aziende di avvio per la prima volta, sempre visualizzeranno Skype all'interfaccia utente di Business, anche se è stata selezionata l'esperienza con client Lync impostando il criterio client per l'esperienza con client Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f9945-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="f9945-177">Dopo alcuni minuti, all'utente verrà richiesto di passare alla modalità Lync.</span><span class="sxs-lookup"><span data-stu-id="f9945-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="f9945-178">Se desideri visualizzare l'interfaccia utente di Lync al primo avvio del client Skype for Business da parte dell'utente, segui questa procedura prima che il client venga avviato per la prima volta in seguito all'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="f9945-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="f9945-179">Segui i passaggi indicati in precedenza nell'argomento e verifica che il criterio client sia impostato per disabilitare l'interfaccia utente di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f9945-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="f9945-p111">Aggiorna il Registro di sistema nel computer dell'utente. Esegui l'operazione una sola volta, prima del primo avvio del client Skype for Business da parte dell'utente. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer che fa parte di un dominio, vedi la sezione presente successivamente nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="f9945-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="f9945-183">Nella chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** crea un nuovo valore **Binary**.</span><span class="sxs-lookup"><span data-stu-id="f9945-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="f9945-184">**Nome valore** deve essere **EnableSkypeUI**, mentre **Dati valore** deve essere impostato su **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="f9945-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="f9945-185">La chiave dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f9945-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="f9945-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="f9945-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="f9945-187">"CanSharePptInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="f9945-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="f9945-188">"CanShareOneNoteInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="f9945-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="f9945-189">"CanAppShareInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="f9945-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="f9945-190">"EnableSkypeUI" = hex: 00, 00, 00,00</span><span class="sxs-lookup"><span data-stu-id="f9945-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="f9945-191">L'interfaccia utente di Lync verrà visualizzata al primo avvio del client Skype for Business da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f9945-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="f9945-192">Controllare la visualizzazione dell'esercitazione nella schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="f9945-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="f9945-193">Quando si apre Skype per client di Business, il comportamento predefinito consiste nel visualizzare una schermata di benvenuto contenente *la maggior parte delle persone 7 suggerimenti rapidi chiedono*.</span><span class="sxs-lookup"><span data-stu-id="f9945-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="f9945-194">Puoi disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:</span><span class="sxs-lookup"><span data-stu-id="f9945-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="f9945-p113">Nella chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** crea un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **IsBasicTutorialSeenByUser**, mentre **Dati valore** deve essere impostato su **1**.</span><span class="sxs-lookup"><span data-stu-id="f9945-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="f9945-197">La chiave dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f9945-197">The key should look like the following:</span></span>
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="f9945-198">Disattivare l'esercitazione nel client</span><span class="sxs-lookup"><span data-stu-id="f9945-198">Turn off the client tutorial</span></span>

<span data-ttu-id="f9945-199">Se non vuoi che gli utenti siano in grado di accedere all'esercitazione, puoi disattivare l'esercitazione nel client con il seguente valore del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="f9945-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="f9945-p114">Nella chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** crea un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **TutorialFeatureEnabled**, mentre **Dati valore** deve essere impostato su **0**.</span><span class="sxs-lookup"><span data-stu-id="f9945-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="f9945-202">Puoi riattivare l'esercitazione impostando **Dati valore** su **1**.</span><span class="sxs-lookup"><span data-stu-id="f9945-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="f9945-203">Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer che fa parte di un dominio</span><span class="sxs-lookup"><span data-stu-id="f9945-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="f9945-p115">L'aggiornamento del Registro di sistema per la visualizzazione dell'esperienza client Lync al primo avvio del client Skype for Business da parte dell'utente deve essere eseguito una sola volta. Se usi un oggetto Criteri di gruppo per aggiornare il Registro di sistema, devi definire l'oggetto per creare un nuovo valore anziché aggiornare Dati valore. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposterà Dati valore su 0.</span><span class="sxs-lookup"><span data-stu-id="f9945-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="f9945-p116">Nella seguente procedura viene illustrato come modificare il Registro di sistema in modo che l'esperienza client Lync venga visualizzata al primo avvio del client Skype for Business da parte dell'utente. Puoi inoltre utilizzare questa procedura per aggiornare il Registro di sistema e disabilitare l'esercitazione nella schermata iniziale come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f9945-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="f9945-209">**Per creare l'oggetto Criteri di gruppo**</span><span class="sxs-lookup"><span data-stu-id="f9945-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="f9945-210">Avvia la **Console Gestione Criteri di gruppo**.</span><span class="sxs-lookup"><span data-stu-id="f9945-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="f9945-211">Per informazioni su come usare la Console Gestione Criteri di gruppo, vedi [Console Gestione Criteri di gruppo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="f9945-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="f9945-212">Fai clic con il pulsante destro del mouse sul nodo **Oggetti Criteri di gruppo** e seleziona **Nuovo** nel menu.</span><span class="sxs-lookup"><span data-stu-id="f9945-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="f9945-213">Nella finestra di dialogo **Nuovo oggetto Criteri di gruppo** immetti un nome per l'oggetto Criteri di gruppo, ad esempioMakeLyncDefaultUI, quindi fai clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9945-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="f9945-214">Fai clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo creato, quindi seleziona **Modifica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="f9945-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="f9945-215">Nella finestra **Editor Gestione Criteri di gruppo** espandi **Configurazione utente**, espandi **Preferenze**, quindi **Impostazioni di Windows** e seleziona il nodo **Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="f9945-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="f9945-216">Fai clic con il pulsante destro del mouse sul nodo **Registro di sistema**, quindi seleziona **Nuovo** > **Elemento Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="f9945-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="f9945-217">Nella finestra di dialogo **Nuove proprietà Registro di sistema** aggiorna i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f9945-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="f9945-218">**Campo**</span><span class="sxs-lookup"><span data-stu-id="f9945-218">**Field**</span></span>|<span data-ttu-id="f9945-219">**Valore da selezionare o immettere**</span><span class="sxs-lookup"><span data-stu-id="f9945-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9945-220">**Azione**</span><span class="sxs-lookup"><span data-stu-id="f9945-220">**Action**</span></span> <br/> |<span data-ttu-id="f9945-221">**Create**</span><span class="sxs-lookup"><span data-stu-id="f9945-221">**Create**</span></span> <br/> |
|<span data-ttu-id="f9945-222">**Hive**</span><span class="sxs-lookup"><span data-stu-id="f9945-222">**Hive**</span></span> <br/> | <span data-ttu-id="f9945-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="f9945-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="f9945-224">**Percorso chiave**</span><span class="sxs-lookup"><span data-stu-id="f9945-224">**Key Path**</span></span> <br/> |<span data-ttu-id="f9945-225">Software\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="f9945-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="f9945-226">**Nome valore**</span><span class="sxs-lookup"><span data-stu-id="f9945-226">**Value name**</span></span> <br/> |<span data-ttu-id="f9945-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="f9945-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="f9945-228">**Tipo valore**</span><span class="sxs-lookup"><span data-stu-id="f9945-228">**Value type**</span></span> <br/> |<span data-ttu-id="f9945-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="f9945-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="f9945-230">**Dati valore**</span><span class="sxs-lookup"><span data-stu-id="f9945-230">**Value data**</span></span> <br/> |<span data-ttu-id="f9945-231">00000000</span><span class="sxs-lookup"><span data-stu-id="f9945-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="f9945-232">Fai clic su **OK** per salvare le modifiche e quindi chiudi l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f9945-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="f9945-233">Successivamente dovrai collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui vuoi assegnare il criterio, ad esempio un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="f9945-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="f9945-234">**Utilizzare l'oggetto Criteri di gruppo per assegnare il criterio**</span><span class="sxs-lookup"><span data-stu-id="f9945-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="f9945-235">In Console Gestione Criteri di gruppo fai clic con il pulsante destro del mouse sull'unità organizzativa a cui vuoi assegnare il criterio e quindi seleziona **Collega a un oggetto Criteri di gruppo esistente**.</span><span class="sxs-lookup"><span data-stu-id="f9945-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="f9945-236">Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo** seleziona l'oggetto Criteri di gruppo creato, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9945-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="f9945-237">Nel computer dell'utente di destinazione apri un prompt dei comandi e digita il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="f9945-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="f9945-238">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="f9945-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="f9945-p117">Durante l'applicazione dell'oggetto Criteri di gruppo verrà visualizzato il messaggio "Aggiornamento criteri in corso...". Al termine dell'operazione verrà visualizzato il messaggio "Aggiornamento dei criteri utente completato".</span><span class="sxs-lookup"><span data-stu-id="f9945-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="f9945-241">Al prompt dei comandi digita il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="f9945-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="f9945-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="f9945-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="f9945-243">Di seguito dovresti visualizzare "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.</span><span class="sxs-lookup"><span data-stu-id="f9945-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="f9945-p118">Puoi inoltre verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema. Apri Editor del Registro di sistema e accedi alla chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, visualizzerai un valore denominato EnableSkypeUI con il valore 0.</span><span class="sxs-lookup"><span data-stu-id="f9945-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f9945-247">See also</span><span class="sxs-lookup"><span data-stu-id="f9945-247">Related topics</span></span>
[<span data-ttu-id="f9945-248">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f9945-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f9945-249">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="f9945-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
