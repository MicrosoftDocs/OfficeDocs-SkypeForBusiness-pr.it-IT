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
description: UriTypes Table contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati Skype for Business Server 2015.
ms.openlocfilehash: 1e98bc879e7ddb6e2ca92d4f226284e604d22d312f9e2db8c0ff80cad89c33e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295363"
---
# <a name="uritypes-table"></a>Tabella UriTypes
 
UriTypes Table contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati Skype for Business Server 2015.

Quando viene creato il database di registrazione dei dati, vengono creati due record per rappresentare PhoneUri e UserUri e i record creati successivamente a cui viene assegnato in modo dinamico UriTypeId. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco assegnato a un tipo di URI.  <br/> Valori possibili - da 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descrizione dei diversi tipi di URI. I valori seguenti sono pre-assegnati: <br/>  1 - Uri Telefono <br/>  0 - URI utente <br/> <br/>  Altri tipi possibili includono: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
