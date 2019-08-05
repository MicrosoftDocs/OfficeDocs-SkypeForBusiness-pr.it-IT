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
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194731"
---
# <a name="uritypes-table"></a>Tabella UriTypes
 
La tabella UriTypes contiene i diversi tipi di URI (Uniform Resource Identifier) monitorati in Skype for Business Server 2015.

Quando viene creato il DB CDR, vengono creati due record per rappresentare PhoneUri e UserUri e i record creati dopo che sono stati assegnati in modo dinamico UriTypeId. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco assegnato a un tipo URI.  <br/> Valori possibili-da 0 a 255 |
|**UriType** <br/> |nvarchar (256)  <br/> || Descrizioni dei diversi tipi di URI. I valori seguenti sono pre-assegnati: <br/>  URI 1-Phone <br/>  0-URI utente <br/> <br/>  Altri tipi possibili includono: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf: chat<br/>    conf:focus<br/>   MRA<br/>
