---
title: Visualizzazione ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La visualizzazione ConferenceMessageCount archivia le informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815384"
---
# <a name="conferencemessagecount-view"></a>Visualizzazione ConferenceMessageCount
 
La visualizzazione ConferenceMessageCount archivia le informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione ConferenceMessageCount contiene tutte le colonne della [visualizzazione ConferenceSessionDetails](conferencesessiondetails.md) , oltre alle colonne elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha inviato il messaggio.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha inviato i messaggi. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Tenant dell'utente che ha inviato i messaggi. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Numero di messaggi inviati dall'utente durante la sessione di conferenza.  <br/> |
   

