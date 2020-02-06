---
title: Tabella ConferenceUris in Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabella ConfereneUris è una tabella di supporto in cui è archiviato un elenco dei vari URI di conferenza che hanno partecipato a sessioni di conferenza registrate nel database. Ogni record nella tabella rappresenta un URI di conferenza.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815314"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabella ConferenceUris in Skype for Business Server 2015
 
La tabella ConfereneUris è una tabella di supporto in cui è archiviato un elenco dei vari URI di conferenza che hanno partecipato a sessioni di conferenza registrate nel database. Ogni record nella tabella rappresenta un URI di conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateTime  <br/> |Principale  <br/> |Indicatore di data e ora, interno usato.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo URI della conferenza.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||URI conferenza.  <br/> |
|**Checksum** <br/> |int  <br/> ||Checksum di ConferenceUri. Usato per aumentare la velocità delle ricerche nel database.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Esterna  <br/> |Tipo di URI, ad esempio conf: chat per la conferenza di messaggistica istantanea o conf: audio-video per conferenze audio/video. Per altre informazioni, vedere la tabella [tabella UriTypes](uritypes.md) . <br/> |
   

