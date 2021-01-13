---
title: Tabella DeRegisterType in Skype for Business Server 2015
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
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio ' client avviato ',' Registrazione scaduta ' oppure ' client interrotto la risposta '.
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816076"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabella DeRegisterType in Skype for Business Server 2015
 
La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio ' client avviato ',' Registrazione scaduta ' oppure ' client interrotto la risposta '.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principale  <br/> ||
|**DeRegisterReason** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  0 - Sconosciuto <br/>  1-annullamento della registrazione avviata dal client <br/>  2-Registrazione scaduta <br/>  3-client bloccato <br/>  4-attributi degli utenti modificati <br/>  5-registrar preferito cambiato <br/>  6-client legacy in modalità sopravvivenza <br/> |
   

