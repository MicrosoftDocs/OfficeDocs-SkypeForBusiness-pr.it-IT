---
title: Esportare contenuto con le API di esportazione di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In questo articolo imparerai a esportare il contenuto di Teams usando le API di esportazione di Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ffbea482ac15d1362eabc720fe2c05a8b5954954
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562645"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Esportare contenuto con le API di esportazione di Microsoft Teams

Le API di esportazione di Teams consentono di esportare 1:1, chat di gruppo, chat delle riunioni e messaggi di canale da Microsoft Teams. Se l'organizzazione deve esportare i messaggi di Microsoft Teams, è possibile estrarli usando le API di esportazione di Teams. *Messaggio di chat* rappresenta un singolo messaggio di chat all'interno di un [canale](/graph/api/resources/channel) o [di una chat](/graph/api/resources/chat). Il messaggio di chat può essere un messaggio di chat radice o parte di un thread di risposta definito dalla proprietà **replyToId** nel messaggio di chat.

Ecco alcuni esempi su come usare queste API di esportazione:

- **Esempio 1**: se hai abilitato Microsoft Teams nella tua organizzazione e vuoi esportare tutti i messaggi di Microsoft Teams a livello di programmazione passando l'intervallo di date per un determinato utente o team.
- **Esempio 2**: per esportare a livello di programmazione tutti i messaggi di utenti o team ogni giorno fornendo un intervallo di date. Le API di esportazione possono recuperare tutti i messaggi creati o aggiornati durante l'intervallo di date specificato.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Cosa è supportato dalle API di esportazione di Teams?

- **Esportazione in blocco del messaggio di Teams:** Le API di esportazione di Teams supportano fino a 200 RPS per app Per tenant e 600 RPS per un'applicazione, con questi limiti dovrebbe essere possibile esportare in blocco i messaggi di Teams.
- **Contesto applicazione**: per chiamare Microsoft Graph, l'app deve acquisire un token di accesso dal Microsoft Identity Platform. Il token di accesso contiene informazioni sull'app e sulle autorizzazioni di cui dispone per le risorse e le API disponibili tramite Microsoft Graph. Per ottenere un token di accesso, l'app deve essere registrata con il Microsoft Identity Platform ed essere autorizzata da un utente o un amministratore per accedere alle risorse di Microsoft Graph necessarie.

    Se hai già familiarità con l'integrazione di un'app con il Microsoft Identity Platform per ottenere token, vedi la sezione [Passaggi successivi](/graph/auth/auth-concepts#next-steps) per informazioni ed esempi specifici di Microsoft Graph.
- **Ambiente ibrido:** Esportare i messaggi di supporto delle API inviati dagli utenti di cui è stato eseguito il provisioning in ambiente ibrido (Exchange locale e Teams). Tutti i messaggi inviati da utenti configurati per l'ambiente ibrido saranno accessibili usando esporta API.
- **Messaggi eliminati dall'utente:** I messaggi eliminati dagli utenti dal client Teams sono accessibili usando le API di esportazione fino a 21 giorni dal momento dell'eliminazione.
- **Allegati dei messaggi:** Le API di esportazione includono i collegamenti agli allegati inviati come parte dei messaggi. Con l'opzione Esporta API è possibile recuperare i file allegati nei messaggi.
- **Proprietà dei messaggi di chat:** Fai riferimento all'elenco completo delle proprietà supportate da Teams Export API [qui](/graph/api/resources/chatmessage#properties).

> [!NOTE]
> Le API di esportazione non supportano *le reazioni*.

## <a name="how-to-access-teams-export-apis"></a>Come accedere alle API di esportazione di Teams

- **L'esempio 1** è una query semplice per recuperare tutti i messaggi di un utente o di un team senza alcun filtro:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **L'esempio 2** è una query di esempio per recuperare tutti i messaggi di un utente o di un team specificando filtri di data/ora e i primi 50 messaggi:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> L'API restituisce una risposta con collegamento alla pagina successiva in caso di più risultati. Per ottenere il set di risultati successivo, basta chiamare GET sull'URL da @odata.nextlink. Se @odata.nextlink non è presente o null, vengono recuperati tutti i messaggi.

## <a name="prerequisites-to-access-teams-export-apis"></a>Prerequisiti per accedere alle API di esportazione di Teams

- Le API di Microsoft Teams in Microsoft Graph che accedono a dati sensibili sono considerate API protette. Le API di esportazione richiedono una convalida aggiuntiva, oltre alle autorizzazioni e al consenso, prima di poterle usare. Per richiedere l'accesso a queste API protette, completa il [modulo di richiesta](https://aka.ms/teamsgraph/requestaccess).
- Le autorizzazioni dell'applicazione vengono usate dalle app che vengono eseguite senza una presentazione utente connessa; autorizzazioni dell'applicazione possono essere concesse solo da un amministratore. Sono necessarie le autorizzazioni seguenti:
  - *Chat.Read.All*: consente l'accesso a tutti i messaggi 1:1, chat di gruppo e chat di riunione
  - *ChannelMessage.Read.All*: consente l'accesso a tutti i messaggi del canale
  - *User.Read.All*: consente l'accesso all'elenco di utenti per un tenant

## <a name="license-requirements-for-teams-export-apis"></a>Requisiti di licenza per le API di esportazione di Teams

L'API di esportazione supporta gli scenari di sicurezza e conformità (S+C) e di utilizzo generale tramite un parametro di query del modello. Gli scenari S+C (modello A) includono la capacità di seeding e richiedono una sottoscrizione E5 e gli scenari di utilizzo generali (modello B) sono disponibili per tutte le sottoscrizioni ed è solo a consumo. Per altre informazioni sulla capacità di seeding e sui costi di consumo, vedi [Requisiti di gestione delle licenze e di pagamento per le API Microsoft Graph Teams](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>Scenari S+C/Modello A

Riservato alle applicazioni che eseguono funzioni di sicurezza e/o conformità, gli utenti devono avere licenze E5 specifiche per usare questa funzionalità e ricevere capacità di seeding. La capacità di seeding è per utente e viene calcolata al mese ed è aggregata a livello di tenant. Per l'utilizzo oltre la capacità di seeding, i proprietari delle app vengono fatturati per il consumo di API. Il modello A può accedere solo ai messaggi provenienti da utenti con una licenza E5 assegnata.

### <a name="general-usagemodel-b-scenarios"></a>Utilizzo generale/Scenari modello B

Disponibile per tutti gli scenari non correlati a S+C, non esistono requisiti di licenza o capacità di seeding. Quando i contatori di consumo diventano disponibili, ai proprietari delle app verrà addebitato un costo per tutte le chiamate API mensili.

### <a name="evaluation-mode-default"></a>Modalità di valutazione (impostazione predefinita)

Nessuna dichiarazione del modello consente l'accesso alle API con un utilizzo limitato per ogni applicazione richiedente ai fini della valutazione.

## <a name="json-representation"></a>Rappresentazione JSON

L'esempio seguente è una rappresentazione JSON della risorsa:

Spazio dei nomi: microsoft.graph

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

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

> [!NOTE]
> Per altri dettagli sulla risorsa chatMessage, vedere l'articolo sul [tipo di risorsa chatMessage](/graph/api/resources/chatmessage) .
