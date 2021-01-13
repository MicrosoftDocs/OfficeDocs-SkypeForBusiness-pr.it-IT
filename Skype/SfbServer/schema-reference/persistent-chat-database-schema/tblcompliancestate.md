---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809726"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, not null  <br/> |ID dell'ultimo evento di conformità elaborato.  <br/> |
|activeServerID  <br/> |int, not null  <br/> |ID del server di conformità che detiene il blocco esclusivo sul database, o -1 se assente.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Ora di scadenza del blocco (se activeServerID è diverso da  -1).  <br/> |
   

