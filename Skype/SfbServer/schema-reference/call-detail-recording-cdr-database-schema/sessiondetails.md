---
title: Tabella SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Ogni record rappresenta una sessione peer-to-peer, che potrebbe essere una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea a due parti o un altro tipo di sessione. È possibile eseguire un join di tabella con la tabella media per trovare i dettagli di ogni elemento multimediale coinvolto in questa sessione.
ms.openlocfilehash: d6c0d68cf5b8efd83cc764e74a56621cdd591ac1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194743"
---
# <a name="sessiondetails-table"></a>Tabella SessionDetails
 
Ogni record rappresenta una sessione peer-to-peer, che potrebbe essere una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea a due parti o un altro tipo di sessione. È possibile eseguire un join di tabella con la [tabella media](media.md) per trovare i dettagli di ogni elemento multimediale coinvolto in questa sessione.
  
Tieni presente che i campi IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone sono stati eliminati dalla tabella SessionDetails usata in Skype for Business Server 2015.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora della richiesta della sessione. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. * per altre informazioni, vedere la [tabella finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||GUID per la correlazione di più sessioni.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateTime  <br/> |Esterna  <br/> |Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Esterna  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **ReplacesDialogIdTime** per identificare in modo univoco una sessione sostituita da questa sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**User1Id** <br/> |int  <br/> |Esterna  <br/> |ID di un utente nella sessione. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**User2Id** <br/> |int  <br/> |Esterna  <br/> |ID dell'altro utente nella sessione. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID che identifica l'endpoint usato dal primo utente della sessione.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID che identifica l'endpoint usato dal secondo utente nella sessione.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Esterna  <br/> |L'originale all'URI utente nella richiesta SIP. per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**SessionStartedById** <br/> |int  <br/> |Esterna  <br/> |ID dell'utente che ha avviato la sessione. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Esterna  <br/> |Indica l'ID dell'utente di chi è il chiamante per conto. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Esterna  <br/> |ID dell'utente con cui si fa riferimento alla chiamata. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**ServerId** <br/> |int  <br/> |Esterna  <br/> |ID del server front-end usato per questa sessione. Per altre informazioni, vedere la [tabella server](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Esterna  <br/> |ID del pool in cui è stata acquisita la sessione. Per altre informazioni, vedere la [tabella pool](pools.md) . <br/> |
|**ContentTypeID** <br/> |int  <br/> |Esterna  <br/> |Tipo di contenuto usato nella sessione. Per altre informazioni, vedere la [tabella ContentTypes in Skype for Business Server 2015](contenttypes.md) . <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Esterna  <br/> |Versione client usata da User1. Per altre informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Esterna  <br/> |Versione client usata da User2. Per altre informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Esterna  <br/> |Server perimetrale usato da User1. Per altre informazioni, vedere la [tabella EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Esterna  <br/> |Edge Server usato da User2. Per altre informazioni, vedere la [tabella EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**IsUser1Internal** <br/> |po'  <br/> ||Se l'utente User1 ha effettuato l'accesso da Internal o not.  <br/> |
|**IsUser2Internal** <br/> |po'  <br/> ||Se User2 è connesso da Internal o not.  <br/> |
|**InviteTime** <br/> |DateTime  <br/> ||L'ora della prima richiesta di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO). Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseTime** <br/> |DateTime  <br/> ||L'ora della risposta al primo messaggio di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Codice di risposta SIP per l'invito alla sessione. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID di diagnostica acquisito dall'intestazione SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Esterna  <br/> |Chiama priorità. Per altre informazioni, vedere la [Tabella CallPriorities in Skype for Business Server 2015](callpriorities.md) . <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Numero di messaggi inviati da User1 durante la sessione.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Numero di messaggi inviati da User2 durante la sessione.  <br/> |
|**SessionEndTime** <br/> |DateTime  <br/> ||Ora alla fine della sessione.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Set di bit che indica il tipo di elemento multimediale della sessione. Sono elencate le definizioni dei tipi:  <br/> 1-MESSAGGISTICA ISTANTANEA  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-AUDIO  <br/> 32-VIDEO  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Set di bit che indica gli attributi User1. Sono elencate le definizioni di attributo seguenti:  <br/> 0x01-integrato con il telefono desktop  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Set di bit che indica gli attributi User2. Sono elencate le definizioni di attributo seguenti:  <br/> 0x01-integrato con il telefono desktop  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Set di bit che indica gli attributi di chiamata. Sono elencate le definizioni di attributo seguenti:  <br/> 0x01-Riprova sessione  <br/> 0x02-chiamata effettuata dall'agente per conto di un gruppo di risposte  <br/> |
|**Elaborate** <br/> |po'  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   
\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se più sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1, per un altro sarà 2 e così via.
  

