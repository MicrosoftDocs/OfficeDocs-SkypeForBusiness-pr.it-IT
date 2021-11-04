---
title: Visualizzazione McuJoinsAndLeaves
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La visualizzazione McuJoinsAndLeaves contiene informazioni sulla partecipazione e l'abbandono da parte degli utenti in un server per conferenze. In ogni record di questa visualizzazione sono inclusi dettagli di chiamata su una combinazione di partecipazione o abbandono di un utente e un server per conferenze. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 509eca981381b052962ac516a1b0d5537e8c27f1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763334"
---
# <a name="mcujoinsandleaves-view"></a>Visualizzazione McuJoinsAndLeaves
 
La visualizzazione McuJoinsAndLeaves contiene informazioni sulla partecipazione e l'abbandono da parte degli utenti in un server per conferenze. In ogni record di questa visualizzazione sono inclusi dettagli di chiamata su una combinazione di partecipazione o abbandono di un utente e un server per conferenze. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Data e ora dell'istanza di conferenza. Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella [Conferenze Skype for Business Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare l'istanza di conferenza. Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella [Conferenze Skype for Business Server 2015.](conferences.md) <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |URI del server per le conferenze al quale l'utente è connesso.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |URI del server per le conferenze al quale l'utente è connesso. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versione del client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte. Per ulteriori dettagli, vedere la [tabella UserAgentDef.](useragentdef.md) <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome di categoria del client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifica in maniera univoca la combinazione utente/dispositivo per gli utenti connessi a più di un dispositivo contemporaneamente.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit che determina se l'utente è interno o meno.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Ora della richiesta di sessione. Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Ora di connessione dell'utente al server per conferenze.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Ora di disconnessione dell'utente dal server per conferenze.  <br/> |
   

