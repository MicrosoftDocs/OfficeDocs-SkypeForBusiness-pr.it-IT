---
title: Visualizzazione SessionDetails
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
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: Nella visualizzazione SessionDetails vengono archiviate informazioni relative alle sessioni peer-to-peer, ovvero le chiamate telefoniche VoIP-VoIP, le sessioni di messaggistica istantanea tra due utenti e altri tipi di sessioni. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 5a278960912ac38dc75fe398e3d75de710785800
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767454"
---
# <a name="sessiondetails-view"></a>Visualizzazione SessionDetails
 
Nella visualizzazione SessionDetails vengono archiviate informazioni relative alle sessioni peer-to-peer, ovvero le chiamate telefoniche VoIP-VoIP, le sessioni di messaggistica istantanea tra due utenti e altri tipi di sessioni. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Ora della richiesta di sessione. Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per ulteriori [informazioni, vedere la tabella Dialogs Skype for Business Server 2015](dialogs.md) Table. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**InviteTime** <br/> |datetime  <br/> |Ora della prima richiesta INVITE. Questo campo è solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha avviato la sessione.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che si è unito alla sessione.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha avviato la sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che si è unito alla sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Tenant dell'utente che ha avviato la sessione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che si è unito alla sessione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'endpoint dell'utente che ha avviato la sessione.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'endpoint dell'utente che si è unito alla sessione.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Ora di fine della sessione.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Numero di messaggi inviati dall'utente che ha avviato la sessione.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Numero di messaggi inviati dall'utente che si è unito alla sessione.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versione del client utilizzato dall'utente che ha avviato la sessione.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client utilizzato dall'utente che ha avviato la sessione. Per ulteriori dettagli, vedere la [tabella UserAgentDef.](useragentdef.md) <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nome della categoria del client utilizzato dall'utente che ha avviato la sessione.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versione del client utilizzato dall'utente che si è unito alla sessione.  <br/> |
|**ToClientType** <br/> |int  <br/> |Client utilizzato dall'utente che si è unito alla sessione. Per ulteriori dettagli, vedere la [tabella UserAgentDef.](useragentdef.md) <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nome della categoria del client utilizzato dall'utente che si è unito alla sessione.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI dell'utente di destinazione della sessione.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Tipo di URI dell'utente di destinazione della sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI dell'utente per conto del quale è stata avviata la sessione.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente per conto del quale è stata avviata la sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente per conto del quale è stata avviata la sessione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha fatto riferimento alla sessione.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha fatto riferimento alla sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che ha fatto riferimento alla sessione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID del dialogo SIP. Il formato è:  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID utilizzato per correlare più sessioni.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Ora del dialogo sostituito dalla sessione. Valore utilizzato in combinazione con ReplaceDialogIdSeq per identificare in modo univoco un dialogo sostituito dalla sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numero di ID per identificare la sessione. Valore utilizzato in combinazione con ReplaceDialogIdTime per identificare in modo univoco un dialogo sostituito dalla sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID del dialogo SIP sostituito dalla sessione. Il formato è:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID di diagnostica acquisito dalle intestazioni SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo del contenuto della sessione.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del Front End Server che ha acquisito i dati della sessione.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN del pool che ha acquisito i dati della sessione.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica se l'utente che ha avviato la sessione ha eseguito l'accesso dalla rete interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica se l'utente che si è unito alla sessione ha eseguito l'accesso dalla rete interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Priorità di chiamata della sessione.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01 - Integrato con il telefono da scrivania  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01 - Integrato con il telefono da scrivania  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica gli attributi di chiamata. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01 - Sessione ripetuta  <br/> 0x02 - Chiamata eseguita da agente per conto di un Response Group  <br/> |
|**Posizione** <br/> |varchar(max)  <br/> |Posizione della chiamata di emergenza.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto Skype for Business Server 2015.  <br/> |
   

