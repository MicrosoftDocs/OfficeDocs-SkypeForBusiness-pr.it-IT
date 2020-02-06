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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabella CallType è una tabella statica in cui è archiviato l'elenco dei tipi di chiamata possibili.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815434"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabella CallType in Skype for Business Server 2015
 
La tabella CallType è una tabella statica in cui è archiviato l'elenco dei tipi di chiamata possibili.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Principale  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valori consentiti: <br/>  0--sconosciuto <br/>  1-messaggistica istantanea <br/>  2--condivisione applicazioni <br/>  3--audio <br/>  4-audio e video <br/>  5-trasferimento di file <br/> |
   

