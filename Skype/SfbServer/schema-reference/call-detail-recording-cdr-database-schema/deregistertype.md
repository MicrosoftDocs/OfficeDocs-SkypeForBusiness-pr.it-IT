---
title: Tabella DeRegisterType in Skype for Business Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio "client avviato", "Registrazione scaduta" o "client smesso di rispondere".
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815294"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabella DeRegisterType in Skype for Business Server 2015
 
La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio "client avviato", "Registrazione scaduta" o "client smesso di rispondere".
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**DeRegisterReason** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  0--sconosciuto <br/>  1--annullamento della registrazione avviata dal client <br/>  2--Registrazione scaduta <br/>  3-client arrestato <br/>  4--attributi utente modificati <br/>  5-modifica del registrar preferito <br/>  6--client legacy in modalità Survival <br/> |
   

