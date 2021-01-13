---
title: Tabella Roles
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabella Roles è una tabella statica in cui viene archiviato l'elenco di possibili ruoli per conferenze, ad esempio partecipante e relatore.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809976"
---
# <a name="roles-table"></a>Tabella Roles
 
La tabella Roles è una tabella statica in cui viene archiviato l'elenco di possibili ruoli per conferenze, ad esempio partecipante e relatore.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**Ruolo** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Relatore <br/>  2 - Partecipante <br/> |
   

