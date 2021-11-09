---
title: Tabella UriTypes
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati Skype for Business Server 2015.
ms.openlocfilehash: ed0cc7e62aba47af6622f821af785d8daf571649
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859763"
---
# <a name="uritypes-table"></a>Tabella UriTypes
 
La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati Skype for Business Server 2015.

Quando viene creato il database di registrazione chiamata, vengono creati due record per rappresentare PhoneUri e UserUri e i record creati successivamente a cui viene assegnato in modo dinamico UriTypeId. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco assegnato a un tipo di URI.  <br/> Valori possibili - da 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descrizione dei diversi tipi di URI. I valori seguenti sono pre-assegnati: <br/>  1 - URI Telefono <br/>  0 - URI utente <br/> <br/>  Altri tipi possibili includono: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
