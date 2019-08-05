---
title: Tabella ClientVersions in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La Tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei vari tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta una versione client.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194842"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabella ClientVersions in Skype for Business Server 2015
 
La Tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei vari tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta una versione client.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Principale  <br/> |Numero univoco che identifica questo tipo di client e la versione.  <br/> |
|**Versione** <br/> |**nvarchar (256)** <br/> ||Nome versione.  <br/> |
|**TipoClient** <br/> |int  <br/> ||Specifica il tipo di client usato nella sessione. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

