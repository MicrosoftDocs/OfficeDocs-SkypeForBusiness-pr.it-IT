---
title: Dettagli della visualizzazione QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Le viste disponibili soddisfano gli scenari più comuni per la restituzione di dati dal database di SQL Server QoE. È consigliabile utilizzare le visualizzazioni per la creazione di report personalizzati anziché accedere direttamente alle tabelle di database. questo perché è più probabile che le visualizzazioni mantengano la compatibilità con le versioni future.
ms.openlocfilehash: f8d6536522a04623f150ab03ba448af8c55bd401adc8e4484ac47d1cf48ccffa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347721"
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
   

