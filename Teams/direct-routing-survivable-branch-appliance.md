---
title: SBA routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di distribuzione principali necessarie e le considerazioni relative al routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9e64dc908bafdd63b17e22716e76c4f04df1409
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588600"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="23914-103">Survivable Branch Appliance (SBA) per il routing diretto-anteprima pubblica</span><span class="sxs-lookup"><span data-stu-id="23914-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="23914-104">Si tratta di una versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="23914-104">This is a public preview release.</span></span>

<span data-ttu-id="23914-105">Occasionalmente, un sito del cliente che usa il routing diretto per la connessione al sistema telefonico Microsoft può avvertire un'interruzione di Internet.</span><span class="sxs-lookup"><span data-stu-id="23914-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="23914-106">Supponiamo che il sito del cliente, detto ramo, non possa connettersi temporaneamente al cloud Microsoft tramite il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="23914-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="23914-107">Tuttavia, l'Intranet all'interno del ramo è ancora completamente funzionante e gli utenti possono connettersi al controller di bordo della sessione che fornisce connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="23914-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="23914-108">Questo articolo descrive come usare un Survivable Branch Appliance (SBA) per consentire a Microsoft Phone System di continuare a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in caso di interruzione.</span><span class="sxs-lookup"><span data-stu-id="23914-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23914-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="23914-109">Prerequisites</span></span>

<span data-ttu-id="23914-110">L'SBA è un codice distribuibile fornito da Microsoft ai fornitori SBC che incorporano il codice nel firmware del proprio SBCs.</span><span class="sxs-lookup"><span data-stu-id="23914-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed the code into the firmware of their SBCs.</span></span> 

<span data-ttu-id="23914-111">Per ottenere il firmware più recente del controller di bordo della sessione con l'appliance Survivable embedded, contattare il fornitore SBC.</span><span class="sxs-lookup"><span data-stu-id="23914-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="23914-112">Inoltre, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="23914-112">In addition, the following is required:</span></span>

- <span data-ttu-id="23914-113">SBC deve essere configurato per il bypass multimediale per verificare che il client Microsoft Teams nel sito di succursale possa avere flussi multimediali direttamente con SBC.</span><span class="sxs-lookup"><span data-stu-id="23914-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="23914-114">TLS 1.2 deve essere abilitato nel sistema operativo della SBA VM.</span><span class="sxs-lookup"><span data-stu-id="23914-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="23914-115">Client Team supportati</span><span class="sxs-lookup"><span data-stu-id="23914-115">Supported Teams clients</span></span>

<span data-ttu-id="23914-116">La funzionalità SBA è supportata nei client Microsoft Team seguenti:</span><span class="sxs-lookup"><span data-stu-id="23914-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="23914-117">Windows desktop di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23914-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="23914-118">Desktop di Microsoft teams macOS</span><span class="sxs-lookup"><span data-stu-id="23914-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="23914-119">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="23914-119">How it works</span></span>

<span data-ttu-id="23914-120">Durante un'interruzione di Internet, il client teams dovrebbe passare automaticamente alla SBA e le chiamate in corso dovrebbero continuare senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="23914-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="23914-121">Non è necessaria alcuna azione da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="23914-121">No action is required from the user.</span></span> <span data-ttu-id="23914-122">Non appena il client teams rileva che Internet è alto e tutte le chiamate in uscita sono terminate, il client ritornerà alla modalità operativa normale e si collegherà ad altri servizi di teams.</span><span class="sxs-lookup"><span data-stu-id="23914-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="23914-123">L'SBA caricherà i record di dati delle chiamate raccolti nel cloud e la cronologia delle chiamate verrà aggiornata in modo che queste informazioni siano disponibili per la revisione da parte dell'amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="23914-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="23914-124">Quando il client Microsoft teams è in modalità offline, è disponibile la seguente funzionalità relativa alle chiamate:</span><span class="sxs-lookup"><span data-stu-id="23914-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="23914-125">Effettuare chiamate PSTN tramite SBA/SBC locale con il flusso di elementi multimediali attraverso SBC.</span><span class="sxs-lookup"><span data-stu-id="23914-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="23914-126">Ricezione di chiamate PSTN tramite SBA/SBC locale con il flusso di elementi multimediali attraverso SBC.</span><span class="sxs-lookup"><span data-stu-id="23914-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="23914-127">Tenere premuto e riprendere le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="23914-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="23914-128">Configurazione</span><span class="sxs-lookup"><span data-stu-id="23914-128">Configuration</span></span>

<span data-ttu-id="23914-129">Per il funzionamento della funzionalità SBA, il client Teams deve sapere quali SBAs sono disponibili in ogni sito di succursale e quali SBAs sono assegnati agli utenti di tale sito.</span><span class="sxs-lookup"><span data-stu-id="23914-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="23914-130">I passaggi di configurazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="23914-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="23914-131">Creare il SBAs.</span><span class="sxs-lookup"><span data-stu-id="23914-131">Create the SBAs.</span></span>
2. <span data-ttu-id="23914-132">Creare i criteri di sopravvivenza della filiale teams.</span><span class="sxs-lookup"><span data-stu-id="23914-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="23914-133">Assegnare il criterio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="23914-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="23914-134">Registrare un'applicazione per l'SBA con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="23914-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="23914-135">Tutta la configurazione viene eseguita usando i cmdlet di PowerShell per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="23914-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="23914-136">L'interfaccia di amministrazione di teams non supporta ancora la funzionalità Direct routing SBA.</span><span class="sxs-lookup"><span data-stu-id="23914-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="23914-137">Per informazioni sulla configurazione di SBC, con collegamenti alla documentazione del fornitore di SBC, vedere Configurazione del controller bordo sessione alla fine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="23914-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="23914-138">Creare il SBAs</span><span class="sxs-lookup"><span data-stu-id="23914-138">Create the SBAs</span></span>

<span data-ttu-id="23914-139">Per creare il SBAs, si utilizzerà il cmdlet New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="23914-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="23914-140">Questo cmdlet ha i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="23914-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="23914-141">Parametro</span><span class="sxs-lookup"><span data-stu-id="23914-141">Parameter</span></span>| <span data-ttu-id="23914-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23914-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="23914-143">Identity</span><span class="sxs-lookup"><span data-stu-id="23914-143">Identity</span></span>  | <span data-ttu-id="23914-144">Il nome di dominio completo della SBA</span><span class="sxs-lookup"><span data-stu-id="23914-144">The FQDN of the SBA</span></span>  |
| <span data-ttu-id="23914-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="23914-145">Fqdn</span></span> | <span data-ttu-id="23914-146">Il nome di dominio completo della SBA</span><span class="sxs-lookup"><span data-stu-id="23914-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="23914-147">Sito</span><span class="sxs-lookup"><span data-stu-id="23914-147">Site</span></span> | <span data-ttu-id="23914-148">TenantNetworkSite in cui si trova l'SBA</span><span class="sxs-lookup"><span data-stu-id="23914-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="23914-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23914-149">Description</span></span> | <span data-ttu-id="23914-150">Testo in formato gratuito</span><span class="sxs-lookup"><span data-stu-id="23914-150">Free format text</span></span> |
|||

<span data-ttu-id="23914-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="23914-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.dk -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="23914-152">Creare i criteri di sopravvivenza della filiale Teams</span><span class="sxs-lookup"><span data-stu-id="23914-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="23914-153">Per creare un criterio, usare il cmdlet New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="23914-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="23914-154">Questo cmdlet contiene i parametri seguenti.</span><span class="sxs-lookup"><span data-stu-id="23914-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="23914-155">Tieni presente che il criterio può contenere uno o più SBAs.</span><span class="sxs-lookup"><span data-stu-id="23914-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="23914-156">Parametro</span><span class="sxs-lookup"><span data-stu-id="23914-156">Parameter</span></span>| <span data-ttu-id="23914-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23914-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="23914-158">Identity</span><span class="sxs-lookup"><span data-stu-id="23914-158">Identity</span></span> | <span data-ttu-id="23914-159">Identità del criterio</span><span class="sxs-lookup"><span data-stu-id="23914-159">The identity of the policy</span></span> |
| <span data-ttu-id="23914-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="23914-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="23914-161">Il nome di dominio completo dello SBA (s) nel sito</span><span class="sxs-lookup"><span data-stu-id="23914-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="23914-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="23914-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.dk, sba2.contoso.com} 
```

<span data-ttu-id="23914-163">Puoi aggiungere o rimuovere SBAs da un criterio usando il cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="23914-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="23914-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="23914-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="23914-165">Assegnare un criterio a un utente</span><span class="sxs-lookup"><span data-stu-id="23914-165">Assign a policy to a user</span></span>

<span data-ttu-id="23914-166">Per assegnare il criterio a singoli utenti, si utilizzerà il cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="23914-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="23914-167">Questo cmdlet contiene i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="23914-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="23914-168">Parametro</span><span class="sxs-lookup"><span data-stu-id="23914-168">Parameter</span></span>| <span data-ttu-id="23914-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23914-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="23914-170">Identity</span><span class="sxs-lookup"><span data-stu-id="23914-170">Identity</span></span> | <span data-ttu-id="23914-171">Identità dell'utente</span><span class="sxs-lookup"><span data-stu-id="23914-171">The identity of the user</span></span> |
| <span data-ttu-id="23914-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="23914-172">PolicyName</span></span> | <span data-ttu-id="23914-173">Identità del criterio</span><span class="sxs-lookup"><span data-stu-id="23914-173">The identity of the policy</span></span> |
||

<span data-ttu-id="23914-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="23914-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="23914-175">È possibile rimuovere un criterio da un utente concedendo il criterio $Null come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="23914-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="23914-176">Registrare un'applicazione per l'SBA con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="23914-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="23914-177">Per consentire diversi SBAs usati all'interno del tenant per leggere i dati richiesti da Microsoft 365, è necessario registrare un'applicazione per l'ASB con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="23914-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="23914-178">Per altre informazioni sulla registrazione delle applicazioni, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="23914-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="23914-179">Sviluppare app line-of-business per Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="23914-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="23914-180">[Registrare un'applicazione con la piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="23914-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="23914-181">Devi solo registrare una sola applicazione per l'uso da parte di tutti i SBAs nel tenant.</span><span class="sxs-lookup"><span data-stu-id="23914-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="23914-182">Per la registrazione SBA sono necessari i valori seguenti creati dalla registrazione:</span><span class="sxs-lookup"><span data-stu-id="23914-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="23914-183">ID applicazione (client)</span><span class="sxs-lookup"><span data-stu-id="23914-183">Application (client) ID</span></span> 
- <span data-ttu-id="23914-184">Segreto client</span><span class="sxs-lookup"><span data-stu-id="23914-184">Client secret</span></span> 

<span data-ttu-id="23914-185">Per l'applicazione SBA, tieni presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="23914-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="23914-186">Il nome può essere quello che si decide.</span><span class="sxs-lookup"><span data-stu-id="23914-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="23914-187">Tipi di account supportati = solo account nella directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23914-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="23914-188">L'URI di reindirizzamento Web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="23914-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="23914-189">Token di concessione impliciti = token di accesso e token di ID.</span><span class="sxs-lookup"><span data-stu-id="23914-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="23914-190">Autorizzazioni API = Skype and Teams tenant Access-> autorizzazioni per le applicazioni-> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="23914-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="23914-191">Segreto client: è possibile usare qualsiasi descrizione e scadenza.</span><span class="sxs-lookup"><span data-stu-id="23914-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="23914-192">Ricordarsi di copiare il segreto client subito dopo averlo creato.</span><span class="sxs-lookup"><span data-stu-id="23914-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="23914-193">L'ID applicazione (client) viene visualizzato nella scheda Panoramica.</span><span class="sxs-lookup"><span data-stu-id="23914-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="23914-194">Seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="23914-194">Then follow these steps:</span></span>

1. <span data-ttu-id="23914-195">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="23914-195">Register the application.</span></span>
2. <span data-ttu-id="23914-196">Impostare i token di concessione impliciti.</span><span class="sxs-lookup"><span data-stu-id="23914-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="23914-197">Impostare le autorizzazioni API.</span><span class="sxs-lookup"><span data-stu-id="23914-197">Set the API permissions.</span></span>
4. <span data-ttu-id="23914-198">Creare il segreto client.</span><span class="sxs-lookup"><span data-stu-id="23914-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="23914-199">Configurazione del controller del bordo della sessione</span><span class="sxs-lookup"><span data-stu-id="23914-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="23914-200">Per informazioni dettagliate su come configurare il controller di bordo della sessione con l'appliance Survivable Branch incorporata, vedere la documentazione fornita dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="23914-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="23914-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="23914-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="23914-202">Ribbon</span><span class="sxs-lookup"><span data-stu-id="23914-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="23914-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="23914-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="23914-204">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="23914-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="23914-205">Segnalazione dei problemi</span><span class="sxs-lookup"><span data-stu-id="23914-205">Reporting issues</span></span>

<span data-ttu-id="23914-206">Segnalare eventuali problemi all'organizzazione di supporto del fornitore SBC.</span><span class="sxs-lookup"><span data-stu-id="23914-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="23914-207">Quando si segnala il problema, indicare di avere un Survivable Branch Appliance configurato.</span><span class="sxs-lookup"><span data-stu-id="23914-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="23914-208">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="23914-208">Known issues</span></span>

- <span data-ttu-id="23914-209">Quando si aggiungono nuovi dispositivi Survivable Branch, potrebbe essere necessario un po' di tempo prima di poterli usare in criteri Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="23914-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="23914-210">Quando si assegna un criterio Survivable Branch Appliance a un utente, potrebbe essere necessario un po' di tempo prima che l'SBA venga visualizzato nell'output di Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="23914-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="23914-211">La ricerca in numero inverso rispetto ai contatti di Azure AD non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="23914-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="23914-212">L'SBA non supporta le impostazioni di inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="23914-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="23914-213">L'esecuzione di una chiamata di emergenza a un numero di emergenza configurato per la chiamata di emergenza dinamica (E911) non è supportata.</span><span class="sxs-lookup"><span data-stu-id="23914-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="23914-214">L'output di Get-CsOnlineUser Mostra TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="23914-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
