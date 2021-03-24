---
title: Scenari di prestazioni per lo strumento Di stress e prestazioni di Skype for Business Server 2015
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
description: Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test di carico e prestazioni, utilizzando lo strumento Stress and Performance.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105372"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scenari di prestazioni per lo strumento Di stress e prestazioni di Skype for Business Server 2015
 
Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test di carico e prestazioni, utilizzando lo strumento Stress and Performance.
  
Per eseguire lo strumento Di stress e prestazioni di Skype for Business Server 2015 (LyncPerfTool), la topologia di Skype for Business Server 2015 deve prima essere configurata per gli scenari pertinenti. Se Skype for Business Server 2015 non è configurato o non è configurato correttamente, è molto probabile che la simulazione del carico non riesca. Con lo strumento Di stress e prestazioni di Skype for Business Server 2015, stiamo fornendo script di Skype for Business Server Management Shell di esempio e file di risorse di base come parte del [download dello strumento.](https://www.microsoft.com/download/details.aspx?id=50367) Questi possono essere usati come punto di partenza per configurare la distribuzione di Skype for Business Server. In questo articolo vengono descritti Windows PowerShell esempi forniti.
  
> [!NOTE]
> Questo argomento non ti aiuterà a descrivere come configurare Skype for Business Server 2015 in generale, abbiamo altri argomenti relativi alla pianificazione e alla distribuzione. Per informazioni dettagliate sull'Windows PowerShell in Skype for Business Server 2015, vedere la documentazione di Skype for Business Server Management Shell all'indirizzo Insert introduction HERE. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informazioni sull'esecuzione degli script di Skype for Business Server Management Shell

Microsoft fornisce script di PowerShell di esempio che è possibile usare per preparare le simulazioni di carico. Poiché questi script sono destinati alla simulazione del carico, è possibile trovarli semplici e permissivi. Potrebbe non essere appropriato per l'ambiente di produzione. Anche in questo caso si sottolinea che questi script sono esempi, è necessario esaminarli e in molti casi apportare modifiche rilevanti per l'ambiente prima di poterli utilizzare in modo pratico. Come minimo, ci si aspetterebbe che sia necessario modificare lo script RSG (Response Service Group) con la topologia in mente (per specificare gli agenti assegnati ai gruppi di agenti). Ma non è necessario eseguir, se non è necessario.
  
> [!CAUTION]
> Si prega di fare attenzione a rivedere e comprendere questi esempi. Durante l'esecuzione degli script verranno sovrascritte tutte le impostazioni esistenti nella topologia. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomi delle versioni client dello Strumento stress e prestazioni

Potrebbe essere necessario configurare il criterio Controllo versione client se in precedenza sono state modificate le impostazioni rispetto ai valori predefiniti. In caso di dubbi, consultare la documentazione relativa al controllo [della versione client](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).
  
Lo strumento Stress and Performance usa per impostazione predefinita le seguenti versioni dell'agente utente quando comunica con Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (Strumento stress e prestazioni di Skype for Business Server 2015)
    
- OCPHONE/.0.522
    
Per il client per dispositivi mobili (UCWA) in LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
