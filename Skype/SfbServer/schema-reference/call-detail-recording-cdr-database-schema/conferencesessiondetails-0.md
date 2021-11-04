---
title: Tabella ConferenceSessionDetails in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Ogni record rappresenta una sessione di conferenza, che può indicare la sessione con Focus o la sessione con un server per conferenze specifico.
ms.openlocfilehash: 087dd056dae0041ab63934b25038672a74410343
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759448"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabella ConferenceSessionDetails in Skype for Business Server 2015
 
Ogni record rappresenta una sessione di conferenza, che può indicare la sessione con Focus o la sessione con un server per conferenze specifico.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |Primaria, esterna  <br/> |Ora della richiesta di sessione; utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione di conferenza. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare la sessione. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione di conferenza. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI di conferenza Focus associato alla sessione. Per ulteriori informazioni, vedere la tabella [ConferenceUris Skype for Business Server 2015.](conferenceuris.md) Si tratta di un URI di conferenza basata su Focus. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificatore che consente di distinguere le istanze delle conferenze ricorrenti. Ogni istanza ha lo stesso ConferenceURI ma un valore ConfInstance diverso.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI di conferenza del server per conferenze associato alla sessione. Per ulteriori informazioni, vedere la tabella [ConferenceUris Skype for Business Server 2015.](conferenceuris.md) Si tratta di un URI di conferenza basata su server di conferenza. Per le sessioni di conferenza Focus, questa colonna sarà null. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |ID di un utente nella sessione di conferenza. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||GUID per l'identificazione dell'istanza dell'endpoint. Ad esempio, se un utente accede a due computer con lo stesso account, ogni computer disporrà di un ID endpoint diverso.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |Indica l'ID dell'utente per conto del quale il chiamante esegue la chiamata. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |ID dell'utente da quale proviene la chiamata. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Versione del client utilizzata dall'utente della conferenza. Per ulteriori informazioni, vedere la tabella [ClientVersions Skype for Business Server 2015.](clientversions.md) <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Versione del client utilizzata dal server per conferenze. Per ulteriori informazioni, vedere la tabella [ClientVersions Skype for Business Server 2015.](clientversions.md) <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |Numero ID per l'identificazione della finestra di dialogo sostituita dalla sessione corrente. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |Numero ID per l'identificazione della sessione. Valore utilizzato in combinazione con **ReplacesDialogIdTime** per identificare in modo univoco una sessione sostituita da questa sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica se la sessione è stata avviata dal server per conferenze.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica se la sessione è stata terminata dal server per conferenze.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Indica se l'utente è connesso dall'interno o meno.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Codice di risposta SIP (Session Initiation Protocol) all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID di diagnostica acquisito dall'intestazione SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |ID del Front End Server utilizzato per questa sessione. Per ulteriori [informazioni, vedere](servers.md) la tabella Servers. <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |ID del pool in cui è stata acquisita la sessione. Per ulteriori [informazioni, vedere](pools.md) la tabella Pools. <br/> |
|**MediationServerId** <br/> |int  <br/> |Foreign  <br/> |Mediation Server utilizzato dalla chiamata. Per ulteriori informazioni, vedere la tabella [MediationServers.](mediationservers.md) <br/> |
|**GatewayId** <br/> |int  <br/> |Foreign  <br/> |Gateway utilizzato dalla chiamata. Per ulteriori informazioni, vedere la tabella [Gateways Skype for Business Server 2015.](gateways.md) <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |Server perimetrale utilizzato dalla chiamata. Per ulteriori informazioni, vedere la tabella [EdgeServers Skype for Business Server 2015.](edgeservers.md) <br/> |
|**ContentTypeId** <br/> |int  <br/> |Foreign  <br/> |Tipo di contenuto utilizzato nella sessione. Per ulteriori informazioni, vedere [la tabella ContentTypes Skype for Business Server 2015.](contenttypes.md) <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Ora della prima richiesta INVITE. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Ora della prima risposta SIP. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Ora di fine della sessione.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Foreign  <br/> |Contiene il valore del tipo di URI MCU dalla [tabella UriTypes.](uritypes.md) Questo campo è usato per migliorare le prestazioni di query.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Set di bit che indica gli attributi dell'utente. Sono incluse le definizioni di attributo seguenti: <br/>  Integrato con telefono da tavolo  - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Set di bit che indica gli attributi della chiamata. Sono incluse le definizioni di attributo seguenti: <br/>  Sessione ripetuta  - 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto Skype for Business Server 2015.  <br/> |
   
\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se più sessioni iniziano esattamente alla stessa ora, il valore SessionIdSeq per una sarà 1, per l'altra sarà 2 e così via.
  

