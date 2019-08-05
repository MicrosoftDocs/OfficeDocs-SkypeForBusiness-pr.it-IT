---
title: Tabella User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabella utente è una tabella di supporto in cui è archiviato un elenco dei vari utenti che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un solo utente.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194571"
---
# <a name="user-table"></a>Tabella User
 
La tabella utente è una tabella di supporto in cui è archiviato un elenco dei vari utenti che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un solo utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo utente.  <br/> |
|**URI** <br/> |nvarchar (450)  <br/> |Univoci  <br/> |Stringa URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 è un tipo URI sconosciuto.  <br/> 2 è l'URI dell'utente.  <br/> 4 è l'URI della conferenza.  <br/> 8 è l'URI del telefono.  <br/> |
|**TenantKey** <br/> |int  <br/> |Esterna  <br/> |Tenant dell'utente, a cui si fa riferimento dalla tabella tenant.  <br/> |
|**LastPoorCallTime** <br/> |DateTime  <br/> ||Indicatore di data e ora più recente quando l'utente ha ricevuto una chiamata audio scadente.  <br/> |
|**NextUpdateTS** <br/> |DateTime  <br/> ||Solo per uso interno.  <br/> |
   

