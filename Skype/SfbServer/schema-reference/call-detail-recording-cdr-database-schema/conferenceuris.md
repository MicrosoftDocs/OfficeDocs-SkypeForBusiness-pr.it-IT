---
title: Tabella ConferenceUris in Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabella ConferenceUris è una tabella di supporto in cui viene archiviato un elenco dei diversi URI conferenza che hanno partecipato a sessioni di conferenze registrate nel database. Ogni record della tabella rappresenta un URI conferenza.
ms.openlocfilehash: 7d7f0ea8504faa3e23d981a74e65062fdb6d5836
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744022"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabella ConferenceUris in Skype for Business Server 2015
 
La tabella ConferenceUris è una tabella di supporto in cui viene archiviato un elenco dei diversi URI conferenza che hanno partecipato a sessioni di conferenze registrate nel database. Ogni record della tabella rappresenta un URI conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Principale  <br/> |Timestamp, utilizzo interno.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'URI della conferenza.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI della conferenza.  <br/> |
|**Checksum** <br/> |int  <br/> ||Checksum di ConferenceUri. Utilizzato per aumentare la velocità delle ricerche nel database.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Tipo di URI, ad esempio conf:chat per la conferenza di messaggistica istantanea o conf:audio-video per la conferenza audio e video. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
   

