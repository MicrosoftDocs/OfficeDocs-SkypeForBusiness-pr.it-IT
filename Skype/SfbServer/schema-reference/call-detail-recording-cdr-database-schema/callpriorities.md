---
title: Tabella CallPriorities in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".
ms.openlocfilehash: 21924d712ff4ee658f757911ce168fe8b662357d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743212"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabella CallPriorities in Skype for Business Server 2015
 
La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**Priorità** <br/> |nvarchar(256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Non urgente <br/>  2 - Normale <br/>  3 - Urgente <br/>  4 - Emergenza <br/> |
   

