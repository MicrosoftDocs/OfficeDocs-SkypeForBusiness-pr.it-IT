---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: a4b17a234b8efe1b661c1ebbe31a8ed34b0d5935
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854100"
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
   

