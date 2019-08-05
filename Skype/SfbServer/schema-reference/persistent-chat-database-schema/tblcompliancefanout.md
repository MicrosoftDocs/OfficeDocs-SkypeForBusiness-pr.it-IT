---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene tutti i server che hanno elaborato un evento di conformità.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194694"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout contiene tutti i server che hanno elaborato un evento di conformità.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identità del server (corrispondente alla tabella tblServerIdentity. serverID).  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|fanoutEventID  <br/> |Chiave esterna con ricerca nella tabella tblComplianceData. cmplEventID.  <br/> |
   

