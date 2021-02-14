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
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integrare cartelle cliniche elettroniche in Microsoft Teams

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell'app Pazienti vengono archiviati nella cassetta postale del gruppo di Office 365 che backup il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non sono più accessibili tramite l'interfaccia utente. Gli utenti possono creare di nuovo i propri elenchi usando [l'app Elenchi.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti. Per iniziare, vedere il modello Pazienti in Elenchi. Per altre informazioni su come gestire l'app Elenchi nell'organizzazione, vedere [Gestire l'app Elenchi.](../../manage-lists-app.md)

Questo articolo è destinato a uno sviluppatore IT sanitario generale interessato a usare le API FHIR sopra un sistema di informazioni mediche per connettersi a Microsoft Teams. In questo modo si consentirerebbero scenari di coordinamento delle cure che corrispondano alle esigenze di un'organizzazione sanitaria.

Gli articoli collegati documentano le specifiche dell'interfaccia FHIR per l'app Pazienti di Microsoft Teams e le sezioni seguenti spiegano cosa è necessario per configurare un server FHIR e connettersi all'app Pazienti nell'ambiente di sviluppo o nel tenant. È anche necessario conoscere la documentazione del server FHIR scelto, che deve essere una delle opzioni supportate:

- Datica (tramite [l'offerta di CMI)](https://datica.com/compliant-managed-integration/)
- Infor Cloverleaf (attraverso il [bridge di Infor FHIR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redox (tramite il [server R^FHIR)](https://www.redoxengine.com/fhir/)
- Dapasoft (tramite [Lopelar su FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Questo processo non include i passaggi che usano l'interfaccia di amministrazione di Microsoft Teams o i cmdlet di PowerShell per abilitare le funzionalità. La configurazione viene interamente eseguita sul lato server/servizio FHIR e nel client dell'app Pazienti.

Di seguito è illustrata l'architettura dell'app Pazienti:

![Diagramma dell'architettura dell'app Pazienti](../../media/patients-app-architecture.png)

Le sezioni seguenti illustrano i requisiti del livello di accesso ai dati FHIR per l'app Pazienti che un server FHIR (o API FHIR abilitate per EHR) deve soddisfare per l'integrazione con l'app Pazienti, inclusi i seguenti:

- Aspettative per l'autenticazione degli utenti
- Requisiti funzionali e tecnici dell'interfaccia di integrazione
- Aspettative relative a prestazioni e affidabilità
- Aspettative circa le risorse FHIR supportate per l'app Pazienti
- Processo di integrazione e modello di impegno previsto
- Come iniziare a usare FHIR e affrontare alcune sfide comuni con l'app Pazienti
- Requisiti futuri per l'iterazione successiva dell'app Pazienti

> [!NOTE]
> Nelle sezioni seguenti la parola "partner" o "partner di interoperabilità" viene usata per fare riferimento a un'organizzazione di terze parti che consente l'integrazione ai sistemi EHR per l'app Pazienti tramite FHIR e sta implementando un server FHIR in linea con le specifiche elencate.

## <a name="functional-and-technical-requirements"></a>Requisiti funzionali e tecnici  

### <a name="authentication"></a>Autenticazione  

L'autorizzazione  a livello di app senza supporto per l'autorizzazione a livello utente è il modo più comunemente supportato per eseguire trasformazioni di dati ed esporre connessioni ai dati EHR tramite FHIR, anche se il sistema EHR potrebbe implementare l'autorizzazione a livello utente. Il servizio di interoperabilità (Partner) ottiene un accesso elevato ai dati EHR e quando espongono gli stessi dati delle risorse FHIR appropriate non è passato un contesto di autorizzazione al consumer del servizio di interoperabilità (l'app Pazienti) che integra il servizio di interoperabilità o la piattaforma. L'app Pazienti non sarà in grado di applicare l'autorizzazione a livello utente, ma supporta l'autenticazione da applicazione a applicazione tra l'app Pazienti e il servizio del partner di interoperabilità.

Di seguito è descritto il modello di autenticazione applicazione-applicazione:

L'autenticazione da servizio a servizio deve essere eseguita tramite il flusso delle credenziali [client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)di OAuth 2.0. Il servizio partner deve fornire quanto segue:

1. Il servizio partner consente all'app Pazienti di creare un account con il Partner, che consente all'app Pazienti di generare e proprietà di client_id e client_secret, gestiti tramite un portale di registrazione di autenticazione sul server di autenticazione del partner.

2. Il servizio partner è proprietario del sistema di autenticazione/autorizzazione, che accetta e verifica (autentica) le credenziali del client fornite e restituisce un token di accesso con un suggerimento per il tenant nell'ambito, come descritto di seguito.

3. Per motivi di sicurezza o in caso di violazione segreta, l'app Pazienti può generare nuovamente il segreto e invalidare o eliminare il vecchio segreto (esempio dello stesso è disponibile nel portale di Azure - Registrazione dell'app AAD).

4. L'endpoint dei metadati che ospita l'istruzione di conformità deve essere non autenticato, deve essere accessibile senza token di autenticazione.

5. Il servizio partner fornisce l'endpoint token per l'app Pazienti per richiedere un token di accesso usando un flusso di credenziali del client. L'URL del token come da server di autorizzazione deve fare parte dell'istruzione di conformità (capacità) FHIR recuperata dai metadati sul server FHIR, come in questo esempio:

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

Una richiesta per un token di accesso è costituita dai parametri seguenti:

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

Il servizio partner fornisce client_id e client_secret per pazienti, gestite tramite un portale di registrazione Auth a lato del partner. Il servizio partner fornisce l'endpoint per richiedere il token di accesso usando un flusso di credenziali del client. Una risposta corretta deve includere i parametri token_type, access_token e expires_in risposta.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routing: mapping del tenant AAD all'endpoint provider

L'app Pazienti si connette a un servizio partner tramite un singolo endpoint. Il servizio partner è proprietario e gestisce un meccanismo per associare ogni cliente Microsoft (ID tenant AAD) a un provider sanitario corrispondente (server FHIR) su cui lavora il servizio partner.

Il mapping del tenant AAD a un endpoint provider usa l'ID tenant AAD (GUID). L'app Pazienti passa l'ID tenant nell'ambito, richiedendo un token di accesso per ogni richiesta. Il servizio partner mantiene il mapping dell'ID tenant all'endpoint del provider e reindirizza le richieste a un endpoint provider in base all'ID tenant. A questo scopo, il partner supporta la configurazione completa (manualmente o tramite un portale come parte dell'onboarding delle organizzazioni provider alla piattaforma di interoperabilità).

Di seguito è illustrato il flusso di lavoro Autenticazione e routing:

![Diagramma del flusso di lavoro Autenticazione e routing](../../media/Patient-app-6.png)

1. Richiedi token di accesso all'app inviando:
 
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

3. Richiedere dati protetti con token di accesso.

4. Messaggio di autorizzazione: selezionare il server FHIR appropriato a cui instradare dall'ID tenant nell'ambito.

5. Invia i dati protetti dall'app dal server FHIR autorizzato dopo l'autenticazione con il token dell'app.

## <a name="interfaces"></a>Interfacce

Chiamate e campi specifici usati dall'app Pazienti sono documentati negli articoli seguenti. Selezionare l'interfaccia applicabile alle API FHIR Server/FHIR.

- [Specifica dell'interfaccia DSTU2](dstu2-interface.md)
- [Specifica dell'interfaccia STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Prestazioni e affidabilità

Mentre l'app Pazienti è in anteprima privata, non ci sono garanzie sulle prestazioni end-to-end. I fattori che influiscono sulle prestazioni includono le latenze relative di tutti i passaggi coinvolti nel flusso di lavoro, a partire dall'EHR nell'ambiente del sistema sanitario, al partner di interoperabilità e alla loro infrastruttura, tra cui il server FHIR e fino all'ecosistema di Office 365 e all'app Pazienti.

![Illustrazione delle prestazioni dei partner di interoperabilità](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Introduzione a FHIR  

Se non hai mai utilizzato FHIR e hai bisogno di un facile accesso a un server FHIR che puoi esporre all'interfaccia di integrazione di Microsoft Teams EHR, Microsoft ha un server FHIR open-source disponibile per l'uso da parte di tutti gli sviluppatori. Vedere l'articolo Che cos'è il [server FHIR](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) per Azure per altre informazioni sul server FHIR open source disponibile da Microsoft e distribuirlo per le organizzazioni.

È anche possibile usare l'ambiente EHR sandbox HSPC Open per creare un EHR che supporta anche un server FHIR aperto e usarlo per giocare con l'app Pazienti. È consigliabile consultare la documentazione relativa alla [sandbox HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) La sandbox offre non solo un modo semplice, orientato all'interfaccia utente e semplice da usare per creare, aggiungere e modificare Pazienti, ma offre anche diversi esempi per iniziare. 
