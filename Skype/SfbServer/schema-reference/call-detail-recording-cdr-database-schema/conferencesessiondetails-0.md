---
title: Tabella ConferenceSessionDetails in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Ogni record rappresenta una sessione di conferenza, che può essere la sessione con lo stato attiva o la sessione con uno specifico server di conferenza.
ms.openlocfilehash: 95cf64589cdcd0fd38b4e29cd4e863c870f2a7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815344"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabella ConferenceSessionDetails in Skype for Business Server 2015
 
Ogni record rappresenta una sessione di conferenza, che può essere la sessione con lo stato attiva o la sessione con uno specifico server di conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora della richiesta di sessione; usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione di conferenza. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione di conferenza. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Esterna  <br/> |URI della conferenza dello stato di attivazione relativo a questa sessione. Per altre informazioni, vedere la [tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . Questo URI è un URI di conferenza basato sullo stato. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificatore che distingue tra le istanze delle conferenze periodiche. Ogni istanza di conferenza ricorrente ha lo stesso ConferenceURI, ma un valore ConfInstance diverso.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Esterna  <br/> |URI conferenza del server delle conferenze correlato a questa sessione. Per altre informazioni, vedere la [tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . Questo URI è l'URI per conferenze basato su server di conferenza. Per le sessioni di conferenza dello stato di attivazione, questa colonna sarà null. <br/> |
|**UserId** <br/> |int  <br/> |Esterna  <br/> |ID di un utente nella sessione di conferenza. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||GUID per identificare l'istanza di endpoint. Ad esempio, se un utente accede a computer diversi con lo stesso account, ogni computer avrà un ID endpoint diverso.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Esterna  <br/> |Indica l'ID dell'utente di chi è il chiamante per conto. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Esterna  <br/> |ID dell'utente con cui si fa riferimento alla chiamata. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Esterna  <br/> |Versione client usata dall'utente della conferenza. Per altre informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Esterna  <br/> |Versione client usata dal server conferenza. Per altre informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**ReplaceDialogIdTime** <br/> |DateTime  <br/> |Esterna  <br/> |Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Esterna  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **ReplacesDialogIdTime** per identificare in modo univoco una sessione sostituita da questa sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**IsStartedByConfServer** <br/> |po'  <br/> ||Indica se la sessione è stata avviata dal server dei servizi di conferenza.  <br/> |
|**IsEndedByConfServer** <br/> |po'  <br/> ||Indica se la sessione è terminata dal server dei servizi di conferenza.  <br/> |
|**IsUserInternal** <br/> |po'  <br/> ||Se l'utente ha effettuato l'accesso da Internal o not.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Codice di risposta SIP (Session Initiation Protocol) all'invito alla sessione. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID di diagnostica acquisito dall'intestazione SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Esterna  <br/> |ID del server front-end usato per questa sessione. Per altre informazioni, vedere la [tabella server](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Esterna  <br/> |ID del pool in cui è stata acquisita la sessione. Per altre informazioni, vedere la [tabella pool](pools.md) . <br/> |
|**MediationServerId** <br/> |int  <br/> |Esterna  <br/> |Server di mediazione che la chiamata sta usando. Per altre informazioni, vedere la [Tabella MediationServers](mediationservers.md) . <br/> |
|**GatewayId** <br/> |int  <br/> |Esterna  <br/> |Il gateway che la chiamata sta usando. Per altre informazioni, vedere la [tabella gateway in Skype for Business Server 2015](gateways.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Esterna  <br/> |Server perimetrale usato dalla chiamata. Per altre informazioni, vedere la [tabella EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**ContentTypeId** <br/> |int  <br/> |Esterna  <br/> |Tipo di contenuto usato nella sessione. Per altre informazioni, vedere la [tabella ContentTypes in Skype for Business Server 2015](contenttypes.md) . <br/> |
|**InviteTime** <br/> |DateTime  <br/> ||L'ora della prima richiesta di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseTime** <br/> |DateTime  <br/> ||Ora della prima risposta SIP. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**SessionEndTime** <br/> |DateTime  <br/> ||Ora di fine della sessione.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Esterna  <br/> |Contiene il valore di tipo URI MCU della [tabella UriTypes](uritypes.md). Questo campo viene usato per migliorare le prestazioni delle query.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Set di bit che indica gli attributi utente. Sono elencate le definizioni di attributo seguenti: <br/>  Integrazione con il telefono da tavolo-1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Set di bit che indica gli attributi di chiamata. Sono elencate le definizioni di attributo seguenti: <br/>  Riprova sessione-1 <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   
\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se più sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1, per un altro sarà 2 e così via.
  

