---
title: Tabella CallType in Skype for Business Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabella CallType è una tabella statica in cui viene archiviato l'elenco dei tipi di chiamata possibili.
ms.openlocfilehash: 05bfcf5b13735a460f8122fc6b1ce5eeddf94b97
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743192"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabella CallType in Skype for Business Server 2015
 
La tabella CallType è una tabella statica in cui viene archiviato l'elenco dei tipi di chiamata possibili.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Principale  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Messaggistica istantanea <br/>  2 - Condivisione applicazioni <br/>  3 - Audio <br/>  4 - Audio e Video <br/>  5 - Trasferimento file <br/> |
   

