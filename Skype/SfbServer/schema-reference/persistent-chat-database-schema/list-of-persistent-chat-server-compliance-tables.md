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
ms.openlocfilehash: b41d8a3f3c5e42f9e4c29eeb6cb81774b5b177aee18c67dc52bc4c9009f67c8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303669"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server
 
Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Elenco delle tabelle di conformità del server chat persistente

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Include gli eventi di conformità ancora non elaborati da tutti gli adattatori configurati.  <br/> Questa tabella include eventi correlati a Persistent Chat, ad esempio messaggi di chat e download di file. Gli eventi dei partecipanti vengono registrati dalla tabella ComplianceParticipant.  <br/> I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella ComplianceFanout.  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Include i server che hanno elaborato un evento di conformità. È strettamente associata alla tabella ComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Include i partecipanti correnti per servizio chat e per server. Viene gestito in base agli eventi di conformità di parte e di partecipazione ricevuti dal servizio Persistent Chat.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene informazioni relative allo stato di conformità a livello di pool.  <br/> |
   

