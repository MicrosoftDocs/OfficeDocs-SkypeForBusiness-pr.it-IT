---
title: Visualizzazione ConferenceMessageCount
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813296"
---
# <a name="conferencemessagecount-view"></a>Visualizzazione ConferenceMessageCount
 
La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione ConferenceMessageCount contiene tutte le colonne della [visualizzazione ConferenceSessionDetails](conferencesessiondetails.md) , oltre alle colonne elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha inviato il messaggio.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha inviato il messaggio. Per ulteriori informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Tenant dell'utente che ha inviato i messaggi. Per ulteriori informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Numero di messaggi inviati dall'utente durante la sessione di conferenza.  <br/> |
   

