---
title: Visualizzazione conferenze
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: La visualizzazione conferenze archivia le informazioni sulle conferenze. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 2e49a60be1651c34fb874c62bbee8c993eb00983
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194836"
---
# <a name="conferences-view"></a>Visualizzazione conferenze
 
La visualizzazione conferenze archivia le informazioni sulle conferenze. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Ora della richiesta della sessione. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI per la conferenza.  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI conferenza. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Usato per le conferenze periodiche. Ogni istanza di una conferenza ricorrente ha lo stesso ConferenceUri ma un ConfInstance diverso.  <br/> |
|**ConferenceStartTime** <br/> |DateTime  <br/> |Ora di inizio per la conferenza.  <br/> |
|**ConferenceEndTime** <br/> |DateTime  <br/> |Ora di fine per la conferenza.  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha organizzato la conferenza.  <br/> |
|**OrganizerType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha organizzato la conferenza. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**OrganizerTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente che ha organizzato la conferenza. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**Pool** <br/> |nvarchar (256)  <br/> |Nome di dominio completo del pool che ha ospitato la conferenza.  <br/> |
|**Contrassegno** <br/> |smallint  <br/> |Maschera di bit che contiene gli attributi della conferenza. I valori possibili sono:  <br/> 0X01-transazione sintetica  <br/> |
   

