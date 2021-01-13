---
title: Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server
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
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813056"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server
 
Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Elenco delle tabelle di conformità del server chat persistente

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Include gli eventi di conformità ancora non elaborati da tutti gli adattatori configurati.  <br/> In questa tabella sono inclusi gli eventi relativi a chat persistente, ad esempio i messaggi di chat e i download di file. Gli eventi dei partecipanti vengono registrati dalla tabella ComplianceParticipant.  <br/> I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella ComplianceFanout.  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Include i server che hanno elaborato un evento di conformità. È strettamente associata alla tabella ComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Include i partecipanti correnti per servizio chat e per server. Viene mantenuto in base agli eventi di conformità di join e parti ricevuti dal servizio chat persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene informazioni relative allo stato di conformità a livello di pool.  <br/> |
   

