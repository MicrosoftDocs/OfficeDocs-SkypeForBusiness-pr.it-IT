---
title: Routing diretto SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di distribuzione di base necessarie e considerazioni sul routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196490"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="087ea-103">Appliance diramazione configurabile (SBA) per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="087ea-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="087ea-104">In alcuni casi, un sito del cliente che usa l'instradamento diretto per connettersi al Sistema telefonico Microsoft potrebbe verificarsi un'interruzione di Internet.</span><span class="sxs-lookup"><span data-stu-id="087ea-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="087ea-105">Si supponga che il sito del cliente, detto ramo, non sia temporaneamente in grado di connettersi al cloud Microsoft tramite l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="087ea-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="087ea-106">Tuttavia, la Intranet all'interno del ramo è ancora completamente funzionale e gli utenti possono connettersi al controller dei confini della sessione (SBC) che fornisce connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="087ea-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="087ea-107">In questo articolo viene descritto come utilizzare un appliance SBA (ESA) per consentire al Sistema telefonico Microsoft di continuare a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in caso di interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="087ea-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="087ea-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="087ea-108">Prerequisites</span></span>

<span data-ttu-id="087ea-109">L'SBA è codice distribuibile fornito da Microsoft ai fornitori di SBC che quindi incorporano il codice nel firmware o lo distribuiscono separatamente per eseguirlo in una macchina virtuale o hardware separata.</span><span class="sxs-lookup"><span data-stu-id="087ea-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="087ea-110">Per ottenere l'ultima versione del firmware session border controller con l'appliance SBC embedded, contattare il fornitore del controller SBC.</span><span class="sxs-lookup"><span data-stu-id="087ea-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="087ea-111">Inoltre, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="087ea-111">In addition, the following is required:</span></span>

- <span data-ttu-id="087ea-112">È necessario configurare SBC per il bypass multimediale per garantire che il client Microsoft Teams nel sito di succursale possa disporre di elementi multimediali direttamente con SBC.</span><span class="sxs-lookup"><span data-stu-id="087ea-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="087ea-113">TLS1.2 deve essere abilitato nel sistema operativo SBA VM.</span><span class="sxs-lookup"><span data-stu-id="087ea-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="087ea-114">Client di Teams supportati</span><span class="sxs-lookup"><span data-stu-id="087ea-114">Supported Teams clients</span></span>

<span data-ttu-id="087ea-115">La funzionalità SBA è supportata nei client Microsoft Teams seguenti:</span><span class="sxs-lookup"><span data-stu-id="087ea-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="087ea-116">Microsoft Teams per Windows desktop</span><span class="sxs-lookup"><span data-stu-id="087ea-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="087ea-117">Microsoft Teams macOS desktop</span><span class="sxs-lookup"><span data-stu-id="087ea-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="087ea-118">Come funziona</span><span class="sxs-lookup"><span data-stu-id="087ea-118">How it works</span></span>

<span data-ttu-id="087ea-119">Durante un'interruzione della connessione Internet, il client Teams dovrebbe passare automaticamente all'SBA e le chiamate in corso dovrebbero continuare senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="087ea-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="087ea-120">Non è richiesta alcuna azione da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="087ea-120">No action is required from the user.</span></span> <span data-ttu-id="087ea-121">Non appena il client Teams rileva che Internet è in funzione e le chiamate in uscita sono completate, il client torna alla modalità normale e si connette ad altri servizi di Teams.</span><span class="sxs-lookup"><span data-stu-id="087ea-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="087ea-122">L'SBA carica i dati di chiamata raccolti nel cloud e la cronologia delle chiamate viene aggiornata in modo che queste informazioni siano disponibili per la revisione da parte dell'amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="087ea-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="087ea-123">Quando il client Microsoft Teams è in modalità offline, è disponibile la seguente funzionalità correlata alle chiamate:</span><span class="sxs-lookup"><span data-stu-id="087ea-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="087ea-124">Effettuare chiamate PSTN tramite SBA/SBC locale con elementi multimediali che attraversano l'SBC.</span><span class="sxs-lookup"><span data-stu-id="087ea-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="087ea-125">Ricezione di chiamate PSTN tramite SBA/SBC locale con elementi multimediali che attraversano l'SBC.</span><span class="sxs-lookup"><span data-stu-id="087ea-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="087ea-126">In attesa e ripresa delle chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="087ea-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="087ea-127">Configurazione</span><span class="sxs-lookup"><span data-stu-id="087ea-127">Configuration</span></span>

<span data-ttu-id="087ea-128">Per il funzionamento della funzionalità SBA, il client Teams deve sapere quali SBA sono disponibili in ogni sito di succursale e quali SBA sono assegnate agli utenti nel sito.</span><span class="sxs-lookup"><span data-stu-id="087ea-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="087ea-129">I passaggi di configurazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="087ea-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="087ea-130">Creare gli SBA.</span><span class="sxs-lookup"><span data-stu-id="087ea-130">Create the SBAs.</span></span>
2. <span data-ttu-id="087ea-131">Creare i criteri di affidabilità dei rami di Teams.</span><span class="sxs-lookup"><span data-stu-id="087ea-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="087ea-132">Assegnare il criterio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="087ea-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="087ea-133">Registrare un'applicazione per sBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="087ea-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="087ea-134">Tutte le configurazioni vengono eseguite usando i cmdlet di PowerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="087ea-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="087ea-135">L'interfaccia di amministrazione di Teams non supporta ancora la funzionalità Direct Routing SBA.</span><span class="sxs-lookup"><span data-stu-id="087ea-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="087ea-136">Per informazioni sulla configurazione di SBC, con collegamenti alla documentazione del fornitore di SBC, vedere la configurazione di Session Border Controller alla fine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="087ea-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="087ea-137">Creare gli SBA</span><span class="sxs-lookup"><span data-stu-id="087ea-137">Create the SBAs</span></span>

<span data-ttu-id="087ea-138">Per creare gli SBA, si userà il cmdlet New-CsTeamsSurvivableBranchAppliance istruzione.</span><span class="sxs-lookup"><span data-stu-id="087ea-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="087ea-139">Questo cmdlet contiene i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="087ea-139">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="087ea-140">Parametro</span><span class="sxs-lookup"><span data-stu-id="087ea-140">Parameter</span></span>| <span data-ttu-id="087ea-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="087ea-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="087ea-142">Identity</span><span class="sxs-lookup"><span data-stu-id="087ea-142">Identity</span></span>  | <span data-ttu-id="087ea-143">Identità dell'SBA</span><span class="sxs-lookup"><span data-stu-id="087ea-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="087ea-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="087ea-144">Fqdn</span></span> | <span data-ttu-id="087ea-145">Nome di dominio completo dell'SBA</span><span class="sxs-lookup"><span data-stu-id="087ea-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="087ea-146">Sito</span><span class="sxs-lookup"><span data-stu-id="087ea-146">Site</span></span> | <span data-ttu-id="087ea-147">TenantNetworkSite in cui si trova l'SBA</span><span class="sxs-lookup"><span data-stu-id="087ea-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="087ea-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="087ea-148">Description</span></span> | <span data-ttu-id="087ea-149">Testo in formato libero</span><span class="sxs-lookup"><span data-stu-id="087ea-149">Free format text</span></span> |
|||

<span data-ttu-id="087ea-150">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="087ea-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="087ea-151">Creare i criteri di affidabilità dei rami di Teams</span><span class="sxs-lookup"><span data-stu-id="087ea-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="087ea-152">Per creare un criterio, usare il cmdlet New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="087ea-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="087ea-153">Questo cmdlet contiene i parametri seguenti.</span><span class="sxs-lookup"><span data-stu-id="087ea-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="087ea-154">Si noti che il criterio può contenere uno o più SBA.</span><span class="sxs-lookup"><span data-stu-id="087ea-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="087ea-155">Parametro</span><span class="sxs-lookup"><span data-stu-id="087ea-155">Parameter</span></span>| <span data-ttu-id="087ea-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="087ea-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="087ea-157">Identity</span><span class="sxs-lookup"><span data-stu-id="087ea-157">Identity</span></span> | <span data-ttu-id="087ea-158">Identità del criterio</span><span class="sxs-lookup"><span data-stu-id="087ea-158">The identity of the policy</span></span> |
| <span data-ttu-id="087ea-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="087ea-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="087ea-160">Nome completo degli SBA nel sito</span><span class="sxs-lookup"><span data-stu-id="087ea-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="087ea-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="087ea-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="087ea-162">È possibile aggiungere o rimuovere gli SBA da un criterio usando il cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy locale.</span><span class="sxs-lookup"><span data-stu-id="087ea-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="087ea-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="087ea-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="087ea-164">Assegnare criteri a un utente</span><span class="sxs-lookup"><span data-stu-id="087ea-164">Assign a policy to a user</span></span>

<span data-ttu-id="087ea-165">Per assegnare il criterio a singoli utenti, si userà il cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="087ea-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="087ea-166">Questo cmdlet contiene i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="087ea-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="087ea-167">Parametro</span><span class="sxs-lookup"><span data-stu-id="087ea-167">Parameter</span></span>| <span data-ttu-id="087ea-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="087ea-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="087ea-169">Identity</span><span class="sxs-lookup"><span data-stu-id="087ea-169">Identity</span></span> | <span data-ttu-id="087ea-170">Identità dell'utente</span><span class="sxs-lookup"><span data-stu-id="087ea-170">The identity of the user</span></span> |
| <span data-ttu-id="087ea-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="087ea-171">PolicyName</span></span> | <span data-ttu-id="087ea-172">Identità dei criteri</span><span class="sxs-lookup"><span data-stu-id="087ea-172">The identity of the policy</span></span> |
||

<span data-ttu-id="087ea-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="087ea-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="087ea-174">È possibile rimuovere un criterio da un utente concedendo il criterio di $Null predefinito, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="087ea-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="087ea-175">Registrare un'applicazione per sBA con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="087ea-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="087ea-176">Per consentire a SBA diversi usati all'interno del tenant di leggere i dati necessari da Microsoft 365, è necessario registrare un'applicazione per l'SBA in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="087ea-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="087ea-177">Per altre informazioni sulla registrazione delle applicazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="087ea-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="087ea-178">Sviluppare app line-of-business per Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="087ea-178">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="087ea-179">[Registrare un'applicazione nella piattaforma di identità Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="087ea-179">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="087ea-180">È necessario registrare una sola applicazione per l'uso da parte di tutti gli account di servizio (SBA) nel tenant.</span><span class="sxs-lookup"><span data-stu-id="087ea-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="087ea-181">Per la registrazione dell'SBA, sono necessari i valori seguenti creati dalla registrazione:</span><span class="sxs-lookup"><span data-stu-id="087ea-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="087ea-182">ID applicazione (client)</span><span class="sxs-lookup"><span data-stu-id="087ea-182">Application (client) ID</span></span> 
- <span data-ttu-id="087ea-183">Segreto client</span><span class="sxs-lookup"><span data-stu-id="087ea-183">Client secret</span></span> 

<span data-ttu-id="087ea-184">Per l'applicazione SBA, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="087ea-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="087ea-185">Il nome può essere quello che si decide.</span><span class="sxs-lookup"><span data-stu-id="087ea-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="087ea-186">Tipi di account supportati = Account solo in questa directory organizzativa.</span><span class="sxs-lookup"><span data-stu-id="087ea-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="087ea-187">L'URI reindirizzamento Web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="087ea-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="087ea-188">Token di concessione impliciti = token di accesso e token ID.</span><span class="sxs-lookup"><span data-stu-id="087ea-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="087ea-189">Autorizzazioni API = Accesso amministratore tenant Skype e Teams -> autorizzazioni applicazione -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="087ea-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="087ea-190">Segreto client: è possibile usare qualsiasi descrizione e scadenza.</span><span class="sxs-lookup"><span data-stu-id="087ea-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="087ea-191">Ricordarsi di copiare il segreto client immediatamente dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="087ea-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="087ea-192">ID applicazione (client) visualizzato nella scheda Panoramica.</span><span class="sxs-lookup"><span data-stu-id="087ea-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="087ea-193">Quindi, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="087ea-193">Then follow these steps:</span></span>

1. <span data-ttu-id="087ea-194">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="087ea-194">Register the application.</span></span>
2. <span data-ttu-id="087ea-195">Impostare i token di concessione impliciti.</span><span class="sxs-lookup"><span data-stu-id="087ea-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="087ea-196">Impostare le autorizzazioni API.</span><span class="sxs-lookup"><span data-stu-id="087ea-196">Set the API permissions.</span></span>
4. <span data-ttu-id="087ea-197">Creare il segreto client.</span><span class="sxs-lookup"><span data-stu-id="087ea-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="087ea-198">Configurazione di Session Border Controller</span><span class="sxs-lookup"><span data-stu-id="087ea-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="087ea-199">Per istruzioni dettagliate su come configurare il controller dei confini della sessione con l'appliance Diramazione configurabile incorporato, vedere la documentazione fornita dal fornitore di SBC:</span><span class="sxs-lookup"><span data-stu-id="087ea-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="087ea-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="087ea-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="087ea-201">Barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="087ea-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="087ea-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="087ea-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="087ea-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="087ea-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="087ea-204">Segnalazione di problemi</span><span class="sxs-lookup"><span data-stu-id="087ea-204">Reporting issues</span></span>

<span data-ttu-id="087ea-205">Segnalare eventuali problemi all'organizzazione di supporto del fornitore di SBC.</span><span class="sxs-lookup"><span data-stu-id="087ea-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="087ea-206">Quando si segnala il problema, indicare che è stato configurato un appliance diramazione configurabile.</span><span class="sxs-lookup"><span data-stu-id="087ea-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="087ea-207">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="087ea-207">Known issues</span></span>

- <span data-ttu-id="087ea-208">Quando si aggiungono nuovi appliance per branch utilizzabili, può essere necessario del tempo prima che sia possibile usarli nei criteri per le appliance di succursale configurabili.</span><span class="sxs-lookup"><span data-stu-id="087ea-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="087ea-209">Quando si assegnano i criteri per l'appliance a ramo configurabile a un utente, può essere necessario del tempo prima che l'SBA venga visualizzato nell'output di Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="087ea-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="087ea-210">La ricerca inversa dei numeri nei contatti di Azure AD non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="087ea-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="087ea-211">L'SBA non supporta le impostazioni di inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="087ea-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="087ea-212">Non è possibile effettuare chiamate di emergenza a un numero di emergenza configurato per le chiamate di emergenza dinamiche (E911).</span><span class="sxs-lookup"><span data-stu-id="087ea-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="087ea-213">L'output Get-CsOnlineUser mostra TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="087ea-213">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
