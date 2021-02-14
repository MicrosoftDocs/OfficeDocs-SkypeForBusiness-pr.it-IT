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
description: Informazioni sull'integrazione di record sanitari elettronici nell'app Pazienti di Microsoft Teams con le API FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803544"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="30e5a-103">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30e5a-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="30e5a-104">A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span><span class="sxs-lookup"><span data-stu-id="30e5a-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="30e5a-105">I dati dell'app Pazienti vengono archiviati nella cassetta postale del gruppo di Office 365 che backup il team.</span><span class="sxs-lookup"><span data-stu-id="30e5a-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="30e5a-106">Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non sono più accessibili tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="30e5a-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="30e5a-107">Gli utenti possono creare di nuovo i propri elenchi usando [l'app Elenchi.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="30e5a-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="30e5a-108">Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="30e5a-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="30e5a-109">Per iniziare, vedere il modello Pazienti in Elenchi.</span><span class="sxs-lookup"><span data-stu-id="30e5a-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="30e5a-110">Per altre informazioni su come gestire l'app Elenchi nell'organizzazione, vedere [Gestire l'app Elenchi.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="30e5a-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="30e5a-111">Questo articolo è destinato a uno sviluppatore IT sanitario generale interessato a usare le API FHIR sopra un sistema di informazioni mediche per connettersi a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="30e5a-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="30e5a-112">In questo modo si consentirerebbero scenari di coordinamento delle cure che corrispondano alle esigenze di un'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="30e5a-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="30e5a-113">Gli articoli collegati documentano le specifiche dell'interfaccia FHIR per l'app Pazienti di Microsoft Teams e le sezioni seguenti spiegano cosa è necessario per configurare un server FHIR e connettersi all'app Pazienti nell'ambiente di sviluppo o nel tenant.</span><span class="sxs-lookup"><span data-stu-id="30e5a-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="30e5a-114">È anche necessario conoscere la documentazione del server FHIR scelto, che deve essere una delle opzioni supportate:</span><span class="sxs-lookup"><span data-stu-id="30e5a-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="30e5a-115">Datica (tramite [l'offerta di CMI)](https://datica.com/compliant-managed-integration/)</span><span class="sxs-lookup"><span data-stu-id="30e5a-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="30e5a-116">Infor Cloverleaf (attraverso il [bridge di Infor FHIR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="30e5a-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="30e5a-117">Redox (tramite il [server R^FHIR)](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="30e5a-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="30e5a-118">Dapasoft (tramite [Lopelar su FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="30e5a-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="30e5a-119">Questo processo non include i passaggi che usano l'interfaccia di amministrazione di Microsoft Teams o i cmdlet di PowerShell per abilitare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="30e5a-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="30e5a-120">La configurazione viene interamente eseguita sul lato server/servizio FHIR e nel client dell'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="30e5a-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="30e5a-121">Di seguito è illustrata l'architettura dell'app Pazienti:</span><span class="sxs-lookup"><span data-stu-id="30e5a-121">Illustrated below is the architecture of the Patients app:</span></span>

![Diagramma dell'architettura dell'app Pazienti](../../media/patients-app-architecture.png)

<span data-ttu-id="30e5a-123">Le sezioni seguenti illustrano i requisiti del livello di accesso ai dati FHIR per l'app Pazienti che un server FHIR (o API FHIR abilitate per EHR) deve soddisfare per l'integrazione con l'app Pazienti, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="30e5a-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="30e5a-124">Aspettative per l'autenticazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="30e5a-124">Expectations around user authentication</span></span>
- <span data-ttu-id="30e5a-125">Requisiti funzionali e tecnici dell'interfaccia di integrazione</span><span class="sxs-lookup"><span data-stu-id="30e5a-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="30e5a-126">Aspettative relative a prestazioni e affidabilità</span><span class="sxs-lookup"><span data-stu-id="30e5a-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="30e5a-127">Aspettative circa le risorse FHIR supportate per l'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="30e5a-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="30e5a-128">Processo di integrazione e modello di impegno previsto</span><span class="sxs-lookup"><span data-stu-id="30e5a-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="30e5a-129">Come iniziare a usare FHIR e affrontare alcune sfide comuni con l'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="30e5a-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="30e5a-130">Requisiti futuri per l'iterazione successiva dell'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="30e5a-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="30e5a-131">Nelle sezioni seguenti la parola "partner" o "partner di interoperabilità" viene usata per fare riferimento a un'organizzazione di terze parti che consente l'integrazione ai sistemi EHR per l'app Pazienti tramite FHIR e sta implementando un server FHIR in linea con le specifiche elencate.</span><span class="sxs-lookup"><span data-stu-id="30e5a-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="30e5a-132">Requisiti funzionali e tecnici</span><span class="sxs-lookup"><span data-stu-id="30e5a-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="30e5a-133">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="30e5a-133">Authentication</span></span>  

<span data-ttu-id="30e5a-134">L'autorizzazione  a livello di app senza supporto per l'autorizzazione a livello utente è il modo più comunemente supportato per eseguire trasformazioni di dati ed esporre connessioni ai dati EHR tramite FHIR, anche se il sistema EHR potrebbe implementare l'autorizzazione a livello utente.</span><span class="sxs-lookup"><span data-stu-id="30e5a-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="30e5a-135">Il servizio di interoperabilità (Partner) ottiene un accesso elevato ai dati EHR e quando espongono gli stessi dati delle risorse FHIR appropriate non è passato un contesto di autorizzazione al consumer del servizio di interoperabilità (l'app Pazienti) che integra il servizio di interoperabilità o la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="30e5a-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="30e5a-136">L'app Pazienti non sarà in grado di applicare l'autorizzazione a livello utente, ma supporta l'autenticazione da applicazione a applicazione tra l'app Pazienti e il servizio del partner di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="30e5a-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="30e5a-137">Di seguito è descritto il modello di autenticazione applicazione-applicazione:</span><span class="sxs-lookup"><span data-stu-id="30e5a-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="30e5a-138">L'autenticazione da servizio a servizio deve essere eseguita tramite il flusso delle credenziali [client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)di OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="30e5a-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="30e5a-139">Il servizio partner deve fornire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="30e5a-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="30e5a-140">Il servizio partner consente all'app Pazienti di creare un account con il Partner, che consente all'app Pazienti di generare e proprietà di client_id e client_secret, gestiti tramite un portale di registrazione di autenticazione sul server di autenticazione del partner.</span><span class="sxs-lookup"><span data-stu-id="30e5a-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="30e5a-141">Il servizio partner è proprietario del sistema di autenticazione/autorizzazione, che accetta e verifica (autentica) le credenziali del client fornite e restituisce un token di accesso con un suggerimento per il tenant nell'ambito, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="30e5a-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="30e5a-142">Per motivi di sicurezza o in caso di violazione segreta, l'app Pazienti può generare nuovamente il segreto e invalidare o eliminare il vecchio segreto (esempio dello stesso è disponibile nel portale di Azure - Registrazione dell'app AAD).</span><span class="sxs-lookup"><span data-stu-id="30e5a-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="30e5a-143">L'endpoint dei metadati che ospita l'istruzione di conformità deve essere non autenticato, deve essere accessibile senza token di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="30e5a-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="30e5a-144">Il servizio partner fornisce l'endpoint token per l'app Pazienti per richiedere un token di accesso usando un flusso di credenziali del client.</span><span class="sxs-lookup"><span data-stu-id="30e5a-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="30e5a-145">L'URL del token come da server di autorizzazione deve fare parte dell'istruzione di conformità (capacità) FHIR recuperata dai metadati sul server FHIR, come in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="30e5a-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

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

<span data-ttu-id="30e5a-146">Una richiesta per un token di accesso è costituita dai parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="30e5a-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="30e5a-147">Il servizio partner fornisce client_id e client_secret per pazienti, gestite tramite un portale di registrazione Auth a lato del partner.</span><span class="sxs-lookup"><span data-stu-id="30e5a-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="30e5a-148">Il servizio partner fornisce l'endpoint per richiedere il token di accesso usando un flusso di credenziali del client.</span><span class="sxs-lookup"><span data-stu-id="30e5a-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="30e5a-149">Una risposta corretta deve includere i parametri token_type, access_token e expires_in risposta.</span><span class="sxs-lookup"><span data-stu-id="30e5a-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="30e5a-150">Routing: mapping del tenant AAD all'endpoint provider</span><span class="sxs-lookup"><span data-stu-id="30e5a-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="30e5a-151">L'app Pazienti si connette a un servizio partner tramite un singolo endpoint.</span><span class="sxs-lookup"><span data-stu-id="30e5a-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="30e5a-152">Il servizio partner è proprietario e gestisce un meccanismo per associare ogni cliente Microsoft (ID tenant AAD) a un provider sanitario corrispondente (server FHIR) su cui lavora il servizio partner.</span><span class="sxs-lookup"><span data-stu-id="30e5a-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="30e5a-153">Il mapping del tenant AAD a un endpoint provider usa l'ID tenant AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="30e5a-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="30e5a-154">L'app Pazienti passa l'ID tenant nell'ambito, richiedendo un token di accesso per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="30e5a-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="30e5a-155">Il servizio partner mantiene il mapping dell'ID tenant all'endpoint del provider e reindirizza le richieste a un endpoint provider in base all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="30e5a-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="30e5a-156">A questo scopo, il partner supporta la configurazione completa (manualmente o tramite un portale come parte dell'onboarding delle organizzazioni provider alla piattaforma di interoperabilità).</span><span class="sxs-lookup"><span data-stu-id="30e5a-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="30e5a-157">Di seguito è illustrato il flusso di lavoro Autenticazione e routing:</span><span class="sxs-lookup"><span data-stu-id="30e5a-157">The Authentication and Routing workflow is shown below:</span></span>

![Diagramma del flusso di lavoro Autenticazione e routing](../../media/Patient-app-6.png)

1. <span data-ttu-id="30e5a-159">Richiedi token di accesso all'app inviando:</span><span class="sxs-lookup"><span data-stu-id="30e5a-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="30e5a-160">Rispondere con un token dell'app:</span><span class="sxs-lookup"><span data-stu-id="30e5a-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="30e5a-161">Richiedere dati protetti con token di accesso.</span><span class="sxs-lookup"><span data-stu-id="30e5a-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="30e5a-162">Messaggio di autorizzazione: selezionare il server FHIR appropriato a cui instradare dall'ID tenant nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="30e5a-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="30e5a-163">Invia i dati protetti dall'app dal server FHIR autorizzato dopo l'autenticazione con il token dell'app.</span><span class="sxs-lookup"><span data-stu-id="30e5a-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="30e5a-164">Interfacce</span><span class="sxs-lookup"><span data-stu-id="30e5a-164">Interfaces</span></span>

<span data-ttu-id="30e5a-165">Chiamate e campi specifici usati dall'app Pazienti sono documentati negli articoli seguenti.</span><span class="sxs-lookup"><span data-stu-id="30e5a-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="30e5a-166">Selezionare l'interfaccia applicabile alle API FHIR Server/FHIR.</span><span class="sxs-lookup"><span data-stu-id="30e5a-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="30e5a-167">Specifica dell'interfaccia DSTU2</span><span class="sxs-lookup"><span data-stu-id="30e5a-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="30e5a-168">Specifica dell'interfaccia STU3</span><span class="sxs-lookup"><span data-stu-id="30e5a-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="30e5a-169">Prestazioni e affidabilità</span><span class="sxs-lookup"><span data-stu-id="30e5a-169">Performance and Reliability</span></span>

<span data-ttu-id="30e5a-170">Mentre l'app Pazienti è in anteprima privata, non ci sono garanzie sulle prestazioni end-to-end.</span><span class="sxs-lookup"><span data-stu-id="30e5a-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="30e5a-171">I fattori che influiscono sulle prestazioni includono le latenze relative di tutti i passaggi coinvolti nel flusso di lavoro, a partire dall'EHR nell'ambiente del sistema sanitario, al partner di interoperabilità e alla loro infrastruttura, tra cui il server FHIR e fino all'ecosistema di Office 365 e all'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="30e5a-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Illustrazione delle prestazioni dei partner di interoperabilità](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="30e5a-173">Introduzione a FHIR</span><span class="sxs-lookup"><span data-stu-id="30e5a-173">Get started with FHIR</span></span>  

<span data-ttu-id="30e5a-174">Se non hai mai utilizzato FHIR e hai bisogno di un facile accesso a un server FHIR che puoi esporre all'interfaccia di integrazione di Microsoft Teams EHR, Microsoft ha un server FHIR open-source disponibile per l'uso da parte di tutti gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="30e5a-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="30e5a-175">Vedere l'articolo Che cos'è il [server FHIR](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) per Azure per altre informazioni sul server FHIR open source disponibile da Microsoft e distribuirlo per le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="30e5a-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="30e5a-176">È anche possibile usare l'ambiente EHR sandbox HSPC Open per creare un EHR che supporta anche un server FHIR aperto e usarlo per giocare con l'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="30e5a-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="30e5a-177">È consigliabile consultare la documentazione relativa alla [sandbox HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)</span><span class="sxs-lookup"><span data-stu-id="30e5a-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="30e5a-178">La sandbox offre non solo un modo semplice, orientato all'interfaccia utente e semplice da usare per creare, aggiungere e modificare Pazienti, ma offre anche diversi esempi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="30e5a-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
