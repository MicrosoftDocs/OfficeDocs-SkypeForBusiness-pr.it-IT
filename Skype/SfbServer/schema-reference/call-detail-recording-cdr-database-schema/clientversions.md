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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La Tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei vari tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta una versione client.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815404"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabella ClientVersions in Skype for Business Server 2015
 
La Tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei vari tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta una versione client.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Principale  <br/> |Numero univoco che identifica questo tipo di client e la versione.  <br/> |
|**Versione** <br/> |**nvarchar (256)** <br/> ||Nome versione.  <br/> |
|**TipoClient** <br/> |int  <br/> ||Specifica il tipo di client usato nella sessione. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

