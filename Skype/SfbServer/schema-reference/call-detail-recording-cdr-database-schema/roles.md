---
title: Tabella Ruoli
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 'La tabella Roles è una tabella statica in cui viene archiviato l''elenco di possibili ruoli per conferenze, ad esempio partecipante e relatore.'
---

# <a name="roles-table"></a>Tabella Ruoli
 
La tabella Roles è una tabella statica in cui viene archiviato l'elenco di possibili ruoli per conferenze, ad esempio partecipante e relatore.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**Ruolo** <br/> |nvarchar(256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Relatore <br/>  2 - Partecipante <br/> |
   

