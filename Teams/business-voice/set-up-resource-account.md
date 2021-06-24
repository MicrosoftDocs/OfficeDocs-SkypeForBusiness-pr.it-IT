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
ms.openlocfilehash: df5001b6f757b407e96a473d302c79d837af957c
ms.sourcegitcommit: 38fa37d83704200911866cf017566fcb128ea2fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105168"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="d3698-103">Passaggio 4: Configurare un account della risorsa Voce aziendale</span><span class="sxs-lookup"><span data-stu-id="d3698-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="d3698-104">Gli account delle risorse non sono assegnati a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="d3698-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="d3698-105">Gli account delle risorse, che usano una licenza utente virtuale gratuita, vengono invece usati dai dispositivi e dai servizi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3698-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="d3698-106">In Microsoft Teams, agli account delle risorse vengono assegnati numeri di telefono e quindi associati agli operatori automatici e alle code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d3698-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="d3698-107">Associando gli account delle risorse agli operatori automatici e alle code di chiamata, è possibile aggiungere uno o più numeri a numero verde o a pedaggio.</span><span class="sxs-lookup"><span data-stu-id="d3698-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="d3698-108">Ad esempio, è possibile associare un account della risorsa a un numero a pedaggio a un operatore automatico per i chiamanti locali.</span><span class="sxs-lookup"><span data-stu-id="d3698-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="d3698-109">Per le chiamate interurbane, è possibile associare un altro account della risorsa a un numero verde allo stesso operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="d3698-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="d3698-110">Le sezioni di questo articolo illustrano come configurare un account della risorsa e quindi assegnare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="d3698-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="d3698-111">In seguito, l'account della risorsa verrà associato a un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="d3698-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

<span data-ttu-id="d3698-112">Il video seguente mostra come completare questi passaggi nell'interfaccia Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d3698-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="d3698-113">Ottenere licenze utente virtuali</span><span class="sxs-lookup"><span data-stu-id="d3698-113">Obtain virtual user licenses</span></span>

<span data-ttu-id="d3698-114">Gli account delle risorse richiedono una licenza per poter usare operatori automatici e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d3698-114">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="d3698-115">È possibile usare una licenza *Microsoft 365 Sistema telefonico - Utente* virtuale.</span><span class="sxs-lookup"><span data-stu-id="d3698-115">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="d3698-116">È necessario eseguire la procedura seguente solo se si è effettuato l'accesso a un periodo di valutazione di Business Voice.</span><span class="sxs-lookup"><span data-stu-id="d3698-116">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="d3698-117">Se sono state acquistate licenze Business Voice, le licenze virtuali dovrebbero già essere applicate al proprio account.</span><span class="sxs-lookup"><span data-stu-id="d3698-117">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="d3698-118">Per verificare se si hanno già licenze virtuali, accedere Microsoft 365 un account con autorizzazioni di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d3698-118">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="d3698-119">Quindi vai a Fatturazione > [Tuoi prodotti](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span><span class="sxs-lookup"><span data-stu-id="d3698-119">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="d3698-120">Se si hanno licenze virtuali, verranno visualizzate **come Microsoft 365 Sistema telefonico - Utente virtuale.**</span><span class="sxs-lookup"><span data-stu-id="d3698-120">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="d3698-121">Aprire il interfaccia di amministrazione di Microsoft 365 e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d3698-121">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="d3698-122">Nel riquadro di spostamento sinistro passare a <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank"> **Componenti**  > </a>aggiuntivi Servizi di acquisto  >  **fatturazione**  >  **Vedere tutti i prodotti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="d3698-122">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="d3698-123">Scorrere fino alla fine per trovare la licenza **Microsoft 365 Sistema telefonico - Utente** virtuale.</span><span class="sxs-lookup"><span data-stu-id="d3698-123">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="d3698-124">Seleziona **Dettagli**, quindi **Acquista**.</span><span class="sxs-lookup"><span data-stu-id="d3698-124">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="d3698-125">Nella pagina di acquisto della licenza selezionare il numero di licenze utente virtuali desiderate.</span><span class="sxs-lookup"><span data-stu-id="d3698-125">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="d3698-126">È necessaria una licenza virtuale per ogni operatore automatico e coda di chiamata che si prevede di configurare.</span><span class="sxs-lookup"><span data-stu-id="d3698-126">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="d3698-127">È consigliabile selezionare almeno cinque licenze per configurare più operatori automatici e code di chiamata in futuro senza dover acquistare subito altre licenze.</span><span class="sxs-lookup"><span data-stu-id="d3698-127">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="d3698-128">Deselezionare **Assegna automaticamente a tutti gli utenti senza licenze.**</span><span class="sxs-lookup"><span data-stu-id="d3698-128">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="d3698-129">Selezionare **Estrai adesso.**</span><span class="sxs-lookup"><span data-stu-id="d3698-129">Select **Check out now**.</span></span>
7. <span data-ttu-id="d3698-130">Confermare l'ordine, **selezionare Avanti** e quindi **Eseguire l'ordine.**</span><span class="sxs-lookup"><span data-stu-id="d3698-130">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="d3698-131">Tenere presente che è comunque necessario  **acquistare** la licenza anche se ha un costo pari a zero.</span><span class="sxs-lookup"><span data-stu-id="d3698-131">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="d3698-132">Creare un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="d3698-132">Create a resource account</span></span>

<span data-ttu-id="d3698-133">Dopo aver ricevuto la licenza *Microsoft 365 Sistema telefonico - Utente* virtuale, è possibile creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d3698-133">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add.png)

1. <span data-ttu-id="d3698-135">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d3698-135">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="d3698-136">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **Impostazioni a livello di** organizzazione Account delle  >  **risorse.**</a></span><span class="sxs-lookup"><span data-stu-id="d3698-136">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="d3698-137">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d3698-137">Select **Add**.</span></span>
4. <span data-ttu-id="d3698-138">Nel riquadro **Aggiungi account risorsa** compilare Nome **visualizzato** e quindi **Nome utente.**</span><span class="sxs-lookup"><span data-stu-id="d3698-138">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="d3698-139">Scegliere un nome visualizzato descrittivo, ad esempio "Operatore automatico linea principale" per descrivere lo scopo dell'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="d3698-139">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="d3698-140">In **Tipo di account risorsa** selezionare **Operatore automatico.**</span><span class="sxs-lookup"><span data-stu-id="d3698-140">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="d3698-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d3698-141">Select **Save**.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="d3698-143">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="d3698-143">Assign a license</span></span>

<span data-ttu-id="d3698-144">Dopo aver creato l'account delle risorse, è necessario assegnare una licenza *Microsoft 365 Sistema telefonico -* Utente virtuale o Sistema telefonico *licenza.*</span><span class="sxs-lookup"><span data-stu-id="d3698-144">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Screenshot dell'interfaccia utente per l'assegnazione di licenze nel interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="d3698-146">Aprire il interfaccia di amministrazione di Microsoft 365 e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d3698-146">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="d3698-147">Nel riquadro di spostamento sinistro passare a <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Utenti**  >  **utenti attivi**</a>.</span><span class="sxs-lookup"><span data-stu-id="d3698-147">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="d3698-148">Selezionare l'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="d3698-148">Select your resource account.</span></span>
1. <span data-ttu-id="d3698-149">Nella scheda **Licenze e app,** in **Licenze,** **selezionare Microsoft 365 Sistema telefonico - Utente virtuale**.</span><span class="sxs-lookup"><span data-stu-id="d3698-149">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="d3698-150">Selezionare **Salva modifiche** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="d3698-150">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="d3698-151">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="d3698-151">Assign a service number</span></span>

![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="d3698-153">Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d3698-153">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="d3698-154">Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **Impostazioni a livello di** organizzazione Account delle  >  **risorse.**</a></span><span class="sxs-lookup"><span data-stu-id="d3698-154">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="d3698-155">Selezionare l'account della risorsa appena creato e quindi fare clic su **Assegna/annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="d3698-155">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="d3698-156">**Nell'elenco Telefono tipo di** numero scegliere **Online.**</span><span class="sxs-lookup"><span data-stu-id="d3698-156">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="d3698-157">Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="d3698-157">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="d3698-158">Assicurarsi di includere il codice paese ,ad esempio **+1** 250 555 0012</span><span class="sxs-lookup"><span data-stu-id="d3698-158">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="d3698-159">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d3698-159">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3698-160">Passaggio successivo: Assegnare numeri di telefono agli utenti</span><span class="sxs-lookup"><span data-stu-id="d3698-160">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
