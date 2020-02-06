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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene informazioni sullo stato di conformità a livello di pool.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814634"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene informazioni sullo stato di conformità a livello di pool.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint e non null  <br/> |ID dell'evento di conformità elaborato più recente.  <br/> |
|activeServerID  <br/> |int, not null  <br/> |ID del server di conformità che contiene il blocco esclusivo nel database oppure-1 se nessuno.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Blocca ora di scadenza (se activeServerID non è-1).  <br/> |
   

