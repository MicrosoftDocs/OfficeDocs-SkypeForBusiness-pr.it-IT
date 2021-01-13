---
title: Tabella UriTypes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831686"
---
# <a name="uritypes-table"></a>Tabella UriTypes
 
La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.

Quando viene creato il database di registrazione dettagli chiamata, vengono creati due record per rappresentare PhoneUri e UserUri, nonché i record creati dopo che sono stati assegnati UriTypeId dinamicamente. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco assegnato a un tipo di URI.  <br/> Valori possibili-da 0 a 255 |
|**UriType** <br/> |nvarchar (256)  <br/> || Descrizione dei diversi tipi di URI. I valori seguenti sono preassegnati: <br/>  1-telefono URI <br/>  0-URI utente <br/> <br/>  Altri tipi possibili includono: <br/>conf: ApplicationSharing <br/> conf: audio-video<br/> conf: chat<br/>    conf: Focus<br/>   MRAS<br/>
