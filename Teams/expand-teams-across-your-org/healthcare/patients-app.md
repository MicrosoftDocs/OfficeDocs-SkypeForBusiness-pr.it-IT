---
title: Panoramica dell'app Pazienti
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informazioni su come integrare i record sanitari elettronici nell'app Microsoft teams patients usando le API FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803544"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="4d042-103">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d042-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="4d042-104">Efficace il 30 ottobre 2020, l'app patients è stata ritirata e sostituita dall' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams.</span><span class="sxs-lookup"><span data-stu-id="4d042-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="4d042-105">I dati dell'app patients sono archiviati nella cassetta postale del gruppo del gruppo Office 365 che appoggia il team.</span><span class="sxs-lookup"><span data-stu-id="4d042-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4d042-106">Tutti i dati associati all'app patients vengono mantenuti in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="4d042-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4d042-107">Gli utenti possono ricreare gli elenchi usando l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="4d042-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4d042-108">Con gli elenchi, i team di assistenza nell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team per il monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="4d042-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="4d042-109">Vedere il modello di pazienti in elenchi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="4d042-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="4d042-110">Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="4d042-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="4d042-111">Questo articolo è destinato a uno sviluppatore di servizi sanitari generale interessato all'uso di API FHIR su un sistema di informazioni mediche per la connessione a Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4d042-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="4d042-112">Questo consentirebbe agli scenari di coordinamento delle cure che soddisfano le esigenze di un'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="4d042-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="4d042-113">Gli articoli collegati documentano le specifiche dell'interfaccia FHIR per l'app Microsoft teams patients e le sezioni seguenti spiegano cosa è necessario per configurare un server FHIR e la connessione all'app patients nell'ambiente di sviluppo o nel tenant.</span><span class="sxs-lookup"><span data-stu-id="4d042-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="4d042-114">Dovrai anche avere familiarità con la documentazione del server FHIR che hai scelto, che deve essere una delle opzioni supportate:</span><span class="sxs-lookup"><span data-stu-id="4d042-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="4d042-115">Datica (tramite l'offerta [CMI](https://datica.com/compliant-managed-integration/) )</span><span class="sxs-lookup"><span data-stu-id="4d042-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="4d042-116">Infor Cloverleaf (tramite il [Bridge infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="4d042-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="4d042-117">Redox (tramite il [Server R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="4d042-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="4d042-118">Dapasoft (tramite [corolar in FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="4d042-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="4d042-119">Questo processo non include passaggi che usano l'interfaccia di amministrazione di Microsoft teams o i cmdlet di PowerShell per abilitare le caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="4d042-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="4d042-120">La configurazione viene eseguita completamente sul lato server/servizio di FHIR e nel client dell'app pazienti.</span><span class="sxs-lookup"><span data-stu-id="4d042-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="4d042-121">Di seguito è illustrata l'architettura dell'app patients:</span><span class="sxs-lookup"><span data-stu-id="4d042-121">Illustrated below is the architecture of the Patients app:</span></span>

![Diagramma dell'architettura dell'app patients](../../media/patients-app-architecture.png)

<span data-ttu-id="4d042-123">Le sezioni seguenti illustrano i requisiti del livello di accesso ai dati di FHIR-only per l'app patients che deve soddisfare un server FHIR (o EHR Enabled FHIR API) per l'integrazione con l'app patients, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d042-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="4d042-124">Aspettative intorno all'autenticazione utente</span><span class="sxs-lookup"><span data-stu-id="4d042-124">Expectations around user authentication</span></span>
- <span data-ttu-id="4d042-125">Requisiti funzionali e tecnici dell'interfaccia di integrazione</span><span class="sxs-lookup"><span data-stu-id="4d042-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="4d042-126">Aspettative intorno alle prestazioni e all'affidabilità</span><span class="sxs-lookup"><span data-stu-id="4d042-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="4d042-127">Aspettative intorno alle risorse di FHIR da supportare per l'app pazienti</span><span class="sxs-lookup"><span data-stu-id="4d042-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="4d042-128">Processo per l'integrazione e il modello di impegno previsto</span><span class="sxs-lookup"><span data-stu-id="4d042-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="4d042-129">Come iniziare a usare FHIR e alcune sfide comuni affrontate con l'app patients</span><span class="sxs-lookup"><span data-stu-id="4d042-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="4d042-130">Requisiti futuri per l'iterazione successiva dell'app patients</span><span class="sxs-lookup"><span data-stu-id="4d042-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="4d042-131">Nelle sezioni seguenti viene usato il termine "partner" o "partner di interoperabilità" per fare riferimento a qualsiasi organizzazione di terze parti che consente l'integrazione nei sistemi EHR per l'app patients tramite FHIR e sta implementando un server FHIR in modo che corrisponda alle specifiche elencate.</span><span class="sxs-lookup"><span data-stu-id="4d042-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="4d042-132">Requisiti funzionali e tecnici</span><span class="sxs-lookup"><span data-stu-id="4d042-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="4d042-133">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="4d042-133">Authentication</span></span>  

<span data-ttu-id="4d042-134">L'autorizzazione a livello di app *senza supporto per l'autorizzazione a livello utente* è il modo più comune per eseguire trasformazioni dei dati ed esporre le connessioni ai dati di EHR tramite FHIR, anche se il sistema EHR potrebbe implementare l'autorizzazione a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="4d042-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="4d042-135">Il servizio di interoperabilità (partner) Ottiene l'accesso elevato ai dati di EHR e quando espongono gli stessi dati delle risorse FHIR appropriate non esiste alcun contesto di autorizzazione passato al consumer del servizio di interoperabilità (l'app patients) che si integra con il servizio o la piattaforma di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="4d042-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="4d042-136">L'app patients non sarà in grado di applicare l'autorizzazione a livello di utente, ma supporta l'applicazione per l'autenticazione delle applicazioni tra l'app patients e il servizio del partner di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="4d042-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="4d042-137">Il modello di autenticazione dell'applicazione per l'applicazione è descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="4d042-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="4d042-138">Il servizio per l'autenticazione del servizio deve essere eseguito tramite il [flusso di credenziali client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2,0.</span><span class="sxs-lookup"><span data-stu-id="4d042-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="4d042-139">Il servizio partner deve specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4d042-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="4d042-140">Il servizio partner consente all'app patients di creare un account con il partner, che consente all'app patients di generare e possedere client_id e client_secret, gestito tramite un portale di registrazione auth nel server di autenticazione del partner.</span><span class="sxs-lookup"><span data-stu-id="4d042-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="4d042-141">Il servizio partner è proprietario del sistema di autenticazione/autorizzazione, che accetta e verifica (autentica) le credenziali del client fornite e restituisce un token di accesso con il suggerimento del tenant nell'ambito, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="4d042-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="4d042-142">Per motivi di sicurezza o in caso di violazione segreta, l'app patients può rigenerare il segreto e invalidare o eliminare il vecchio segreto (l'esempio è disponibile nella registrazione di un'app di Azure Portal-AAD).</span><span class="sxs-lookup"><span data-stu-id="4d042-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="4d042-143">L'endpoint dei metadati che ospita l'istruzione di conformità deve essere non autenticato, ma dovrebbe essere accessibile senza il token di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4d042-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="4d042-144">Il servizio partner fornisce l'endpoint del token per l'app patients per richiedere un token di accesso usando un flusso di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="4d042-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="4d042-145">L'URL del token come per il server di autorizzazione deve far parte dell'istruzione di conformità FHIR (funzionalità) recuperata dai metadati nel server FHIR, come in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="4d042-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="4d042-146">Una richiesta di un token di accesso è costituita dai parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d042-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="4d042-147">Il servizio partner offre la client_id e client_secret per l'app patients, gestita tramite un portale di registrazione auth sul lato del partner.</span><span class="sxs-lookup"><span data-stu-id="4d042-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="4d042-148">Il servizio partner fornisce l'endpoint per richiedere il token di accesso usando un flusso di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="4d042-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="4d042-149">Una risposta corretta deve includere i parametri token_type, access_token e expires_in.</span><span class="sxs-lookup"><span data-stu-id="4d042-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="4d042-150">Routing: mapping del tenant di AAD all'endpoint del provider</span><span class="sxs-lookup"><span data-stu-id="4d042-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="4d042-151">L'app patients si connette a un servizio partner tramite un singolo endpoint.</span><span class="sxs-lookup"><span data-stu-id="4d042-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="4d042-152">Il servizio partner è proprietario e gestisce un meccanismo per eseguire il mapping di ogni cliente Microsoft (ID tenant di AAD) a un provider di servizi sanitari (FHIR Server) con cui il servizio partner sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="4d042-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="4d042-153">Il mapping del tenant di AAD a un endpoint del provider usa l'ID tenant di AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="4d042-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="4d042-154">L'app patients passa l'ID tenant nell'ambito, mentre richiede un token di accesso per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="4d042-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="4d042-155">Il servizio partner mantiene il mapping dell'ID tenant all'endpoint del provider e reindirizza le richieste a un endpoint del provider in base all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="4d042-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="4d042-156">A questo scopo, il partner supporta la configurazione alla fine (manualmente o tramite un portale come parte dell'onboarding delle organizzazioni di provider alla propria piattaforma di interoperabilità).</span><span class="sxs-lookup"><span data-stu-id="4d042-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="4d042-157">Il flusso di lavoro di autenticazione e routing è illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4d042-157">The Authentication and Routing workflow is shown below:</span></span>

![Diagramma del flusso di lavoro di autenticazione e routing](../../media/Patient-app-6.png)

1. <span data-ttu-id="4d042-159">Richiedi il token di accesso all'app inviando:</span><span class="sxs-lookup"><span data-stu-id="4d042-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="4d042-160">Rispondere con un token dell'app:</span><span class="sxs-lookup"><span data-stu-id="4d042-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="4d042-161">Richiedi dati protetti con il token di accesso.</span><span class="sxs-lookup"><span data-stu-id="4d042-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="4d042-162">Messaggio di autorizzazione: selezionare il server di FHIR appropriato da instradare dall'ID tenant nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="4d042-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="4d042-163">Invia i dati protetti dall'app dal server FHIR autorizzato dopo l'autenticazione con il token dell'app.</span><span class="sxs-lookup"><span data-stu-id="4d042-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="4d042-164">Interfacce</span><span class="sxs-lookup"><span data-stu-id="4d042-164">Interfaces</span></span>

<span data-ttu-id="4d042-165">Le chiamate e i campi specifici usati dall'app patients sono documentati negli articoli seguenti.</span><span class="sxs-lookup"><span data-stu-id="4d042-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="4d042-166">Selezionare l'interfaccia applicabile alle API di FHIR server/FHIR.</span><span class="sxs-lookup"><span data-stu-id="4d042-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="4d042-167">Specifica dell'interfaccia DSTU2</span><span class="sxs-lookup"><span data-stu-id="4d042-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="4d042-168">Specifica dell'interfaccia STU3</span><span class="sxs-lookup"><span data-stu-id="4d042-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="4d042-169">Prestazioni e affidabilità</span><span class="sxs-lookup"><span data-stu-id="4d042-169">Performance and Reliability</span></span>

<span data-ttu-id="4d042-170">Mentre l'app patients è in anteprima privata, non ci sono garanzie sulle prestazioni end-to-end.</span><span class="sxs-lookup"><span data-stu-id="4d042-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="4d042-171">I fattori relativi alle prestazioni includono la latenza relativa di tutti i luppoli coinvolti nel flusso di lavoro, a partire dalla EHR nell'ambiente del sistema sanitario, al partner di interoperabilità e ai loro infra, incluso il server FHIR, oltre all'app ecosistemi e pazienti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d042-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Esempio di prestazioni di interoperabilità partner](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="4d042-173">Introduzione a FHIR</span><span class="sxs-lookup"><span data-stu-id="4d042-173">Get started with FHIR</span></span>  

<span data-ttu-id="4d042-174">Se non si ha familiarità con FHIR e si ha bisogno di un facile accesso a un server FHIR che può essere esposto all'interfaccia di integrazione di Microsoft teams EHR, Microsoft ha un server di FHIR Open-Source disponibile per tutti gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="4d042-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="4d042-175">Vedere l'articolo su [FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) per altre informazioni sul server open source FHIR disponibile da Microsoft e distribuirlo per le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4d042-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="4d042-176">Puoi anche usare l'ambiente HSPC Open sandbox EHR per creare un EHR che supporti anche un server FHIR aperto e usarlo per giocare con l'app pazienti.</span><span class="sxs-lookup"><span data-stu-id="4d042-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="4d042-177">È consigliabile leggere la [documentazione della sandbox di HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span><span class="sxs-lookup"><span data-stu-id="4d042-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="4d042-178">La sandbox non solo offre un modo semplice, orientato all'interfaccia utente e facile da usare per creare, aggiungere e modificare i pazienti, ma offre anche diversi esempi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="4d042-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
