---
title: Decidere come gestire gli attributi dopo la rimozione delle autorizzazioni
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In questo articolo viene descritto come gestire gli attributi dopo la rimozione delle autorizzazioni dell'ambiente locale.
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458992"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="609ac-103">Decidere come gestire gli attributi dopo la rimozione delle autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="609ac-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="609ac-104">Per impostazione predefinita, tutti gli utenti precedentemente abilitati per Skype for Business Server e successivamente spostati nel cloud hanno ancora attributi msRTCSIP configurati in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="609ac-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="609ac-105">Questi attributi, in particolare l'indirizzo sip (msRTCSIP-PrimaryUserAddress) e il numero di telefono potenzialmente (msRTCSIP-Line), continuano a essere sincronizzati in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="609ac-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="609ac-106">Se sono necessarie modifiche a uno degli attributi msRTCSIP, queste modifiche devono essere apportate in Active Directory locale e quindi sincronizzate con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="609ac-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="609ac-107">Tuttavia, una volta rimossa Skype for Business Server distribuzione, gli Skype for Business Server non saranno disponibili per gestire questi attributi.</span><span class="sxs-lookup"><span data-stu-id="609ac-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="609ac-108">Sono disponibili due opzioni per gestire questa situazione:</span><span class="sxs-lookup"><span data-stu-id="609ac-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="609ac-109">Lasciare gli utenti abilitati Skype for Business account del server e gestire gli attributi msRTCSIP utilizzando gli strumenti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="609ac-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="609ac-110">Ciò garantisce la perdita del servizio per gli utenti migrati e consente di rimuovere facilmente la distribuzione di Skype for Business Server eliminando (ad esempio, la cancellazione) dei server, senza una rimozione completa.</span><span class="sxs-lookup"><span data-stu-id="609ac-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="609ac-111">Tuttavia, i nuovi utenti con licenza non avranno questi attributi popolati in Active Directory locale e dovranno essere gestiti online.</span><span class="sxs-lookup"><span data-stu-id="609ac-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="609ac-112">Cancellare tutti gli attributi msRTCSIP dagli utenti migrati in Active Directory locale e gestire questi attributi utilizzando gli strumenti online.</span><span class="sxs-lookup"><span data-stu-id="609ac-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="609ac-113">Questo metodo consente un approccio di gestione coerente per gli utenti esistenti e nuovi, tuttavia può potenzialmente causare una perdita temporanea del servizio durante il processo di rimozione delle autorizzazioni locale.</span><span class="sxs-lookup"><span data-stu-id="609ac-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="609ac-114">Metodo 1 - Gestire gli indirizzi SIP e i numeri di telefono per gli utenti in Active Directory</span><span class="sxs-lookup"><span data-stu-id="609ac-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="609ac-115">Gli amministratori possono gestire gli utenti spostati in precedenza da un Skype for Business Server locale al cloud, anche dopo la rimozione della distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="609ac-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="609ac-116">Se si desidera apportare modifiche all'indirizzo SIP di un utente o al numero di telefono di un utente (e l'indirizzo sip o il numero di telefono ha già un valore in Active Directory locale), è necessario eseguire questa operazione in Active Directory locale e consentire il flusso dei valori fino ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="609ac-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="609ac-117">Non richiede l'utilizzo di Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="609ac-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="609ac-118">È invece possibile modificare questi attributi direttamente in Active Directory locale, utilizzando lo snap-in MMC Utenti e computer di Active Directory (come illustrato di seguito) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="609ac-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="609ac-119">Se si utilizza lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Editor attributi e individuare gli attributi appropriati da modificare:</span><span class="sxs-lookup"><span data-stu-id="609ac-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="609ac-120">Per modificare l'indirizzo SIP di un utente, modificare la proprietà `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="609ac-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="609ac-121">Se `ProxyAddresses` l'attributo contiene un indirizzo SIP, aggiornare anche tale valore come procedura consigliata.</span><span class="sxs-lookup"><span data-stu-id="609ac-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="609ac-122">Anche se l'indirizzo sip in viene ignorato da O365 se viene popolato, può essere utilizzato `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` da altri componenti locali.</span><span class="sxs-lookup"><span data-stu-id="609ac-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="609ac-123">Per modificare il numero di telefono di un utente, modificare `msRTCSIP-Line` *se ha già un valore*.</span><span class="sxs-lookup"><span data-stu-id="609ac-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Strumento Utenti e computer di Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="609ac-125">Se l'utente originariamente non aveva un valore per l'ambiente locale prima dello spostamento, è possibile modificare il numero di telefono utilizzando il parametro - nel `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) nel modulo powerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="609ac-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="609ac-126">Questi passaggi non sono necessari per i nuovi utenti creati dopo la disabilitazione ibrida e possono essere gestiti direttamente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="609ac-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="609ac-127">Se si ha familiarità con l'utilizzo della combinazione di questi metodi e con l'abbandono degli attributi msRTCSIP in locale in Active Directory, è possibile semplicemente ri-immagine dei server Skype for Business locali.</span><span class="sxs-lookup"><span data-stu-id="609ac-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="609ac-128">Tuttavia, se si preferisce cancellare tutti gli attributi msRTCSIP ed eseguire una disinstallazione tradizionale di Skype for Business Server, utilizzare il metodo 2.</span><span class="sxs-lookup"><span data-stu-id="609ac-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="609ac-129">Metodo 2 - Cancellare Skype for Business per tutti gli utenti locali in Active Directory</span><span class="sxs-lookup"><span data-stu-id="609ac-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="609ac-130">Questa opzione richiede ulteriori sforzi e una pianificazione adeguata perché è necessario eseguire di nuovo il provisioning degli utenti spostati in precedenza da un Skype for Business Server locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="609ac-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="609ac-131">Questi utenti possono essere categorizzati in due categorie diverse: gli utenti senza Sistema telefonico e gli utenti con Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="609ac-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="609ac-132">Gli utenti con Sistema telefonico si verificano una perdita temporanea del servizio telefonico durante la transizione del numero di telefono dalla gestione in Active Directory locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="609ac-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="609ac-133">**È consigliabile eseguire un progetto pilota che coinvolge un numero limitato di utenti con Sistema telefonico prima di avviare le operazioni in blocco degli utenti.**</span><span class="sxs-lookup"><span data-stu-id="609ac-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="609ac-134">Per distribuzioni di grandi dimensioni gli utenti possono essere elaborati in gruppi più piccoli in finestre di tempo diverse.</span><span class="sxs-lookup"><span data-stu-id="609ac-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="609ac-135">Questo processo è più semplice per gli utenti che hanno un indirizzo SIP e UserPrincipalName corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="609ac-136">Per le organizzazioni con utenti con valori non corrispondenti tra questi due attributi, è necessario fare attenzione come indicato di seguito per una transizione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="609ac-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="609ac-137">Se sono stati configurati endpoint dell'applicazione ibrida locale per operatori automatici o code di chiamata, assicurarsi di spostare questi endpoint in Microsoft 365 prima di rimuovere le autorizzazioni Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="609ac-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="609ac-138">Verificare che il seguente cmdlet di PowerShell Skype for Business locale restituisca un risultato vuoto.</span><span class="sxs-lookup"><span data-stu-id="609ac-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="609ac-139">Un risultato vuoto indica che nessun utente è ospitato in locale e che è stato spostato in Microsoft 365 o è stato disabilitato:</span><span class="sxs-lookup"><span data-stu-id="609ac-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="609ac-140">Registrare il numero di telefono corrente degli utenti (LineUri), UserPrincipalName e le informazioni correlate eseguendo il cmdlet di PowerShell Skype for Business Server locale seguente per esportare i dati degli utenti:</span><span class="sxs-lookup"><span data-stu-id="609ac-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="609ac-141">Prima di procedere con SfbUserSettings.csv file e verificare che tutti i dati utente siano stati esportati correttamente.</span><span class="sxs-lookup"><span data-stu-id="609ac-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="609ac-142">È consigliabile conservare una copia di questo file.</span><span class="sxs-lookup"><span data-stu-id="609ac-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="609ac-143">Non utilizzare questo file nei passaggi seguenti per l'elaborazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="609ac-144">Creare un file con un gruppo di utenti da utilizzare nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="609ac-145">Una volta completato correttamente il primo gruppo di utenti, procedere con il gruppo di utenti successivo.</span><span class="sxs-lookup"><span data-stu-id="609ac-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="609ac-146">Nell'esempio seguente i gruppi di utenti vengono selezionati in ordine alfabetico, ma è possibile filtrare gli utenti in base ai criteri che corrispondono al modo in cui si desidera elaborare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="609ac-147">Prima di procedere con SfbUsers.csv file e verificare che i dati utente siano stati esportati correttamente.</span><span class="sxs-lookup"><span data-stu-id="609ac-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="609ac-148">In un passaggio successivo saranno necessari LineUri (numero di telefono), UserPrincipalName, SamAccountName e SipAddress da questo file.</span><span class="sxs-lookup"><span data-stu-id="609ac-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="609ac-149">Eliminare le informazioni sugli attributi Skype for Business Server da Active Directory per il set di utenti pronti per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="609ac-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="609ac-150">Esistono 2 passaggi per questo processo, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="609ac-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="609ac-151">Dopo il ciclo di AAD Sync successivo dopo l'esecuzione di questo passaggio, gli utenti con Sistema telefonico spostati in precedenza da un Skype for Business Server locale al cloud perderanno la possibilità di effettuare e ricevere chiamate fino al completamento e alla conferma del passaggio 8 nel passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="609ac-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="609ac-152">Inoltre, assicurati di aver salvato i numeri di telefono e le informazioni correlate dell'utente secondo il passaggio 2, poiché queste informazioni sono necessarie per tale passaggio.</span><span class="sxs-lookup"><span data-stu-id="609ac-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="609ac-153">Successivamente, per lo stesso set di utenti, cancellare il valore di msRTCSIP-DeploymentLocator usando PowerShell di Active Directory locale:</span><span class="sxs-lookup"><span data-stu-id="609ac-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="609ac-154">Eseguire il seguente cmdlet di Active Directory Windows PowerShell locale per aggiungere nuovamente il valore dell'indirizzo SIP ai proxyAddresses di Active Directory locali.</span><span class="sxs-lookup"><span data-stu-id="609ac-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="609ac-155">In questo modo si evitano problemi di interoperabilità che si basano su questo attributo.</span><span class="sxs-lookup"><span data-stu-id="609ac-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="609ac-156">Esegui Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="609ac-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="609ac-157">Attendere il completamento del provisioning degli utenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="609ac-158">È possibile monitorare lo stato di avanzamento del provisioning degli utenti eseguendo il comando Skype for Business PowerShell online seguente.</span><span class="sxs-lookup"><span data-stu-id="609ac-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="609ac-159">Il comando Skype for Business PowerShell online seguente restituisce un risultato vuoto non appena il processo viene completato.</span><span class="sxs-lookup"><span data-stu-id="609ac-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="609ac-160">Eseguire il seguente comando Skype for Business PowerShell online per assegnare numeri di telefono e abilitare gli utenti per Sistema telefonico:</span><span class="sxs-lookup"><span data-stu-id="609ac-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="609ac-161">Se si dispone ancora di endpoint Skype for Business (client Skype o telefoni di terze parti), è anche necessario impostare -HostedVoiceMail su $true.</span><span class="sxs-lookup"><span data-stu-id="609ac-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="609ac-162">Se l'organizzazione usa solo Teams endpoint per gli utenti abilitati alla funzionalità vocale, questa impostazione non è applicabile agli utenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="609ac-163">Verificare che il provisioning degli Sistema telefonico funzionalità sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="609ac-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="609ac-164">Il comando Skype for Business PowerShell online seguente restituisce un risultato vuoto non appena il processo viene completato.</span><span class="sxs-lookup"><span data-stu-id="609ac-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="609ac-165">Ripetere i passaggi da 3 a 9 finché non vengono elaborati tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="609ac-166">Verificare che tutti gli utenti siano stati elaborati correttamente eseguendo i due comandi di PowerShell seguenti.</span><span class="sxs-lookup"><span data-stu-id="609ac-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="609ac-167">Comando PowerShell Skype for Business Server locale:</span><span class="sxs-lookup"><span data-stu-id="609ac-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="609ac-168">Skype for Business Comando PowerShell online:</span><span class="sxs-lookup"><span data-stu-id="609ac-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="609ac-169">Dopo aver completato tutti i passaggi nel metodo 2, vedere Spostare gli endpoint dell'applicazione ibrida da locale a [online](decommission-move-on-prem-endpoints.md) e Rimuovere il [Skype for Business Server](decommission-remove-on-prem.md) locale per ulteriori passaggi per rimuovere la distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="609ac-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="609ac-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="609ac-170">See also</span></span>

- [<span data-ttu-id="609ac-171">Consolidamento cloud per Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="609ac-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="609ac-172">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="609ac-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

