---
title: Configurare un account Microsoft 365 Business Voice risorsa
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare un account Microsoft 365 Business Voice per l'uso con gli operatori automatici.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130376"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="c1534-103">Passaggio 4: Configurare un account della risorsa Voce aziendale</span><span class="sxs-lookup"><span data-stu-id="c1534-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="c1534-104">In Microsoft Teams è necessario un account della risorsa per ogni operatore automatico o coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c1534-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="c1534-105">Agli account delle risorse possono essere assegnati anche numeri di telefono di servizio.</span><span class="sxs-lookup"><span data-stu-id="c1534-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="c1534-106">In questo modo si assegnano i numeri di telefono agli operatori automatici e alle code di chiamata, consentendo ai chiamanti esterni Teams di raggiungere l'operatore automatico o la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c1534-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="c1534-107">Ottenere licenze utente virtuali</span><span class="sxs-lookup"><span data-stu-id="c1534-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="c1534-108">Gli account delle risorse richiedono una licenza per poter usare operatori automatici e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c1534-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="c1534-109">È possibile usare una licenza *Microsoft 365 Sistema telefonico - Utente* virtuale.</span><span class="sxs-lookup"><span data-stu-id="c1534-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="c1534-110">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1534-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="c1534-111">Passare a **Componenti** aggiuntivi Servizi di  >    >  **acquisto fatturazione**  >  **Vedere tutti i prodotti aggiuntivi**</span><span class="sxs-lookup"><span data-stu-id="c1534-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="c1534-112">Scorrere fino alla fine per trovare la licenza **Microsoft 365 Sistema telefonico - Utente** virtuale.</span><span class="sxs-lookup"><span data-stu-id="c1534-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="c1534-113">Seleziona **Dettagli**, quindi **Acquista**.</span><span class="sxs-lookup"><span data-stu-id="c1534-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="c1534-114">Nella pagina di acquisto della licenza selezionare il numero di licenze utente virtuali desiderate.</span><span class="sxs-lookup"><span data-stu-id="c1534-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="c1534-115">È necessaria una licenza virtuale per ogni operatore automatico e coda di chiamata che si prevede di configurare.</span><span class="sxs-lookup"><span data-stu-id="c1534-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="c1534-116">È consigliabile selezionare almeno cinque licenze per configurare più operatori automatici e code di chiamata in futuro senza dover acquistare subito altre licenze.</span><span class="sxs-lookup"><span data-stu-id="c1534-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="c1534-117">Deselezionare **Assegna automaticamente a tutti gli utenti senza licenze.**</span><span class="sxs-lookup"><span data-stu-id="c1534-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="c1534-118">Selezionare **Estrai adesso.**</span><span class="sxs-lookup"><span data-stu-id="c1534-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="c1534-119">Confermare l'ordine, **selezionare Avanti** e quindi **Eseguire l'ordine.**</span><span class="sxs-lookup"><span data-stu-id="c1534-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="c1534-120">Tenere presente che è comunque necessario  **acquistare** la licenza anche se ha un costo pari a zero.</span><span class="sxs-lookup"><span data-stu-id="c1534-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="c1534-121">Creare un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="c1534-121">Create a resource account</span></span>

<span data-ttu-id="c1534-122">Dopo aver ricevuto la licenza *Microsoft 365 Sistema telefonico - Utente* virtuale, è possibile creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="c1534-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add.png)

1. <span data-ttu-id="c1534-124">Nell'Teams di amministrazione espandere **Impostazioni a** livello di organizzazione e quindi fare clic su **Account risorse.**</span><span class="sxs-lookup"><span data-stu-id="c1534-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="c1534-125">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1534-125">Select **Add**.</span></span>
3. <span data-ttu-id="c1534-126">Nel riquadro **Aggiungi account risorsa** compilare Nome **visualizzato** e quindi **Nome utente.**</span><span class="sxs-lookup"><span data-stu-id="c1534-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="c1534-127">Scegliere un nome visualizzato descrittivo, ad esempio "Operatore automatico linea principale" per descrivere lo scopo dell'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="c1534-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="c1534-128">In **Tipo di account risorsa** selezionare **Operatore automatico.**</span><span class="sxs-lookup"><span data-stu-id="c1534-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="c1534-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c1534-129">Select **Save**.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="c1534-131">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="c1534-131">Assign a license</span></span>

<span data-ttu-id="c1534-132">Dopo aver creato l'account delle risorse, è necessario assegnare una licenza *Microsoft 365 Sistema telefonico -* Utente virtuale o Sistema telefonico *licenza.*</span><span class="sxs-lookup"><span data-stu-id="c1534-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Screenshot dell'interfaccia utente per l'assegnazione di licenze nell'interfaccia Microsoft 365 di amministrazione](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="c1534-134">Nell'Microsoft 365 di amministrazione passare a **Utenti**  >  **attivi**.</span><span class="sxs-lookup"><span data-stu-id="c1534-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="c1534-135">Selezionare l'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="c1534-135">Select your resource account.</span></span>
1. <span data-ttu-id="c1534-136">Nella scheda **Licenze e app,** in **Licenze,** **selezionare Microsoft 365 Sistema telefonico - Utente virtuale**.</span><span class="sxs-lookup"><span data-stu-id="c1534-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="c1534-137">Selezionare **Salva modifiche** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="c1534-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="c1534-138">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="c1534-138">Assign a service number</span></span>

![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="c1534-140">Nell'Teams di amministrazione passare a **Impostazioni a** livello di organizzazione e quindi Account **risorse.**</span><span class="sxs-lookup"><span data-stu-id="c1534-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="c1534-141">Selezionare l'account della risorsa appena creato e quindi fare clic su **Assegna/annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="c1534-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="c1534-142">**Nell'elenco Telefono tipo di** numero scegliere **Online.**</span><span class="sxs-lookup"><span data-stu-id="c1534-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="c1534-143">Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c1534-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="c1534-144">Assicurarsi di includere il codice paese ,ad esempio **+1** 250 555 0012</span><span class="sxs-lookup"><span data-stu-id="c1534-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="c1534-145">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c1534-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="c1534-146">Non è necessario selezionare un operatore automatico **in** Assegna a perché l'operatore automatico a cui si vuole aggiungere il numero è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="c1534-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c1534-147">Passaggio successivo: Assegnare numeri di telefono agli utenti</span><span class="sxs-lookup"><span data-stu-id="c1534-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
