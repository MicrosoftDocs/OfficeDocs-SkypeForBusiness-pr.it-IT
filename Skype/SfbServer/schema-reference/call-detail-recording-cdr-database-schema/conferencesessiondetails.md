---
title: Visualizzazione ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: La visualizzazione ConferenceSessionDetails archivia le informazioni sulle sessioni multiparte. Ogni record rappresenta una sessione di conferenza, che può essere la sessione con lo stato attiva o la sessione con uno specifico server di conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 3dc345c10836a34f99baa4d6a088ab152b23427d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815334"
---
# <a name="conferencesessiondetails-view"></a>Visualizzazione ConferenceSessionDetails
 
La visualizzazione ConferenceSessionDetails archivia le informazioni sulle sessioni multiparte. Ogni record rappresenta una sessione di conferenza, che può essere la sessione con lo stato attiva o la sessione con uno specifico server di conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Ora della richiesta della sessione. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**InviteTime** <br/> |DateTime  <br/> |Ora della prima richiesta di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI della conferenza.  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)  <br/> |URI del tipo di conferenza. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificatore che distingue tra le istanze delle conferenze periodiche. Ogni istanza di conferenza ricorrente ha lo stesso ConferenceURI, ma un valore ConfInstance diverso.  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)  <br/> |URI del server dei servizi di conferenza.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI di conferenza server. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI dell'utente coinvolto nella sessione.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente di cui è stata parte della sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente di cui è stata parte della sessione. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'utente di cui faceva parte della sessione.  <br/> |
|**EndTime** <br/> |DateTime  <br/> |Ora di fine della sessione.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar (256)  <br/> |Versione di Conference Server.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo di server conferenza. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)  <br/> |Categoria Server conferenze.  <br/> |
|**UserClientVersion** <br/> |nvarchar (256)  <br/> |Versione del client usata dall'utente che ha partecipato alla sessione.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client usato dall'utente che ha partecipato alla sessione. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nome della categoria del client usata dall'utente che faceva parte della sessione.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |URI dell'utente per conto della quale è stata avviata la sessione.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente per conto della quale è stata avviata la sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente per cui è stata avviata la sessione. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha fatto riferimento alla sessione.  <br/> |
|**ReferredByUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha fatto riferimento alla sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**ReferredByUriTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente che ha fatto riferimento alla sessione. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |ID finestra di dialogo SIP. Il formato è  <br/> :d ialog; from-tag; to-Tag  <br/> |
|**ReplaceDialogIdTime** <br/> |DateTime  <br/> |Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita da questa sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |ID finestra di dialogo SIP che sostituisce la sessione. Il formato dell'is:  <br/> finestra di dialogo; da-tag; to-Tag  <br/> |
|**IsStartedByConfServer** <br/> |po'  <br/> |Indica se la sessione è stata avviata dal server dei servizi di conferenza.  <br/> |
|**IsEndedByConfServer** <br/> |po'  <br/> |Indica se la sessione è stata terminata dal server dei servizi di conferenza.  <br/> |
|**IsUserInternal** <br/> |po'  <br/> |Indica se l'utente ha effettuato l'accesso dalla rete interna.  <br/> |
|**ResponseTime** <br/> |DateTime  <br/> |Ora della risposta al primo messaggio di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP per l'invito alla sessione. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID di diagnostica acquisito dalle intestazioni SIP della sessione.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> |Tipo di contenuto per la sessione.  <br/> |
|**FrontEnd** <br/> |nvarchar (256)  <br/> |Nome di dominio completo del server front-end che ha acquisito i dati per la sessione.  <br/> |
|**Pool** <br/> |nvarchar (256)  <br/> |Nome di dominio completo del pool che ha acquisito i dati per la sessione.  <br/> |
|**MediationServer** <br/> |nvarchar (256)  <br/> |Mediation Server usato dall'utente che ha partecipato alla sessione.  <br/> |
|**Gateway** <br/> |nvarchar (256)  <br/> |Gateway usato dall'utente che ha partecipato alla sessione.  <br/> |
|**EdgeServer** <br/> |nvarchar (256)  <br/> |FQDN dell'Edge Server usato dall'utente che ha partecipato alla sessione.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica gli attributi dell'utente che ha partecipato alla sessione. Le definizioni di attributo seguenti sono consentite:  <br/> 0x01-integrato con il telefono desktop  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica gli attributi di chiamata. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01-riprovato Session0  <br/> X02-chiamata effettuata dall'agente per conto di un gruppo di risposte  <br/> |
   

