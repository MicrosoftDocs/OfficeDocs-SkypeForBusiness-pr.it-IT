---
title: Scenari di prestazioni per lo strumento Skype for Business Server 2015 Stress and Performance
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
description: Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test delle prestazioni e del carico, utilizzando lo strumento Stress and Performance.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814706"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scenari di prestazioni per lo strumento Skype for Business Server 2015 Stress and Performance
 
Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test delle prestazioni e del carico, utilizzando lo strumento Stress and Performance.
  
Per eseguire lo strumento Skype for Business Server 2015 Stress and Performance (LyncPerfTool), la topologia di Skype for Business Server 2015 deve prima essere configurata per gli scenari pertinenti. Se Skype for Business Server 2015 non è configurato o non è configurato correttamente, è molto probabile che la simulazione del carico non riesca. Con lo strumento Skype for Business Server 2015 Stress and Performance, stiamo fornendo script di esempio di Skype for Business Server Management Shell e file di risorse di base come parte del [download dello strumento.](https://www.microsoft.com/download/details.aspx?id=50367) Questi possono essere usati come punto di partenza per configurare la distribuzione di Skype for Business Server. In questo articolo vengono descritti Windows PowerShell esempi forniti.
  
> [!NOTE]
> In questo argomento non viene descritto come configurare Skype for Business Server 2015 in generale, sono disponibili altri argomenti relativi alla pianificazione e alla distribuzione. Per informazioni dettagliate sull'Windows PowerShell in Skype for Business Server 2015, vedere la documentazione di Skype for Business Server Management Shell in Insert introduction HERE. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informazioni sull'esecuzione degli script di Skype for Business Server Management Shell

Microsoft fornisce script di PowerShell di esempio che è possibile usare per preparare le simulazioni di carico. Poiché questi script sono destinati alla simulazione del carico, saranno semplici e permissivi. Potrebbe non essere appropriato per l'ambiente di produzione. Anche in questo caso si sottolinea che questi script sono esempi, è necessario esaminarli e in molti casi apportare modifiche rilevanti per il proprio ambiente prima di poterli utilizzare in modo pratico. Come minimo, ci si aspetterebbe che sia necessario modificare lo script di Response Service Group (RSG) con la topologia in considerazione (per specificare gli agenti assegnati ai gruppi di agenti). Ma non è necessario eseguire questa, se non è necessario.
  
> [!CAUTION]
> Si prega di esaminare e comprendere questi esempi. Durante l'esecuzione, gli script sovrascriveranno le impostazioni esistenti nella topologia. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomi delle versioni client dello Strumento stress e prestazioni

Potrebbe essere necessario configurare il criterio Controllo versione client se in precedenza sono state modificate le impostazioni rispetto ai valori predefiniti. In caso di dubbi, consultare la documentazione relativa al controllo [della versione client.](https://msdn.microsoft.com/vsto/jj923060)
  
Lo strumento Stress and Performance usa le seguenti versioni agente utente per impostazione predefinita quando comunica con Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Per il client per dispositivi mobili (UCWA) in LyncPerfTool:
  
- Strumento UCWA Perf/Conferenza Web
    
- UCWA Perf Tool/Mobile
    

