---
title: Configurare un account di risorse in Skype for Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: configurare un account delle risorse per Skype for Business Server 2019.
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185546"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="66e43-103">Configurare gli account delle risorse</span><span class="sxs-lookup"><span data-stu-id="66e43-103">Configure resource accounts</span></span>

<span data-ttu-id="66e43-104">Le implementazioni ibride di Skype for Business Server 2019 usano solo i servizi cloud forniti dal sistema telefonico per la messaggistica unificata e non si integrano con Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="66e43-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="66e43-105">In Skype for Business Server 2019 ora è possibile usare le code di chiamata cloud e gli operatori automatici descritti in [Ecco cosa si ottiene con il sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span><span class="sxs-lookup"><span data-stu-id="66e43-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="66e43-106">Per usare questi servizi di sistema telefonico con Skype for Business Server 2019, è necessario creare account di risorse che fungono da endpoint dell'applicazione e possono essere assegnati numeri di telefono, quindi usare l'interfaccia di amministrazione di Team online per configurare la coda di chiamata o l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66e43-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="66e43-107">Questo account delle risorse può essere ospitato online (vedere [gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts) per creare gli account delle risorse ospitati online) o locali come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="66e43-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="66e43-108">In genere si avranno più nodi del servizio di sistema telefonico, ognuno dei quali è mappato a un account di risorse, che può essere ospitato online o in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66e43-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="66e43-109">Se si ha un operatore automatico di messaggistica unificata di Exchange e un sistema di accodamento delle chiamate, prima di passare a Exchange Server 2019 o Exchange Online è necessario registrare manualmente i dettagli come descritto di seguito e quindi implementare un sistema completamente nuovo con l'interfaccia di amministrazione di Teams .</span><span class="sxs-lookup"><span data-stu-id="66e43-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="66e43-110">Panoramica</span><span class="sxs-lookup"><span data-stu-id="66e43-110">Overview</span></span>

<span data-ttu-id="66e43-111">Se il servizio di sistema telefonico richiede un numero di servizio, le varie dipendenze possono essere soddisfatte nella sequenza seguente:</span><span class="sxs-lookup"><span data-stu-id="66e43-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="66e43-112">Ottenere un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="66e43-112">Obtain a service number</span></span>
2. <span data-ttu-id="66e43-113">Acquistare una licenza per il sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="66e43-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="66e43-114">Creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="66e43-114">Create the resource account.</span></span> <span data-ttu-id="66e43-115">Per avere un account di risorse associato è necessario un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66e43-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="66e43-116">Attendere la sincronizzazione di Active Directory tra online e in locale</span><span class="sxs-lookup"><span data-stu-id="66e43-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="66e43-117">Assegnare la licenza di sistema telefonico all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="66e43-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="66e43-118">Assegnare un numero di servizio all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="66e43-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="66e43-119">Creare un servizio di sistema telefonico (una coda di chiamata o un operatore automatico)</span><span class="sxs-lookup"><span data-stu-id="66e43-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="66e43-120">Associare l'account delle risorse a un servizio: (New-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="66e43-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="66e43-121">Se l'operatore automatico o la coda di chiamata è annidata in un operatore automatico di primo livello, l'account di risorse associato deve avere solo un numero di telefono se si vogliono più punti di entrata nella struttura degli operatori automatici e delle code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66e43-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="66e43-122">Per reindirizzare le chiamate alle persone dell'organizzazione ospitate online, devono avere una licenza per il **sistema telefonico** ed essere abilitate per Enterprise Voice o avere piani di chiamata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="66e43-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="66e43-123">Vedere [assegnare le licenze di Microsoft teams](/MicrosoftTeams/assign-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="66e43-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="66e43-124">Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66e43-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="66e43-125">Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="66e43-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="66e43-126">Se il servizio di sistema telefonico che si sta creando sarà annidato e non sarà necessario un numero di telefono, il processo sarà:</span><span class="sxs-lookup"><span data-stu-id="66e43-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="66e43-127">Creare l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="66e43-127">Create the resource account</span></span>  
2. <span data-ttu-id="66e43-128">Attendere la sincronizzazione di Active Directory tra online e in locale</span><span class="sxs-lookup"><span data-stu-id="66e43-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="66e43-129">Creare un servizio di sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="66e43-129">Create a Phone System service</span></span>
4. <span data-ttu-id="66e43-130">Associare l'account delle risorse a un servizio di sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="66e43-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="66e43-131">Creare un account delle risorse con un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="66e43-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="66e43-132">La creazione di un account delle risorse che usa un numero di telefono richiede l'esecuzione delle attività seguenti nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="66e43-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="66e43-133">Porta o ottenere un numero di servizio gratuito o a pagamento.</span><span class="sxs-lookup"><span data-stu-id="66e43-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="66e43-134">Il numero non può essere assegnato ad altri account di servizi vocali o risorse.</span><span class="sxs-lookup"><span data-stu-id="66e43-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="66e43-135">Prima di assegnare un numero di telefono a un account delle risorse, è necessario ottenere o trasferire i numeri di servizio a pagamento o a numero verde esistenti.</span><span class="sxs-lookup"><span data-stu-id="66e43-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="66e43-136">Dopo aver ottenuto il numero di telefono o i numeri di servizio gratuiti, verranno visualizzati nei numeri di telefono della**segreteria** > **telefonica**di **Microsoft teams** > e il **tipo di numero** elencato verrà elencato come **servizio gratuito**.</span><span class="sxs-lookup"><span data-stu-id="66e43-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="66e43-137">Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](/MicrosoftTeams/getting-service-phone-numbers) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="66e43-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="66e43-138">Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="66e43-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="66e43-139">Vai a [gestire i numeri di telefono per l'organizzazione](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) per vedere come farlo dall'esterno degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="66e43-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="66e43-140">Acquistare una licenza di sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="66e43-140">Buy a Phone System license.</span></span> <span data-ttu-id="66e43-141">Vedere</span><span class="sxs-lookup"><span data-stu-id="66e43-141">See:</span></span>  
   - [<span data-ttu-id="66e43-142">Office 365 Enterprise E1 e E3</span><span class="sxs-lookup"><span data-stu-id="66e43-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="66e43-143">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="66e43-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="66e43-144">Software aziendale di Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="66e43-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="66e43-145">Creare un account di risorse locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni servizio di sistema telefonico e assegnargli un nome, un indirizzo SIP e così via.</span><span class="sxs-lookup"><span data-stu-id="66e43-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="66e43-146">Per altre informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="66e43-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="66e43-147">Opzionale Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di un annuncio tra online e in locale oppure forzare una sincronizzazione e procedere alla configurazione online dei servizi di sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="66e43-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="66e43-148">Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è necessario caricarlo `import-module adsync` per eseguire il comando):</span><span class="sxs-lookup"><span data-stu-id="66e43-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="66e43-149">Per altre informazioni su questo comando, vedere [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .</span><span class="sxs-lookup"><span data-stu-id="66e43-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="66e43-150">Assegnare la licenza di sistema telefonico all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="66e43-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="66e43-151">Vedere [assegnare licenze di Microsoft teams](/MicrosoftTeams/assign-teams-licenses) e [assegnare licenze a un solo utente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="66e43-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="66e43-152">Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="66e43-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="66e43-153">In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66e43-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="66e43-154">Assegnare il numero di servizio all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="66e43-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="66e43-155">Usare il `Set-CsHybridApplicationEndpoint` comando per assegnare un numero di telefono (con l'opzione-LineUri) all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="66e43-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="66e43-156">Per altre informazioni su questo comando, vedere [set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="66e43-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="66e43-157">Per assegnare un routing diretto o un numero ibrido a un account delle risorse, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="66e43-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="66e43-158">L'account delle risorse avrà bisogno di un numero di telefono assegnato se verrà assegnato a un operatore automatico di primo livello o a una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66e43-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="66e43-159">I numeri di telefono degli utenti (abbonati) non possono essere assegnati a un account delle risorse, ma possono essere usati solo numeri di telefono a pagamento o a numero verde.</span><span class="sxs-lookup"><span data-stu-id="66e43-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="66e43-160">Creare il servizio di sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="66e43-160">Create the Phone system service.</span></span> <span data-ttu-id="66e43-161">Vedere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66e43-161">See one of the following:</span></span>

   - [<span data-ttu-id="66e43-162">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="66e43-163">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="66e43-164">Associare l'account delle risorse al servizio di sistema telefonico scelto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="66e43-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="66e43-165">Un esempio di implementazione di piccole imprese è disponibile in [Small Business example-configurare un operatore automatico](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) e un [esempio di piccola impresa-configurare una coda di chiamata](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="66e43-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="66e43-166">Creare un account delle risorse senza un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="66e43-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="66e43-167">Questa sezione illustra la creazione di un account delle risorse ospitato in locale.</span><span class="sxs-lookup"><span data-stu-id="66e43-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="66e43-168">La creazione di un account delle risorse ospitato online viene discussa in [gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts).</span><span class="sxs-lookup"><span data-stu-id="66e43-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="66e43-169">Questi passaggi sono necessari se si sta creando un nuovo sistema di servizio di sistema telefonico o una struttura di ricompilazione creata originariamente nella messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="66e43-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="66e43-170">Accedere al server front-end Skype for business ed eseguire i cmdlet di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="66e43-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="66e43-171">Creare un account di risorse locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni servizio di sistema telefonico e assegnargli un nome, un indirizzo SIP e così via.</span><span class="sxs-lookup"><span data-stu-id="66e43-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="66e43-172">Per altre informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="66e43-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="66e43-173">Opzionale Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di un annuncio tra online e in locale oppure forzare una sincronizzazione e procedere alla configurazione online dei servizi di sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="66e43-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="66e43-174">Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è necessario caricarlo `import-module adsync` per eseguire il comando):</span><span class="sxs-lookup"><span data-stu-id="66e43-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="66e43-175">Per altre informazioni su questo comando, vedere [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .</span><span class="sxs-lookup"><span data-stu-id="66e43-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="66e43-176">Creare il servizio di sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="66e43-176">Create the Phone system service.</span></span> <span data-ttu-id="66e43-177">Vedere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66e43-177">See one of the following:</span></span>
   - [<span data-ttu-id="66e43-178">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="66e43-179">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="66e43-180">Associare l'account delle risorse e il servizio di sistema telefonico scelto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="66e43-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="66e43-181">Un esempio di implementazione di piccole imprese è disponibile in [Small Business example-configurare un operatore automatico](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) e un [esempio di piccola impresa-configurare una coda di chiamata](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="66e43-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="66e43-182">Testare l'implementazione</span><span class="sxs-lookup"><span data-stu-id="66e43-182">Test the implementation</span></span>

<span data-ttu-id="66e43-183">Il modo migliore per testare l'implementazione consiste nel chiamare il numero configurato per un servizio di sistema telefonico e connettersi a uno degli agenti o dei menu.</span><span class="sxs-lookup"><span data-stu-id="66e43-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="66e43-184">È anche possibile inserire rapidamente una chiamata di prova usando il **pulsante test** nel riquadro azioni dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="66e43-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="66e43-185">Se si vogliono apportare modifiche a un servizio di sistema telefonico, selezionarlo e quindi nel riquadro azioni fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="66e43-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="66e43-186">Spostamento di un operatore automatico di Exchange UM o di una coda di chiamata nel sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="66e43-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="66e43-187">La migrazione dalla messaggistica unificata di Exchange al sistema telefonico richiede la ricreazione della struttura della coda di chiamata e dell'operatore automatico, che esegue direttamente la migrazione da una a un'altra non è supportata.</span><span class="sxs-lookup"><span data-stu-id="66e43-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="66e43-188">Per implementare di nuovo un set di code di chiamata e operatori automatici:</span><span class="sxs-lookup"><span data-stu-id="66e43-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="66e43-189">Ottenere un elenco di tutti gli operatori automatici di messaggistica unificata di Exchange e delle code di chiamata eseguendo il comando seguente nel sistema Exchange 2013 o 2016 durante l'accesso come amministratore:</span><span class="sxs-lookup"><span data-stu-id="66e43-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="66e43-190">Per ogni coda di messaggistica unificata di Exchange o l'operatore automatico, annotarne la posizione nella struttura, le impostazioni e ottenere copie di file audio o di sintesi vocale associati (il GUID nell'output sarà il nome di una cartella in cui sono archiviati i file).</span><span class="sxs-lookup"><span data-stu-id="66e43-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="66e43-191">Per ottenere questi dettagli, è possibile eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="66e43-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="66e43-192">Per altre informazioni su questo comando, vedere [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="66e43-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="66e43-193">Un elenco completo delle opzioni che potrebbe essere necessario acquisire è presso [i membri di UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , ma le opzioni più importanti da notare sono:</span><span class="sxs-lookup"><span data-stu-id="66e43-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="66e43-194">Orari di ufficio</span><span class="sxs-lookup"><span data-stu-id="66e43-194">Business hours</span></span>
    - <span data-ttu-id="66e43-195">Orari non lavorativi</span><span class="sxs-lookup"><span data-stu-id="66e43-195">Non-business hours</span></span>
    - <span data-ttu-id="66e43-196">Lingua</span><span class="sxs-lookup"><span data-stu-id="66e43-196">Language</span></span>
    - <span data-ttu-id="66e43-197">Calendario festività</span><span class="sxs-lookup"><span data-stu-id="66e43-197">Holiday schedule</span></span>

3. <span data-ttu-id="66e43-198">Creare nuovi endpoint locali come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="66e43-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="66e43-199">Assegnare all'operatore automatico di primo livello un numero temporaneo per scopi di test.</span><span class="sxs-lookup"><span data-stu-id="66e43-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="66e43-200">Configurare un servizio di sistema telefonico che usa gli endpoint come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="66e43-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="66e43-201">Potrebbe essere utile usare gli esercizi nell'esempio di esercitazione intitolato [Small Business-configurare un operatore automatico](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) per creare una mappa logica delle gerarchie nel vecchio sistema di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="66e43-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="66e43-202">Testare il servizio di sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="66e43-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="66e43-203">Riassegnare il numero di telefono collegato alla coda di chiamata di messaggistica unificata di Exchange o all'operatore automatico al servizio di sistema telefonico corrispondente.</span><span class="sxs-lookup"><span data-stu-id="66e43-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="66e43-204">A questo punto, se è già stata eseguita la migrazione della segreteria telefonica di messaggistica unificata, è necessario essere in grado di eseguire la migrazione a Exchange Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66e43-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="66e43-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e43-205">See Also</span></span>

[<span data-ttu-id="66e43-206">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="66e43-207">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="66e43-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="66e43-208">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="66e43-209">Pianificare gli operatori automatici del cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="66e43-210">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="66e43-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="66e43-211">Pianificare il servizio cloud Voicemail per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="66e43-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="66e43-212">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="66e43-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="66e43-213">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="66e43-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="66e43-214">[Gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts) - \(per creare account risorse ospitati online\)</span><span class="sxs-lookup"><span data-stu-id="66e43-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
