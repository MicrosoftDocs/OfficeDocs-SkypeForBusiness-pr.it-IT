---
title: Scenari di prestazioni per lo Skype for Business Server 2015 Stress and Performance Tool
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test di carico e prestazioni, utilizzando lo strumento Stress and Performance.
ms.openlocfilehash: 212a6fa1adc49508982e996ecdf61afc183d186b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611905"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scenari di prestazioni per lo Skype for Business Server 2015 Stress and Performance Tool
 
Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test di carico e prestazioni, utilizzando lo strumento Stress and Performance.
  
Per eseguire lo strumento Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), la topologia di Skype for Business Server 2015 deve prima essere configurata per gli scenari rilevanti per l'utente. Se Skype for Business Server 2015 non è configurato o non è configurato correttamente, è molto probabile che la simulazione del carico non riesca. Con lo Skype for Business Server 2015 Stress and Performance Tool, stiamo fornendo script di esempio Skype for Business Server Management Shell e file di risorse di base come parte del [download dello strumento.](https://www.microsoft.com/download/details.aspx?id=50367) Possono essere usati come punto di partenza per la configurazione della distribuzione Skype for Business Server distribuzione. In questo articolo vengono descritti Windows PowerShell esempi forniti.
  
> [!NOTE]
> In questo argomento non viene descritto come configurare Skype for Business Server 2015 in generale, sono disponibili altri argomenti relativi alla pianificazione e alla distribuzione. Per informazioni dettagliate sull'Windows PowerShell in Skype for Business Server 2015, vedere la documentazione di Skype for Business Server Management Shell all'indirizzo Insert introduction HERE. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informazioni sull'Skype for Business Server degli script di Management Shell

Microsoft fornisce script di PowerShell di esempio che è possibile usare per preparare le simulazioni di carico. Poiché questi script sono destinati alla simulazione del carico, è possibile trovarli semplici e permissivi. Potrebbe non essere appropriato per l'ambiente di produzione. Anche in questo caso si sottolinea che questi script sono esempi, è necessario esaminarli e in molti casi apportare modifiche rilevanti per l'ambiente prima di poterli utilizzare in modo pratico. Come minimo, ci si aspetterebbe che sia necessario modificare lo script RSG (Response Service Group) con la topologia in mente (per specificare gli agenti assegnati ai gruppi di agenti). Ma non è necessario eseguire questa attività, se non è necessario.
  
> [!CAUTION]
> Si prega di fare attenzione a rivedere e comprendere questi esempi. Durante l'esecuzione degli script verranno sovrascritte tutte le impostazioni esistenti nella topologia. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomi delle versioni client dello Strumento stress e prestazioni

Potrebbe essere necessario configurare il criterio Controllo versione client se in precedenza sono state modificate le impostazioni rispetto ai valori predefiniti. In caso di dubbi, consultare la documentazione relativa al controllo [della versione client](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).
  
Lo strumento Stress and Performance usa per impostazione predefinita le seguenti versioni di User Agent per comunicare con Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Per il client per dispositivi mobili (UCWA) in LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
