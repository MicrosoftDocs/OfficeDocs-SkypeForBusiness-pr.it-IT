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
ms.openlocfilehash: 618f26394f2b4acc44d56b814bd31c20ffe1a370
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282778"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="5b928-103">Passaggio 4: Configurare un account della risorsa Voce aziendale</span><span class="sxs-lookup"><span data-stu-id="5b928-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="5b928-104">Gli account delle risorse non sono assegnati a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="5b928-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="5b928-105">Gli account delle risorse, che usano una licenza utente virtuale gratuita, vengono invece usati dai dispositivi e dai servizi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5b928-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="5b928-106">In Microsoft Teams, agli account delle risorse vengono assegnati numeri di telefono e quindi associati agli operatori automatici e alle code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5b928-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="5b928-107">Associando gli account delle risorse agli operatori automatici e alle code di chiamata, è possibile aggiungere uno o più numeri a numero verde o a pedaggio.</span><span class="sxs-lookup"><span data-stu-id="5b928-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="5b928-108">Ad esempio, è possibile associare un account della risorsa a un numero a pedaggio a un operatore automatico per i chiamanti locali.</span><span class="sxs-lookup"><span data-stu-id="5b928-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="5b928-109">Per le chiamate interurbane, è possibile associare un altro account della risorsa a un numero verde allo stesso operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="5b928-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="5b928-110">Le sezioni di questo articolo illustrano come configurare un account della risorsa e quindi assegnare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5b928-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="5b928-111">In seguito, l'account della risorsa verrà associato a un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="5b928-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="5b928-112">Ottenere licenze utente virtuali</span><span class="sxs-lookup"><span data-stu-id="5b928-112">Obtain virtual user licenses</span></span>

<span data-ttu-id="5b928-113">Gli account delle risorse richiedono una licenza per poter usare operatori automatici e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5b928-113">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="5b928-114">È possibile usare una licenza *Microsoft 365 Sistema telefonico - Utente* virtuale.</span><span class="sxs-lookup"><span data-stu-id="5b928-114">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="5b928-115">È necessario eseguire la procedura seguente solo se si è effettuato l'accesso a un periodo di valutazione di Business Voice.</span><span class="sxs-lookup"><span data-stu-id="5b928-115">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="5b928-116">Se sono state acquistate licenze Business Voice, le licenze virtuali dovrebbero già essere applicate al proprio account.</span><span class="sxs-lookup"><span data-stu-id="5b928-116">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="5b928-117">Per verificare se si hanno già licenze virtuali, accedere Microsoft 365 un account con autorizzazioni di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="5b928-117">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="5b928-118">Quindi vai a Fatturazione > [Tuoi prodotti](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span><span class="sxs-lookup"><span data-stu-id="5b928-118">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="5b928-119">Se si hanno licenze virtuali, verranno visualizzate **come Microsoft 365 Sistema telefonico - Utente virtuale.**</span><span class="sxs-lookup"><span data-stu-id="5b928-119">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="5b928-120">Aprire l'Microsoft 365 di amministrazione e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="5b928-120">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="5b928-121">Nel riquadro di spostamento sinistro passare a <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank"> **Componenti**  > </a>aggiuntivi Servizi di acquisto  >  **fatturazione**  >  **Vedere tutti i prodotti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="5b928-121">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="5b928-122">Scorrere fino alla fine per trovare la licenza **Microsoft 365 Sistema telefonico - Utente** virtuale.</span><span class="sxs-lookup"><span data-stu-id="5b928-122">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="5b928-123">Seleziona **Dettagli**, quindi **Acquista**.</span><span class="sxs-lookup"><span data-stu-id="5b928-123">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="5b928-124">Nella pagina di acquisto della licenza selezionare il numero di licenze utente virtuali desiderate.</span><span class="sxs-lookup"><span data-stu-id="5b928-124">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="5b928-125">È necessaria una licenza virtuale per ogni operatore automatico e coda di chiamata che si prevede di configurare.</span><span class="sxs-lookup"><span data-stu-id="5b928-125">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="5b928-126">È consigliabile selezionare almeno cinque licenze per configurare più operatori automatici e code di chiamata in futuro senza dover acquistare subito altre licenze.</span><span class="sxs-lookup"><span data-stu-id="5b928-126">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="5b928-127">Deselezionare **Assegna automaticamente a tutti gli utenti senza licenze.**</span><span class="sxs-lookup"><span data-stu-id="5b928-127">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="5b928-128">Selezionare **Estrai adesso.**</span><span class="sxs-lookup"><span data-stu-id="5b928-128">Select **Check out now**.</span></span>
7. <span data-ttu-id="5b928-129">Confermare l'ordine, **selezionare Avanti** e quindi **Eseguire l'ordine.**</span><span class="sxs-lookup"><span data-stu-id="5b928-129">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="5b928-130">Tenere presente che è comunque necessario  **acquistare** la licenza anche se ha un costo pari a zero.</span><span class="sxs-lookup"><span data-stu-id="5b928-130">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="5b928-131">Creare un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="5b928-131">Create a resource account</span></span>

<span data-ttu-id="5b928-132">Dopo aver ricevuto la licenza *Microsoft 365 Sistema telefonico - Utente* virtuale, è possibile creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5b928-132">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add.png)

1. <span data-ttu-id="5b928-134">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="5b928-134">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="5b928-135">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **Impostazioni a livello di** organizzazione Account delle  >  **risorse.**</a></span><span class="sxs-lookup"><span data-stu-id="5b928-135">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="5b928-136">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5b928-136">Select **Add**.</span></span>
4. <span data-ttu-id="5b928-137">Nel riquadro **Aggiungi account risorsa** compilare Nome **visualizzato** e quindi **Nome utente.**</span><span class="sxs-lookup"><span data-stu-id="5b928-137">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="5b928-138">Scegliere un nome visualizzato descrittivo, ad esempio "Operatore automatico linea principale" per descrivere lo scopo dell'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="5b928-138">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="5b928-139">In **Tipo di account risorsa** selezionare **Operatore automatico.**</span><span class="sxs-lookup"><span data-stu-id="5b928-139">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="5b928-140">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b928-140">Select **Save**.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="5b928-142">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="5b928-142">Assign a license</span></span>

<span data-ttu-id="5b928-143">Dopo aver creato l'account delle risorse, è necessario assegnare una licenza *Microsoft 365 Sistema telefonico -* Utente virtuale o Sistema telefonico *licenza.*</span><span class="sxs-lookup"><span data-stu-id="5b928-143">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Screenshot dell'interfaccia utente per l'assegnazione di licenze nell'interfaccia Microsoft 365 di amministrazione](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="5b928-145">Aprire l'Microsoft 365 di amministrazione e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="5b928-145">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="5b928-146">Nel riquadro di spostamento sinistro passare a <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Utenti**  >  **utenti attivi**</a>.</span><span class="sxs-lookup"><span data-stu-id="5b928-146">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="5b928-147">Selezionare l'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="5b928-147">Select your resource account.</span></span>
1. <span data-ttu-id="5b928-148">Nella scheda **Licenze e app,** in **Licenze,** **selezionare Microsoft 365 Sistema telefonico - Utente virtuale**.</span><span class="sxs-lookup"><span data-stu-id="5b928-148">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="5b928-149">Selezionare **Salva modifiche** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="5b928-149">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="5b928-150">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="5b928-150">Assign a service number</span></span>

![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="5b928-152">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="5b928-152">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="5b928-153">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **Impostazioni a livello di** organizzazione Account delle  >  **risorse.**</a></span><span class="sxs-lookup"><span data-stu-id="5b928-153">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="5b928-154">Selezionare l'account della risorsa appena creato e quindi fare clic su **Assegna/annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="5b928-154">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="5b928-155">**Nell'elenco Telefono tipo di** numero scegliere **Online.**</span><span class="sxs-lookup"><span data-stu-id="5b928-155">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="5b928-156">Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="5b928-156">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="5b928-157">Assicurarsi di includere il codice paese ,ad esempio **+1** 250 555 0012</span><span class="sxs-lookup"><span data-stu-id="5b928-157">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="5b928-158">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b928-158">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b928-159">Passaggio successivo: Assegnare numeri di telefono agli utenti</span><span class="sxs-lookup"><span data-stu-id="5b928-159">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
