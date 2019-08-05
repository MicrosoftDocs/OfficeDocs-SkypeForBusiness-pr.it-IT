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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194748"
---
# <a name="roles-table"></a>Tabella Roles
 
La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**Ruolo** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  0-sconosciuto <br/>  1-relatore <br/>  2-partecipante <br/> |
   

