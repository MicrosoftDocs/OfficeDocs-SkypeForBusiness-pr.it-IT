---
title: Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire le prestazioni e i test di carico, utilizzando lo strumento stress and performance.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814706"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015
 
Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire le prestazioni e i test di carico, utilizzando lo strumento stress and performance.
  
Per eseguire lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 (LyncPerfTool), è innanzitutto necessario configurare la topologia di Skype for Business Server 2015 per gli scenari rilevanti per l'utente. Se Skype for Business Server 2015 non è configurato o è configurato in modo errato, è probabile che la simulazione di carico abbia esito negativo. Con lo strumento per lo stress e le prestazioni di Skype for Business Server 2015, vengono fornite esempi di script di gestione della shell di Skype for Business Server e file di risorse di base come parte del [download dello strumento](https://www.microsoft.com/download/details.aspx?id=50367). Questi possono essere utilizzati come punto di partenza per la configurazione della distribuzione di Skype for Business Server. In questo articolo vengono descritti gli esempi di Windows PowerShell forniti.
  
> [!NOTE]
> In questo argomento non viene descritto come configurare Skype for Business Server 2015 in genere, sono disponibili altri argomenti per la pianificazione e la distribuzione. Per informazioni dettagliate sull'utilizzo di Windows PowerShell in Skype for Business Server 2015, vedere la documentazione su Skype for Business Server Management Shell all'articolo Introduzione qui. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informazioni sull'esecuzione degli script di Skype for Business Server Management Shell

Vengono fornite esempi di script PowerShell che è possibile utilizzare per preparare le simulazioni di carico. Poiché questi script sono destinati alla simulazione del carico, è possibile trovarli come semplici e permissivi. Potrebbe non essere appropriato per l'ambiente di produzione. Anche in questo caso viene sottolineato che questi script sono campioni, è necessario esaminarli e, in molti casi, apportare modifiche rilevanti all'ambiente prima di essere in grado di utilizzarli in modo pratico. Come minimo, è prevedibile che sia necessario modificare lo script di Response Service Group (RSG) con la topologia in mente (per specificare gli agenti assegnati ai gruppi di agenti). Tuttavia, non è necessario eseguirlo, se non si ha necessità di farlo.
  
> [!CAUTION]
> Fare attenzione a controllare e comprendere questi esempi. Gli script sovrascrivono le impostazioni esistenti nella topologia quando vengono eseguite. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomi delle versioni client dello strumento di stress e prestazioni

Potrebbe essere necessario configurare i criteri di controllo della versione client se le impostazioni sono state modificate in precedenza dai valori predefiniti. In caso di dubbi, vedere la [documentazione relativa alla verifica della versione client](https://msdn.microsoft.com/vsto/jj923060).
  
Lo strumento stress and performance utilizza le seguenti versioni di agente utente per impostazione predefinita durante la comunicazione con Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (strumento di stress e prestazioni di Skype for Business Server 2015)
    
- OCPHONE/.0.522
    
Per il client Mobility (UCWA) in LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/mobile
    

