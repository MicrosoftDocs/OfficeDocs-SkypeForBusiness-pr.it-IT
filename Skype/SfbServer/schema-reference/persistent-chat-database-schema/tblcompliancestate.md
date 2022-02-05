---
title: tblComplianceState
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.
---

# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, not null  <br/> |ID dell'ultimo evento di conformità elaborato.  <br/> |
|activeServerID  <br/> |int, not null  <br/> |ID del server di conformità che detiene il blocco esclusivo sul database, o -1 se assente.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Ora di scadenza del blocco (se activeServerID è diverso da  -1).  <br/> |
   

