---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout include i server che hanno elaborato un evento di conformità.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809796"
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
   

