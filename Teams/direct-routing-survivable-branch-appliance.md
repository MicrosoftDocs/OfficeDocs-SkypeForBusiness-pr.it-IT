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
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di base necessarie per la distribuzione e le considerazioni sul routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589240"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="82794-103">SBA (Survivable Branch Appliance) per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="82794-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="82794-104">In alcuni casi, un sito del cliente che usa Routing diretto per connettersi Telefono Microsoft sistema potrebbe verificarsi un'interruzione di Internet.</span><span class="sxs-lookup"><span data-stu-id="82794-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="82794-105">Si supponga che il sito del cliente, denominato filiale, temporaneamente non possa connettersi al cloud Microsoft tramite Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="82794-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="82794-106">Tuttavia, la Intranet all'interno del ramo è ancora completamente funzionante e gli utenti possono connettersi al Session Border Controller (SBC) che fornisce la connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="82794-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="82794-107">Questo articolo descrive come usare un Survivable Branch Appliance (SBA) per consentire a Telefono Microsoft System di continuare a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in caso di interruzione.</span><span class="sxs-lookup"><span data-stu-id="82794-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="82794-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="82794-108">Prerequisites</span></span>

<span data-ttu-id="82794-109">L'SBA è un codice distribuibile fornito da Microsoft ai fornitori SBC che incorporano il codice nel firmware o lo distribuiscono separatamente per fare in modo che SBA sia eseguito in una macchina virtuale o hardware separata.</span><span class="sxs-lookup"><span data-stu-id="82794-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="82794-110">Per ottenere il firmware più recente di Session Border Controller con il Survivable Branch Appliance incorporato, contattare il fornitore SBC.</span><span class="sxs-lookup"><span data-stu-id="82794-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="82794-111">Inoltre, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="82794-111">In addition, the following is required:</span></span>

- <span data-ttu-id="82794-112">L'SBC deve essere configurato per Media Bypass per assicurarsi che il client Microsoft Teams nel sito di succursale possa avere elementi multimediali che fluino direttamente con SBC.</span><span class="sxs-lookup"><span data-stu-id="82794-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="82794-113">TLS1.2 deve essere abilitato nel sistema operativo della macchina virtuale SBA.</span><span class="sxs-lookup"><span data-stu-id="82794-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="82794-114">Client Teams supportati</span><span class="sxs-lookup"><span data-stu-id="82794-114">Supported Teams clients</span></span>

<span data-ttu-id="82794-115">La caratteristica SBA è supportata nei client Microsoft Teams seguenti:</span><span class="sxs-lookup"><span data-stu-id="82794-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="82794-116">Microsoft Teams Windows desktop</span><span class="sxs-lookup"><span data-stu-id="82794-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="82794-117">Microsoft Teams desktop macOS</span><span class="sxs-lookup"><span data-stu-id="82794-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="82794-118">Come funziona</span><span class="sxs-lookup"><span data-stu-id="82794-118">How it works</span></span>

<span data-ttu-id="82794-119">Durante un'interruzione di Internet, il client Teams passare automaticamente all'SBA e le chiamate in corso dovrebbero continuare senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="82794-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="82794-120">Non è richiesta alcuna azione da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="82794-120">No action is required from the user.</span></span> <span data-ttu-id="82794-121">Non appena il client Teams rileva che Internet è in funzione e le chiamate in uscita vengono completate, il client torna alla normale modalità di funzionamento e si connette ad altri Teams servizi.</span><span class="sxs-lookup"><span data-stu-id="82794-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="82794-122">L'SBA carica i record dei dati delle chiamate raccolti nel cloud e la cronologia delle chiamate viene aggiornata in modo che queste informazioni siano disponibili per la revisione da parte dell'amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="82794-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="82794-123">Quando il client Microsoft Teams è in modalità offline, è disponibile la funzionalità correlata alle chiamate seguente:</span><span class="sxs-lookup"><span data-stu-id="82794-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="82794-124">Effettuare chiamate PSTN tramite SBA/SBC locale con elementi multimediali che fluire attraverso la SBC.</span><span class="sxs-lookup"><span data-stu-id="82794-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="82794-125">Ricezione di chiamate PSTN tramite SBA/SBC locale con elementi multimediali che scorrono attraverso la SBC.</span><span class="sxs-lookup"><span data-stu-id="82794-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="82794-126">Blocco e ripresa delle chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="82794-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="82794-127">Configurazione</span><span class="sxs-lookup"><span data-stu-id="82794-127">Configuration</span></span>

<span data-ttu-id="82794-128">Per il funzionamento della caratteristica SBA, il client di Teams deve sapere quali SBA sono disponibili in ogni sito di succursale e quali SBA sono assegnate agli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="82794-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="82794-129">I passaggi di configurazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="82794-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="82794-130">Creare le SBA.</span><span class="sxs-lookup"><span data-stu-id="82794-130">Create the SBAs.</span></span>
2. <span data-ttu-id="82794-131">Creare i criteri di Teams di succursale.</span><span class="sxs-lookup"><span data-stu-id="82794-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="82794-132">Assegnare il criterio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="82794-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="82794-133">Registrare un'applicazione per l'SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82794-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="82794-134">Tutta la configurazione viene eseguita usando Skype for Business cmdlet di PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="82794-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="82794-135">L'Teams di amministrazione non supporta ancora la funzionalità SBA Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="82794-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="82794-136">Per informazioni sulla configurazione di SBC, con collegamenti alla documentazione del fornitore SBC, vedere Configurazione di Session Border Controller alla fine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="82794-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="82794-137">Creare le SBA</span><span class="sxs-lookup"><span data-stu-id="82794-137">Create the SBAs</span></span>

<span data-ttu-id="82794-138">Per creare le SBA, si userà il cmdlet New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="82794-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="82794-139">Questo cmdlet ha i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="82794-139">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="82794-140">Parametro</span><span class="sxs-lookup"><span data-stu-id="82794-140">Parameter</span></span>| <span data-ttu-id="82794-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82794-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="82794-142">Identity</span><span class="sxs-lookup"><span data-stu-id="82794-142">Identity</span></span>  | <span data-ttu-id="82794-143">Identità dell'SBA</span><span class="sxs-lookup"><span data-stu-id="82794-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="82794-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="82794-144">Fqdn</span></span> | <span data-ttu-id="82794-145">FQDN dell'SBA</span><span class="sxs-lookup"><span data-stu-id="82794-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="82794-146">Sito</span><span class="sxs-lookup"><span data-stu-id="82794-146">Site</span></span> | <span data-ttu-id="82794-147">TenantNetworkSite in cui si trova l'SBA</span><span class="sxs-lookup"><span data-stu-id="82794-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="82794-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82794-148">Description</span></span> | <span data-ttu-id="82794-149">Formato testo libero</span><span class="sxs-lookup"><span data-stu-id="82794-149">Free format text</span></span> |
|||

<span data-ttu-id="82794-150">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="82794-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="82794-151">Creare i criteri Teams di succursale</span><span class="sxs-lookup"><span data-stu-id="82794-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="82794-152">Per creare un criterio, usare il cmdlet New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="82794-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="82794-153">Questo cmdlet ha i parametri seguenti.</span><span class="sxs-lookup"><span data-stu-id="82794-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="82794-154">Si noti che il criterio può contenere uno o più SBA.</span><span class="sxs-lookup"><span data-stu-id="82794-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="82794-155">Parametro</span><span class="sxs-lookup"><span data-stu-id="82794-155">Parameter</span></span>| <span data-ttu-id="82794-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82794-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="82794-157">Identity</span><span class="sxs-lookup"><span data-stu-id="82794-157">Identity</span></span> | <span data-ttu-id="82794-158">Identità dei criteri</span><span class="sxs-lookup"><span data-stu-id="82794-158">The identity of the policy</span></span> |
| <span data-ttu-id="82794-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="82794-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="82794-160">FQDN degli SBA nel sito</span><span class="sxs-lookup"><span data-stu-id="82794-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="82794-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="82794-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="82794-162">È possibile aggiungere o rimuovere IAS da un criterio usando il cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="82794-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="82794-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="82794-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="82794-164">Assegnare un criterio a un utente</span><span class="sxs-lookup"><span data-stu-id="82794-164">Assign a policy to a user</span></span>

<span data-ttu-id="82794-165">Per assegnare il criterio a singoli utenti, si userà il cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="82794-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="82794-166">Questo cmdlet ha i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="82794-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="82794-167">Parametro</span><span class="sxs-lookup"><span data-stu-id="82794-167">Parameter</span></span>| <span data-ttu-id="82794-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82794-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="82794-169">Identity</span><span class="sxs-lookup"><span data-stu-id="82794-169">Identity</span></span> | <span data-ttu-id="82794-170">L'identità dell'utente</span><span class="sxs-lookup"><span data-stu-id="82794-170">The identity of the user</span></span> |
| <span data-ttu-id="82794-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="82794-171">PolicyName</span></span> | <span data-ttu-id="82794-172">Identità dei criteri</span><span class="sxs-lookup"><span data-stu-id="82794-172">The identity of the policy</span></span> |
||

<span data-ttu-id="82794-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="82794-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="82794-174">È possibile rimuovere un criterio da un utente concedendo $Null criteri di protezione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="82794-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="82794-175">Registrare un'applicazione per l'SBA con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="82794-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="82794-176">Per consentire a SBA diversi usati all'interno del tenant di leggere i dati necessari da Microsoft 365, è necessario registrare un'applicazione per l'SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82794-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="82794-177">Per altre informazioni sulla registrazione dell'applicazione, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="82794-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="82794-178">Sviluppare app line-of-business per Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="82794-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="82794-179">[Registrare un'applicazione con il Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="82794-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="82794-180">È necessario registrare una sola applicazione per l'uso da parte di tutti gli SBA nel tenant.</span><span class="sxs-lookup"><span data-stu-id="82794-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="82794-181">Per la registrazione SBA, sono necessari i valori seguenti creati dalla registrazione:</span><span class="sxs-lookup"><span data-stu-id="82794-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="82794-182">ID applicazione (client)</span><span class="sxs-lookup"><span data-stu-id="82794-182">Application (client) ID</span></span> 
- <span data-ttu-id="82794-183">Segreto client</span><span class="sxs-lookup"><span data-stu-id="82794-183">Client secret</span></span> 

<span data-ttu-id="82794-184">Per l'applicazione SBA, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="82794-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="82794-185">Il nome può essere quello che si decide.</span><span class="sxs-lookup"><span data-stu-id="82794-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="82794-186">Tipi di account supportati = Account solo in questa directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82794-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="82794-187">Uri di reindirizzamento Web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="82794-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="82794-188">Token di concessione implicita = token di accesso e token ID.</span><span class="sxs-lookup"><span data-stu-id="82794-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="82794-189">Autorizzazioni API = Skype e Teams di amministrazione tenant -> autorizzazioni dell'applicazione -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="82794-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="82794-190">Segreto client: è possibile usare qualsiasi descrizione e scadenza.</span><span class="sxs-lookup"><span data-stu-id="82794-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="82794-191">Ricordarsi di copiare il segreto client subito dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="82794-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="82794-192">L'ID applicazione (client) viene visualizzato nella scheda Panoramica.</span><span class="sxs-lookup"><span data-stu-id="82794-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="82794-193">Quindi, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="82794-193">Then follow these steps:</span></span>

1. <span data-ttu-id="82794-194">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="82794-194">Register the application.</span></span>
2. <span data-ttu-id="82794-195">Impostare i token di concessione impliciti.</span><span class="sxs-lookup"><span data-stu-id="82794-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="82794-196">Impostare le autorizzazioni API.</span><span class="sxs-lookup"><span data-stu-id="82794-196">Set the API permissions.</span></span>
4. <span data-ttu-id="82794-197">Creare il segreto client.</span><span class="sxs-lookup"><span data-stu-id="82794-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="82794-198">Configurazione di Session Border Controller</span><span class="sxs-lookup"><span data-stu-id="82794-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="82794-199">Per istruzioni dettagliate su come configurare session border controller con il Survivable Branch Appliance incorporato, vedere la documentazione fornita dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="82794-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="82794-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="82794-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="82794-201">Barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="82794-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="82794-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="82794-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="82794-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="82794-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="82794-204">Segnalazione di problemi</span><span class="sxs-lookup"><span data-stu-id="82794-204">Reporting issues</span></span>

<span data-ttu-id="82794-205">Segnalare eventuali problemi all'organizzazione di supporto del fornitore SBC.</span><span class="sxs-lookup"><span data-stu-id="82794-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="82794-206">Quando si segnala il problema, indicare che è configurato un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="82794-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="82794-207">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="82794-207">Known issues</span></span>

- <span data-ttu-id="82794-208">Quando si aggiungono nuovi Survivable Branch Appliance, può essere necessario del tempo prima di poterli usare nei criteri di Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="82794-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="82794-209">Quando si assegnano criteri di Survivable Branch Appliance a un utente, potrebbe essere necessario del tempo prima che l'SBA venga visualizzato nell'output di Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="82794-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="82794-210">La ricerca inversa dei numeri nei contatti di Azure AD non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="82794-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="82794-211">L'SBA non supporta le impostazioni di inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="82794-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="82794-212">L'esecuzione di una chiamata di emergenza a un numero di emergenza configurato per le chiamate di emergenza dinamiche (E911) non è supportata.</span><span class="sxs-lookup"><span data-stu-id="82794-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>
