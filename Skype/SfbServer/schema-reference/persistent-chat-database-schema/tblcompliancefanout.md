---
title: tblComplianceFanout
ms.reviewer: ''
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout include i server che hanno elaborato un evento di conformità.
ms.openlocfilehash: fdddd6bc1157e76ff94d86d6553da3a7308cd0f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420879"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout include i server che hanno elaborato un evento di conformità.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identità del server (corrispondente alla tabella tblServerIdentity.serverID).  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|fanoutEventID  <br/> |Chiave esterna con ricerca nella tabella tblComplianceData.cmplEventID.  <br/> |
   

