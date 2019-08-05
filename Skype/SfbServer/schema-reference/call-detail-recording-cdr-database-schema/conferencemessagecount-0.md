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
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La visualizzazione ConferenceMessageCount archivia le informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194840"
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
   

