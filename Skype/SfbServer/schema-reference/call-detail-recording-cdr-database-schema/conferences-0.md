---
title: Visualizzazione Conferenze
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: Nella visualizzazione Conferenze sono archiviate informazioni sulle conferenze. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 500a03e85a3339d28227a5b65d5a3c206fc34723
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828629"
---
# <a name="conferences-view"></a>Visualizzazione Conferenze
 
Nella visualizzazione Conferenze sono archiviate informazioni sulle conferenze. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Ora della richiesta di sessione. Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI per la conferenza.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo dell'URI conferenza. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Utilizzato per conferenze ricorrenti. Ogni istanza di una conferenza ricorrente ha lo stesso ConferenceUri, ma una ConfInstance diversa.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Ora di inizio della conferenza.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Ora di fine della conferenza.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha organizzato la conferenza.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha organizzato la conferenza. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che ha organizzato la conferenza. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nome di dominio completo del pool che ha ospitato la conferenza.  <br/> |
|**Contrassegno** <br/> |smallint  <br/> |Maschera di bit che contiene attributi conferenza. I valori possibili sono:  <br/> 0X01 - Transazione sintetica  <br/> |
   

