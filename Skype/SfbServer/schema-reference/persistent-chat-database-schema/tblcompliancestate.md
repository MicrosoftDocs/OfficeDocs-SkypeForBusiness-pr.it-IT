---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene informazioni sullo stato di conformità a livello di pool.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194692"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene informazioni sullo stato di conformità a livello di pool.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint e non null  <br/> |ID dell'evento di conformità elaborato più recente.  <br/> |
|activeServerID  <br/> |int, not null  <br/> |ID del server di conformità che contiene il blocco esclusivo nel database oppure-1 se nessuno.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Blocca ora di scadenza (se activeServerID non è-1).  <br/> |
   

