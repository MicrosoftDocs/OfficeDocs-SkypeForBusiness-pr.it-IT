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
ms.openlocfilehash: 81ee29e5b25080f841ab578214694f563c7cc6b14fe791b1c6b26dc5ea741859
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351935"
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
   

