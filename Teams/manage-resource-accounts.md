---
title: Gestire gli account delle risorse in Teams
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In questo articolo imparerai a creare, modificare e gestire gli account delle risorse in Microsoft Teams.
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031022"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="27185-103">Gestire gli account di risorsa in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27185-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="27185-104">Un account delle risorse è un oggetto utente disabilitato in Azure AD e può essere usato per rappresentare le risorse in generale.</span><span class="sxs-lookup"><span data-stu-id="27185-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="27185-105">Ad esempio, un account della risorsa può essere usato in Exchange per rappresentare le sale riunioni e consentire loro di avere un numero di telefono e un calendario.</span><span class="sxs-lookup"><span data-stu-id="27185-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="27185-106">Un account delle risorse può essere installato in Microsoft 365 o in locale utilizzando Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="27185-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="27185-107">In Microsoft Teams è necessario un account della risorsa per ogni operatore automatico o coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="27185-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="27185-108">Agli account delle risorse possono essere assegnati anche numeri di telefono di servizio.</span><span class="sxs-lookup"><span data-stu-id="27185-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="27185-109">In questo modo, è possibile assegnare numeri di telefono agli operatori automatici e alle code di chiamata, consentendo ai chiamanti dall'esterno di Teams di raggiungere l'operatore automatico o la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="27185-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="27185-110">Questo articolo illustra come creare account delle risorse e prepararli per l'uso con operatori automatici e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="27185-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="27185-111">Prima di iniziare le procedure descritte in questo articolo, assicurarsi di aver eseguito le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27185-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="27185-112">Ottenere licenze utente virtuali</span><span class="sxs-lookup"><span data-stu-id="27185-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="27185-113">Ottenere numeri di servizio</span><span class="sxs-lookup"><span data-stu-id="27185-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="27185-114">Ottenere licenze utente virtuali</span><span class="sxs-lookup"><span data-stu-id="27185-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="27185-115">Ogni account delle risorse richiede una licenza per poter lavorare con gli operatori automatici e le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="27185-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="27185-116">È possibile usare una licenza *gratuita Sistema telefonico Microsoft 365 - Utente* virtuale.</span><span class="sxs-lookup"><span data-stu-id="27185-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="27185-117">Per ottenere queste licenze, vedere [Licenza utente virtuale.](teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="27185-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="27185-118">Più avanti in questo articolo viene spiegato come assegnare la licenza a un account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="27185-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="27185-119">Per ottenere la licenza Utente virtuale, nell'interfaccia di amministrazione di Microsoft 365 passare ad Abbonamenti a componenti aggiuntivi di servizi di acquisto di fatturazione e scorrere fino alla fine - verrà visualizzato Sistema telefonico - Licenza Utente  >    >   virtuale. </span><span class="sxs-lookup"><span data-stu-id="27185-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="27185-120">Seleziona **Acquista ora.**</span><span class="sxs-lookup"><span data-stu-id="27185-120">Select **Buy now**.</span></span> <span data-ttu-id="27185-121">Il costo è zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.</span><span class="sxs-lookup"><span data-stu-id="27185-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="27185-122">Ottenere numeri di servizio</span><span class="sxs-lookup"><span data-stu-id="27185-122">Obtain service numbers</span></span>

<span data-ttu-id="27185-123">I numeri di servizio sono facoltativi per gli operatori automatici e le code di chiamata, tuttavia è necessario almeno un numero di servizio per consentire ai chiamanti di raggiungere la configurazione dell'operatore automatico e della coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="27185-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="27185-124">Per qualsiasi operatore automatico o coda di chiamata che desideri essere raggiungibile direttamente da un numero di servizio, devi avere un account delle risorse con un numero di servizio associato.</span><span class="sxs-lookup"><span data-stu-id="27185-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="27185-125">Gli account delle risorse possono usare numeri di servizio a numero verde o a numero verde.</span><span class="sxs-lookup"><span data-stu-id="27185-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="27185-126">Puoi richiedere nuovi numeri o portarne di nuovi da un altro gestore.</span><span class="sxs-lookup"><span data-stu-id="27185-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="27185-127">Per ottenere nuovi numeri di servizio, consulta Recupero [dei numeri di telefono di servizio.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="27185-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="27185-128">Per trasferire un numero da un altro gestore, consulta [Trasferire i numeri di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="27185-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="27185-129">Creare un account delle risorse</span><span class="sxs-lookup"><span data-stu-id="27185-129">Create a resource account</span></span>

<span data-ttu-id="27185-130">È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="27185-130">You can create a resource account in the Teams admin center.</span></span>

![Screenshot dell'interfaccia utente aggiungi account risorsa](media/resource-account-add.png)

1. <span data-ttu-id="27185-132">Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**</span><span class="sxs-lookup"><span data-stu-id="27185-132">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="27185-133">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="27185-133">Click **Add**.</span></span>

3. <span data-ttu-id="27185-134">Nel riquadro **Aggiungi account risorsa** compilare il campo Nome **visualizzato,** Nome **utente** e il tipo di **account risorsa.**</span><span class="sxs-lookup"><span data-stu-id="27185-134">In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**.</span></span> <span data-ttu-id="27185-135">Il tipo di account della risorsa può **essere** operatore automatico o coda **di** chiamata, a seconda di come intendi utilizzare questo account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="27185-135">The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="27185-136">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27185-136">Click **Save**.</span></span>

![Screenshot di un elenco di account delle risorse](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="27185-138">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="27185-138">Assign a license</span></span>

<span data-ttu-id="27185-139">Per ogni account della risorsa è necessario assegnare una licenza Sistema telefonico *Microsoft 365 -* Utente virtuale o *Sistema telefonico.*</span><span class="sxs-lookup"><span data-stu-id="27185-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Screenshot dell'interfaccia utente Assegna licenze nell'interfaccia di amministrazione di Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="27185-141">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="27185-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="27185-142">Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**</span><span class="sxs-lookup"><span data-stu-id="27185-142">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="27185-143">Fare clic **su Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="27185-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="27185-144">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="27185-144">Assign a service number</span></span>

<span data-ttu-id="27185-145">Se si prevede di usare l'account della risorsa con un operatore automatico o una coda di chiamata che richiede un numero di servizio, assegnare un numero all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="27185-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Screenshot dell'interfaccia utente Assegna numero di servizio](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="27185-147">Nell'interfaccia di amministrazione  di Teams, nella pagina Account risorse, selezionare l'account della risorsa a cui assegnare un numero di servizio e quindi fare clic su **Assegna/Annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="27185-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="27185-148">**Nell'elenco a** discesa Tipo di numero di telefono scegliere il tipo di numero da usare.</span><span class="sxs-lookup"><span data-stu-id="27185-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="27185-149">Nella casella **Numero di telefono assegnato,** cerca il numero che desideri utilizzare e fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="27185-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="27185-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27185-150">Click **Save**.</span></span>


<span data-ttu-id="27185-151">Per assegnare un routing diretto o un numero ibrido a un account delle risorse, è necessario usare PowerShell:</span><span class="sxs-lookup"><span data-stu-id="27185-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="27185-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="27185-152">Next steps</span></span>

<span data-ttu-id="27185-153">Una volta completata la configurazione dell'account della risorsa e aver assegnato un numero di servizio, se necessario, sei pronto a usare l'account della risorsa con un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="27185-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="27185-154">Vedere i riferimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27185-154">See the following references:</span></span>

 - [<span data-ttu-id="27185-155">Operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="27185-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="27185-156">Coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="27185-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="27185-157">È possibile modificare il nome visualizzato e **il** tipo di account risorsa **dell'account** della risorsa usando **l'opzione Modifica.**</span><span class="sxs-lookup"><span data-stu-id="27185-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="27185-158">Al **termine,** fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="27185-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="27185-159">Modificare un account delle risorse esistente per usare una licenza utente virtuale</span><span class="sxs-lookup"><span data-stu-id="27185-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="27185-160">Se si decide di cambiare le licenze  dell'account delle risorse esistente da una licenza Sistema telefonico a una licenza Utente virtuale, è necessario acquisire la licenza utente virtuale gratuita e quindi seguire i passaggi dell'interfaccia di amministrazione di Microsoft 365 per spostare gli utenti in un altro [abbonamento.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)</span><span class="sxs-lookup"><span data-stu-id="27185-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="27185-161">Rimuovere sempre una licenza Sistema telefonico completa e assegnare la licenza Utente virtuale nella stessa attività di licenza.</span><span class="sxs-lookup"><span data-stu-id="27185-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="27185-162">Se si rimuove la licenza precedente, salvare le modifiche all'account, aggiungere la nuova licenza e quindi salvare di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto.</span><span class="sxs-lookup"><span data-stu-id="27185-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="27185-163">In questo caso, è consigliabile creare un nuovo account della risorsa per la licenza Utente virtuale e rimuovere l'account di risorsa interrotto.</span><span class="sxs-lookup"><span data-stu-id="27185-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="27185-164">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="27185-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="27185-165">Per gli account delle risorse ospitati su Skype for Business Server 2019, che possono essere utilizzati con code di chiamata cloud e operatori automatici cloud, consulta Pianificare le code di chiamata [cloud](/SkypeforBusiness/hybrid/plan-call-queue) o pianificare gli operatori automatici [cloud.](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)</span><span class="sxs-lookup"><span data-stu-id="27185-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="27185-166">Le implementazioni ibride (numeri ospitati sul routing diretto) vengono configurate usando il cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) in un server locale di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="27185-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="27185-167">Gli ID applicazione da usare durante la creazione delle istanze dell'applicazione sono:</span><span class="sxs-lookup"><span data-stu-id="27185-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="27185-168">**Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="27185-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="27185-169">**Coda di chiamata:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="27185-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="27185-170">Se desideri che la coda di chiamata o l'operatore automatico sia ricercabile dagli utenti di Skype For Business Server 2019, devi creare i tuoi account delle risorse su Skype For Business Server 2019, perché gli account delle risorse online non vengono sincronizzati con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27185-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="27185-171">Quando i record SRV DNS per sipfederationtls risolvono il problema  in Skype for Business Server 2019, è necessario creare account delle risorse in Skype For Business Server 2019 usando SfB Management Shell e sincronizzarli con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="27185-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="27185-172">Per implementazioni ibride con Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="27185-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="27185-173">Pianificare gli operatori automatici cloud</span><span class="sxs-lookup"><span data-stu-id="27185-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="27185-174">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="27185-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="27185-175">Configurare gli account delle risorse locali</span><span class="sxs-lookup"><span data-stu-id="27185-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="27185-176">Eliminare un account di risorsa</span><span class="sxs-lookup"><span data-stu-id="27185-176">Delete a resource account</span></span>

<span data-ttu-id="27185-177">Assicurarsi di dissociare il numero di telefono dall'account delle risorse prima di eliminarlo, per evitare di rimanere bloccati in modalità in sospeso per il numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="27185-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="27185-178">A questo punto, è possibile eliminare l'account delle risorse nell'interfaccia di amministrazione di Microsoft 365, nella scheda Utenti.</span><span class="sxs-lookup"><span data-stu-id="27185-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="27185-179">Per rimuovere l'associazione di un numero di telefono per l'instradamento diretto dall'account delle risorse, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="27185-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
