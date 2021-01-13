---
title: Tabella user
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800076"
---
# <a name="user-table"></a>Tabella user
 
La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'utente.  <br/> |
|**URI** <br/> |nvarchar (450)  <br/> |Univoco  <br/> |Stringa URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 è un tipo di URI sconosciuto.  <br/> 2 è un URI utente.  <br/> 4 è un URI conferenza.  <br/> 8 è un URI telefono.  <br/> |
|**TenantKey** <br/> |int  <br/> |Stranieri  <br/> |Tenant dell'utente, cui viene fatto riferimento dalla tabella Tenant.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Ultimo indicatore di data e ora in cui si è verificata una chiamata audio di qualità scadente per l'utente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo per uso interno.  <br/> |
   

