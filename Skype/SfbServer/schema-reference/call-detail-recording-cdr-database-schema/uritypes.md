---
title: Tabella UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814844"
---
# <a name="uritypes-table"></a>Tabella UriTypes
 
La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.

Quando viene creato il DB CDR, vengono creati due record per rappresentare PhoneUri e UserUri e i record creati dopo che sono stati assegnati in modo dinamico UriTypeId. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco assegnato a un tipo URI.  <br/> Valori possibili-da 0 a 255 |
|**UriType** <br/> |nvarchar (256)  <br/> || Descrizioni dei diversi tipi di URI. I valori seguenti sono pre-assegnati: <br/>  URI 1-Phone <br/>  0-URI utente <br/> <br/>  Altri tipi possibili includono: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf: chat<br/>    conf:focus<br/>   MRA<br/>
