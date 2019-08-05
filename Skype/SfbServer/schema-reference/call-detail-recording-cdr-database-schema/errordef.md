---
title: Tabella ErrorDef in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabella ErrorDef archivia le informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194810"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabella ErrorDef in Skype for Business Server 2015
 
La tabella ErrorDef archivia le informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Principale  <br/> |Numero ID univoco che identifica questo tipo di errore.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Codice di risposta SIP standard associato a questo errore.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID diagnostica Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Esterna  <br/> |Tipo di chiamata. Per altre informazioni, vedere la [tabella CallType in Skype for Business Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Tipo di richiesta non riuscita.  <br/> Questi dati possono essere convertiti in formato testo usando la sintassi seguente:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |Tipo di contenuto della richiesta non riuscita.  <br/> Questi dati possono essere convertiti in formato testo usando la sintassi seguente:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

