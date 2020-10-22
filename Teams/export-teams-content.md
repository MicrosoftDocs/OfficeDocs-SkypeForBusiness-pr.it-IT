---
title: Esportare contenuto con le API di esportazione di Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In questo articolo vengono illustrate le informazioni su come esportare il contenuto dei team tramite le API di esportazione di Microsoft teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 026b7f238b059b4e310fa2216b482c68f2528780
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650979"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Esportare contenuto con le API di esportazione di Microsoft Teams

Le API di esportazione dei team consentono di esportare i messaggi di 1:1 e di chat di gruppo da Microsoft teams. Se l'organizzazione deve esportare i messaggi di Microsoft teams, è possibile estrarli usando le API di esportazione di teams. *Messaggio di chat* rappresenta un singolo messaggio di chat all'interno di un [canale](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) o una [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta). Il messaggio di chat può essere un messaggio di chat radice o parte di un thread di risposta definito dalla proprietà **replyToId** nel messaggio di chat.

Ecco alcuni esempi su come usare queste API di esportazione:

- **Esempio 1**: se sono stati abilitati Microsoft teams nell'organizzazione e si vogliono esportare tutti i messaggi di Microsoft teams fino a una data a livello di codice, passando l'intervallo di date per un utente specifico.
- **Esempio 2**: se si vuole esportare a livello di codice tutti i messaggi degli utenti ogni giorno fornendo un intervallo di date. Le API di esportazione possono recuperare tutti i messaggi creati o aggiornati durante l'intervallo di date specifico.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Cosa è supportato dalle API di esportazione dei team?

- **Esportazione in blocco del messaggio teams:** Le API di esportazione dei team supportano fino a 200 RPS per app per tenant e 600 RPS per un'applicazione, con questi limiti dovresti essere in grado di esportare in blocco i messaggi di teams.
- **Contesto applicazione**: per chiamare Microsoft Graph, la tua app deve acquisire un token di accesso dalla piattaforma Microsoft Identity. Il token di accesso contiene informazioni sulla tua app e sulle autorizzazioni per le risorse e le API disponibili tramite Microsoft Graph. Per ottenere un token di accesso, la tua app deve essere registrata con la piattaforma di identità Microsoft ed essere autorizzata da un utente o da un amministratore per accedere alle risorse di Microsoft Graph necessarie.

    Se si ha già familiarità con l'integrazione di un'app con la piattaforma Microsoft Identity per ottenere i token, vedere la sezione [passaggi successivi](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) per informazioni ed esempi specifici di Microsoft Graph.
- **Ambiente ibrido:** Le API di esportazione supportano i messaggi inviati dagli utenti che hanno eseguito il provisioning in ambiente ibrido (Exchange locale e teams). Tutti i messaggi inviati dagli utenti configurati per l'ambiente ibrido saranno accessibili con le API di esportazione.
- **Messaggi eliminati dall'utente:** I messaggi eliminati dall'utente da teams client possono essere raggiunti usando le API di esportazione fino a 30 giorni dopo l'eliminazione.
- **Allegati ai messaggi:** Le API di esportazione includono i collegamenti agli allegati inviati come parte dei messaggi. Uso delle API di esportazione è possibile recuperare i file allegati nei messaggi.
- **Proprietà del messaggio di chat:** Fare riferimento all'elenco completo delle proprietà supportate da teams Export [Apis.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Come accedere alle API di esportazione di Teams

- L' **esempio 1** è una semplice query per recuperare tutti i messaggi di un utente senza filtri:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- L' **esempio 2** è una query di esempio per recuperare tutti i messaggi di un utente specificando i filtri di data e ora e i primi 50 messaggi:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>L'API restituisce la risposta con il collegamento alla pagina successiva in caso di più risultati. Per ottenere il prossimo set di risultati, chiama semplicemente GET sull'URL da @odata. nextlink. Se @odata. NEXTLINK non è presente o null, vengono recuperati tutti i messaggi.

## <a name="prerequisites-to-access-teams-export-apis"></a>Prerequisiti per accedere alle API di esportazione di Teams 

- Le API di esportazione di teams sono attualmente in anteprima. Sarà disponibile solo per gli utenti e i tenant che dispongono delle [licenze necessarie](https://aka.ms/teams-changenotification-licenses) per le API. In futuro, Microsoft può richiedere ai clienti di pagare commissioni aggiuntive in base alla quantità di dati a cui è possibile accedere tramite l'API.
- Le API di Microsoft teams in Microsoft Graph che accedono ai dati riservati sono considerate API protette. Le API di esportazione richiedono la convalida aggiuntiva, oltre le autorizzazioni e il consenso, prima di poterle usare. Per richiedere l'accesso a queste API protette, completare il [modulo di richiesta](https://aka.ms/teamsgraph/requestaccess).
- Le autorizzazioni dell'applicazione vengono usate dalle app che vengono eseguite senza un utente di cui è stato eseguito l'accesso. le autorizzazioni dell'applicazione possono essere consentite solo da un amministratore. Sono necessarie le autorizzazioni seguenti:

    - *Chat. Read. All*: consente l'accesso a tutti i messaggi di 1:1 e di chat di gruppo 
    - *User. Read. All*: consente l'accesso all'elenco di utenti per un tenant 

## <a name="json-representation"></a>Rappresentazione JSON

L'esempio seguente è una rappresentazione JSON della risorsa:

Spazio dei nomi: Microsoft. Graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {
                    "id": "0de69e5e-2da8-4cf2-821f-5e6585b2c65b",
                    "displayName": "User Name",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "19:0de69e5e-2da8-4cf2-821f-5e6585b2c65b_5c64e248-3269-4268-a36e-0f80314e9c39@unq.gbl.spaces"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Per altre informazioni sulla risorsa chatMessage, Vedi l'articolo relativo al [tipo di risorsa chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .
