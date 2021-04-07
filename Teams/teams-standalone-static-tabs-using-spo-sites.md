---
title: Creare un'app "Portale Intranet" di Teams da un sito o una pagina di SharePoint Online
author: cichur
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: A partire da una pagina o un sito di SharePoint Online, creare una scheda personale autonoma che può essere usata come portale Intranet per l'organizzazione.
localization_priority: Priority
ms.openlocfilehash: c6d138b1bf95edb619de6563f644e76ec123e3c6
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607541"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="bfe93-103">Creare un'app "Portale Intranet" di Teams da un sito o una pagina di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bfe93-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="bfe93-104">Eseguire i passaggi descritti in questo articolo per creare un'app autonoma e statica all'interno di Teams che collega al sito Intranet dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bfe93-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="bfe93-105">Verrà creata un'*app personale di Teams* per il sito Intranet di SharePoint, che verrà visualizzata sotto forma di scheda all'interno di Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe93-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="bfe93-106">Questa scheda può contenere informazioni importanti per tutti gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe93-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="bfe93-107">Si tratta di un modo rapido e pratico per consentire agli utenti di Teams di accedere agli aggiornamenti semplicemente facendo clic su una scheda.</span><span class="sxs-lookup"><span data-stu-id="bfe93-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="bfe93-108">Tenere presente che per il processo illustrato è **necessario usare** una pagina o un sito di SharePoint *moderno*.</span><span class="sxs-lookup"><span data-stu-id="bfe93-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="bfe93-109">Questo processo non è disponibile per le pagine o i siti *classici*.</span><span class="sxs-lookup"><span data-stu-id="bfe93-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfe93-110">Assicurarsi che il sideload delle app di Teams sia abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="bfe93-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="bfe93-111">A seconda della fase in cui ci si trova nel processo di migrazione del portale di amministrazione di Teams, può essere necessario abilitarlo in Teams > Amministrazione o in Amministrazione > Impostazioni > Servizi e componenti aggiuntivi > Microsoft Teams > App > App esterne, nella versione precedente del portale.</span><span class="sxs-lookup"><span data-stu-id="bfe93-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="bfe93-112">Usare App Studio per creare l'app autonoma di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bfe93-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="bfe93-113">Informazioni preliminari:</span><span class="sxs-lookup"><span data-stu-id="bfe93-113">Before you begin:</span></span>

1. <span data-ttu-id="bfe93-114">È necessario conoscere l'URL di una pagina o un sito di comunicazione o del team moderno di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bfe93-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>

   <span data-ttu-id="bfe93-115">Questi siti avranno sempre */teams/* o */sites/* nel percorso.</span><span class="sxs-lookup"><span data-stu-id="bfe93-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="bfe93-116">È necessario conoscere il sottodominio del tenant, che verrà usato nel segnaposto **{{subdomain}}**.</span><span class="sxs-lookup"><span data-stu-id="bfe93-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="bfe93-117">In questo articolo si userà **{{siteUrl}}** come segnaposto per l'*URL* del sito o della pagina scelta.</span><span class="sxs-lookup"><span data-stu-id="bfe93-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>

   <span data-ttu-id="bfe93-118">URL di *esempio*: </span><span class="sxs-lookup"><span data-stu-id="bfe93-118">Example *URLs*:</span></span>
   
   - `https://contoso.sharepoint.com/teams/Contoso`
      <br/><span data-ttu-id="bfe93-119">*oppure*</span><span class="sxs-lookup"><span data-stu-id="bfe93-119">*or*</span></span>
   - `https://contoso.sharepoint.com/sites/Contoso`
        
4. <span data-ttu-id="bfe93-120">Inoltre, si userà **{{sitePath}}** per indicare il *percorso* dell'URL, ad esempio /teams/Contoso.</span><span class="sxs-lookup"><span data-stu-id="bfe93-120">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>

   <span data-ttu-id="bfe93-121">Percorsi di *esempio*:</span><span class="sxs-lookup"><span data-stu-id="bfe93-121">Example *paths*:</span></span>
   
   - <span data-ttu-id="bfe93-122">/teams/Contoso</span><span class="sxs-lookup"><span data-stu-id="bfe93-122">/teams/Contoso</span></span>
     <br/><span data-ttu-id="bfe93-123">*oppure*</span><span class="sxs-lookup"><span data-stu-id="bfe93-123">*or*</span></span>
   - <span data-ttu-id="bfe93-124">/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="bfe93-124">/sites/Contoso</span></span>

<span data-ttu-id="bfe93-125">Per iniziare, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="bfe93-125">Begin by following the steps below:</span></span>

1. <span data-ttu-id="bfe93-126">Passare allo Store di Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe93-126">Go to the Teams Store.</span></span>

2. <span data-ttu-id="bfe93-127">Installare o aprire App Studio.</span><span class="sxs-lookup"><span data-stu-id="bfe93-127">Install or open App Studio.</span></span>

3. <span data-ttu-id="bfe93-128">Fare clic su **Apri** accanto all'opzione dell'app.</span><span class="sxs-lookup"><span data-stu-id="bfe93-128">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="bfe93-129">Con App Studio aperto, fare clic su **Manifest Editor** (Editor manifesto).</span><span class="sxs-lookup"><span data-stu-id="bfe93-129">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="bfe93-130">Selezionare **Create a new app** (Crea una nuova app).</span><span class="sxs-lookup"><span data-stu-id="bfe93-130">**Create a new app**.</span></span>

6. <span data-ttu-id="bfe93-131">Compilare i dettagli dell'app in **App Details**.</span><span class="sxs-lookup"><span data-stu-id="bfe93-131">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="bfe93-132">Fare clic su **Tabs** (Schede) in Capabilities (Funzionalità).</span><span class="sxs-lookup"><span data-stu-id="bfe93-132">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="bfe93-133">Fare clic su **Add** (Aggiungi) nella sezione Personal Tab (scheda personale).</span><span class="sxs-lookup"><span data-stu-id="bfe93-133">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="bfe93-134">Inserire il nome \*\*\*\* e **un nuovo ID entità univoco**.</span><span class="sxs-lookup"><span data-stu-id="bfe93-134">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="bfe93-135">Inserire **URL del contenuto e URL del sito Web**.</span><span class="sxs-lookup"><span data-stu-id="bfe93-135">Fill in the **contentURL and Website URL**.</span></span>

    - <span data-ttu-id="bfe93-136">**URL del contenuto**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="bfe93-136">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
    
    - <span data-ttu-id="bfe93-137">**URL del sito Web**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="bfe93-137">**websiteUrl**: {{siteUrl}}</span></span>

      <span data-ttu-id="bfe93-138">Esempio di **URL del contenuto**: </span><span class="sxs-lookup"><span data-stu-id="bfe93-138">Example **contentURL**:</span></span>
      
      `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. <span data-ttu-id="bfe93-139">Passare a **Domains and Permissions** (Domini e autorizzazioni).</span><span class="sxs-lookup"><span data-stu-id="bfe93-139">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="bfe93-140">Verificare che la sezione domini validi contenga il nome del dominio di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bfe93-140">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="bfe93-141">Esempio: `contoso.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="bfe93-141">Example: `contoso.sharepoint.com`</span></span>

12. <span data-ttu-id="bfe93-142">Aggiungere le proprietà di **Single Sign-On** dell'app Web seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfe93-142">Add the following web app **single sign-on** properties:</span></span>

    <span data-ttu-id="bfe93-143">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bfe93-143">Example:</span></span>
    
    - <span data-ttu-id="bfe93-144">**AAD application ID**: 00000003-0000-0ff1-ce00-000000000000</span><span class="sxs-lookup"><span data-stu-id="bfe93-144">**AAD application ID**: 00000003-0000-0ff1-ce00-000000000000</span></span>
    
    - <span data-ttu-id="bfe93-145">Url di **risorsa**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="bfe93-145">**Resource Url**: {{subdomain}}.sharepoint.com</span></span>

      ![Single Sign-On dell'app Web, con ID e URL.](media/personal-app.png)

13. <span data-ttu-id="bfe93-147">**Salvare** queste proprietà e quindi passare a **Test and distribute** (Test e distribuzione).</span><span class="sxs-lookup"><span data-stu-id="bfe93-147">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="bfe93-148">Installare l'app per testare personalmente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bfe93-148">Install the app to test the application personally.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bfe93-149">Se non si usa App Studio di Teams, sarà necessario comprimere il file manifest.JSON appena creato, passare all'App Store in Teams e fare clic sul collegamento **Carica un' app personalizzata** nell'angolo in basso a destra dell'App Store.</span><span class="sxs-lookup"><span data-stu-id="bfe93-149">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="bfe93-150">In questo modo, l'app verrà resa disponibile.</span><span class="sxs-lookup"><span data-stu-id="bfe93-150">This will make the app available to you.</span></span>

15. <span data-ttu-id="bfe93-151">L'app è ora disponibile come scheda personale da caricare e visualizzare in Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe93-151">Now the app is available as a personal tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-personal-tab"></a><span data-ttu-id="bfe93-152">Testare e visualizzare la nuova scheda personale</span><span class="sxs-lookup"><span data-stu-id="bfe93-152">Test and view your new personal tab</span></span>

<span data-ttu-id="bfe93-153">Per visualizzare la nuova scheda sul desktop di Teams, passare ai puntini di sospensione **...**, sul lato sinistro della barra dell'app.</span><span class="sxs-lookup"><span data-stu-id="bfe93-153">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="bfe93-154">Trovare la nuova app, caricarla e testare l'applicazione autonoma in Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe93-154">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="bfe93-155">Se si vuole rendere disponibile la nuova app in una posizione più in alto nel menu a sinistra, è necessario usare un'impostazione di criteri per l'app.</span><span class="sxs-lookup"><span data-stu-id="bfe93-155">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="bfe93-156">Questa impostazione è disponibile nella sezione di amministrazione del team > criteri app > aggiungere un'applicazione bloccata.</span><span class="sxs-lookup"><span data-stu-id="bfe93-156">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="bfe93-157">Quando si assegnano i criteri a un utente per il test, la modifica viene visualizzata dopo poche ore.</span><span class="sxs-lookup"><span data-stu-id="bfe93-157">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="bfe93-158">Tenendo presente questo aspetto, decidere se l'app dovrebbe comparire non appena possibile per evitare ritardi.</span><span class="sxs-lookup"><span data-stu-id="bfe93-158">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="bfe93-159">Per visualizzare e testare la nuova app in un dispositivo mobile, aprire il menu dell'app toccando la freccia (**^**) sopra la barra delle schede nella parte inferiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="bfe93-159">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="bfe93-160">Individuare l'app e accedervi nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="bfe93-160">Find your app and navigate to it on your mobile device.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="bfe93-161">File Manifest.JSON di esempio</span><span class="sxs-lookup"><span data-stu-id="bfe93-161">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="bfe93-162">Il file JSON generato avrà un aspetto simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="bfe93-162">The JSON file you generate will look something like the one below.</span></span>

```json
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.9/MicrosoftTeams.schema.json",

    "manifestVersion": "1.9",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso",

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet",

        "full": "Intranet Portal for Contoso"

    },

    "description": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

            "entityId": "communicationSiteTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
