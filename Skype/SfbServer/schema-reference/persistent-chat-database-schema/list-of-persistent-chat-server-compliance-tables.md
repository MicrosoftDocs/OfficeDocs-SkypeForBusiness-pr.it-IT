---
title: Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.
ms.openlocfilehash: 673fe278f4b68af5e5d46925a6ef6184cb8cd47b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771892"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server
 
Lo schema del database di conformità di Persistent Chat è costituito dalle tabelle seguenti.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Elenco delle tabelle di conformità del server chat persistente

|**Tavolo**|**Descrizione**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Include gli eventi di conformità ancora non elaborati da tutti gli adattatori configurati.  <br/> Questa tabella include eventi correlati a Persistent Chat, ad esempio messaggi di chat e download di file. Gli eventi dei partecipanti vengono registrati dalla tabella ComplianceParticipant.  <br/> I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella ComplianceFanout.  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Include i server che hanno elaborato un evento di conformità. È strettamente associata alla tabella ComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Include i partecipanti correnti per servizio chat e per server. Viene gestito in base agli eventi di conformità di parte e di partecipazione ricevuti dal servizio Persistent Chat.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene informazioni relative allo stato di conformità a livello di pool.  <br/> |
   

