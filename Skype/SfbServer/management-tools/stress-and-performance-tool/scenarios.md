---
title: Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire prestazioni e test di carico, usando lo strumento stress e prestazioni.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803876"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015
 
Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire prestazioni e test di carico, usando lo strumento stress e prestazioni.
  
Per eseguire lo strumento di stress e prestazioni di Skype for Business Server 2015 (LyncPerfTool), la topologia di Skype for Business Server 2015 deve prima essere configurata per gli scenari rilevanti. Se Skype for Business Server 2015 non è configurato o è configurato in modo errato, è probabile che la simulazione di caricamento non riesca. Con lo strumento di stress e prestazioni di Skype for Business Server 2015, stiamo fornendo gli script di Skype for Business Server Management Shell di esempio e i file di risorse di base come parte del [download dello strumento](https://www.microsoft.com/download/details.aspx?id=50367). Questi possono essere usati come punto di partenza per configurare la distribuzione di Skype for Business Server. In questo articolo vengono illustrati gli esempi di Windows PowerShell forniti.
  
> [!NOTE]
> Questo argomento non ti aiuterà a descrivere come configurare Skype for Business Server 2015 in generale, abbiamo altri argomenti per la pianificazione e la distribuzione. Per informazioni dettagliate sull'uso di Windows PowerShell in Skype for Business Server 2015, vedere la documentazione di Skype for Business Server Management Shell in Inserisci introduzione qui. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Informazioni sull'uso degli script di Skype for Business Server Management Shell

Stiamo fornendo script di PowerShell di esempio che puoi usare per preparare le simulazioni di caricamento. Dato che questi script sono destinati alla simulazione del carico, li troverai semplici e permissivi. Potrebbe non essere appropriato per l'ambiente di produzione. Ancora una volta sottolineiamo che questi script sono esempi, è necessario rivederli e in molti casi apportare modifiche rilevanti per l'ambiente prima di poterlo usare in modo pratico. Come minimo, ci aspettiamo che tu debba modificare lo script RSG (Response Service Group) con la topologia in mente (per specificare gli agenti assegnati ai gruppi di agenti). Ma non devi eseguire questa funzione, se non è necessario.
  
> [!CAUTION]
> Prestare particolare attenzione a rivedere e comprendere questi esempi. Gli script sovrascriveranno le impostazioni esistenti nella topologia quando verranno eseguite. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomi di versione client dello strumento stress e prestazioni

Potrebbe essere necessario configurare i criteri di controllo della versione client se in precedenza sono state modificate le impostazioni dei valori predefiniti. In caso di dubbi, verificare la [documentazione relativa alla verifica della versione client](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
Lo strumento sollecitazione e prestazioni usa le versioni seguenti dell'agente utente per impostazione predefinita durante la comunicazione con Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (strumento di stress e prestazioni di Skype for Business Server 2015)
    
- OCPHONE/.0.522
    
Per il client Mobility (UCWA) in LyncPerfTool:
  
- Strumento Perf UCWA/conferenza Web
    
- Strumento Perf UCWA/mobile
    

