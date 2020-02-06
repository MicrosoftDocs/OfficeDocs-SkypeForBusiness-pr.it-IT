---
title: Visualizzazione McuJoinsAndLeaves
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
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La Visualizzazione McuJoinsAndLeaves archivia le informazioni sugli utenti che partecipano e lasciano informazioni per un server di conferenza. Ogni record in questa visualizzazione contiene i dettagli delle chiamate su una combinazione di un utente che partecipa o abbandona e Conferencing Server. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 7a7569795d55620051e617d9312d87f3c96c628a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815094"
---
# <a name="mcujoinsandleaves-view"></a>Visualizzazione McuJoinsAndLeaves
 
La Visualizzazione McuJoinsAndLeaves archivia le informazioni sugli utenti che partecipano e lasciano informazioni per un server di conferenza. Ogni record in questa visualizzazione contiene i dettagli delle chiamate su una combinazione di un utente che partecipa o abbandona e Conferencing Server. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Ora dell'istanza di conferenza. Usato in combinazione con SessionIdSeq per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare l'istanza di conferenza. Usato in combinazione con SessionIdTime per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**McuUri** <br/> |nvarchar (256)  <br/> |URI del server dei servizi di conferenza a cui l'utente ha effettuato la connessione.  <br/> |
|**McuUriType** <br/> |nvarchar (256)  <br/> |URI del server dei servizi di conferenza a cui l'utente ha effettuato la connessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI dell'utente di cui è stata acquisita l'entrata/uscita delle informazioni sul server dei servizi di conferenza.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Il tipo di URI dell'utente di cui è stata acquisita l'immissione/uscita delle informazioni sul server di conferenza. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar (256)  <br/> |Il tenant dell'utente di cui è stata acquisita l'entrata/uscita delle informazioni sul server di conferenza. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**UserClientVersion** <br/> |nvarchar (256)  <br/> |La versione del client usata dall'utente di cui è stata acquisita l'entrata/uscita delle informazioni sul server di conferenza.  <br/> |
|**UserClientType** <br/> |int  <br/> |Il client usato dall'utente per cui sono state acquisite le informazioni di join/leave del server dei servizi di conferenza. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nome della categoria del client usata dall'utente di cui è stata acquisita l'entrata/uscita delle informazioni del server dei servizi di conferenza.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifica in modo univoco la combinazione utente/dispositivo per gli utenti che accedono simultaneamente a più dispositivi.  <br/> |
|**IsUserFromPstn** <br/> |po'  <br/> |Bit che indica se l'utente è un utente interno o meno.  <br/> |
|**DialogSessionIdTime** <br/> |DateTime  <br/> |Ora della richiesta della sessione. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |ID finestra di dialogo SIP della sessione. Il formato è: Dialog; from-tag; to-tag.  <br/> |
|**UserJoinTime** <br/> |DateTime  <br/> |Volta che l'utente ha aderito al server dei servizi di conferenza.  <br/> |
|**UserLeaveTime** <br/> |DateTime  <br/> |Volta che l'utente ha lasciato il server dei servizi di conferenza.  <br/> |
   

