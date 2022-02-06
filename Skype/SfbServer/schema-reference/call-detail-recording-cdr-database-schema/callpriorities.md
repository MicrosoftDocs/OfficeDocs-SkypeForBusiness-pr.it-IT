---
title: Tabella CallPriorities in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: 'La tabella CallPriorities è una tabella statica in cui è archiviato l''elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".'
---

# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabella CallPriorities in Skype for Business Server 2015
 
La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità di chiamata, ad esempio "emergenza", "urgente" o "normale".
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**Priorità** <br/> |nvarchar(256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Non urgente <br/>  2 - Normale <br/>  3 - Urgente <br/>  4 - Emergenza <br/> |
   

