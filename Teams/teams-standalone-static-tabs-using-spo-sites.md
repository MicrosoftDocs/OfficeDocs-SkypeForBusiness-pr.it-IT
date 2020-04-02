---
title: Creare un'app del portale Intranet di un team da un sito o una pagina di SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: È possibile usare un sito o una pagina di SharePoint Online esistente e creare una scheda statica autonoma che può essere usata come portale Intranet per l'organizzazione.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106633"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="bd96e-103">Creare un'app del portale Intranet di un team da un sito o una pagina di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bd96e-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="bd96e-104">Seguire i passaggi di questo articolo per creare un'app autonoma e statica all'interno di team che si collega al sito Intranet per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd96e-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="bd96e-105">Viene creata un' *app personale teams* del sito Intranet di SharePoint che verrà visualizzata come tabulazione all'interno di teams.</span><span class="sxs-lookup"><span data-stu-id="bd96e-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="bd96e-106">Questa scheda può contenere informazioni importanti per tutti gli utenti del team.</span><span class="sxs-lookup"><span data-stu-id="bd96e-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="bd96e-107">Si tratta di un modo rapido e comodo per consentire agli utenti di accedere agli aggiornamenti solo con una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="bd96e-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="bd96e-108">Tenere presente che il processo visualizzato **deve usare** un sito o una pagina di SharePoint *moderna* per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="bd96e-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="bd96e-109">Questo processo non è disponibile per i siti o le pagine *classiche* .</span><span class="sxs-lookup"><span data-stu-id="bd96e-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd96e-110">Accertarsi che il caricamento laterale delle app team sia abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="bd96e-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="bd96e-111">A seconda di dove ci si trova nel processo di migrazione del portale di amministrazione di teams, potrebbe essere necessario abilitarlo in teams > admin o in amministrazione > impostazioni > servizi e componenti aggiuntivi > Microsoft teams > app > app esterne, nella versione precedente del portale.</span><span class="sxs-lookup"><span data-stu-id="bd96e-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="bd96e-112">Usare App Studio per creare l'app autonoma di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bd96e-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="bd96e-113">''' Prima di iniziare:</span><span class="sxs-lookup"><span data-stu-id="bd96e-113">''' Before you begin:</span></span>
1. <span data-ttu-id="bd96e-114">È necessario conoscere l'URL di un sito del team o di una comunicazione moderna di SharePoint Online o di una pagina.</span><span class="sxs-lookup"><span data-stu-id="bd96e-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="bd96e-115">Questi siti avranno sempre */Teams/)* o */sites/* nei percorsi.</span><span class="sxs-lookup"><span data-stu-id="bd96e-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="bd96e-116">È necessario conoscere il sottodominio del tenant, che verrà usato nel segnaposto **{{subdomain}}**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="bd96e-117">Questo articolo userà il segnaposto **{{SiteUrl}}** per l' *URL* del sito o della pagina che hai scelto.</span><span class="sxs-lookup"><span data-stu-id="bd96e-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="bd96e-118">*URL*di esempio https://contoso.sharepoint.com/teams/Contoso: *oppure*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="bd96e-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="bd96e-119">Inoltre, **{{sitePath}}** verrà usato per indicare il *percorso* dell'URL (es:/teams/contoso).</span><span class="sxs-lookup"><span data-stu-id="bd96e-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="bd96e-120">*Percorsi*di esempio:/teams/Contoso *o* /sites/contoso</span><span class="sxs-lookup"><span data-stu-id="bd96e-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="bd96e-121">Iniziare seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bd96e-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="bd96e-122">Accedere allo store teams.</span><span class="sxs-lookup"><span data-stu-id="bd96e-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="bd96e-123">Installare o aprire App Studio.</span><span class="sxs-lookup"><span data-stu-id="bd96e-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="bd96e-124">Fare clic su **Apri**, accanto all'opzione app.</span><span class="sxs-lookup"><span data-stu-id="bd96e-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="bd96e-125">Con App Studio aperto, fare clic su **editor manifesto**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="bd96e-126">**Creare una nuova app**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-126">**Create a new app**.</span></span>

6. <span data-ttu-id="bd96e-127">Compilare tutti i **Dettagli dell'app**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="bd96e-128">Fare clic su **schede** in funzionalità.</span><span class="sxs-lookup"><span data-stu-id="bd96e-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="bd96e-129">Fare clic su **Aggiungi** in scheda personale.</span><span class="sxs-lookup"><span data-stu-id="bd96e-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="bd96e-130">Immettere il **nome** e scegliere **un nuovo ID entità univoco**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="bd96e-131">Inserire il **contenturl e l'URL del sito Web**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="bd96e-132">**contentUrl**: {{SiteUrl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="bd96e-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="bd96e-133">**web'iteUrl**: {{siteurl}}'' esempio **contenturl**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="bd96e-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="bd96e-134">Passare a **Domains e Permissi'ns**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="bd96e-135">Verificare che la sezione domini validi contenga il nome di dominio di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bd96e-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="bd96e-136">'' Esempio: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="bd96e-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="bd96e-137">Aggiungere le seguenti proprietà **Single Sign-on per** l'app Web:'' esempio:''''' **ID applicazione AAD**: **URL della risorsa**00000003-0000-0FF1-CE00-000000000000: {{subdomain}}. SharePoint. ![com '''''' web app Single Sign-on, con ID e URL.](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="bd96e-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="bd96e-138">**Salvare** queste proprietà e quindi passare a **test e Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="bd96e-139">Installa l'app per testare personalmente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bd96e-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd96e-140">Se non usi teams App Studio, dovrai. zippare il manifesto. File JSON appena creato, passare all'App Store in teams e fare clic su **upload Custom app** link (nell'angolo in basso a destra dell'app Store).</span><span class="sxs-lookup"><span data-stu-id="bd96e-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="bd96e-141">In questo modo l'app potrà essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="bd96e-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="bd96e-142">Ora l'app è disponibile come scheda statica da caricare e visualizzare in teams.</span><span class="sxs-lookup"><span data-stu-id="bd96e-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="bd96e-143">Testare e visualizzare la nuova scheda statica</span><span class="sxs-lookup"><span data-stu-id="bd96e-143">Test and view your new static tab</span></span>

<span data-ttu-id="bd96e-144">Per visualizzare la nuova scheda del desktop teams, passare ai puntini di sospensione (**...**) sul lato sinistro della barra dell'app.</span><span class="sxs-lookup"><span data-stu-id="bd96e-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="bd96e-145">Trova la tua nuova app, caricala e prova l'applicazione autonoma in teams.</span><span class="sxs-lookup"><span data-stu-id="bd96e-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="bd96e-146">Se vuoi rendere disponibile la nuova app nel menu a sinistra in una posizione più alta, devi usare un'impostazione di criteri per le app.</span><span class="sxs-lookup"><span data-stu-id="bd96e-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="bd96e-147">Questa impostazione è disponibile nella sezione amministrazione del team > criteri delle app > aggiungere un'applicazione bloccata.</span><span class="sxs-lookup"><span data-stu-id="bd96e-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="bd96e-148">Quando si assegna il criterio a un utente per il test, la modifica verrà visualizzata 24 ore più tardi.</span><span class="sxs-lookup"><span data-stu-id="bd96e-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="bd96e-149">Tenendo presente questo aspetto, decidi dove inserire l'app prima di tutto per evitare ritardi.</span><span class="sxs-lookup"><span data-stu-id="bd96e-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="bd96e-150">Per visualizzare e testare la nuova app in un dispositivo mobile, aprire il cassetto dell'app toccando la freccia (**^**) sopra la barra delle schede nella parte inferiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="bd96e-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="bd96e-151">Trova la tua app e passala nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="bd96e-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="bd96e-152">Il supporto per dispositivi mobili è attualmente in anteprima per sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="bd96e-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="bd96e-153">Per abilitare l'anteprima dello sviluppatore, passare a impostazioni > informazioni e quindi abilitare la modalità anteprima sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="bd96e-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="bd96e-154">File manifest. JSON di esempio</span><span class="sxs-lookup"><span data-stu-id="bd96e-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="bd96e-155">Il file OCS che si genera avrà un aspetto simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="bd96e-155">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso" 

    },                     
                        
    "des    ription": {                 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 
''
    "staticTabs": [ 

        { 
                                       
                     "       nti        Id":       "com    unicat    onSi    eTab", 
                                       
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