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
ms.localizationpriority: medium
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: Nella tabella ErrorDef sono archiviate informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
ms.openlocfilehash: 4d10e5c8a83e486fe16808a3cf5f38f7ffd15937
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615532"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabella ErrorDef in Skype for Business Server 2015
 
Nella tabella ErrorDef sono archiviate informazioni su ogni tipo di errore che può verificarsi. Ogni record è un tipo di errore.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Principale  <br/> |Numero ID univoco che identifica questo tipo di errore.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Codice di risposta SIP standard associato a questo errore.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID diagnostica Microsoft.  <br/> |
|**CallTypeId** <br/> |Soglia  <br/> |Foreign  <br/> |Tipo di chiamata. Per ulteriori informazioni, vedere la tabella [CallType Skype for Business Server 2015.](calltype.md) <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Tipo della richiesta non riuscita.  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Tipo di contenuto della richiesta non riuscita.  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

