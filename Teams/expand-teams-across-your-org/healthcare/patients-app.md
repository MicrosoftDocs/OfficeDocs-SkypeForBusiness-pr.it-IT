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
ms.openlocfilehash: c80560cb0df48d5c95cf5db2e7bed14a2e0f047d
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772247"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integrare cartelle cliniche elettroniche in Microsoft Teams

> [!NOTE]
> Efficace il 30 ottobre 2020, l'app patients è stata ritirata e sostituita dall' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams. Con gli elenchi, i team di assistenza nell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team per il monitoraggio generale dei pazienti. Vedere il modello di pazienti in elenchi per iniziare. Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md)

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Questo articolo è destinato a uno sviluppatore di servizi sanitari generale interessato all'uso di API FHIR su un sistema di informazioni mediche per la connessione a Microsoft teams. Questo consentirebbe agli scenari di coordinamento delle cure che soddisfano le esigenze di un'organizzazione sanitaria.

Gli articoli collegati documentano le specifiche dell'interfaccia FHIR per l'app Microsoft teams patients e le sezioni seguenti spiegano cosa è necessario per configurare un server FHIR e la connessione all'app patients nell'ambiente di sviluppo o nel tenant. Dovrai anche avere familiarità con la documentazione del server FHIR che hai scelto, che deve essere una delle opzioni supportate:

- Datica (tramite l'offerta [CMI](https://datica.com/compliant-managed-integration/) )
- Infor Cloverleaf (tramite il [Bridge infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (tramite il [Server R ^ FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (tramite [corolar in FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Questo processo non include passaggi che usano l'interfaccia di amministrazione di Microsoft teams o i cmdlet di PowerShell per abilitare le caratteristiche. La configurazione viene eseguita completamente sul lato server/servizio di FHIR e nel client dell'app pazienti.

Di seguito è illustrata l'architettura dell'app patients:

![Diagramma dell'architettura dell'app patients](../../media/patients-app-architecture.png)

Le sezioni seguenti illustrano i requisiti del livello di accesso ai dati di FHIR-only per l'app patients che deve soddisfare un server FHIR (o EHR Enabled FHIR API) per l'integrazione con l'app patients, inclusi i seguenti:

- Aspettative intorno all'autenticazione utente
- Requisiti funzionali e tecnici dell'interfaccia di integrazione
- Aspettative intorno alle prestazioni e all'affidabilità
- Aspettative intorno alle risorse di FHIR da supportare per l'app pazienti
- Processo per l'integrazione e il modello di impegno previsto
- Come iniziare a usare FHIR e alcune sfide comuni affrontate con l'app patients
- Requisiti futuri per l'iterazione successiva dell'app patients

> [!NOTE]
> Nelle sezioni seguenti viene usato il termine "partner" o "partner di interoperabilità" per fare riferimento a qualsiasi organizzazione di terze parti che consente l'integrazione nei sistemi EHR per l'app patients tramite FHIR e sta implementando un server FHIR in modo che corrisponda alle specifiche elencate.

## <a name="functional-and-technical-requirements"></a>Requisiti funzionali e tecnici  

### <a name="authentication"></a>Autenticazione  

L'autorizzazione a livello di app *senza supporto per l'autorizzazione a livello utente* è il modo più comune per eseguire trasformazioni dei dati ed esporre le connessioni ai dati di EHR tramite FHIR, anche se il sistema EHR potrebbe implementare l'autorizzazione a livello di utente. Il servizio di interoperabilità (partner) Ottiene l'accesso elevato ai dati di EHR e quando espongono gli stessi dati delle risorse FHIR appropriate non esiste alcun contesto di autorizzazione passato al consumer del servizio di interoperabilità (l'app patients) che si integra con il servizio o la piattaforma di interoperabilità. L'app patients non sarà in grado di applicare l'autorizzazione a livello di utente, ma supporta l'applicazione per l'autenticazione delle applicazioni tra l'app patients e il servizio del partner di interoperabilità.

Il modello di autenticazione dell'applicazione per l'applicazione è descritto di seguito:

Il servizio per l'autenticazione del servizio deve essere eseguito tramite il [flusso di credenziali client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2,0. Il servizio partner deve specificare quanto segue:

1. Il servizio partner consente all'app patients di creare un account con il partner, che consente all'app patients di generare e possedere client_id e client_secret, gestito tramite un portale di registrazione auth nel server di autenticazione del partner.

2. Il servizio partner è proprietario del sistema di autenticazione/autorizzazione, che accetta e verifica (autentica) le credenziali del client fornite e restituisce un token di accesso con il suggerimento del tenant nell'ambito, come descritto di seguito.

3. Per motivi di sicurezza o in caso di violazione segreta, l'app patients può rigenerare il segreto e invalidare o eliminare il vecchio segreto (l'esempio è disponibile nella registrazione di un'app di Azure Portal-AAD).

4. L'endpoint dei metadati che ospita l'istruzione di conformità deve essere non autenticato, ma dovrebbe essere accessibile senza il token di autenticazione.

5. Il servizio partner fornisce l'endpoint del token per l'app patients per richiedere un token di accesso usando un flusso di credenziali client. L'URL del token come per il server di autorizzazione deve far parte dell'istruzione di conformità FHIR (funzionalità) recuperata dai metadati nel server FHIR, come in questo esempio:

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

Una richiesta di un token di accesso è costituita dai parametri seguenti:

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

Il servizio partner offre la client_id e client_secret per l'app patients, gestita tramite un portale di registrazione auth sul lato del partner. Il servizio partner fornisce l'endpoint per richiedere il token di accesso usando un flusso di credenziali client. Una risposta corretta deve includere i parametri token_type, access_token e expires_in.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routing: mapping del tenant di AAD all'endpoint del provider

L'app patients si connette a un servizio partner tramite un singolo endpoint. Il servizio partner è proprietario e gestisce un meccanismo per eseguire il mapping di ogni cliente Microsoft (ID tenant di AAD) a un provider di servizi sanitari (FHIR Server) con cui il servizio partner sta lavorando.

Il mapping del tenant di AAD a un endpoint del provider usa l'ID tenant di AAD (GUID). L'app patients passa l'ID tenant nell'ambito, mentre richiede un token di accesso per ogni richiesta. Il servizio partner mantiene il mapping dell'ID tenant all'endpoint del provider e reindirizza le richieste a un endpoint del provider in base all'ID tenant. A questo scopo, il partner supporta la configurazione alla fine (manualmente o tramite un portale come parte dell'onboarding delle organizzazioni di provider alla propria piattaforma di interoperabilità).

Il flusso di lavoro di autenticazione e routing è illustrato di seguito:

![Diagramma del flusso di lavoro di autenticazione e routing](../../media/Patient-app-6.png)

1. Richiedi il token di accesso all'app inviando:
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. Rispondere con un token dell'app:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Richiedi dati protetti con il token di accesso.

4. Messaggio di autorizzazione: selezionare il server di FHIR appropriato da instradare dall'ID tenant nell'ambito.

5. Invia i dati protetti dall'app dal server FHIR autorizzato dopo l'autenticazione con il token dell'app.

## <a name="interfaces"></a>Interfacce

Le chiamate e i campi specifici usati dall'app patients sono documentati negli articoli seguenti. Selezionare l'interfaccia applicabile alle API di FHIR server/FHIR.

- [Specifica dell'interfaccia DSTU2](dstu2-interface.md)
- [Specifica dell'interfaccia STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Prestazioni e affidabilità

Mentre l'app patients è in anteprima privata, non ci sono garanzie sulle prestazioni end-to-end. I fattori relativi alle prestazioni includono la latenza relativa di tutti i luppoli coinvolti nel flusso di lavoro, a partire dalla EHR nell'ambiente del sistema sanitario, al partner di interoperabilità e ai loro infra, incluso il server FHIR, oltre all'app ecosistemi e pazienti di Office 365.

![Esempio di prestazioni di interoperabilità partner](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Introduzione a FHIR  

Se non si ha familiarità con FHIR e si ha bisogno di un facile accesso a un server FHIR che può essere esposto all'interfaccia di integrazione di Microsoft teams EHR, Microsoft ha un server di FHIR Open-Source disponibile per tutti gli sviluppatori. Vedere l'articolo su [FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) per altre informazioni sul server open source FHIR disponibile da Microsoft e distribuirlo per le organizzazioni.

Puoi anche usare l'ambiente HSPC Open sandbox EHR per creare un EHR che supporti anche un server FHIR aperto e usarlo per giocare con l'app pazienti. È consigliabile leggere la [documentazione della sandbox di HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox). La sandbox non solo offre un modo semplice, orientato all'interfaccia utente e facile da usare per creare, aggiungere e modificare i pazienti, ma offre anche diversi esempi per iniziare. 
