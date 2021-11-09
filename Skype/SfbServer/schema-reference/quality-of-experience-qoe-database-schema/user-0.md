---
title: Tabella utente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.
ms.openlocfilehash: cdb1717d8cf842450f65a4d21efc953d2c1adffe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834834"
---
# <a name="user-table"></a>Tabella utente
 
La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'utente.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Univoco  <br/> |Stringa URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 è un tipo di URI sconosciuto.  <br/> 2 è un URI utente.  <br/> 4 è un URI conferenza.  <br/> 8 è un URI telefono.  <br/> |
|**TenantKey** <br/> |int  <br/> |Foreign  <br/> |Tenant dell'utente, cui viene fatto riferimento dalla tabella Tenant.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Ultimo indicatore di data e ora in cui si è verificata una chiamata audio di qualità scadente per l'utente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo per uso interno.  <br/> |
   

