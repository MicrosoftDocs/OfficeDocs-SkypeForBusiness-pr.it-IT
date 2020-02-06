---
title: Tabella CallPriorities in Skype for Business Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815444"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabella CallPriorities in Skype for Business Server 2015
 
La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**Priorità** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  0-sconosciuto <br/>  1-non urgente <br/>  2-normale <br/>  3-urgente <br/>  4-emergenza <br/> |
   

