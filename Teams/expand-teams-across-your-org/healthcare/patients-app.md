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
description: Informazioni sull'integrazione di Electronic Healthcare Records nell'app Microsoft Teams Patients con le API FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096210"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="370d2-103">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="370d2-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="370d2-104">A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span><span class="sxs-lookup"><span data-stu-id="370d2-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="370d2-105">I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team.</span><span class="sxs-lookup"><span data-stu-id="370d2-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="370d2-106">Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="370d2-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="370d2-107">Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="370d2-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="370d2-108">Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="370d2-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="370d2-109">Estrai il modello Coordinamento pazienti in Elenchi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="370d2-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="370d2-110">Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="370d2-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="370d2-111">Questo articolo è destinato a uno sviluppatore IT sanitario generale interessato all'uso delle API FHIR in cima a un sistema di informazioni mediche per connettersi a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="370d2-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="370d2-112">In questo modo si consentirebbe scenari di coordinamento dell'assistenza che soddisfano le esigenze di un'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="370d2-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="370d2-113">Gli articoli collegati documentano le specifiche dell'interfaccia FHIR per l'app Pazienti di Microsoft Teams e le sezioni seguenti spiegano cosa è necessario per configurare un server FHIR e connettersi all'app Pazienti nell'ambiente di sviluppo o nel tenant.</span><span class="sxs-lookup"><span data-stu-id="370d2-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="370d2-114">Sarà inoltre necessario avere familiarità con la documentazione del server FHIR scelto, che deve essere una delle opzioni supportate:</span><span class="sxs-lookup"><span data-stu-id="370d2-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="370d2-115">Datica (tramite [l'offerta CMI)](https://datica.com/compliant-managed-integration/)</span><span class="sxs-lookup"><span data-stu-id="370d2-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="370d2-116">Infor Cloverleaf (attraverso il [Ponte Infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="370d2-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="370d2-117">Ripeti (tramite il [server R^FHIR)](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="370d2-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="370d2-118">Dapasoft (tramite [Corolar su FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="370d2-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="370d2-119">Questo processo non include i passaggi che usano l'interfaccia di amministrazione di Microsoft Teams o i cmdlet di PowerShell per abilitare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="370d2-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="370d2-120">La configurazione viene eseguita interamente sul lato server/servizio FHIR e nel client dell'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="370d2-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="370d2-121">Di seguito è illustrata l'architettura dell'app Pazienti:</span><span class="sxs-lookup"><span data-stu-id="370d2-121">Illustrated below is the architecture of the Patients app:</span></span>

![Diagramma dell'architettura dell'app Pazienti](../../media/patients-app-architecture.png)

<span data-ttu-id="370d2-123">Le sezioni seguenti illustrano i requisiti del livello di accesso ai dati FHIR-only per l'app Patients che un server FHIR (o API FHIR abilitate per EHR) deve soddisfare per potersi integrare con l'app Patients, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="370d2-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="370d2-124">Aspettative per l'autenticazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="370d2-124">Expectations around user authentication</span></span>
- <span data-ttu-id="370d2-125">Requisiti funzionali e tecnici dell'interfaccia di integrazione</span><span class="sxs-lookup"><span data-stu-id="370d2-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="370d2-126">Aspettative relative a prestazioni e affidabilità</span><span class="sxs-lookup"><span data-stu-id="370d2-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="370d2-127">Aspettative relative alle risorse FHIR supportate per l'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="370d2-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="370d2-128">Processo di integrazione e modello di coinvolgimento previsto</span><span class="sxs-lookup"><span data-stu-id="370d2-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="370d2-129">Come iniziare a usare FHIR e alcune sfide comuni affrontate con l'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="370d2-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="370d2-130">Requisiti futuri per la prossima iterazione dell'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="370d2-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="370d2-131">Nelle sezioni seguenti la parola "partner" o "partner di interoperabilità" viene usata per fare riferimento a qualsiasi organizzazione di terze parti che consente l'integrazione nei sistemi EHR per l'app Patients tramite FHIR e sta implementando un server FHIR in base alle specifiche elencate.</span><span class="sxs-lookup"><span data-stu-id="370d2-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="370d2-132">Requisiti funzionali e tecnici</span><span class="sxs-lookup"><span data-stu-id="370d2-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="370d2-133">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="370d2-133">Authentication</span></span>  

<span data-ttu-id="370d2-134">L'autorizzazione  a livello di app senza supporto per l'autorizzazione a livello di utente è il modo più comunemente supportato per eseguire trasformazioni dei dati ed esporre le connessioni ai dati EHR tramite FHIR, anche se il sistema EHR potrebbe implementare l'autorizzazione a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="370d2-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="370d2-135">Il servizio di interoperabilità (partner) ottiene l'accesso elevato ai dati EHR e, quando espongono gli stessi dati delle risorse FHIR appropriate, non viene passato alcun contesto di autorizzazione all'interop service consumer (l'app Patients) che si integra con il servizio di interoperabilità o la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="370d2-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="370d2-136">L'app Pazienti non sarà in grado di applicare l'autorizzazione a livello di utente, ma supporta l'autenticazione applicazione-applicazione tra l'app Pazienti e il servizio del partner Interop.</span><span class="sxs-lookup"><span data-stu-id="370d2-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="370d2-137">Il modello di autenticazione applicazione-applicazione è descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="370d2-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="370d2-138">L'autenticazione da servizio a servizio deve essere eseguita tramite il flusso delle credenziali [client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)di OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="370d2-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="370d2-139">Il servizio partner deve fornire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="370d2-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="370d2-140">Il servizio partner consente all'app Pazienti di creare un account con il partner, che consente all'app Pazienti di generare e gestire client_id e client_secret, gestiti tramite un portale di registrazione dell'autenticazione sul server di autenticazione del partner.</span><span class="sxs-lookup"><span data-stu-id="370d2-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="370d2-141">Il servizio partner è proprietario del sistema di autenticazione/autorizzazione, che accetta e verifica (autentica) le credenziali del client fornite e restituisce un token di accesso con l'hint del tenant nell'ambito, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="370d2-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="370d2-142">Per motivi di sicurezza o in caso di violazione segreta, l'app Pazienti può generare di nuovo il segreto ed invalidare o eliminare il vecchio segreto (esempio dello stesso è disponibile nel portale di Azure - Registrazione dell'app AAD).</span><span class="sxs-lookup"><span data-stu-id="370d2-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="370d2-143">L'endpoint dei metadati che ospita l'istruzione di conformità deve essere non autenticato, dovrebbe essere accessibile senza token di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="370d2-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="370d2-144">Il servizio partner fornisce l'endpoint del token per l'app Pazienti per richiedere un token di accesso usando un flusso di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="370d2-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="370d2-145">L'URL del token in base al server di autorizzazione deve far parte dell'istruzione di conformità (capacità) FHIR recuperata dai metadati nel server FHIR, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="370d2-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

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

<span data-ttu-id="370d2-146">Una richiesta per un token di accesso è costituita dai parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="370d2-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="370d2-147">Il servizio per i partner fornisce client_id e client_secret per pazienti, gestita tramite un portale di registrazione Auth sul lato del partner.</span><span class="sxs-lookup"><span data-stu-id="370d2-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="370d2-148">Il servizio partner fornisce l'endpoint per richiedere il token di accesso usando un flusso di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="370d2-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="370d2-149">Una risposta corretta deve includere i parametri token_type, access_token e expires_in.</span><span class="sxs-lookup"><span data-stu-id="370d2-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="370d2-150">Routing: mapping del tenant AAD all'endpoint provider</span><span class="sxs-lookup"><span data-stu-id="370d2-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="370d2-151">L'app Pazienti si connette a un servizio partner tramite un singolo endpoint.</span><span class="sxs-lookup"><span data-stu-id="370d2-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="370d2-152">Il servizio partner è proprietario e gestisce un meccanismo per eseguire il mapping di ogni cliente Microsoft (ID tenant AAD) a un rispettivo provider sanitario (server FHIR) con cui il servizio partner sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="370d2-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="370d2-153">Il mapping del tenant AAD a un endpoint provider usa l'ID tenant AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="370d2-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="370d2-154">L'app Pazienti passa l'ID tenant nell'ambito, richiedendo un token di accesso per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="370d2-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="370d2-155">Il servizio partner mantiene il mapping dell'ID tenant all'endpoint provider e reindirizza le richieste a un endpoint provider in base all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="370d2-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="370d2-156">A questo scopo, il partner supporta la configurazione alla fine (manualmente o tramite un portale nell'ambito dell'onboarding delle organizzazioni provider alla propria piattaforma di interoperabilità).</span><span class="sxs-lookup"><span data-stu-id="370d2-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="370d2-157">Il flusso di lavoro Autenticazione e routing è illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="370d2-157">The Authentication and Routing workflow is shown below:</span></span>

![Diagramma del flusso di lavoro Autenticazione e routing](../../media/Patient-app-6.png)

1. <span data-ttu-id="370d2-159">Richiedi token di accesso all'app inviando:</span><span class="sxs-lookup"><span data-stu-id="370d2-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="370d2-160">Rispondere con un token dell'app:</span><span class="sxs-lookup"><span data-stu-id="370d2-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="370d2-161">Richiedere dati protetti con il token di accesso.</span><span class="sxs-lookup"><span data-stu-id="370d2-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="370d2-162">Messaggio di autorizzazione: selezionare il server FHIR appropriato a cui eseguire il routing dall'ID tenant nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="370d2-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="370d2-163">Invia i dati protetti dall'app dal server FHIR autorizzato dopo l'autenticazione con il token dell'app.</span><span class="sxs-lookup"><span data-stu-id="370d2-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="370d2-164">Interfacce</span><span class="sxs-lookup"><span data-stu-id="370d2-164">Interfaces</span></span>

<span data-ttu-id="370d2-165">Le chiamate e i campi specifici usati dall'app Pazienti sono documentati negli articoli seguenti.</span><span class="sxs-lookup"><span data-stu-id="370d2-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="370d2-166">Selezionare l'interfaccia applicabile alle API FHIR server/FHIR.</span><span class="sxs-lookup"><span data-stu-id="370d2-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="370d2-167">Specifica dell'interfaccia DSTU2</span><span class="sxs-lookup"><span data-stu-id="370d2-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="370d2-168">Specifica dell'interfaccia STU3</span><span class="sxs-lookup"><span data-stu-id="370d2-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="370d2-169">Prestazioni e affidabilità</span><span class="sxs-lookup"><span data-stu-id="370d2-169">Performance and Reliability</span></span>

<span data-ttu-id="370d2-170">Mentre l'app Pazienti è in anteprima privata, non ci sono garanzie sulle prestazioni end-to-end.</span><span class="sxs-lookup"><span data-stu-id="370d2-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="370d2-171">I fattori relativi alle prestazioni includono le latenze relative di tutti i hop coinvolti nel flusso di lavoro, a partire dall'EHR nell'ambiente del sistema sanitario, al partner Interop e alla relativa infrastruttura, tra cui il server FHIR e l'ecosistema di Office 365 e l'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="370d2-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Illustrazione delle prestazioni dei partner di interoperabilità](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="370d2-173">Introduzione a FHIR</span><span class="sxs-lookup"><span data-stu-id="370d2-173">Get started with FHIR</span></span>  

<span data-ttu-id="370d2-174">Se non si ha la prima versione di FHIR e si ha bisogno di un facile accesso a un server FHIR che è possibile esporre all'interfaccia di integrazione di Microsoft Teams EHR, Microsoft ha un server FHIR open source disponibile per tutti gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="370d2-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="370d2-175">Vedere [l'articolo Che cos'è FHIR Server per Azure](/azure/healthcare-apis/overview-open-source-server) per altre informazioni sul server FHIR open source disponibile da Microsoft e distribuirlo per le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="370d2-175">Please see the [What is FHIR Server for Azure](/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="370d2-176">È anche possibile usare l'ambiente HSPC Open sandbox EHR per creare un EHR che supporta anche un server FHIR aperto e usarlo per giocare con l'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="370d2-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="370d2-177">È consigliabile leggere la documentazione relativa alla [sandbox HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)</span><span class="sxs-lookup"><span data-stu-id="370d2-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="370d2-178">La sandbox non solo offre un modo semplice, orientato all'interfaccia utente e facile da usare per creare, aggiungere e modificare pazienti, ma offre anche diversi esempi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="370d2-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>