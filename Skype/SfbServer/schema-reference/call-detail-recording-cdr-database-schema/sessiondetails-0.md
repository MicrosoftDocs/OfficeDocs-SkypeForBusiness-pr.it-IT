---
title: Visualizzazione SessionDetails
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
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La visualizzazione SessionDetails archivia le informazioni sulle sessioni peer-to-peer, che potrebbero essere una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea a due parti o un altro tipo di sessione. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: f1d0d68fe152f277c02c53fd87afdb0ea4e4ab0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814914"
---
# <a name="sessiondetails-view"></a>Visualizzazione SessionDetails
 
La visualizzazione SessionDetails archivia le informazioni sulle sessioni peer-to-peer, che potrebbero essere una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea a due parti o un altro tipo di sessione. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Ora della richiesta della sessione. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella finestre di dialogo nella tabella Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**InviteTime** <br/> |DateTime  <br/> |Ora della prima richiesta di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO). Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha avviato la sessione.  <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha partecipato alla sessione.  <br/> |
|**FromUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha avviato la sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**ToUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha partecipato alla sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar (450)  <br/> |Tenant dell'utente che ha avviato la sessione. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**Totenant** <br/> |nvarchar (256)  <br/> |Il tenant dell'utente che ha partecipato alla sessione. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco del punto finale dell'utente che ha avviato la sessione.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco del punto finale dell'utente che ha partecipato alla sessione.  <br/> |
|**EndTime** <br/> |DateTime  <br/> |Ora di fine della sessione.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Numero di messaggi inviati dall'utente che ha avviato la sessione.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Numero di messaggi inviati dall'utente che ha partecipato alla sessione.  <br/> |
|**FromClientVersion** <br/> |nvarchar (256)  <br/> |Versione del client usata dall'utente che ha avviato la sessione.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client usato dall'utente che ha avviato la sessione. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**FromClientCategory** <br/> |nvarchar (64)  <br/> |Nome della categoria del client usata dall'utente che ha avviato la sessione.  <br/> |
|**ToClientVersion** <br/> |nvarchar (256)  <br/> |Versione del client usata dall'utente che ha partecipato alla sessione  <br/> |
|**ToClientType** <br/> |int  <br/> |Client usato dall'utente che ha partecipato alla sessione. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**ToClientCategory** <br/> |nvarchar (64)  <br/> |Nome della categoria del client usata dall'utente che ha partecipato alla sessione.  <br/> |
|**TargetUri** <br/> |nvarchar (450)  <br/> |URI dell'utente di destinazione della sessione.  <br/> |
|**TargetUriType** <br/> |nvarchar (450)  <br/> |Tipo di URI dell'utente di destinazione per la sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |URI dell'utente per conto della quale è stata avviata la sessione.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente per conto della quale è stata avviata la sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente per cui è stata avviata la sessione. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha fatto riferimento alla sessione.  <br/> |
|**ReferredByUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha fatto riferimento alla sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**ReferredByTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente che ha fatto riferimento alla sessione. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |ID finestra di dialogo SIP. Il formato è:  <br/> finestra di dialogo; da-tag; to-Tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID usato per correlare più sessioni.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateTime  <br/> |Ora della finestra di dialogo che è stata sostituita dalla sessione. Usato in combinazione con ReplaceDialogIdSeq per identificare in modo univoco una finestra di dialogo che viene sostituita dalla sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una finestra di dialogo che viene sostituita dalla sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |ID finestra di dialogo SIP che sostituisce la sessione. Il formato è:  <br/> finestra di dialogo; da-tag; to-Tag  <br/> |
|**ResponseTime** <br/> |DateTime  <br/> |Ora della risposta al primo messaggio di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP per l'invito alla sessione. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID di diagnostica acquisito dalle intestazioni SIP.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> |Tipo di contenuto per la sessione.  <br/> |
|**FrontEnd** <br/> |nvarchar (256)  <br/> |Nome di dominio completo del server front-end che ha acquisito i dati per la sessione.  <br/> |
|**Pool** <br/> |nvarchar (256)  <br/> |Nome di dominio completo del pool che ha acquisito i dati per la sessione.  <br/> |
|**FromEdgeServer** <br/> |nvarchar (256)  <br/> |FQDN dell'Edge Server usato dall'utente che ha avviato la sessione.  <br/> |
|**ToEdgeServer** <br/> |nvarchar (256)  <br/> |FQDN dell'Edge Server usato dall'utente che ha avviato la sessione  <br/> |
|**IsFromInternal** <br/> |po'  <br/> |Indica se l'utente che ha avviato la sessione ha effettuato l'accesso dalla rete interna.  <br/> |
|**IsToInternal** <br/> |po'  <br/> |Indica se l'utente che ha partecipato alla sessione ha effettuato l'accesso dalla rete interna.  <br/> |
|**CallPriority** <br/> |nvarchar (256)  <br/> |Priorità chiamata della sessione.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01-integrato con il telefono desktop  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01-integrato con il telefono desktop  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica gli attributi di chiamata. Sono consentite le definizioni di attributo seguenti:  <br/> 0x01-Riprova sessione  <br/> 0x02-chiamata effettuata dall'agente per conto di un gruppo di risposte  <br/> |
|**Posizione** <br/> |varchar (max)  <br/> |Posizione della chiamata di emergenza.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> |Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

