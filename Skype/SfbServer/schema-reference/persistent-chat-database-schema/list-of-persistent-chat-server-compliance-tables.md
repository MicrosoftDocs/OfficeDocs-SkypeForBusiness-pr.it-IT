---
title: Elenco delle tabelle di conformità Persistent Chat Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Lo schema del database di conformità della chat persistente è costituito dalle tabelle seguenti.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194716"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Elenco delle tabelle di conformità Persistent Chat Server in Skype for Business Server
 
Lo schema del database di conformità della chat persistente è costituito dalle tabelle seguenti.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Elenco delle tabelle di conformità Persistent Chat Server

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda configurata.  <br/> Questa tabella include eventi relativi alla chat persistente, ad esempio messaggi di chat e download di file. (Gli eventi dei partecipanti vengono registrati dalla tabella tblComplianceParticipant).  <br/> I server che hanno elaborato gli eventi in questa tabella sono elencati nella tabella tblComplianceFanout.  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contiene i server che hanno elaborato un evento di conformità. Questa tabella è strettamente associata alla tabella tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contiene partecipanti correnti per servizio di chat e per server. Viene mantenuto in base agli eventi di conformità di join e part ricevuti dal servizio chat persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene informazioni sullo stato di conformità a livello di pool.  <br/> |
   

