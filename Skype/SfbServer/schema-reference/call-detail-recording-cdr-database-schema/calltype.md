---
title: Tabella CallType in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabella CallType è una tabella statica in cui è archiviato l'elenco dei tipi di chiamata possibili.
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194849"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabella CallType in Skype for Business Server 2015
 
La tabella CallType è una tabella statica in cui è archiviato l'elenco dei tipi di chiamata possibili.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Principale  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valori consentiti: <br/>  0--sconosciuto <br/>  1-messaggistica istantanea <br/>  2--condivisione applicazioni <br/>  3--audio <br/>  4-audio e video <br/>  5-trasferimento di file <br/> |
   

