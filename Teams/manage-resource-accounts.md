---
title: Gestire gli account delle risorse in teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In questo articolo verrà illustrato come creare, modificare e gestire gli account delle risorse in Microsoft teams.
ms.openlocfilehash: 90e8ab26782424c6cc341936f185a253c6d1fbe6
ms.sourcegitcommit: eb8b573a426b6a68c763968c4cd2d45bc0d6a4b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46672857"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="2a8c6-103">Gestire gli account di risorsa in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a8c6-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="2a8c6-104">Un account di risorse è noto anche come *oggetto utente disabilitato* in Azure ad e può essere usato per rappresentare le risorse in generale.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="2a8c6-105">In Exchange potrebbe essere usato per rappresentare le sale riunioni, ad esempio, e consentire loro di avere un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="2a8c6-106">Un account delle risorse può essere ospitato in Microsoft 365 o in locale con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="2a8c6-107">In Microsoft teams o Skype for business online ogni coda di chiamata di sistema telefonico o operatore automatico è necessaria per avere almeno un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="2a8c6-108">Se un account di risorse richiede un numero di telefono assegnato dipenderà dall'uso previsto della coda di chiamata associata o dell'operatore automatico, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="2a8c6-109">È anche possibile fare riferimento agli articoli sulle code di chiamata e gli operatori automatici collegati nella parte inferiore di questo articolo prima di assegnare un numero di telefono a un account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![esempio di account di risorse e licenze utente](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="2a8c6-111">Questo articolo si applica sia a Microsoft teams che a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="2a8c6-112">Per gli account delle risorse ospitati in Skype for Business Server 2019, vedere [configurare gli account di risorse](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="2a8c6-113">Assegnare un numero di telefono a una coda di chiamata di sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="2a8c6-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="2a8c6-114">Se l'organizzazione usa già almeno una licenza per il sistema telefonico, per assegnare un numero di telefono a una coda di chiamata di sistema telefonico, il processo è:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="2a8c6-115">Ottenere un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-115">Obtain a service number.</span></span>
2. <span data-ttu-id="2a8c6-116">Ottenere un sistema telefonico gratuito- [licenza per gli utenti virtuali](teams-add-on-licensing/virtual-user.md) o una licenza per il sistema telefonico a pagamento da usare con l'account delle risorse o con una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="2a8c6-117">Creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-117">Create the resource account.</span></span> <span data-ttu-id="2a8c6-118">Per avere un account di risorse associato è necessario un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="2a8c6-119">Assegnare il sistema telefonico o un sistema telefonico-licenza utente virtuale per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="2a8c6-120">Assegnare un numero di telefono del servizio all'account risorse a cui sono state assegnate solo le licenze.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="2a8c6-121">Creare una coda di chiamata di sistema telefonico o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="2a8c6-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="2a8c6-122">Collegare l'account delle risorse con una coda di chiamata o un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="2a8c6-123">Se l'operatore automatico o la coda di chiamata è annidata in un operatore automatico di primo livello, l'account di risorse associato ha bisogno solo di un numero di telefono se si vogliono più punti di entrata nella struttura degli operatori automatici e delle code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-123">If the auto attendant or call queue is nested under a top-level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="2a8c6-124">Per reindirizzare le chiamate alle persone dell'organizzazione ospitate online, devono avere una licenza di **sistema telefonico** ed essere abilitate per Enterprise Voice o avere piani di chiamata Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="2a8c6-125">Vedere [assegnare licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="2a8c6-126">Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="2a8c6-127">Ad esempio, Esegui: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="2a8c6-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="2a8c6-128">Per evitare problemi con l'account delle risorse, seguire questa procedura in questo ordine.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="2a8c6-129">Se la coda di chiamata del sistema telefonico o l'operatore automatico che si sta creando verranno annidati e non sarà necessario un numero di telefono, il processo sarà:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="2a8c6-130">Creare l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="2a8c6-130">Create the resource account</span></span>
2. <span data-ttu-id="2a8c6-131">Creare una coda di chiamata di sistema telefonico o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="2a8c6-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="2a8c6-132">Associare l'account delle risorse a una coda di chiamata o a un operatore automatico del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="2a8c6-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="2a8c6-133">Creare un account delle risorse con un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="2a8c6-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="2a8c6-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="2a8c6-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a8c6-135">Un numero di telefono non viene assegnato direttamente all'operatore automatico o alla coda di chiamata, bensì all'account delle risorse associato all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="2a8c6-136">Un operatore automatico o una coda di chiamata di primo livello richiede un numero di telefono collegato all'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="2a8c6-137">Per creare un account delle risorse che usa un numero di telefono, il processo è:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="2a8c6-138">Porta o ottenere un numero di servizio gratuito o a pagamento.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="2a8c6-139">Il numero non può essere assegnato ad altri account di servizi vocali o risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="2a8c6-140">Prima di assegnare un numero di telefono a un account delle risorse, è necessario ottenere o trasferire i numeri di servizio a pagamento o a numero verde esistenti.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="2a8c6-141">Dopo aver ottenuto i numeri di telefono del servizio a pagamento o a pedaggio, questi vengono visualizzati nei numeri di telefono per l'interfaccia di **amministrazione di Microsoft teams**  >  **Voice**  >  **Phone numbers**e il **tipo di numero** verrà elencato come **servizio gratuito**.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="2a8c6-142">Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="2a8c6-143">Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="2a8c6-144">In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="2a8c6-145">Ottenere una licenza per l'utente virtuale del sistema telefonico o una normale licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="2a8c6-146">Per ottenere la licenza per gli utenti virtuali, nell'interfaccia di amministrazione di Microsoft 365 **Billing**passare a  >  **Purchase services**  >  **abbonamenti al componente aggiuntivo** fatturazione servizi di acquisto e scorrere fino alla fine: verrà visualizzata la licenza "sistema telefonico-utente virtuale".</span><span class="sxs-lookup"><span data-stu-id="2a8c6-146">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="2a8c6-147">Selezionare **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-147">Select **Buy now**.</span></span> <span data-ttu-id="2a8c6-148">È disponibile un costo zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="2a8c6-149">Creare un nuovo account di risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-149">Create a new resource account.</span></span> <span data-ttu-id="2a8c6-150">Vedere [creare un account risorse nell'interfaccia di amministrazione di Microsoft teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) o [creare un account di risorse in PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-150">See [Create a resource account in the Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in PowerShell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="2a8c6-151">Assegnare un sistema telefonico-licenza per l' [utente virtuale](teams-add-on-licensing/virtual-user.md) o un sistema telefonico per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="2a8c6-152">Vedere [assegnare licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) e [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
5. <span data-ttu-id="2a8c6-153">Assegnare il numero di servizio all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="2a8c6-154">Vedere [assegnare/annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="2a8c6-155">Configurare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="2a8c6-156">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="2a8c6-157">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="2a8c6-158">Collegare l'account della risorsa all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="2a8c6-159">Vedere [assegnare o annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="2a8c6-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="2a8c6-160">Quando si crea un account di risorse durante la creazione di un operatore automatico, le licenze vengono applicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="2a8c6-161">Creare un account delle risorse senza un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="2a8c6-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="2a8c6-162">Un operatore automatico o una coda di chiamata annidata richiederà un account delle risorse, ma in molti casi l'account di risorse corrispondente non avrà bisogno di un numero di telefono e delle licenze necessarie per il supporto di un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="2a8c6-163">La creazione di un account delle risorse che non necessita di un numero di telefono richiede l'esecuzione delle attività seguenti nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="2a8c6-164">Creare un nuovo account di risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-164">Create a new resource account.</span></span> <span data-ttu-id="2a8c6-165">Vedere [creare un account risorse nell'interfaccia di amministrazione di Microsoft teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) o [creare un account di risorse in PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in PowerShell](#create-a-resource-account-in-powershell).</span></span>

2. <span data-ttu-id="2a8c6-166">Configurare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="2a8c6-167">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="2a8c6-168">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
   
3. <span data-ttu-id="2a8c6-169">Assegnare l'account della risorsa alla coda di chiamata o all'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="2a8c6-170">Vedere [assegnare/annullare l'assegnazione di numeri di telefono e servizi](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2a8c6-171">Creare un account risorse nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a8c6-171">Create a resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="2a8c6-172">Dopo aver acquistato una licenza di sistema telefonico, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Org-wide settings**, accedere agli  >  **account delle risorse**delle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-172">After you've bought a Phone System license, in the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**.</span></span>

![Screenshot della pagina account risorse](media/r-a-master.png)

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/teamscallout1.png)

<span data-ttu-id="2a8c6-175">Per creare un nuovo account di risorse, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-175">To create a new resource account, click **Add**.</span></span> <span data-ttu-id="2a8c6-176">Nel riquadro **Aggiungi account risorse** compilare il **nome visualizzato**, **nomeutente** (il nome di dominio deve essere popolato automaticamente) e il **tipo di account delle** risorse per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-176">In the **Add resource account** pane, fill out **Display name**, **Username** (the domain name should populate automatically), and **Resource account type** for the resource account.</span></span> <span data-ttu-id="2a8c6-177">Il tipo di account delle risorse può essere l' **operatore automatico** o la **coda di chiamata**, a seconda dell'app che intendi associare all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-177">The resource account type can be either **Auto attendant** or **Call queue**, depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="2a8c6-178">Quando si è pronti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-178">When you're ready, click **Save**.</span></span>

![Screenshot delle nuove opzioni dell'account delle risorse](media/res-acct.png)

<span data-ttu-id="2a8c6-180">Applicare quindi una licenza all'account delle risorse nell'interfaccia di amministrazione di Microsoft 365, come descritto in [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-180">Next, apply a license to the resource account in the Microsoft 365 Admin center, as described in [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="2a8c6-181">Modificare l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="2a8c6-181">Edit resource account</span></span> 

<span data-ttu-id="2a8c6-182">![Icona del numero 2, facendo riferimento a un callout nello screenshot precedente ](media/teamscallout2.png) è possibile modificare il **nome visualizzato** dell'account delle risorse e il tipo di **account delle risorse** usando l'opzione **modifica** .</span><span class="sxs-lookup"><span data-stu-id="2a8c6-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="2a8c6-183">Al termine, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="2a8c6-183">Click **Save** when you are done.</span></span>

![Screenshot dell'opzione modifica account risorse](media/r-a-edit.png)

<span data-ttu-id="2a8c6-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="2a8c6-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="2a8c6-186">Assegnare/annullare l'assegnazione di numeri di telefono e servizi</span><span class="sxs-lookup"><span data-stu-id="2a8c6-186">Assign/unassign phone numbers and services</span></span>

<span data-ttu-id="2a8c6-187">![Icona del numero 3, facendo riferimento a un callout nello screenshot precedente ](media/teamscallout3.png) dopo aver creato l'account delle risorse e assegnato la licenza, è possibile fare clic su **assegna/Annulla assegnazione** per assegnare un numero di servizio all'account della risorsa, impostare il tipo di numero di telefono oppure assegnare l'account di risorse a un operatore automatico o una coda di chiamata già esistente.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) After you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="2a8c6-188">L'assegnazione di un numero di routing diretto può essere eseguita solo tramite cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="2a8c6-189">Se non è ancora stata creata la coda di chiamata o l'operatore automatico che si associa all'account della risorsa, lasciarlo vuoto.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account, leave that field blank.</span></span> <span data-ttu-id="2a8c6-190">Puoi collegare l'account delle risorse mentre lo crei.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="2a8c6-191">Al termine, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="2a8c6-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="2a8c6-192">Le opzioni per il **tipo di numero di telefono** sono:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="2a8c6-193">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2a8c6-193">None</span></span>
- <span data-ttu-id="2a8c6-194">Online</span><span class="sxs-lookup"><span data-stu-id="2a8c6-194">Online</span></span>
- <span data-ttu-id="2a8c6-195">Numeri verdi</span><span class="sxs-lookup"><span data-stu-id="2a8c6-195">Toll-free</span></span>
- <span data-ttu-id="2a8c6-196">Locale</span><span class="sxs-lookup"><span data-stu-id="2a8c6-196">On-premises</span></span>

![Screenshot delle opzioni di assegnazione/disassegnazione](media/r-a-assign.png)

<span data-ttu-id="2a8c6-198">Per assegnare un routing diretto o un numero ibrido a un account di risorse, è necessario usare PowerShell, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a8c6-199">Se l'account delle risorse non ha una licenza valida, un controllo interno causerà un errore quando si tenta di assegnare il numero di telefono all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="2a8c6-200">Non sarà possibile assegnare il numero o associare l'account delle risorse a una coda di chiamata o a un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a8c6-201">Un numero di telefono non viene assegnato direttamente all'operatore automatico o alla coda di chiamata, bensì all'account delle risorse associato all'operatore automatico o alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="2a8c6-202">Cambiare un account di risorse esistente per usare una licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="2a8c6-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="2a8c6-203">Se si decide di cambiare le licenze per l'account delle risorse esistenti da una licenza di sistema telefonico a una licenza per gli utenti virtuali, è necessario acquisire la licenza per gli utenti virtuali gratuita e quindi seguire i passaggi dell'interfaccia di amministrazione di Microsoft 365 per [spostare gli utenti in un altro abbonamento](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-203">If you decide to switch the licenses on your existing resource account from a Phone System license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="2a8c6-204">Rimuovere sempre una licenza per il sistema telefonico completo e assegnare la licenza utente virtuale nella stessa attività di licenza.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="2a8c6-205">Se si rimuove la vecchia licenza, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="2a8c6-206">In questo caso, è consigliabile creare un nuovo account risorse per la licenza per gli utenti virtuali e rimuovere l'account delle risorse interrotte.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="2a8c6-207">Creare un account risorse in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a8c6-207">Create a resource account in PowerShell</span></span>

<span data-ttu-id="2a8c6-208">A seconda che il proprio account di risorse si trovi online o in Skype for Business Server 2019, è necessario connettersi al prompt di PowerShell appropriato con i privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate PowerShell prompt with Admin privileges.</span></span>

- <span data-ttu-id="2a8c6-209">Gli esempi di cmdlet di PowerShell seguenti mostrano la creazione di un account delle risorse ospitato online con [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-209">The following PowerShell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="2a8c6-210">Per gli account delle risorse ospitati in Skype for Business Server 2019 che possono essere usati con le code delle chiamate cloud e gli operatori automatici del cloud, vedere [pianificare le code delle chiamate cloud](/SkypeforBusiness/hybrid/plan-call-queue) o gli [operatori automatici di piano cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="2a8c6-211">Le implementazioni ibride (numeri assegnati al routing diretto) vengono configurate usando il cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) in un server di Skype for Business Server 2019 locale.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="2a8c6-212">L'ID applicazione che devi usare durante la creazione delle istanze dell'applicazione è:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="2a8c6-213">**Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="2a8c6-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="2a8c6-214">**Coda di chiamata:** 11cd3e2e-FCCB-42AD-Ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="2a8c6-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="2a8c6-215">Se si vuole che la coda di chiamata o l'operatore automatico siano ricercabili dagli utenti di Skype for Business Server 2019, è consigliabile creare gli account delle risorse in Skype for Business Server 2019, poiché gli account delle risorse online non vengono sincronizzati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="2a8c6-216">Quando i record SRV DNS per sipfederationtls si risolvono in Skype for Business Server 2019, gli account delle risorse **devono** essere creati in Skype for business server 2019 usando SFB Management Shell e sincronizzati con Azure ad online.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="2a8c6-217">Per creare un account delle risorse online per l'uso con un operatore automatico, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ```powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="2a8c6-218">Non sarà possibile usare l'account delle risorse finché non si applica una licenza.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="2a8c6-219">Per informazioni su come applicare una licenza a un account nell'interfaccia di amministrazione di Microsoft 365, vedere[assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) e [assegnare licenze Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="2a8c6-219">To learn how to apply a license to an account in the Microsoft 365 admin center, see[Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="2a8c6-220">Opzionale Dopo aver applicato la licenza corretta all'account delle risorse, è possibile assegnare un numero di telefono all'account delle risorse, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-220">(Optional) After the correct license is applied to the resource account, you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="2a8c6-221">Non tutti gli account delle risorse richiedono un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="2a8c6-222">Se non è stata applicata una licenza per l'account delle risorse, l'assegnazione del numero di telefono non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-222">If you didn't apply a license to the resource account, the phone number assignment will fail.</span></span>

   ```powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="2a8c6-223">Per altre informazioni su questo comando, vedere [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2a8c6-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2a8c6-224">È più semplice impostare il numero di telefono online usando l'interfaccia di amministrazione di Microsoft teams, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="2a8c6-225">Per assegnare un numero di telefono di routing diretto a un account delle risorse (ospitati in Microsoft teams o Skype for Business Server 2019), usare il cmdlet seguente per PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online PowerShell:</span></span>

   ```powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2a8c6-226">Gestire le impostazioni dell'account delle risorse nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a8c6-226">Manage resource account settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="2a8c6-227">Per gestire le impostazioni dell'account delle risorse nell'interfaccia di amministrazione di Microsoft teams, passare a account risorse per **le impostazioni a livello di organizzazione**  >  **Resource accounts**, selezionare l'account delle risorse per cui modificare le impostazioni e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-227">To manage resource account settings in Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click **Edit**.</span></span> <span data-ttu-id="2a8c6-228">Nel riquadro **modifica account risorse** è possibile modificare queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-228">On the **Edit resource account** pane, you can change these settings:</span></span>

- <span data-ttu-id="2a8c6-229">**Nome visualizzato** per l'account</span><span class="sxs-lookup"><span data-stu-id="2a8c6-229">**Display name** for the account</span></span>
- <span data-ttu-id="2a8c6-230">Coda di chiamata o operatore automatico che usa l'account</span><span class="sxs-lookup"><span data-stu-id="2a8c6-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="2a8c6-231">Numero di telefono assegnato all'account</span><span class="sxs-lookup"><span data-stu-id="2a8c6-231">Phone number assigned to the account</span></span>

<span data-ttu-id="2a8c6-232">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-232">When finished, click **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="2a8c6-233">Eliminare un account delle risorse</span><span class="sxs-lookup"><span data-stu-id="2a8c6-233">Delete a resource account</span></span>

<span data-ttu-id="2a8c6-234">Assicurarsi di dissociare il numero di telefono dall'account delle risorse prima di eliminarlo, per evitare che il numero di servizio venga bloccato in modalità in sospeso.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="2a8c6-235">Puoi eseguire questa operazione usando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-235">You can do that using the following cmdlet:</span></span>

```powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="2a8c6-236">Dopo aver eseguito questa operazione, è possibile eliminare l'account delle risorse nell'interfaccia di amministrazione di Microsoft 365, nella scheda utenti.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-236">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="2a8c6-237">Per dissociare un numero di telefono di routing diretto dall'account delle risorse, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="2a8c6-238">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="2a8c6-238">Troubleshooting</span></span>

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2a8c6-239">Il numero di telefono assegnato all'account delle risorse nell'interfaccia di amministrazione di Microsoft teams non è visualizzato</span><span class="sxs-lookup"><span data-stu-id="2a8c6-239">You don't see the phone number assigned to the resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="2a8c6-240">Se il numero di telefono assegnato all'account delle risorse non è visualizzato nell'interfaccia di amministrazione di Microsoft teams e non è possibile assegnare il numero, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-240">If you don't see the phone number assigned to the resource account in the Microsoft Teams admin center and you are unable to assign the number from there, check the following:</span></span>

```powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="2a8c6-241">Se l'attributo Department Visualizza l'endpoint dell'applicazione Skype for business, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-241">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

```powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="2a8c6-242">Aggiornare la pagina Web dell'interfaccia di amministrazione di teams dopo aver eseguito cmldet e si dovrebbe essere in grado di assegnare il numero correttamente.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-242">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a><span data-ttu-id="2a8c6-243">Viene ricevuto un messaggio di errore "non è possibile usare questo account di risorsa per i servizi".</span><span class="sxs-lookup"><span data-stu-id="2a8c6-243">You get a "We can't use this resource account for services."</span></span> <span data-ttu-id="2a8c6-244">messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="2a8c6-244">error message</span></span>

<span data-ttu-id="2a8c6-245"><a name="blocksignin"> </a></span><span class="sxs-lookup"><span data-stu-id="2a8c6-245"><a name="blocksignin"> </a></span></span>

<span data-ttu-id="2a8c6-246">Quando si prova a usare un account delle risorse, viene visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-246">You get the following error message when you try to use a resource account:</span></span>

<span data-ttu-id="2a8c6-247">"Non è possibile usare questo account delle risorse per i servizi.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-247">"We can't use this resource account for services.</span></span> <span data-ttu-id="2a8c6-248">L'account delle risorse deve essere DISABILITAto e bloccato dall'accesso.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-248">The resource account must be DISABLED and BLOCKED from signing in.</span></span> <span data-ttu-id="2a8c6-249">È necessario bloccare le registrazioni per l'account delle risorse nella pagina utenti nell'interfaccia di amministrazione di Microsoft 365. "</span><span class="sxs-lookup"><span data-stu-id="2a8c6-249">You must BLOCK sign-ins for this resource account on the Users page in the Microsoft 365 admin center."</span></span>

<span data-ttu-id="2a8c6-250">Quando si crea un account di risorsa, per impostazione predefinita è disabilitato e l'accesso è bloccato per l'account.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-250">When you create a resource account, by default, it's disabled and sign in is blocked for the account.</span></span> <span data-ttu-id="2a8c6-251">Queste impostazioni non devono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-251">These settings shouldn't be changed.</span></span> <span data-ttu-id="2a8c6-252">Per risolvere il messaggio di errore, bloccare l'account delle risorse dall'accesso.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-252">To resolve this error message, block the resource account from signing in.</span></span> <span data-ttu-id="2a8c6-253">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-253">To do this:</span></span>

1. <span data-ttu-id="2a8c6-254">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **utenti**, cercare e quindi selezionare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-254">In the Microsoft 365 admin center, go to **Users**, search for, and then select the resource account.</span></span>
2. <span data-ttu-id="2a8c6-255">Nella parte superiore del riquadro sotto il nome visualizzato fare clic su **blocca l'utente**, selezionare la casella di controllo **blocca l'utente dalla firma in** e quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-255">At the top of the pane under the display name, click **Block this user?**, select the **Block this user from signing in** check box, and then select **Save changes**.</span></span>

   ![Screenshot dell'opzione blocca l'utente](media/res-acct-block.png)

    <span data-ttu-id="2a8c6-257">Dopo aver eseguito questa operazione, vedrai "Accedi bloccato" sotto il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2a8c6-257">After you do this, you'll see "Sign in blocked" under the display name.</span></span>

      ![Screenshot del messaggio di accesso bloccato](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a><span data-ttu-id="2a8c6-259">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="2a8c6-259">Related Information</span></span>

<span data-ttu-id="2a8c6-260">Per le implementazioni ibride con Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-260">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="2a8c6-261">Pianificare gli operatori automatici cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-261">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="2a8c6-262">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-262">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="2a8c6-263">Configurare gli account delle risorse on-Prem</span><span class="sxs-lookup"><span data-stu-id="2a8c6-263">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="2a8c6-264">Per le implementazioni in teams o Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="2a8c6-264">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="2a8c6-265">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="2a8c6-265">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="2a8c6-266">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-266">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="2a8c6-267">Esempio per piccole imprese - Impostare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="2a8c6-267">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="2a8c6-268">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="2a8c6-268">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="2a8c6-269">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="2a8c6-269">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="2a8c6-270">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="2a8c6-270">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="2a8c6-271">New-CsOnlineApplicationInstanceAssociation</span><span class="sxs-lookup"><span data-stu-id="2a8c6-271">New-CsOnlineApplicationInstanceAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[<span data-ttu-id="2a8c6-272">Sistema telefonico-licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="2a8c6-272">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
