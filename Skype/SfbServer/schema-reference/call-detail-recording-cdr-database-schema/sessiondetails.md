---
title: Tabella SessionDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Ogni record rappresenta una sessione peer-to-peer, ovvero una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea con due partecipanti o un altro tipo di sessione. È possibile eseguire un table join con la tabella Media per trovare i dettagli di ogni supporto coinvolto in questa sessione.
ms.openlocfilehash: 2dee827e93da94378e529964b2911ff1f79793ef
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762024"
---
# <a name="sessiondetails-table"></a>Tabella SessionDetails
 
Ogni record rappresenta una sessione peer-to-peer, ovvero una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea con due partecipanti o un altro tipo di sessione. È possibile eseguire un table join con la [tabella Media per](media.md) trovare i dettagli di ogni supporto coinvolto in questa sessione.
  
Si noti che i campi IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone sono stati eliminati dalla tabella SessionDetails utilizzata Skype for Business Server 2015.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare la sessione. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione.* Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md) <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||GUID per correlare più sessioni.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |Numero ID per l'identificazione della finestra di dialogo sostituita dalla sessione corrente. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |Numero ID per l'identificazione della sessione. Valore utilizzato in combinazione con **ReplacesDialogIdTime** per identificare in modo univoco una sessione sostituita da questa sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**User1Id** <br/> |int  <br/> |Foreign  <br/> |ID di un utente nella sessione. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**User2Id** <br/> |int  <br/> |Foreign  <br/> |ID dell'altro utente nella sessione. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID che identifica l'endpoint utilizzato dal primo utente della sessione.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID che identifica l'endpoint utilizzato dal secondo utente della sessione.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Foreign  <br/> |URI utente di destinazione originale nella richiesta SIP. per [ulteriori informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Foreign  <br/> |ID dell'utente che ha avviato la sessione. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |Indica l'ID dell'utente per conto del quale il chiamante esegue la chiamata. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |ID dell'utente da quale proviene la chiamata. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |ID del Front End Server utilizzato per questa sessione. Per ulteriori [informazioni, vedere](servers.md) la tabella Servers. <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |ID del pool in cui è stata acquisita la sessione. Per ulteriori [informazioni, vedere](pools.md) la tabella Pools. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Foreign  <br/> |Tipo di contenuto utilizzato nella sessione. Per ulteriori informazioni, vedere [la tabella ContentTypes Skype for Business Server 2015.](contenttypes.md) <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Foreign  <br/> |Versione del client utilizzata da User1. Per ulteriori informazioni, vedere la tabella [ClientVersions Skype for Business Server 2015.](clientversions.md) <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Foreign  <br/> |Versione del client utilizzata da User2. Per ulteriori informazioni, vedere la tabella [ClientVersions Skype for Business Server 2015.](clientversions.md) <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |Server perimetrale utilizzato da User1. Per ulteriori informazioni, vedere la tabella [EdgeServers Skype for Business Server 2015.](edgeservers.md) <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |Server perimetrale utilizzato da User2. Per ulteriori informazioni, vedere la tabella [EdgeServers Skype for Business Server 2015.](edgeservers.md) <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Indica se User1 è connesso o meno dall'interno.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Indica se User2 è connesso o meno dall'interno.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Ora della prima richiesta INVITE. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non esiste un messaggio INVITE, il campo conterrà data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO). I dati contenuti in questo campo sono, tipicamente, quelli generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Ora della risposta al primo messaggio INVITE. I dati contenuti in questo campo sono, tipicamente, quelli generati dal messaggio INVITE iniziale nella sessione. Se non esiste un messaggio INVITE, il campo conterrà data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID diagnostica acquisito dall'intestazione SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Foreign  <br/> |Priorità della chiamata. Per ulteriori informazioni, vedere la tabella [CallPriorities Skype for Business Server 2015.](callpriorities.md) <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Numero di messaggi inviati da User1 durante la sessione.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Numero di messaggi inviati da User2 durante la sessione.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Orario al termine della sessione.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Set di bit che indica il tipo di contenuto multimediale della sessione. Di seguito sono elencate le definizioni dei tipi:  <br/> 1- Messaggistica istantanea  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- AUDIO  <br/> 32- VIDEO  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Set di bit che indica gli attributi di User1. Sono elencate le definizioni di attributo seguenti:  <br/> 0x01 - Integrato con telefono da tavolo  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Set di bit che indica gli attributi di User2. Sono elencate le definizioni di attributo seguenti:  <br/> 0x01 - Integrato con telefono da tavolo  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Set di bit che indica gli attributi della chiamata. Sono elencate le definizioni di attributo seguenti:  <br/> 0x01 - Nuovi tentativi di sessione  <br/> 0x02 - Chiamata effettuata da un agente per conto di un Response Group  <br/> |
|**Elaborato** <br/> |bit  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto Skype for Business Server 2015.  <br/> |
   
\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se più sessioni iniziano esattamente alla stessa ora, il valore SessionIdSeq per una sarà 1, per l'altra sarà 2 e così via.
  

