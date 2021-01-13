---
title: Tabella ErrorDef in Skype for Business Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: Nella tabella ErrorDef vengono archiviate informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821726"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabella ErrorDef in Skype for Business Server 2015
 
Nella tabella ErrorDef vengono archiviate informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Principale  <br/> |Numero ID univoco che identifica questo tipo di errore.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Codice di risposta SIP standard associato a questo errore.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID diagnostica Microsoft.  <br/> |
|**CallTypeId** <br/> |Soglia  <br/> |Stranieri  <br/> |Tipo di chiamata. Per ulteriori informazioni, vedere la [tabella CallType in Skype for Business Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Tipo della richiesta non riuscita.  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |Tipo di contenuto della richiesta non riuscita.  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

