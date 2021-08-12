---
title: Tabella DeRegisterType Skype for Business Server 2015
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
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione da parte dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".
ms.openlocfilehash: 606065f0442043d660c917c61b89111b48679145088b4eba9a7a80e668248161
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347791"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabella DeRegisterType Skype for Business Server 2015
 
La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione da parte dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1 - Annullamento della registrazione avviato dal client <br/>  2 - Registrazione scaduta <br/>  3 - Arresto anomalo del client <br/>  4 - Attributi utente modificati <br/>  5 - Registrar preferito modificato <br/>  6 - Client legacy in modalità sopravvivenza <br/> |
   

