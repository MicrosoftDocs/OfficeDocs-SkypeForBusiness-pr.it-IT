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
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993518"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="b13e5-103">Gestire gli account di risorsa in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b13e5-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="b13e5-104">Un account di risorse è un oggetto utente disabilitato in Azure AD e può essere usato per rappresentare le risorse in generale.</span><span class="sxs-lookup"><span data-stu-id="b13e5-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="b13e5-105">Ad esempio, un account di risorse può essere usato in Exchange per rappresentare sale riunioni e consentire loro di avere un numero di telefono e un calendario.</span><span class="sxs-lookup"><span data-stu-id="b13e5-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="b13e5-106">Un account delle risorse può essere ospitato in Microsoft 365 o in locale con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b13e5-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="b13e5-107">In Microsoft teams è necessario un account di risorse per ogni operatore automatico o coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13e5-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="b13e5-108">Gli account delle risorse possono anche essere assegnati numeri di telefono di servizio.</span><span class="sxs-lookup"><span data-stu-id="b13e5-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="b13e5-109">Ecco come assegnare i numeri di telefono agli operatori automatici e alle code di chiamata che consentono ai chiamanti provenienti da team esterni di raggiungere l'operatore automatico o la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13e5-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="b13e5-110">Questo articolo illustra come creare gli account delle risorse e prepararli per l'uso con gli operatori automatici e le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13e5-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="b13e5-111">Prima di iniziare le procedure descritte in questo articolo, verificare di aver eseguito le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b13e5-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="b13e5-112">Ottenere licenze utente virtuali</span><span class="sxs-lookup"><span data-stu-id="b13e5-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="b13e5-113">Ottenere i numeri di servizio</span><span class="sxs-lookup"><span data-stu-id="b13e5-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="b13e5-114">Ottenere licenze utente virtuali</span><span class="sxs-lookup"><span data-stu-id="b13e5-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="b13e5-115">Ogni account delle risorse richiede una licenza per l'utilizzo con gli operatori automatici e le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13e5-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="b13e5-116">È possibile usare un *sistema telefonico gratuito Microsoft 365-* licenza per gli utenti virtuali.</span><span class="sxs-lookup"><span data-stu-id="b13e5-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="b13e5-117">Per ottenere queste licenze, vedere [licenza per gli utenti virtuali](teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="b13e5-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="b13e5-118">Viene illustrato come assegnare la licenza a un account delle risorse più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b13e5-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="b13e5-119">Per ottenere la licenza per gli utenti virtuali, nell'interfaccia di amministrazione di Microsoft 365 **Billing** passare a  >  **Purchase services**  >  **abbonamenti al componente aggiuntivo** fatturazione servizi di acquisto e scorrere fino alla fine: si vedrà il *sistema telefonico-licenza utente virtuale* .</span><span class="sxs-lookup"><span data-stu-id="b13e5-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="b13e5-120">Selezionare **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-120">Select **Buy now**.</span></span> <span data-ttu-id="b13e5-121">È disponibile un costo zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.</span><span class="sxs-lookup"><span data-stu-id="b13e5-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="b13e5-122">Ottenere i numeri di servizio</span><span class="sxs-lookup"><span data-stu-id="b13e5-122">Obtain service numbers</span></span>

<span data-ttu-id="b13e5-123">I numeri di servizio sono facoltativi per gli operatori automatici e le code di chiamata, tuttavia sarà necessario almeno un numero di servizio per consentire ai chiamanti di raggiungere l'operatore automatico e la configurazione delle code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13e5-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="b13e5-124">Per qualsiasi operatore automatico o coda di chiamata che si vuole raggiungere direttamente da un numero di servizio, è necessario disporre di un account delle risorse con un numero di servizio associato.</span><span class="sxs-lookup"><span data-stu-id="b13e5-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="b13e5-125">Gli account delle risorse possono usare numeri di servizio a pagamento o a numero verde.</span><span class="sxs-lookup"><span data-stu-id="b13e5-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="b13e5-126">È possibile richiedere nuovi numeri o trasferire numeri esistenti da un altro vettore.</span><span class="sxs-lookup"><span data-stu-id="b13e5-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="b13e5-127">Per ottenere nuovi numeri di servizio, vedere [recupero di numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="b13e5-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="b13e5-128">Per convertire un numero da un altro vettore, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b13e5-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="b13e5-129">Creare un account di risorse</span><span class="sxs-lookup"><span data-stu-id="b13e5-129">Create a resource account</span></span>

<span data-ttu-id="b13e5-130">È possibile creare un account risorse nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="b13e5-130">You can create a resource account in the Teams admin center.</span></span>

![Screenshot dell'interfaccia utente Aggiungi account risorse](media/resource-account-add.png)

1. <span data-ttu-id="b13e5-132">Nell'interfaccia di amministrazione di teams espandere **impostazioni a livello di organizzazione** e quindi fare clic su **account risorse**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="b13e5-133">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-133">Click **Add**.</span></span>

3. <span data-ttu-id="b13e5-134">Nel riquadro **Aggiungi account risorse** compilare **nome visualizzato** , **nomeutente** e **tipo di account risorse**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="b13e5-135">Il tipo di account delle risorse può essere l' **operatore automatico** o la **coda di chiamata** , a seconda di come si intende usare questo account di risorse.</span><span class="sxs-lookup"><span data-stu-id="b13e5-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="b13e5-136">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-136">Click **Save**.</span></span>

![Screenshot di un elenco di account delle risorse](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="b13e5-138">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="b13e5-138">Assign a license</span></span>

<span data-ttu-id="b13e5-139">Per ogni account delle risorse, è necessario assegnare un *sistema telefonico Microsoft 365-* licenza per l'utente virtuale o per il *sistema telefonico* .</span><span class="sxs-lookup"><span data-stu-id="b13e5-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Screenshot dell'interfaccia utente di assegnazione licenze nell'area di amministrazione di Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="b13e5-141">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account delle risorse a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="b13e5-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="b13e5-142">Nella scheda **licenze e app** , in **licenze** , selezionare **Microsoft 365 Phone System-Virtual User**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="b13e5-143">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="b13e5-144">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="b13e5-144">Assign a service number</span></span>

<span data-ttu-id="b13e5-145">Se si prevede di usare l'account risorse con un operatore automatico o una coda di chiamata che richiede un numero di servizio, assegnare un numero all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="b13e5-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Screenshot dell'interfaccia utente assegna numero di servizio](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="b13e5-147">Nell'interfaccia di amministrazione di teams, nella pagina **account risorse** , selezionare l'account delle risorse a cui si vuole assegnare un numero di servizio e quindi fare clic su **assegna/Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="b13e5-148">Nell'elenco a discesa **tipo di numero di telefono** scegliere il tipo di numero che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="b13e5-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="b13e5-149">Nella casella **numero di telefono assegnato** cercare il numero che si vuole usare e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="b13e5-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b13e5-150">Click **Save**.</span></span>


<span data-ttu-id="b13e5-151">Per assegnare un routing diretto o un numero ibrido a un account di risorse, è necessario usare PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b13e5-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="b13e5-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b13e5-152">Next steps</span></span>

<span data-ttu-id="b13e5-153">Dopo aver completato la configurazione dell'account delle risorse e aver assegnato un numero di servizio, se necessario, è possibile usare l'account delle risorse con un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13e5-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="b13e5-154">Vedere i riferimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b13e5-154">See the following references:</span></span>

 - [<span data-ttu-id="b13e5-155">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="b13e5-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="b13e5-156">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="b13e5-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="b13e5-157">È possibile modificare il **nome visualizzato** dell'account delle risorse e il tipo di **account delle risorse** usando l'opzione **modifica** .</span><span class="sxs-lookup"><span data-stu-id="b13e5-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="b13e5-158">Al termine, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="b13e5-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="b13e5-159">Cambiare un account di risorse esistente per usare una licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="b13e5-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="b13e5-160">Se si decide di cambiare le licenze per l'account delle risorse esistenti da una licenza di **sistema telefonico** a una licenza per gli utenti virtuali, è necessario acquisire la licenza per gli utenti virtuali gratuita e quindi seguire i passaggi dell'interfaccia di amministrazione di Microsoft 365 per [spostare gli utenti in un altro abbonamento](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="b13e5-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="b13e5-161">Rimuovere sempre una licenza per il sistema telefonico completo e assegnare la licenza utente virtuale nella stessa attività di licenza.</span><span class="sxs-lookup"><span data-stu-id="b13e5-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="b13e5-162">Se si rimuove la vecchia licenza, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto.</span><span class="sxs-lookup"><span data-stu-id="b13e5-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="b13e5-163">In questo caso, è consigliabile creare un nuovo account risorse per la licenza per gli utenti virtuali e rimuovere l'account delle risorse interrotte.</span><span class="sxs-lookup"><span data-stu-id="b13e5-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="b13e5-164">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b13e5-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="b13e5-165">Per gli account delle risorse ospitati in Skype for Business Server 2019 che possono essere usati con le code delle chiamate cloud e gli operatori automatici del cloud, vedere [pianificare le code delle chiamate cloud](/SkypeforBusiness/hybrid/plan-call-queue) o gli [operatori automatici di piano cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="b13e5-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="b13e5-166">Le implementazioni ibride (numeri assegnati al routing diretto) vengono configurate usando il cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) in un server di Skype for Business Server 2019 locale.</span><span class="sxs-lookup"><span data-stu-id="b13e5-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="b13e5-167">Gli ID applicazione che è necessario usare durante la creazione delle istanze dell'applicazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="b13e5-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="b13e5-168">**Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="b13e5-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="b13e5-169">**Coda di chiamata:** 11cd3e2e-FCCB-42AD-Ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="b13e5-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="b13e5-170">Se si vuole che la coda di chiamata o l'operatore automatico siano ricercabili dagli utenti di Skype for Business Server 2019, è consigliabile creare gli account delle risorse in Skype for Business Server 2019, poiché gli account delle risorse online non vengono sincronizzati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b13e5-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="b13e5-171">Quando i record SRV DNS per sipfederationtls si risolvono in Skype for Business Server 2019, gli account delle risorse **devono** essere creati in Skype for business server 2019 usando SFB Management Shell e sincronizzati con Azure ad.</span><span class="sxs-lookup"><span data-stu-id="b13e5-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="b13e5-172">Per le implementazioni ibride con Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="b13e5-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="b13e5-173">Pianificare gli operatori automatici cloud</span><span class="sxs-lookup"><span data-stu-id="b13e5-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="b13e5-174">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="b13e5-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="b13e5-175">Configurare gli account delle risorse on-Prem</span><span class="sxs-lookup"><span data-stu-id="b13e5-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="b13e5-176">Eliminare un account delle risorse</span><span class="sxs-lookup"><span data-stu-id="b13e5-176">Delete a resource account</span></span>

<span data-ttu-id="b13e5-177">Assicurarsi di dissociare il numero di telefono dall'account delle risorse prima di eliminarlo, per evitare che il numero di servizio venga bloccato in modalità in sospeso.</span><span class="sxs-lookup"><span data-stu-id="b13e5-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="b13e5-178">Dopo aver eseguito questa operazione, è possibile eliminare l'account delle risorse nell'interfaccia di amministrazione di Microsoft 365, nella scheda utenti.</span><span class="sxs-lookup"><span data-stu-id="b13e5-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="b13e5-179">Per dissociare un numero di telefono di routing diretto dall'account delle risorse, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="b13e5-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
