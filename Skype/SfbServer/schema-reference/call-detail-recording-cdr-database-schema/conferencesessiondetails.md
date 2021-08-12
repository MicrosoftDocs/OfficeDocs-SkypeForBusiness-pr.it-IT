---
title: Visualizzazione ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: Nella visualizzazione ConferenceSessionDetails sono archiviate informazioni sulle sessioni tra più utenti. Ogni record rappresenta una sola sessione di conferenza, che può essere la sessione con Focus o con un server per conferenze specifico. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d11573f8911f02001101c2d6f2e13dd5ec2112017ada115282b9c0ed008176f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337654"
---
# <a name="conferencesessiondetails-view"></a>Visualizzazione ConferenceSessionDetails
 
Nella visualizzazione ConferenceSessionDetails sono archiviate informazioni sulle sessioni tra più utenti. Ogni record rappresenta una sola sessione di conferenza, che può essere la sessione con Focus o con un server per conferenze specifico. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Ora della richiesta di sessione. Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**InviteTime** <br/> |datetime  <br/> |Ora della prima richiesta INVITE. Questo campo in genere viene popolato dai dati generati dal messaggio INVITE iniziale della sessione. Se non ci sono messaggi INVITE, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI della conferenza.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI della conferenza. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificatore che consente di distinguere le istanze delle conferenze ricorrenti. Ogni istanza ha lo stesso ConferenceURI ma un valore ConfInstance diverso.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI del server per conferenze.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI del server per conferenze. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che partecipa alla sessione.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che partecipa alla sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che partecipa alla sessione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'utente che partecipa alla sessione.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Ora di fine della sessione.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versione del Conference Server.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo del Conference Server. Per ulteriori informazioni, vedere la [tabella UserAgentDef.](useragentdef.md) <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Categoria del Conference Server.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versione del client dell'utente che ha partecipato alla sessione.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client dell'utente che ha partecipato alla sessione. Per ulteriori dettagli, vedere la [tabella UserAgentDef.](useragentdef.md) <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome della categoria del client dell'utente che ha partecipato alla sessione.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI dell'utente per conto del quale è stata avviata la sessione.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente per conto del quale è stata avviata la sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente per conto del quale è stata avviata la sessione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha fatto riferimento alla sessione.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha fatto riferimento alla sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che ha fatto riferimento alla sessione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID del dialogo SIP. Il formato è  <br/> :d ialog;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Numero ID per identificare il dialogo sostituito dalla sessione corrente. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita dalla sessione corrente. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID del dialogo SIP che la sessione sostituisce. Il formato è:  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica se la sessione è stata avviata dal server per conferenze.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica se la sessione è stata terminata dal server per conferenze.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica se l'utente ha effettuato l'accesso dalla rete interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID di diagnostica acquisito dalle intestazioni SIP della sessione.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo di contenuto della sessione.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del Front End Server che ha acquisito i dati della sessione.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN del pool che ha acquisito i dati per la sessione.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Mediation Server dell'utente che ha partecipato alla sessione.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> |Gateway dell'utente che ha partecipato alla sessione.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del server perimetrale dell'utente che ha partecipato alla sessione.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica gli attributi dell'utente che ha partecipato alla sessione. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01 - Integrato con il telefono da scrivania  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica gli attributi della chiamata. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01 - Sessione ripetuta  <br/> x02 - Chiamata effettuata da un agente per conto di un Response Group  <br/> |
   

