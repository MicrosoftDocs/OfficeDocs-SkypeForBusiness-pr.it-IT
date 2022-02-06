---
title: Visualizzazione FocusJoinsAndLeaves
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La visualizzazione FocusJoinsAndLeaves contiene informazioni sulle partecipazioni e le uscite per una conferenza. In questa visualizzazione ogni conferenza è rappresentata da un record scritto ogni volta che un utente partecipa o esce da una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
---

# <a name="focusjoinsandleaves-view"></a>Visualizzazione FocusJoinsAndLeaves
 
La visualizzazione FocusJoinsAndLeaves contiene informazioni sulle partecipazioni e le uscite per una conferenza. In questa visualizzazione ogni conferenza è rappresentata da un record scritto ogni volta che un utente partecipa o esce da una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Data e ora dell'istanza di conferenza. Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella Conferenze [Skype for Business Server 2015](conferences.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare l'istanza di conferenza. Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella Conferenze [Skype for Business Server 2015](conferences.md). <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite. Per ulteriori [informazioni, vedere la tabella UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite. Per ulteriori [informazioni, vedere la tabella Tenants](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versione del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite. Per [ulteriori dettagli, vedere UserAgentDef table](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome della categoria del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit che determina se l'utente è interno o meno.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Ora della richiesta di sessione. Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per ulteriori [informazioni, vedere la tabella Dialogs Skype for Business Server 2015](dialogs.md). <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Se un utente è connesso a più computer o dispositivi contemporaneamente, UserInstance consente di identificare in modo univoco la combinazione utente/dispositivo.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Ora in cui l'utente inizia a partecipare alla conferenza.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Ora in cui l'utente esce dalla conferenza.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Ruolo dell'utente nella conferenza, ad esempio Relatore o Partecipante.  <br/> |
   

