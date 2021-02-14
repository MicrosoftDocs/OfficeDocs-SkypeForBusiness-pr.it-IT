---
title: Tabella ConferenceUris in Skype for Business Server
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabella ConferenceUris è una tabella di supporto in cui viene archiviato un elenco dei diversi URI conferenza che hanno partecipato a sessioni di conferenze registrate nel database. Ogni record della tabella rappresenta un URI conferenza.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816136"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabella ConferenceUris in Skype for Business Server
 
La tabella ConferenceUris è una tabella di supporto in cui viene archiviato un elenco dei diversi URI conferenza che hanno partecipato a sessioni di conferenze registrate nel database. Ogni record della tabella rappresenta un URI conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Principale  <br/> |Timestamp, utilizzo interno.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'URI della conferenza.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI della conferenza.  <br/> |
|**Checksum** <br/> |int  <br/> ||Checksum di ConferenceUri. Utilizzato per aumentare la velocità delle ricerche nel database.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Esterna  <br/> |Tipo di URI, ad esempio conf:chat per la conferenza di messaggistica istantanea o conf:audio-video per la conferenza audio e video. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
   

