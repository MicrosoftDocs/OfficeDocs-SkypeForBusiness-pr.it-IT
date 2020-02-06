---
title: Visualizzazione FocusJoinsAndLeaves
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
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La visualizzazione FocusJoinsAndLeaves archivia le informazioni su come partecipare e abbandonare informazioni per una conferenza. Ogni conferenza viene rappresentata in questa visualizzazione da un record scritto ogni volta che un utente si unisce e lascia la conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 771685a5546ef5b462a3ce3955406eb535f4c3eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815194"
---
# <a name="focusjoinsandleaves-view"></a>Visualizzazione FocusJoinsAndLeaves
 
La visualizzazione FocusJoinsAndLeaves archivia le informazioni su come partecipare e abbandonare informazioni per una conferenza. Ogni conferenza viene rappresentata in questa visualizzazione da un record scritto ogni volta che un utente si unisce e lascia la conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Ora dell'istanza di conferenza. Usato in combinazione con SessionIdSeq per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare l'istanza di conferenza. Usato in combinazione con SessionIdTime per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'utente per cui sono state acquisite le informazioni di join/leave di conferenza.  <br/> |
|**UserClientVersion** <br/> |nvarchar (256)  <br/> |Versione del client usata dall'utente in cui sono state acquisite le informazioni di join/leave di conferenza.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client usato dall'utente per cui sono state acquisite le informazioni di join/congedo di conferenza. Per altri dettagli, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nome della categoria del client usata dall'utente in cui sono state acquisite le informazioni di join/leave di conferenza.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |po'  <br/> |Bit che indica se l'utente è un utente interno o meno.  <br/> |
|**DialogSessionIdTime** <br/> |DateTime  <br/> |Ora della richiesta della sessione. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Se un utente ha eseguito l'accesso a più computer o dispositivi contemporaneamente, UserInstance viene usato per identificare in modo univoco la combinazione utente/dispositivo.  <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |ID finestra di dialogo SIP della sessione. Il formato è: Dialog; from-tag; to-tag.  <br/> |
|**UserJoinTime** <br/> |DateTime  <br/> |Ora in cui l'utente ha partecipato alla conferenza.  <br/> |
|**UserLeaveTime** <br/> |DateTime  <br/> |Ora in cui l'utente ha lasciato la conferenza.  <br/> |
|**UserRole** <br/> |nvarchar (256)  <br/> |Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.  <br/> |
   

