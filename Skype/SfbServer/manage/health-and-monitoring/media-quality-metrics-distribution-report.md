---
title: Rapporto distribuzione metriche di qualità multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Riepilogo: informazioni sul Rapporto distribuzione metriche di qualità multimediale in Skype for Business Server.'
ms.openlocfilehash: c39282ab2d5d6ce903affd807d22116a98de3620
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827806"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Rapporto distribuzione metriche di qualità multimediale in Skype for Business Server 
 
**Riepilogo:** Informazioni sul Rapporto distribuzione metriche di qualità multimediale in Skype for Business Server.
  
Il Rapporto distribuzione metriche di qualità multimediale consente di visualizzare un grafico che mostra i valori di distribuzione per una metrica Qualità dell'esperienza, ad esempio instabilità o perdita di pacchetti. Si supponga, ad esempio, che gli utenti esemplino un totale di 10 chiamate telefoniche. Tali 10 chiamate segnalano i seguenti tempi di roundtrip:
  
|**Numero chiamata**|**Tempo di andata e ritorno (millisecondi)**|
|:-----|:-----|
|1   <br/> |50  <br/> |
|2   <br/> |50  <br/> |
|3   <br/> |50  <br/> |
|4   <br/> |50  <br/> |
|5   <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10    <br/> |50  <br/> |
   
La media di questi tempi di andata e ritorno è di 500 millisecondi (5000 diviso per 10). Cinquecento millisecondi è un tempo di andata e ritorno estremamente grande; Di conseguenza, si potrebbe pensare di avere un problema grave con la congestione della rete. I tempi di andata e ritorno lunghi sono in genere il risultato di reti sovraccariche.
  
In realtà, naturalmente, il 90% delle chiamate ha avuto tempi di andata e ritorno eccellenti; si è semplicemente avuto una chiamata non negativa che ha astradato i risultati complessivi. Se si osserva solo il tempo medio di andata e ritorno, si potrebbe passare a una conclusione molto errata.
  
Il Rapporto distribuzione metriche di qualità multimediale consente di evitare di passare a conclusioni erre mostrando una distribuzione grafica di una metrica specificata ,ad esempio il tempo di andata e ritorno. Questi grafici consentono di chiarire che sono stati evasi nove chiamate molto buone e una chiamata molto negativa. A dire il vero, potrebbe essere comunque necessario analizzare ulteriormente tale chiamata; Tuttavia, il fatto che 9 chiamate su 10 siano state molto buone suggerisce che non c'è motivo di apportare modifiche drastiche alla rete, almeno non a questo punto nel tempo.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il Rapporto distribuzione metriche di qualità multimediale.
  
**Filtri del rapporto di distribuzione metriche di qualità multimediale**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Minimo nell'asse x** <br/> |Valore minimo da visualizzare sull'asse X del grafico.  <br/> |
|**Massimo nell'asse x** <br/> |Valore massimo da visualizzare sull'asse X del grafico.  <br/> |
|**Tipo di accesso** <br/> | Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  Interno <br/>  Esterno <br/> |
|**VPN** <br/> | Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  VPN <br/>  Non VPN <br/> |
|**Tipo di rete** <br/> | Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  Cablata <br/>  Wireless <br/> |
   

