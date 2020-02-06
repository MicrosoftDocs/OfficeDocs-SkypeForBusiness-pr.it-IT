---
title: Tabella Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814934"
---
# <a name="roles-table"></a>Tabella Roles
 
La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**Ruolo** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  0-sconosciuto <br/>  1-relatore <br/>  2-partecipante <br/> |
   

