---
title: Dettagli della visualizzazione QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Le viste disponibili soddisfano gli scenari più comuni per la restituzione di dati dal database di SQL Server QoE. È consigliabile utilizzare le visualizzazioni per la creazione di report personalizzati anziché accedere direttamente alle tabelle di database. questo perché è più probabile che le visualizzazioni mantengano la compatibilità con le versioni future.
ms.openlocfilehash: 5e0a4b4c83d6cc2b04eb2075e8f6248a0061cbdb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741772"
---
# <a name="qoe-view-details"></a>Dettagli della visualizzazione QoE
 
Le viste disponibili soddisfano gli scenari più comuni per la restituzione di dati dal database di SQL Server QoE. È consigliabile utilizzare le visualizzazioni per la creazione di report personalizzati anziché accedere direttamente alle tabelle di database. questo perché è più probabile che le visualizzazioni mantengano la compatibilità con le versioni future.
  
|**Nome visualizzazione**|**Descrizione**|
|:-----|:-----|
|[Visualizzazione AudioStreamDetail](audiostreamdetail.md) <br/> |Archivia informazioni su ogni flusso audio nel database.  <br/> |
|[Visualizzazione MediaLine](medialine.md) <br/> |Archivia le informazioni su ogni linea multimediale nel database. Una sessione audio in genere contiene una linea multimediale audio. Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta.  <br/> |
|[Visualizzazione NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Archivia informazioni sulla configurazione della rete.  <br/> |
|[Visualizzazione sessione](session-0.md) <br/> |Archivia informazioni sulle sessioni con record nel database.  <br/> |
|[Visualizzazione UserAgent](useragent-0.md) <br/> |Archivia informazioni sugli agenti utenti coinvolti nelle sessioni con record nel database.  <br/> |
|[Visualizzazione VideoStreamDetail](videostreamdetail.md) <br/> |Archivia informazioni su ogni flusso video nel database.  <br/> |
   

