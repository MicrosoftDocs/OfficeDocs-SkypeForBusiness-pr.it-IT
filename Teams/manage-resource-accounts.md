---
title: Gestire gli account delle risorse in teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Informazioni sulla gestione degli account delle risorse in Microsoft Teams
ms.openlocfilehash: 0508408fbf5bde620cefe9233df4aa62ecf880df
ms.sourcegitcommit: e89c2234fc5aa8f7eeef66ba1ae093a0f7beda85
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "37349264"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="c6edc-103">Gestire gli account delle risorse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6edc-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="c6edc-104"><a name="bk">PhoneNumber</a></span><span class="sxs-lookup"><span data-stu-id="c6edc-104"><a name="bk">phonenumber</a></span></span>

<span data-ttu-id="c6edc-105">Un account di risorse è noto anche come *oggetto utente disabilitato* in Azure ad e può essere usato per rappresentare le risorse in generale.</span><span class="sxs-lookup"><span data-stu-id="c6edc-105">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="c6edc-106">In Exchange potrebbe essere usato per rappresentare le sale riunioni, ad esempio, e consentire loro di avere un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="c6edc-106">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="c6edc-107">Un account delle risorse può essere ospitato in Microsoft 365 o in locale con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6edc-107">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="c6edc-108">In Microsoft teams o Skype for business online ogni coda di chiamata di sistema telefonico o operatore automatico è necessaria per avere un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="c6edc-108">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="c6edc-109">Se un account di risorse richiede un numero di telefono assegnato dipenderà dall'uso previsto della coda di chiamata associata o dell'operatore automatico, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="c6edc-109">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="c6edc-110">È anche possibile fare riferimento agli articoli sulle code di chiamata e gli operatori automatici collegati nella parte inferiore di questo articolo prima di assegnare un numero di telefono a un account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-110">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6edc-111">Un numero di telefono non viene assegnato direttamente all'operatore automatico o alla coda di chiamata, bensì all'account delle risorse associato all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6edc-111">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

![esempio di account di risorse e licenze utente](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="c6edc-113">Questo articolo si applica sia a Microsoft teams che a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="c6edc-113">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="c6edc-114">Per gli account delle risorse ospitati in Skype for Business Server 2019, vedere [configurare gli account di risorse](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="c6edc-114">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>


## <a name="overview"></a><span data-ttu-id="c6edc-115">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c6edc-115">Overview</span></span>

<span data-ttu-id="c6edc-116">Se l'organizzazione usa già almeno una licenza per il sistema telefonico, per assegnare un numero di telefono a una coda di chiamata o a un operatore automatico del sistema telefonico, il processo è:</span><span class="sxs-lookup"><span data-stu-id="c6edc-116">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue or auto attendant the process is:</span></span>

1. <span data-ttu-id="c6edc-117">Ottenere un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="c6edc-117">Obtain a service number.</span></span>
2. <span data-ttu-id="c6edc-118">Ottenere un sistema telefonico gratuito- [licenza per gli utenti virtuali](teams-add-on-licensing/virtual-user.md) o una licenza per il sistema telefonico a pagamento da usare con l'account delle risorse o con una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="c6edc-118">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="c6edc-119">Creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-119">Create the resource account.</span></span> <span data-ttu-id="c6edc-120">Per avere un account di risorse associato è necessario un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6edc-120">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="c6edc-121">Assegnare il sistema telefonico o un sistema telefonico-licenza utente virtuale per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-121">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="c6edc-122">Assegnare un numero di telefono del servizio all'account risorse a cui sono state assegnate solo le licenze.</span><span class="sxs-lookup"><span data-stu-id="c6edc-122">Assign a service phone number to the resource account you just assigned licenses to.</span></span> 
6. <span data-ttu-id="c6edc-123">Creare una coda di chiamata di sistema telefonico o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="c6edc-123">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="c6edc-124">Collegare l'account delle risorse con una coda di chiamata o un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="c6edc-124">Link the resource account with a call queue or auto attendant.</span></span>

<span data-ttu-id="c6edc-125">Se l'operatore automatico o la coda di chiamata è annidata in un operatore automatico di primo livello, l'account di risorse associato deve avere solo un numero di telefono se si vogliono più punti di entrata nella struttura degli operatori automatici e delle code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6edc-125">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="c6edc-126">Per reindirizzare le chiamate alle persone dell'organizzazione ospitate online, devono avere una licenza per il **sistema telefonico** ed essere abilitate per Enterprise Voice o avere piani di chiamata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6edc-126">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c6edc-127">Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c6edc-127">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c6edc-128">Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6edc-128">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c6edc-129">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c6edc-129">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="c6edc-130">Per evitare problemi con l'account delle risorse, seguire questa procedura in questo ordine.</span><span class="sxs-lookup"><span data-stu-id="c6edc-130">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="c6edc-131">Se la coda di chiamata del sistema telefonico o l'operatore automatico che si sta creando verranno annidati e non sarà necessario un numero di telefono, il processo sarà:</span><span class="sxs-lookup"><span data-stu-id="c6edc-131">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="c6edc-132">Creare l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="c6edc-132">Create the resource account</span></span> 
2. <span data-ttu-id="c6edc-133">Creare una coda di chiamata di sistema telefonico o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="c6edc-133">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="c6edc-134">Associare l'account delle risorse a una coda di chiamata o a un operatore automatico del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="c6edc-134">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="c6edc-135">Creare un account delle risorse con un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="c6edc-135">Create a resource account with a phone number</span></span>

<span data-ttu-id="c6edc-136">Un operatore automatico o una coda di chiamata di primo livello richiede un numero di telefono collegato all'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="c6edc-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="c6edc-137">Per creare un account delle risorse che usa un numero di telefono, il processo è:</span><span class="sxs-lookup"><span data-stu-id="c6edc-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="c6edc-138">Porta o ottenere un numero di servizio gratuito o a pagamento.</span><span class="sxs-lookup"><span data-stu-id="c6edc-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="c6edc-139">Il numero non può essere assegnato ad altri account di servizi vocali o risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="c6edc-140">Prima di assegnare un numero di telefono a un account delle risorse, è necessario ottenere o trasferire i numeri di servizio a pagamento o a numero verde esistenti.</span><span class="sxs-lookup"><span data-stu-id="c6edc-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c6edc-141">Dopo aver ottenuto i numeri > **di telefono del** > servizio a pagamento o a pedaggio, questi vengono visualizzati nei numeri di**telefono**per l'interfaccia di **amministrazione di Microsoft teams**e il **tipo di numero** verrà elencato come **servizio gratuito**.</span><span class="sxs-lookup"><span data-stu-id="c6edc-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c6edc-142">Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c6edc-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="c6edc-143">Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="c6edc-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="c6edc-144">In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6edc-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="c6edc-145">Ottenere una licenza per l'utente virtuale del sistema telefonico o una normale licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="c6edc-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span> 

   <span data-ttu-id="c6edc-146">Per ottenere la licenza utente virtuale, a partire dall'interfaccia di amministrazione di Microsoft 365, passare a**abbonamenti al componente aggiuntivo** **fatturazione** > **Servizi** > di acquisto e scorrere fino alla fine: verrà visualizzata la licenza "sistema telefonico-utente virtuale".</span><span class="sxs-lookup"><span data-stu-id="c6edc-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="c6edc-147">Selezionare **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="c6edc-147">Select **Buy now**.</span></span> <span data-ttu-id="c6edc-148">È disponibile un costo zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.</span><span class="sxs-lookup"><span data-stu-id="c6edc-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="c6edc-149">Creare un nuovo account di risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-149">Create a new resource account.</span></span> <span data-ttu-id="c6edc-150">Vedere [creare un account risorse nell'interfaccia di amministrazione di Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [creare un account di risorse in PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="c6edc-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="c6edc-151">Assegnare un sistema telefonico-licenza per l' [utente virtuale](teams-add-on-licensing/virtual-user.md) o un sistema telefonico per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="c6edc-152">Vedere [assegnare licenze di Microsoft teams](assign-teams-licenses.md) e [assegnare licenze a un solo utente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="c6edc-152">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="c6edc-153">Assegnare il numero di servizio all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="c6edc-154">Vedere [assegnare/annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="c6edc-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="c6edc-155">Configurare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6edc-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="c6edc-156">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="c6edc-157">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="c6edc-158">Collegare l'account della risorsa all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6edc-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="c6edc-159">Vedere [assegnare o annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="c6edc-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="c6edc-160">Creare un account delle risorse senza un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="c6edc-160">Create a resource account without a phone number</span></span>

<span data-ttu-id="c6edc-161">Un operatore automatico o una coda di chiamata annidata richiederà un account delle risorse, ma in molti casi l'account di risorse corrispondente non avrà bisogno di un numero di telefono e delle licenze necessarie per il supporto di un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="c6edc-161">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="c6edc-162">La creazione di un account delle risorse che non necessita di un numero di telefono richiede l'esecuzione delle attività seguenti nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="c6edc-162">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="c6edc-163">Creare un nuovo account di risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-163">Create a new resource account.</span></span> <span data-ttu-id="c6edc-164">Vedere [creare un account risorse nell'interfaccia di amministrazione di Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [creare un account di risorse in PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="c6edc-164">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="c6edc-165">Configurare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6edc-165">Set up one of the following:</span></span>
   - [<span data-ttu-id="c6edc-166">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-166">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="c6edc-167">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-167">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="c6edc-168">Assegnare l'account della risorsa alla coda di chiamata o all'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="c6edc-168">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="c6edc-169">Vedere [assegnare o annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="c6edc-169">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="c6edc-170">Creare un account risorse nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6edc-170">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="c6edc-171">Dopo aver acquistato una licenza di sistema telefonico, l'interfaccia di amministrazione di Microsoft teams passa agli**account delle risorse** **delle impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6edc-171">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Screenshot della pagina account risorse](media/r-a-master.png)

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="c6edc-174">Per creare un nuovo account di risorse, fare clic su **+ nuovo account**.</span><span class="sxs-lookup"><span data-stu-id="c6edc-174">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="c6edc-175">Nella finestra popup compilare il nome visualizzato e il nome utente per l'account delle risorse (il nome di dominio deve essere popolato automaticamente), quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c6edc-175">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Screenshot delle nuove opzioni dell'account delle risorse](media/res-acct.png)

<span data-ttu-id="c6edc-177">Applicare quindi una licenza all'account delle risorse nell'interfaccia di amministrazione di Office 365, come descritto in [assegnare licenze agli utenti in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="c6edc-177">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="c6edc-178">Modificare il nome dell'account risorse</span><span class="sxs-lookup"><span data-stu-id="c6edc-178">Edit resource account name</span></span>

<span data-ttu-id="c6edc-179">![Icona del numero 2, facendo riferimento a un callout nello screenshot](media/sfbcallout2.png) precedente è possibile modificare il nome visualizzato dell'account delle risorse usando l'opzione **modifica** .</span><span class="sxs-lookup"><span data-stu-id="c6edc-179">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span> <span data-ttu-id="c6edc-180">Al termine, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="c6edc-180">Click **Save** when you are done.</span></span>
<span data-ttu-id="c6edc-181">![Screenshot dell'opzione modifica account risorse](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="c6edc-181">![Screenshot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="c6edc-182">Assegnare/annullare l'assegnazione di numeri di telefono e servizi</span><span class="sxs-lookup"><span data-stu-id="c6edc-182">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="c6edc-183">![Icona del numero 3, facendo riferimento a un callout nello screenshot](media/sfbcallout3.png) precedente dopo aver creato l'account delle risorse e assegnato la licenza, è possibile fare clic su **assegna/Annulla assegnazione** per assegnare un numero di servizio all'account della risorsa oppure assegnare la risorsa account per un operatore automatico o una coda di chiamata già esistente.</span><span class="sxs-lookup"><span data-stu-id="c6edc-183">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="c6edc-184">L'assegnazione di un numero di routing diretto può essere eseguita solo tramite cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c6edc-184">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="c6edc-185">Se è ancora necessario creare la coda di chiamata o l'operatore automatico, è possibile collegare l'account delle risorse durante la creazione.</span><span class="sxs-lookup"><span data-stu-id="c6edc-185">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="c6edc-186">Al termine, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="c6edc-186">Click **Save** when you are done.</span></span>

<span data-ttu-id="c6edc-187">Per assegnare un routing diretto o un numero ibrido a un account di risorse, è necessario usare PowerShell, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="c6edc-187">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6edc-188">Se l'account delle risorse non ha una licenza valida, un controllo interno causerà un errore quando si tenta di assegnare il numero di telefono all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c6edc-188">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="c6edc-189">Non sarà possibile assegnare il numero o associare l'account delle risorse a una coda di chiamata o a un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="c6edc-189">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

![Screenshot delle opzioni di assegnazione/disassegnazione](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="c6edc-191">Cambiare un account di risorse esistente per usare una licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="c6edc-191">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="c6edc-192">Se si decide di cambiare le licenze per l'account delle risorse esistenti da una licenza di sistema telefonico a una licenza per gli utenti virtuali, è necessario acquisire la licenza per gli utenti virtuali gratuita, quindi seguire i passaggi collegati nell'interfaccia di amministrazione di Microsoft 365 per [spostare gli utenti in un abbonamento diverso](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="c6edc-192">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="c6edc-193">Rimuovere sempre una licenza per il sistema telefonico completo e assegnare la licenza utente virtuale nella stessa attività di licenza.</span><span class="sxs-lookup"><span data-stu-id="c6edc-193">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="c6edc-194">Se si rimuove la vecchia licenza, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto.</span><span class="sxs-lookup"><span data-stu-id="c6edc-194">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="c6edc-195">In questo caso, è consigliabile creare un nuovo account risorse per la licenza per gli utenti virtuali e rimuovere l'account delle risorse interrotte.</span><span class="sxs-lookup"><span data-stu-id="c6edc-195">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="c6edc-196">Creare un account risorse in PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6edc-196">Create a resource account in Powershell</span></span>

<span data-ttu-id="c6edc-197">A seconda che il proprio account di risorse si trovi online o in locale, è necessario connettersi al prompt di PowerShell appropriato con i privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c6edc-197">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="c6edc-198">Gli esempi di cmdlet di PowerShell seguenti mostrano la creazione di un account delle risorse ospitato online con [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c6edc-198">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="c6edc-199">Per gli account delle risorse ospitati in locale in Skype for Business Server 2019 che possono essere usati con le code delle chiamate cloud e gli operatori automatici del cloud, vedere [configurare le code di chiamata cloud](/skypeforbusiness/hybrid/configure-call-queue.md) o [configurare gli operatori automatici del cloud](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="c6edc-199">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="c6edc-200">Le implementazioni ibride (numeri assegnati al routing diretto) useranno [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c6edc-200">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="c6edc-201">L'ID applicazione che devi usare durante la creazione delle istanze dell'applicazione è:</span><span class="sxs-lookup"><span data-stu-id="c6edc-201">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="c6edc-202">**Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="c6edc-202">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="c6edc-203">**Coda di chiamata:** 11cd3e2e-FCCB-42AD-Ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="c6edc-203">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="c6edc-204">Se si vuole che la coda di chiamata o l'operatore automatico vengano ricercati dagli utenti locali, è consigliabile creare gli account delle risorse locale, poiché gli account delle risorse online non vengono sincronizzati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6edc-204">If you want the call queue or auto attendant to be searchable by on-premises users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="c6edc-205">Per creare un account delle risorse online per l'uso con un operatore automatico, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6edc-205">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="c6edc-206">Non sarà possibile usare l'account delle risorse finché non si applica una licenza.</span><span class="sxs-lookup"><span data-stu-id="c6edc-206">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="c6edc-207">Per informazioni su come applicare una licenza a un account nell'interfaccia di amministrazione di Office 365, vedere [assegnare licenze agli utenti in Office 365 per le aziende](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) e [assegnare licenze Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="c6edc-207">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="c6edc-208">Opzionale Dopo aver applicato la licenza corretta all'account delle risorse, è possibile assegnare un numero di telefono all'account delle risorse, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c6edc-208">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="c6edc-209">Non tutti gli account delle risorse richiedono un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="c6edc-209">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="c6edc-210">Se non è stata applicata una licenza per l'account delle risorse, l'assegnazione del numero di telefono non riesce.</span><span class="sxs-lookup"><span data-stu-id="c6edc-210">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="c6edc-211">Per altre informazioni su questo comando, vedere [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c6edc-211">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c6edc-212">È più semplice impostare il numero di telefono online usando l'interfaccia di amministrazione di Microsoft teams, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c6edc-212">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="c6edc-213">Per assegnare un numero di telefono di routing diretto a un account di risorse (ospitati online o in locale), usare il cmdlet seguente per PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="c6edc-213">To assign a direct routing phone number to a resource account (homed either online or on-premises), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="c6edc-214">Gestire le impostazioni dell'account delle risorse nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6edc-214">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="c6edc-215">Per gestire le impostazioni dell'account delle risorse nell'interfaccia di amministrazione di Microsoft teams, passare a**account risorse**per **le impostazioni** > a livello di organizzazione, selezionare l'account delle risorse per cui modificare le impostazioni e quindi fare clic sul pulsante **modifica** .</span><span class="sxs-lookup"><span data-stu-id="c6edc-215">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="c6edc-216">nella schermata **modifica account risorse** sarà possibile modificare queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c6edc-216">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="c6edc-217">**Nome visualizzato** per l'account</span><span class="sxs-lookup"><span data-stu-id="c6edc-217">**Display name** for the account</span></span>
- <span data-ttu-id="c6edc-218">Coda di chiamata o operatore automatico che usa l'account</span><span class="sxs-lookup"><span data-stu-id="c6edc-218">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="c6edc-219">Numero di telefono assegnato all'account</span><span class="sxs-lookup"><span data-stu-id="c6edc-219">Phone number assigned to the account</span></span>

<span data-ttu-id="c6edc-220">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c6edc-220">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="c6edc-221">Eliminare un account delle risorse</span><span class="sxs-lookup"><span data-stu-id="c6edc-221">Delete a resource account</span></span>

<span data-ttu-id="c6edc-222">Assicurarsi di dissociare il numero di telefono dall'account delle risorse prima di eliminarlo, per evitare che il numero di servizio venga bloccato in modalità in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c6edc-222">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="c6edc-223">Puoi eseguire questa operazione usando il seguente unifiedgroup:</span><span class="sxs-lookup"><span data-stu-id="c6edc-223">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="c6edc-224">Dopo aver eseguito questa operazione, è possibile eliminare l'account delle risorse dal portale di amministrazione di Office 365, in scheda utenti.</span><span class="sxs-lookup"><span data-stu-id="c6edc-224">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="c6edc-225">Per dissociare un numero di telefono di routing diretto dall'account delle risorse, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c6edc-225">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="c6edc-226">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c6edc-226">Troubleshooting</span></span>

<span data-ttu-id="c6edc-227">Se non viene visualizzato il numero di telefono assegnato all'account delle risorse nell'interfaccia di amministrazione di teams e non è possibile assegnare il numero da questa posizione, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6edc-227">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="c6edc-228">Se l'attributo Department Visualizza l'endpoint dell'applicazione Skype for business, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c6edc-228">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="c6edc-229">Aggiornare la pagina Web dell'interfaccia di amministrazione di teams dopo aver eseguito cmldet e si dovrebbe essere in grado di assegnare il numero correttamente.</span><span class="sxs-lookup"><span data-stu-id="c6edc-229">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="c6edc-230">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="c6edc-230">Related Information</span></span>

<span data-ttu-id="c6edc-231">Per le implementazioni ibride con Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c6edc-231">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="c6edc-232">Pianificare gli operatori automatici del cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-232">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="c6edc-233">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-233">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="c6edc-234">Configurare gli account delle risorse on-Prem</span><span class="sxs-lookup"><span data-stu-id="c6edc-234">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="c6edc-235">Per le implementazioni in teams o Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="c6edc-235">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="c6edc-236">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="c6edc-236">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="c6edc-237">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-237">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="c6edc-238">Esempio per piccole imprese - Impostare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="c6edc-238">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="c6edc-239">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="c6edc-239">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="c6edc-240">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="c6edc-240">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="c6edc-241">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c6edc-241">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="c6edc-242">Sistema telefonico-licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="c6edc-242">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
