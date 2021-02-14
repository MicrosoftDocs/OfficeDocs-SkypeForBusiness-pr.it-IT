---
title: Tabella DeRegisterType in Skype for Business Server
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816076"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabella DeRegisterType in Skype for Business Server
 
La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Annullamento della registrazione avviato dal client <br/>  2 - Registrazione scaduta <br/>  3 - Arresto anomalo del client <br/>  4 - Attributi utente modificati <br/>  5 - Registrar preferito modificato <br/>  6 - Client legacy in modalità di sopravvivenza <br/> |
   

