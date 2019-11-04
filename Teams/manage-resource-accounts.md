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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Informazioni sulla gestione degli account delle risorse in Microsoft Teams
ms.openlocfilehash: a89fe9df7cc878369a06b9c959609dd435bcbd8c
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925467"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="d38ac-103">Gestire gli account di risorsa in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d38ac-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="d38ac-104">Un account di risorse è noto anche come *oggetto utente disabilitato* in Azure ad e può essere usato per rappresentare le risorse in generale.</span><span class="sxs-lookup"><span data-stu-id="d38ac-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="d38ac-105">In Exchange potrebbe essere usato per rappresentare le sale riunioni, ad esempio, e consentire loro di avere un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="d38ac-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="d38ac-106">Un account delle risorse può essere ospitato in Microsoft 365 o in locale con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d38ac-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="d38ac-107">In Microsoft teams o Skype for business online ogni coda di chiamata di sistema telefonico o operatore automatico è necessaria per avere almeno un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="d38ac-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="d38ac-108">Se un account di risorse richiede un numero di telefono assegnato dipenderà dall'uso previsto della coda di chiamata associata o dell'operatore automatico, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="d38ac-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="d38ac-109">È anche possibile fare riferimento agli articoli sulle code di chiamata e gli operatori automatici collegati nella parte inferiore di questo articolo prima di assegnare un numero di telefono a un account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![esempio di account di risorse e licenze utente](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="d38ac-111">Questo articolo si applica sia a Microsoft teams che a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="d38ac-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="d38ac-112">Per gli account delle risorse ospitati in Skype for Business Server 2019, vedere [configurare gli account di risorse](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="d38ac-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="d38ac-113">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d38ac-113">Overview</span></span>

<span data-ttu-id="d38ac-114">Se l'organizzazione usa già almeno una licenza per il sistema telefonico, per assegnare un numero di telefono a una coda di chiamata di sistema telefonico, il processo è:</span><span class="sxs-lookup"><span data-stu-id="d38ac-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="d38ac-115">Ottenere un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="d38ac-115">Obtain a service number.</span></span>
2. <span data-ttu-id="d38ac-116">Ottenere un sistema telefonico gratuito- [licenza per gli utenti virtuali](teams-add-on-licensing/virtual-user.md) o una licenza per il sistema telefonico a pagamento da usare con l'account delle risorse o con una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="d38ac-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="d38ac-117">Creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-117">Create the resource account.</span></span> <span data-ttu-id="d38ac-118">Per avere un account di risorse associato è necessario un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d38ac-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="d38ac-119">Assegnare il sistema telefonico o un sistema telefonico-licenza utente virtuale per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="d38ac-120">Assegnare un numero di telefono del servizio all'account risorse a cui sono state assegnate solo le licenze.</span><span class="sxs-lookup"><span data-stu-id="d38ac-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="d38ac-121">Creare una coda di chiamata di sistema telefonico o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="d38ac-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="d38ac-122">Collegare l'account delle risorse con una coda di chiamata o un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="d38ac-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="d38ac-123">Se l'operatore automatico o la coda di chiamata è annidata in un operatore automatico di primo livello, l'account di risorse associato deve avere solo un numero di telefono se si vogliono più punti di entrata nella struttura degli operatori automatici e delle code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d38ac-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="d38ac-124">Per reindirizzare le chiamate alle persone dell'organizzazione ospitate online, devono avere una licenza per il **sistema telefonico** ed essere abilitate per Enterprise Voice o avere piani di chiamata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d38ac-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="d38ac-125">Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d38ac-125">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="d38ac-126">Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d38ac-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d38ac-127">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d38ac-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="d38ac-128">Per evitare problemi con l'account delle risorse, seguire questa procedura in questo ordine.</span><span class="sxs-lookup"><span data-stu-id="d38ac-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="d38ac-129">Se la coda di chiamata del sistema telefonico o l'operatore automatico che si sta creando verranno annidati e non sarà necessario un numero di telefono, il processo sarà:</span><span class="sxs-lookup"><span data-stu-id="d38ac-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="d38ac-130">Creare l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="d38ac-130">Create the resource account</span></span>
2. <span data-ttu-id="d38ac-131">Creare una coda di chiamata di sistema telefonico o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="d38ac-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="d38ac-132">Associare l'account delle risorse a una coda di chiamata o a un operatore automatico del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="d38ac-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="d38ac-133">Creare un account delle risorse con un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="d38ac-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="d38ac-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="d38ac-134"></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d38ac-135">Un numero di telefono non viene assegnato direttamente all'operatore automatico o alla coda di chiamata, bensì all'account delle risorse associato all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d38ac-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="d38ac-136">Un operatore automatico o una coda di chiamata di primo livello richiede un numero di telefono collegato all'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="d38ac-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="d38ac-137">Per creare un account delle risorse che usa un numero di telefono, il processo è:</span><span class="sxs-lookup"><span data-stu-id="d38ac-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="d38ac-138">Porta o ottenere un numero di servizio gratuito o a pagamento.</span><span class="sxs-lookup"><span data-stu-id="d38ac-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="d38ac-139">Il numero non può essere assegnato ad altri account di servizi vocali o risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="d38ac-140">Prima di assegnare un numero di telefono a un account delle risorse, è necessario ottenere o trasferire i numeri di servizio a pagamento o a numero verde esistenti.</span><span class="sxs-lookup"><span data-stu-id="d38ac-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="d38ac-141">Dopo aver ottenuto i numeri > **di telefono del** > servizio a pagamento o a pedaggio, questi vengono visualizzati nei numeri di**telefono**per l'interfaccia di **amministrazione di Microsoft teams**e il **tipo di numero** verrà elencato come **servizio gratuito**.</span><span class="sxs-lookup"><span data-stu-id="d38ac-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="d38ac-142">Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d38ac-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="d38ac-143">Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="d38ac-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="d38ac-144">In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d38ac-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="d38ac-145">Ottenere una licenza per l'utente virtuale del sistema telefonico o una normale licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="d38ac-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="d38ac-146">Per ottenere la licenza utente virtuale, a partire dall'interfaccia di amministrazione di Microsoft 365, passare a**abbonamenti al componente aggiuntivo** **fatturazione** > **Servizi** > di acquisto e scorrere fino alla fine: verrà visualizzata la licenza "sistema telefonico-utente virtuale".</span><span class="sxs-lookup"><span data-stu-id="d38ac-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="d38ac-147">Selezionare **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="d38ac-147">Select **Buy now**.</span></span> <span data-ttu-id="d38ac-148">È disponibile un costo zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.</span><span class="sxs-lookup"><span data-stu-id="d38ac-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="d38ac-149">Creare un nuovo account di risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-149">Create a new resource account.</span></span> <span data-ttu-id="d38ac-150">Vedere [creare un account risorse nell'interfaccia di amministrazione di Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [creare un account di risorse in PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="d38ac-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="d38ac-151">Assegnare un sistema telefonico-licenza per l' [utente virtuale](teams-add-on-licensing/virtual-user.md) o un sistema telefonico per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="d38ac-152">Vedere [assegnare licenze di Microsoft teams](assign-teams-licenses.md) e [assegnare licenze a un solo utente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="d38ac-152">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="d38ac-153">Assegnare il numero di servizio all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="d38ac-154">Vedere [assegnare/annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="d38ac-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="d38ac-155">Configurare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d38ac-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="d38ac-156">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="d38ac-157">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="d38ac-158">Collegare l'account della risorsa all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d38ac-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="d38ac-159">Vedere [assegnare o annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="d38ac-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="d38ac-160">Quando si crea un account di risorse durante la creazione di un operatore automatico, le licenze vengono applicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d38ac-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="d38ac-161">Creare un account delle risorse senza un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="d38ac-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="d38ac-162">Un operatore automatico o una coda di chiamata annidata richiederà un account delle risorse, ma in molti casi l'account di risorse corrispondente non avrà bisogno di un numero di telefono e delle licenze necessarie per il supporto di un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="d38ac-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="d38ac-163">La creazione di un account delle risorse che non necessita di un numero di telefono richiede l'esecuzione delle attività seguenti nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="d38ac-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="d38ac-164">Creare un nuovo account di risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-164">Create a new resource account.</span></span> <span data-ttu-id="d38ac-165">Vedere [creare un account risorse nell'interfaccia di amministrazione di Microsoft teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [creare un account di risorse in PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="d38ac-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="d38ac-166">Configurare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d38ac-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="d38ac-167">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="d38ac-168">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="d38ac-169">Assegnare l'account della risorsa alla coda di chiamata o all'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="d38ac-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="d38ac-170">Vedere [assegnare o annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="d38ac-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="d38ac-171">Creare un account risorse nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d38ac-171">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="d38ac-172">Dopo aver acquistato una licenza di sistema telefonico, l'interfaccia di amministrazione di Microsoft teams passa agli**account delle risorse** **delle impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d38ac-172">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Screenshot della pagina account risorse](media/r-a-master.png)

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="d38ac-175">Per creare un nuovo account di risorse, fare clic su **+ nuovo account**.</span><span class="sxs-lookup"><span data-stu-id="d38ac-175">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="d38ac-176">Nella finestra popup compilare il nome visualizzato e il nome utente per l'account delle risorse (il nome di dominio deve essere popolato automaticamente), quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d38ac-176">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Screenshot delle nuove opzioni dell'account delle risorse](media/res-acct.png)

<span data-ttu-id="d38ac-178">Applicare quindi una licenza all'account delle risorse nell'interfaccia di amministrazione di Office 365, come descritto in [assegnare licenze agli utenti in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="d38ac-178">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="d38ac-179">Modificare il nome dell'account risorse</span><span class="sxs-lookup"><span data-stu-id="d38ac-179">Edit resource account name</span></span>

<span data-ttu-id="d38ac-180">![Icona del numero 2, facendo riferimento a un callout nello screenshot](media/sfbcallout2.png) precedente è possibile modificare il nome visualizzato dell'account delle risorse usando l'opzione **modifica** .</span><span class="sxs-lookup"><span data-stu-id="d38ac-180">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span> <span data-ttu-id="d38ac-181">Al termine, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="d38ac-181">Click **Save** when you are done.</span></span>
<span data-ttu-id="d38ac-182">![Screenshot dell'opzione modifica account risorse](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="d38ac-182">![Screenshot of the Edit resource account option](media/r-a-edit.png)</span></span>

<span data-ttu-id="d38ac-183"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="d38ac-183"></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="d38ac-184">Assegnare/annullare l'assegnazione di numeri di telefono e servizi</span><span class="sxs-lookup"><span data-stu-id="d38ac-184">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="d38ac-185">![Icona del numero 3, facendo riferimento a un callout nello screenshot](media/sfbcallout3.png) precedente dopo aver creato l'account delle risorse e assegnato la licenza, è possibile fare clic su **assegna/Annulla assegnazione** per assegnare un numero di servizio all'account della risorsa oppure assegnare la risorsa account per un operatore automatico o una coda di chiamata già esistente.</span><span class="sxs-lookup"><span data-stu-id="d38ac-185">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="d38ac-186">L'assegnazione di un numero di routing diretto può essere eseguita solo tramite cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d38ac-186">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="d38ac-187">Se è ancora necessario creare la coda di chiamata o l'operatore automatico, è possibile collegare l'account delle risorse durante la creazione.</span><span class="sxs-lookup"><span data-stu-id="d38ac-187">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="d38ac-188">Al termine, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="d38ac-188">Click **Save** when you are done.</span></span>

<span data-ttu-id="d38ac-189">Per assegnare un routing diretto o un numero ibrido a un account di risorse, è necessario usare PowerShell, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="d38ac-189">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d38ac-190">Se l'account delle risorse non ha una licenza valida, un controllo interno causerà un errore quando si tenta di assegnare il numero di telefono all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d38ac-190">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="d38ac-191">Non sarà possibile assegnare il numero o associare l'account delle risorse a una coda di chiamata o a un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="d38ac-191">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d38ac-192">Un numero di telefono non viene assegnato direttamente all'operatore automatico o alla coda di chiamata, bensì all'account delle risorse associato all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d38ac-192">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

![Screenshot delle opzioni di assegnazione/disassegnazione](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="d38ac-194">Cambiare un account di risorse esistente per usare una licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="d38ac-194">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="d38ac-195">Se si decide di cambiare le licenze per l'account delle risorse esistenti da una licenza di sistema telefonico a una licenza per gli utenti virtuali, è necessario acquisire la licenza per gli utenti virtuali gratuita, quindi seguire i passaggi collegati nell'interfaccia di amministrazione di Microsoft 365 per [spostare gli utenti in un abbonamento diverso](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="d38ac-195">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="d38ac-196">Rimuovere sempre una licenza per il sistema telefonico completo e assegnare la licenza utente virtuale nella stessa attività di licenza.</span><span class="sxs-lookup"><span data-stu-id="d38ac-196">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="d38ac-197">Se si rimuove la vecchia licenza, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto.</span><span class="sxs-lookup"><span data-stu-id="d38ac-197">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="d38ac-198">In questo caso, è consigliabile creare un nuovo account risorse per la licenza per gli utenti virtuali e rimuovere l'account delle risorse interrotte.</span><span class="sxs-lookup"><span data-stu-id="d38ac-198">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="d38ac-199">Creare un account risorse in PowerShell</span><span class="sxs-lookup"><span data-stu-id="d38ac-199">Create a resource account in Powershell</span></span>

<span data-ttu-id="d38ac-200">A seconda che il proprio account di risorse si trovi online o in Skype for Business Server 2019, è necessario connettersi al prompt di PowerShell appropriato con i privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d38ac-200">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="d38ac-201">Gli esempi di cmdlet di PowerShell seguenti mostrano la creazione di un account delle risorse ospitato online con [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d38ac-201">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="d38ac-202">Per gli account delle risorse ospitati in Skype for Business Server 2019 che possono essere usati con le code delle chiamate cloud e gli operatori automatici del cloud, vedere [configurare le code di chiamata cloud](/skypeforbusiness/hybrid/configure-call-queue.md) o [configurare gli operatori automatici del cloud](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="d38ac-202">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="d38ac-203">Le implementazioni ibride (numeri assegnati al routing diretto) useranno [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d38ac-203">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="d38ac-204">L'ID applicazione che devi usare durante la creazione delle istanze dell'applicazione è:</span><span class="sxs-lookup"><span data-stu-id="d38ac-204">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="d38ac-205">**Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="d38ac-205">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="d38ac-206">**Coda di chiamata:** 11cd3e2e-FCCB-42AD-Ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="d38ac-206">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="d38ac-207">Se si vuole che la coda di chiamata o l'operatore automatico siano ricercabili dagli utenti di Skype for Business Server 2019, è consigliabile creare gli account delle risorse in Skype for Business Server 2019, poiché gli account delle risorse online non vengono sincronizzati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d38ac-207">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="d38ac-208">Quando i record SRV DNS per sipfederationtls si risolvono in Skype for Business Server 2019, gli account delle risorse **devono** essere creati in Skype for business server 2019 usando SFB Management Shell e sincronizzati con Azure ad online.</span><span class="sxs-lookup"><span data-stu-id="d38ac-208">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="d38ac-209">Per creare un account delle risorse online per l'uso con un operatore automatico, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d38ac-209">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="d38ac-210">Non sarà possibile usare l'account delle risorse finché non si applica una licenza.</span><span class="sxs-lookup"><span data-stu-id="d38ac-210">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="d38ac-211">Per informazioni su come applicare una licenza a un account nell'interfaccia di amministrazione di Office 365, vedere [assegnare licenze agli utenti in Office 365 per le aziende](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) e [assegnare licenze Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="d38ac-211">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="d38ac-212">Opzionale Dopo aver applicato la licenza corretta all'account delle risorse, è possibile assegnare un numero di telefono all'account delle risorse, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d38ac-212">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="d38ac-213">Non tutti gli account delle risorse richiedono un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="d38ac-213">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="d38ac-214">Se non è stata applicata una licenza per l'account delle risorse, l'assegnazione del numero di telefono non riesce.</span><span class="sxs-lookup"><span data-stu-id="d38ac-214">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="d38ac-215">Per altre informazioni su questo comando, vedere [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d38ac-215">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d38ac-216">È più semplice impostare il numero di telefono online usando l'interfaccia di amministrazione di Microsoft teams, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d38ac-216">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="d38ac-217">Per assegnare un numero di telefono di routing diretto a un account delle risorse (ospitati in Microsoft teams o Skype for Business Server 2019), usare il cmdlet seguente per PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="d38ac-217">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="d38ac-218">Gestire le impostazioni dell'account delle risorse nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d38ac-218">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="d38ac-219">Per gestire le impostazioni dell'account delle risorse nell'interfaccia di amministrazione di Microsoft teams, passare a**account risorse**per **le impostazioni** > a livello di organizzazione, selezionare l'account delle risorse per cui modificare le impostazioni e quindi fare clic sul pulsante **modifica** .</span><span class="sxs-lookup"><span data-stu-id="d38ac-219">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="d38ac-220">nella schermata **modifica account risorse** sarà possibile modificare queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d38ac-220">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="d38ac-221">**Nome visualizzato** per l'account</span><span class="sxs-lookup"><span data-stu-id="d38ac-221">**Display name** for the account</span></span>
- <span data-ttu-id="d38ac-222">Coda di chiamata o operatore automatico che usa l'account</span><span class="sxs-lookup"><span data-stu-id="d38ac-222">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="d38ac-223">Numero di telefono assegnato all'account</span><span class="sxs-lookup"><span data-stu-id="d38ac-223">Phone number assigned to the account</span></span>

<span data-ttu-id="d38ac-224">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d38ac-224">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="d38ac-225">Eliminare un account delle risorse</span><span class="sxs-lookup"><span data-stu-id="d38ac-225">Delete a resource account</span></span>

<span data-ttu-id="d38ac-226">Assicurarsi di dissociare il numero di telefono dall'account delle risorse prima di eliminarlo, per evitare che il numero di servizio venga bloccato in modalità in sospeso.</span><span class="sxs-lookup"><span data-stu-id="d38ac-226">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="d38ac-227">Puoi eseguire questa operazione usando il seguente unifiedgroup:</span><span class="sxs-lookup"><span data-stu-id="d38ac-227">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="d38ac-228">Dopo aver eseguito questa operazione, è possibile eliminare l'account delle risorse dal portale di amministrazione di Office 365, in scheda utenti.</span><span class="sxs-lookup"><span data-stu-id="d38ac-228">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="d38ac-229">Per dissociare un numero di telefono di routing diretto dall'account delle risorse, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="d38ac-229">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="d38ac-230">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d38ac-230">Troubleshooting</span></span>

<span data-ttu-id="d38ac-231">Se non viene visualizzato il numero di telefono assegnato all'account delle risorse nell'interfaccia di amministrazione di teams e non è possibile assegnare il numero da questa posizione, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d38ac-231">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="d38ac-232">Se l'attributo Department Visualizza l'endpoint dell'applicazione Skype for business, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="d38ac-232">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="d38ac-233">Aggiornare la pagina Web dell'interfaccia di amministrazione di teams dopo aver eseguito cmldet e si dovrebbe essere in grado di assegnare il numero correttamente.</span><span class="sxs-lookup"><span data-stu-id="d38ac-233">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="d38ac-234">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="d38ac-234">Related Information</span></span>

<span data-ttu-id="d38ac-235">Per le implementazioni ibride con Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="d38ac-235">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="d38ac-236">Pianificare gli operatori automatici del cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-236">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="d38ac-237">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-237">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="d38ac-238">Configurare gli account delle risorse on-Prem</span><span class="sxs-lookup"><span data-stu-id="d38ac-238">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="d38ac-239">Per le implementazioni in teams o Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="d38ac-239">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="d38ac-240">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="d38ac-240">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="d38ac-241">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-241">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="d38ac-242">Esempio per piccole imprese - Impostare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="d38ac-242">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="d38ac-243">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="d38ac-243">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="d38ac-244">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="d38ac-244">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="d38ac-245">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d38ac-245">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="d38ac-246">Sistema telefonico-licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="d38ac-246">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
