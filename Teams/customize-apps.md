---
title: Personalizzare le app Microsoft in Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a87ce5f7dd63a78af4a7a1ea5f56aed1cad7263a
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574155"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="7082f-103">Personalizzare le app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7082f-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="7082f-104">Microsoft Teams offre la personalizzazione delle app per migliorare l'esperienza di Teams.</span><span class="sxs-lookup"><span data-stu-id="7082f-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="7082f-105">Alcuni sviluppatori di app consentono di personalizzare un'app dall'amministratore di Teams. L'amministratore può personalizzare o ridenobrare le proprietà dell'app in base alle esigenze dell'organizzazione usando la pagina **Gestisci app dell'interfaccia di** amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="7082f-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="7082f-106">I dettagli che è possibile personalizzare sono:</span><span class="sxs-lookup"><span data-stu-id="7082f-106">The details you can customize are:</span></span>

- <span data-ttu-id="7082f-107">Nome breve</span><span class="sxs-lookup"><span data-stu-id="7082f-107">Short name</span></span>
- <span data-ttu-id="7082f-108">Breve descrizione</span><span class="sxs-lookup"><span data-stu-id="7082f-108">Short description</span></span>
- <span data-ttu-id="7082f-109">Descrizione completa</span><span class="sxs-lookup"><span data-stu-id="7082f-109">Full description</span></span>
- <span data-ttu-id="7082f-110">URL dell'informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="7082f-110">Privacy policy URL</span></span>
- <span data-ttu-id="7082f-111">URL del sito Web</span><span class="sxs-lookup"><span data-stu-id="7082f-111">Website URL</span></span>
- <span data-ttu-id="7082f-112">URL delle condizioni per l'uso</span><span class="sxs-lookup"><span data-stu-id="7082f-112">Terms of use URL</span></span>
- <span data-ttu-id="7082f-113">Icona a colori</span><span class="sxs-lookup"><span data-stu-id="7082f-113">Color icon</span></span>
- <span data-ttu-id="7082f-114">Icona Struttura</span><span class="sxs-lookup"><span data-stu-id="7082f-114">Outline icon</span></span>
- <span data-ttu-id="7082f-115">Colore principale</span><span class="sxs-lookup"><span data-stu-id="7082f-115">Accent color</span></span>

<span data-ttu-id="7082f-116">Per informazioni dettagliate sui campi che è possibile personalizzare, vedere lo schema manifesto di [Teams.](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema)</span><span class="sxs-lookup"><span data-stu-id="7082f-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="7082f-117">Personalizzare i dettagli dell'app</span><span class="sxs-lookup"><span data-stu-id="7082f-117">Customize the app's details</span></span>

<span data-ttu-id="7082f-118">Per iniziare a personalizzare un'app, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7082f-118">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="7082f-119">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="7082f-119">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="7082f-120">Espandere **App di Teams** e selezionare Gestisci **app**.</span><span class="sxs-lookup"><span data-stu-id="7082f-120">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="7082f-121">Controllare la **colonna Personalizzabile** dell'elenco delle app e ordinare in base alle app personalizzabili.</span><span class="sxs-lookup"><span data-stu-id="7082f-121">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![La colonna di personalizzazione ordinata](media/customize-column.png)

   <span data-ttu-id="7082f-123">Sono disponibili tre punti di ingresso per accedere alla caratteristica di personalizzazione:</span><span class="sxs-lookup"><span data-stu-id="7082f-123">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="7082f-124">Selezionare accanto all'app da personalizzare e quindi **scegliere Personalizza**.</span><span class="sxs-lookup"><span data-stu-id="7082f-124">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![Opzione di personalizzazione della selezione 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="7082f-126">Selezionare il nome dell'app e quindi **Personalizzabile.**</span><span class="sxs-lookup"><span data-stu-id="7082f-126">Select the app name and then **Customizable**.</span></span>

     ![Opzione di personalizzazione della selezione 2](media/app-details-customizable.png)

   - <span data-ttu-id="7082f-128">Selezionare il nome dell'app e quindi selezionare **Personalizza** nell'elenco **a discesa** Azioni.</span><span class="sxs-lookup"><span data-stu-id="7082f-128">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![Opzione di personalizzazione della selezione 3](media/customize-action-menu.png)

4. <span data-ttu-id="7082f-130">Espandere la **sezione** Dettagli e personalizzare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7082f-130">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="7082f-131">Nome breve</span><span class="sxs-lookup"><span data-stu-id="7082f-131">Short name</span></span>
    - <span data-ttu-id="7082f-132">Breve descrizione</span><span class="sxs-lookup"><span data-stu-id="7082f-132">Short description</span></span>
    - <span data-ttu-id="7082f-133">Descrizione completa</span><span class="sxs-lookup"><span data-stu-id="7082f-133">Full description</span></span>
    - <span data-ttu-id="7082f-134">Sito Web</span><span class="sxs-lookup"><span data-stu-id="7082f-134">Website</span></span>
    - <span data-ttu-id="7082f-135">URL dell'informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="7082f-135">Privacy policy URL</span></span>
    - <span data-ttu-id="7082f-136">URL delle condizioni per l'uso</span><span class="sxs-lookup"><span data-stu-id="7082f-136">Terms of use URL</span></span>

   ![Le impostazioni di personalizzazione](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="7082f-138">Saranno visibili solo i campi assegnati dallo sviluppatore dell'app come personalizzabili.</span><span class="sxs-lookup"><span data-stu-id="7082f-138">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="7082f-139">Espandere la **sezione** Icona.</span><span class="sxs-lookup"><span data-stu-id="7082f-139">Expand the **Icon** section.</span></span>

   <span data-ttu-id="7082f-140">a.</span><span class="sxs-lookup"><span data-stu-id="7082f-140">a.</span></span> <span data-ttu-id="7082f-141">Caricare un'icona.</span><span class="sxs-lookup"><span data-stu-id="7082f-141">Upload an icon.</span></span> <span data-ttu-id="7082f-142">Usare un'icona a colori (192x192) pixel in formato PNG.</span><span class="sxs-lookup"><span data-stu-id="7082f-142">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="7082f-143">b.</span><span class="sxs-lookup"><span data-stu-id="7082f-143">b.</span></span> <span data-ttu-id="7082f-144">Scegliere un colore per il contorno di un'icona.</span><span class="sxs-lookup"><span data-stu-id="7082f-144">Choose an icon outline color.</span></span> <span data-ttu-id="7082f-145">Usare un solo pixel del contorno trasparente (32x32) in formato PNG.</span><span class="sxs-lookup"><span data-stu-id="7082f-145">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="7082f-146">c.</span><span class="sxs-lookup"><span data-stu-id="7082f-146">c.</span></span> <span data-ttu-id="7082f-147">Selezionare un colore principale dell'app corrispondente all'icona.</span><span class="sxs-lookup"><span data-stu-id="7082f-147">Select an app accent color that matches the icon.</span></span>

    ![Personalizzare le opzioni di colore del riquadro delle icone](media/customize-app-colors.png)

6. <span data-ttu-id="7082f-149">Dopo aver personalizzato l'app, selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="7082f-149">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="7082f-150">Selezionare **Pubblica** per pubblicare l'app personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7082f-150">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="7082f-151">L'app personalizzata è ora elencata nella **pagina Gestisci app.**</span><span class="sxs-lookup"><span data-stu-id="7082f-151">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="7082f-152">Sarà disponibile una sola versione dell'app, perché la personalizzazione delle caratteristiche dell'app non crea una copia dell'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-152">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="7082f-153">Ora gli utenti finali di Teams possono aprire il proprio client Teams per visualizzare l'app personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7082f-153">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![App personalizzata nel client di Teams](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="7082f-155">Considerazioni speciali per la personalizzazione di un'app</span><span class="sxs-lookup"><span data-stu-id="7082f-155">Special considerations for customizing an app</span></span>

<span data-ttu-id="7082f-156">La nota seguente include dettagli importanti sulla personalizzazione di un'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-156">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="7082f-157">Quando si personalizzano le app e qualsiasi descrizione relativa a un'app, assicurarsi di seguire le eventuali linee guida per la personalizzazione fornite dall'autore dell'app nella documentazione o nelle condizioni per l'uso.</span><span class="sxs-lookup"><span data-stu-id="7082f-157">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="7082f-158">L'utente è anche responsabile del rispetto dei diritti di altri utenti per quanto riguarda le immagini di terze parti che potrebbero essere usate.</span><span class="sxs-lookup"><span data-stu-id="7082f-158">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="7082f-159">I dati di personalizzazione forniti dall'amministratore vengono archiviati nell'area geografica più vicina.</span><span class="sxs-lookup"><span data-stu-id="7082f-159">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="7082f-160">L'utente è responsabile della validità dei collegamenti alle condizioni d'uso o all'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="7082f-160">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="7082f-161">Nel caso in cui l'autore dell'app non consenta più la personalizzazione di un campo, nella pagina dei dettagli dell'app viene visualizzato un messaggio che informa l'amministratore dei campi che non possono più essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7082f-161">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="7082f-162">Tutte le modifiche apportate al campo verranno ripristinate ai valori originali.</span><span class="sxs-lookup"><span data-stu-id="7082f-162">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="7082f-163">Le modifiche alla personalizzazione potrebbero richiedere fino a 24 ore per consentire agli utenti di visualizzare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7082f-163">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="7082f-164">Esaminare i dettagli dell'app</span><span class="sxs-lookup"><span data-stu-id="7082f-164">Review app details</span></span>

<span data-ttu-id="7082f-165">È consigliabile visualizzare i dettagli dell'app per esaminare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="7082f-165">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="7082f-166">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="7082f-166">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="7082f-167">Espandere **App di Teams** e selezionare **Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="7082f-167">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="7082f-168">Selezionare il nome dell'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-168">Select the app name.</span></span>

4. <span data-ttu-id="7082f-169">Visualizzare i dettagli dell'app, incluso il nome dell'app originale **Nome breve dell'autore.**</span><span class="sxs-lookup"><span data-stu-id="7082f-169">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personalizzare il nome dell'app del pannello icone](media/app-details-original-name.png)

   <span data-ttu-id="7082f-171">Il **campo Nome breve dell'autore** è visibile solo se è stato modificato il nome breve dell'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-171">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="7082f-172">Reimpostare i dettagli dell'app sul valore predefinito</span><span class="sxs-lookup"><span data-stu-id="7082f-172">Reset app details to default</span></span>

<span data-ttu-id="7082f-173">In qualsiasi momento, è possibile reimpostare i dettagli dell'app sulle impostazioni originali.</span><span class="sxs-lookup"><span data-stu-id="7082f-173">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="7082f-174">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="7082f-174">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="7082f-175">Espandere **App di Teams** e selezionare Gestisci **app**.</span><span class="sxs-lookup"><span data-stu-id="7082f-175">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="7082f-176">Selezionare il nome dell'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-176">Select the app name.</span></span>

4. <span data-ttu-id="7082f-177">Selezionare **Reimposta come predefinito nell'elenco** a **discesa** Azioni.</span><span class="sxs-lookup"><span data-stu-id="7082f-177">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Selezionare Reimposta come predefinita evidenziata](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="7082f-179">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="7082f-179">Frequently asked questions</span></span>

<span data-ttu-id="7082f-180">**Quanto tempo è necessario per consentire agli utenti di visualizzare l'app personalizzata?**</span><span class="sxs-lookup"><span data-stu-id="7082f-180">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="7082f-181">Anche se l'amministratore può vedere immediatamente le modifiche nell'interfaccia di amministrazione di Teams, potrebbero essere necessarie fino a 24 ore prima che gli utenti finali vedano le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7082f-181">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="7082f-182">**Il provider di app può personalizzare l'app per i propri clienti?**</span><span class="sxs-lookup"><span data-stu-id="7082f-182">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="7082f-183">No, l'amministratore di un tenant deve personalizzare l'app per il tenant usando l'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="7082f-183">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="7082f-184">**L'app personalizzata verrà distribuita automaticamente per sostituire l'app personalizzata corrente in un tenant?**</span><span class="sxs-lookup"><span data-stu-id="7082f-184">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="7082f-185">No, gli amministratori del tenant doranno rimuovere manualmente qualsiasi app personalizzata e pubblicare la versione personalizzata dell'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-185">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="7082f-186">Se un'app è stata personalizzata e pubblicata come app personalizzata, la nuova app personalizzata con la caratteristica di personalizzazione dell'app non sostituirà l'app personalizzata corrente.</span><span class="sxs-lookup"><span data-stu-id="7082f-186">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="7082f-187">**Il report sull'utilizzo delle app mostrerà anche i valori personalizzati, ad esempio il nome breve personalizzato?**</span><span class="sxs-lookup"><span data-stu-id="7082f-187">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="7082f-188">No, il report sull'utilizzo dell'app mostrerà comunque il nome originale dell'app inviata dall'autore.</span><span class="sxs-lookup"><span data-stu-id="7082f-188">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="7082f-189">**Quali app è possibile personalizzare usando la funzionalità di personalizzazione dell'app?**</span><span class="sxs-lookup"><span data-stu-id="7082f-189">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="7082f-190">È possibile personalizzare solo le app che possono essere personalizzabili dall'autore dell'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-190">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="7082f-191">L'autore dell'app dovrà acconsentire esplicitamente per consentire ai propri clienti di personalizzare l'app.</span><span class="sxs-lookup"><span data-stu-id="7082f-191">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="7082f-192">**Le proprietà personalizzate verranno visualizzate nella schermata di consenso all'autorizzazione del grafico?**</span><span class="sxs-lookup"><span data-stu-id="7082f-192">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="7082f-193">No, la schermata di consenso all'autorizzazione mostrerà comunque il valore originale inviato dall'autore.</span><span class="sxs-lookup"><span data-stu-id="7082f-193">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="7082f-194">Articolo correlato</span><span class="sxs-lookup"><span data-stu-id="7082f-194">Related article</span></span>

- [<span data-ttu-id="7082f-195">Gestire le app</span><span class="sxs-lookup"><span data-stu-id="7082f-195">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="7082f-196">Personalizzare l'app store</span><span class="sxs-lookup"><span data-stu-id="7082f-196">Customize your app store</span></span>](customize-your-app-store.md)
