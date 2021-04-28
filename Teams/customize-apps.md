---
title: Personalizzare le app Microsoft in Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come personalizzare le app in Microsoft Teams.
ms.openlocfilehash: 100a01c541c79ab62f10f3e11f086cdef5a11996
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059180"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="6e0f9-103">Personalizzare le app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e0f9-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="6e0f9-104">Microsoft Teams offre la personalizzazione delle app per migliorare l'esperienza di Teams.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="6e0f9-105">Alcuni sviluppatori di app consentono di personalizzare un'app dall'amministratore di Teams. L'amministratore può personalizzare o ridenobrare le proprietà dell'app in base alle esigenze dell'organizzazione usando la pagina **Gestisci app dell'interfaccia di** amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="6e0f9-106">I dettagli che è possibile personalizzare sono:</span><span class="sxs-lookup"><span data-stu-id="6e0f9-106">The details you can customize are:</span></span>

- <span data-ttu-id="6e0f9-107">Nome breve</span><span class="sxs-lookup"><span data-stu-id="6e0f9-107">Short name</span></span>
- <span data-ttu-id="6e0f9-108">Breve descrizione</span><span class="sxs-lookup"><span data-stu-id="6e0f9-108">Short description</span></span>
- <span data-ttu-id="6e0f9-109">Descrizione completa</span><span class="sxs-lookup"><span data-stu-id="6e0f9-109">Full description</span></span>
- <span data-ttu-id="6e0f9-110">URL dell'informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="6e0f9-110">Privacy policy URL</span></span>
- <span data-ttu-id="6e0f9-111">URL del sito Web</span><span class="sxs-lookup"><span data-stu-id="6e0f9-111">Website URL</span></span>
- <span data-ttu-id="6e0f9-112">URL delle condizioni per l'uso</span><span class="sxs-lookup"><span data-stu-id="6e0f9-112">Terms of use URL</span></span>
- <span data-ttu-id="6e0f9-113">Icona a colori</span><span class="sxs-lookup"><span data-stu-id="6e0f9-113">Color icon</span></span>
- <span data-ttu-id="6e0f9-114">Icona Struttura</span><span class="sxs-lookup"><span data-stu-id="6e0f9-114">Outline icon</span></span>
- <span data-ttu-id="6e0f9-115">Colore principale</span><span class="sxs-lookup"><span data-stu-id="6e0f9-115">Accent color</span></span>

<span data-ttu-id="6e0f9-116">Per informazioni dettagliate sui campi che è possibile personalizzare, vedere lo schema manifesto di [Teams.](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema)</span><span class="sxs-lookup"><span data-stu-id="6e0f9-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="6e0f9-117">Al momento, la personalizzazione delle app non è supportata in Government Community Cloud High (GCCH) o Department of Defense (DoD).</span><span class="sxs-lookup"><span data-stu-id="6e0f9-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="6e0f9-118">Personalizzare i dettagli dell'app</span><span class="sxs-lookup"><span data-stu-id="6e0f9-118">Customize the app's details</span></span>

<span data-ttu-id="6e0f9-119">Per iniziare a personalizzare un'app, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="6e0f9-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="6e0f9-120">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="6e0f9-121">Espandere **App di Teams** e selezionare Gestisci **app**.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="6e0f9-122">Controllare la **colonna Personalizzabile** dell'elenco delle app e ordinare in base alle app personalizzabili.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![La colonna di personalizzazione ordinata](media/customize-column.png)

   <span data-ttu-id="6e0f9-124">Sono disponibili tre punti di ingresso per accedere alla caratteristica di personalizzazione:</span><span class="sxs-lookup"><span data-stu-id="6e0f9-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="6e0f9-125">Selezionare accanto all'app da personalizzare e quindi **scegliere Personalizza**.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![Opzione di personalizzazione della selezione 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="6e0f9-127">Selezionare il nome dell'app e quindi **Personalizzabile.**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-127">Select the app name and then **Customizable**.</span></span>

     ![Opzione di personalizzazione della selezione 2](media/app-details-customizable.png)

   - <span data-ttu-id="6e0f9-129">Selezionare il nome dell'app e quindi selezionare **Personalizza** nell'elenco **a discesa** Azioni.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![Opzione di personalizzazione della selezione 3](media/customize-action-menu.png)

4. <span data-ttu-id="6e0f9-131">Espandere la **sezione** Dettagli e personalizzare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e0f9-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="6e0f9-132">Nome breve</span><span class="sxs-lookup"><span data-stu-id="6e0f9-132">Short name</span></span>
    - <span data-ttu-id="6e0f9-133">Breve descrizione</span><span class="sxs-lookup"><span data-stu-id="6e0f9-133">Short description</span></span>
    - <span data-ttu-id="6e0f9-134">Descrizione completa</span><span class="sxs-lookup"><span data-stu-id="6e0f9-134">Full description</span></span>
    - <span data-ttu-id="6e0f9-135">Sito Web</span><span class="sxs-lookup"><span data-stu-id="6e0f9-135">Website</span></span>
    - <span data-ttu-id="6e0f9-136">URL dell'informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="6e0f9-136">Privacy policy URL</span></span>
    - <span data-ttu-id="6e0f9-137">URL delle condizioni per l'uso</span><span class="sxs-lookup"><span data-stu-id="6e0f9-137">Terms of use URL</span></span>

   ![Le impostazioni di personalizzazione](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="6e0f9-139">Saranno visibili solo i campi assegnati dallo sviluppatore dell'app come personalizzabili.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="6e0f9-140">Espandere la **sezione** Icona.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="6e0f9-141">a.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-141">a.</span></span> <span data-ttu-id="6e0f9-142">Caricare un'icona.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-142">Upload an icon.</span></span> <span data-ttu-id="6e0f9-143">Usare un'icona a colori (192x192) pixel in formato PNG.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="6e0f9-144">b.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-144">b.</span></span> <span data-ttu-id="6e0f9-145">Scegliere un colore per il contorno di un'icona.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-145">Choose an icon outline color.</span></span> <span data-ttu-id="6e0f9-146">Usare un solo pixel del contorno trasparente (32x32) in formato PNG.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="6e0f9-147">c.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-147">c.</span></span> <span data-ttu-id="6e0f9-148">Selezionare un colore principale dell'app corrispondente all'icona.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-148">Select an app accent color that matches the icon.</span></span>

    ![Personalizzare le opzioni di colore del riquadro delle icone](media/customize-app-colors.png)

6. <span data-ttu-id="6e0f9-150">Dopo aver personalizzato l'app, selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="6e0f9-151">Selezionare **Pubblica** per pubblicare l'app personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="6e0f9-152">L'app personalizzata è ora elencata nella **pagina Gestisci app.**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="6e0f9-153">Sarà disponibile una sola versione dell'app, perché la personalizzazione delle caratteristiche dell'app non crea una copia dell'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="6e0f9-154">Ora gli utenti finali di Teams possono aprire il proprio client Teams per visualizzare l'app personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![App personalizzata nel client di Teams](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="6e0f9-156">Considerazioni speciali per la personalizzazione di un'app</span><span class="sxs-lookup"><span data-stu-id="6e0f9-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="6e0f9-157">La nota seguente include dettagli importanti sulla personalizzazione di un'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="6e0f9-158">Quando si personalizzano le app e qualsiasi descrizione relativa a un'app, assicurarsi di seguire le eventuali linee guida per la personalizzazione fornite dall'autore dell'app nella documentazione o nelle condizioni per l'uso.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="6e0f9-159">L'utente è anche responsabile del rispetto dei diritti di altri utenti per quanto riguarda le immagini di terze parti che potrebbero essere usate.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="6e0f9-160">I dati di personalizzazione forniti dall'amministratore vengono archiviati nell'area geografica più vicina.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="6e0f9-161">L'utente è responsabile della validità dei collegamenti alle condizioni d'uso o all'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="6e0f9-162">Nel caso in cui l'autore dell'app non consenta più la personalizzazione di un campo, nella pagina dei dettagli dell'app viene visualizzato un messaggio che informa l'amministratore dei campi che non possono più essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="6e0f9-163">Tutte le modifiche apportate al campo verranno ripristinate ai valori originali.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="6e0f9-164">Le modifiche alla personalizzazione potrebbero richiedere fino a 24 ore per consentire agli utenti di visualizzare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="6e0f9-165">Esaminare i dettagli dell'app</span><span class="sxs-lookup"><span data-stu-id="6e0f9-165">Review app details</span></span>

<span data-ttu-id="6e0f9-166">È consigliabile visualizzare i dettagli dell'app per esaminare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="6e0f9-167">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="6e0f9-168">Espandere **App di Teams** e selezionare **Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="6e0f9-169">Selezionare il nome dell'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-169">Select the app name.</span></span>

4. <span data-ttu-id="6e0f9-170">Visualizzare i dettagli dell'app, incluso il nome dell'app originale **Nome breve dell'autore.**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personalizzare il nome dell'app del pannello icone](media/original-app-version.png)

   <span data-ttu-id="6e0f9-172">Il **campo Nome breve dell'autore** è visibile solo se è stato modificato il nome breve dell'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="6e0f9-173">Reimpostare i dettagli dell'app sul valore predefinito</span><span class="sxs-lookup"><span data-stu-id="6e0f9-173">Reset app details to default</span></span>

<span data-ttu-id="6e0f9-174">In qualsiasi momento, è possibile reimpostare i dettagli dell'app sulle impostazioni originali.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="6e0f9-175">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="6e0f9-176">Espandere **App di Teams** e selezionare Gestisci **app**.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="6e0f9-177">Selezionare il nome dell'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-177">Select the app name.</span></span>

4. <span data-ttu-id="6e0f9-178">Selezionare **Reimposta come predefinito nell'elenco** a **discesa** Azioni.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Selezionare Reimposta come predefinita evidenziata](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="6e0f9-180">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="6e0f9-180">Frequently asked questions</span></span>

<span data-ttu-id="6e0f9-181">**Quanto tempo è necessario per consentire agli utenti di visualizzare l'app personalizzata?**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="6e0f9-182">Anche se l'amministratore può vedere immediatamente le modifiche nell'interfaccia di amministrazione di Teams, potrebbero essere necessarie fino a 24 ore prima che gli utenti finali vedano le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="6e0f9-183">**Il provider di app può personalizzare l'app per i propri clienti?**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="6e0f9-184">No, l'amministratore di un tenant deve personalizzare l'app per il tenant usando l'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="6e0f9-185">**L'app personalizzata verrà distribuita automaticamente per sostituire l'app personalizzata corrente in un tenant?**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="6e0f9-186">No, gli amministratori del tenant doranno rimuovere manualmente qualsiasi app personalizzata e pubblicare la versione personalizzata dell'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="6e0f9-187">Se un'app è stata personalizzata e pubblicata come app personalizzata, la nuova app personalizzata con la caratteristica di personalizzazione dell'app non sostituirà l'app personalizzata corrente.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="6e0f9-188">**Il report sull'utilizzo delle app mostrerà anche i valori personalizzati, ad esempio il nome breve personalizzato?**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="6e0f9-189">No, il report sull'utilizzo dell'app mostrerà comunque il nome originale dell'app inviata dall'autore.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="6e0f9-190">**Quali app è possibile personalizzare usando la funzionalità di personalizzazione dell'app?**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="6e0f9-191">È possibile personalizzare solo le app che possono essere personalizzabili dall'autore dell'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="6e0f9-192">L'autore dell'app dovrà acconsentire esplicitamente per consentire ai propri clienti di personalizzare l'app.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="6e0f9-193">**Le proprietà personalizzate verranno visualizzate nella schermata di consenso all'autorizzazione del grafico?**</span><span class="sxs-lookup"><span data-stu-id="6e0f9-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="6e0f9-194">No, la schermata di consenso all'autorizzazione mostrerà comunque il valore originale inviato dall'autore.</span><span class="sxs-lookup"><span data-stu-id="6e0f9-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="6e0f9-195">Articolo correlato</span><span class="sxs-lookup"><span data-stu-id="6e0f9-195">Related article</span></span>

- [<span data-ttu-id="6e0f9-196">Gestire le app</span><span class="sxs-lookup"><span data-stu-id="6e0f9-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="6e0f9-197">Personalizzare l'app store</span><span class="sxs-lookup"><span data-stu-id="6e0f9-197">Customize your app store</span></span>](customize-your-app-store.md)
