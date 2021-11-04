---
title: Tabella DeRegisterType in Skype for Business Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione da parte dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".
ms.openlocfilehash: f369416a15f0b1c024dd70fbe97042193940f669
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743992"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabella DeRegisterType in Skype for Business Server 2015
 
La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione da parte dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Annullamento della registrazione avviato dal client <br/>  2 - Registrazione scaduta <br/>  3 - Arresto anomalo del client <br/>  4 - Attributi utente modificati <br/>  5 - Registrar preferito modificato <br/>  6 - Client legacy in modalità sopravvivenza <br/> |
   

