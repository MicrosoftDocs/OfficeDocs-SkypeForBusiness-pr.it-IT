---
title: Visualizzazione ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 1308b0e9aeb8954df8010d0c1d55036eff1a3dac
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856523"
---
# <a name="conferencemessagecount-view"></a>Visualizzazione ConferenceMessageCount
 
La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione ConferenceMessageCount contiene tutte le colonne nella visualizzazione [ConferenceSessionDetails,](conferencesessiondetails.md) oltre alle colonne elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha inviato il messaggio.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha inviato il messaggio. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Tenant dell'utente che ha inviato i messaggi. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Numero di messaggi inviati dall'utente durante la sessione di conferenza.  <br/> |
   

