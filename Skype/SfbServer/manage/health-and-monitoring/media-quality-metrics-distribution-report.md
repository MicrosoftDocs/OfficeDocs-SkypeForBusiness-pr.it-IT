---
title: Il rapporto distribuzione metriche di qualità multimediale in Skype for Business Server
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
description: 'Riepilogo: informazioni sul rapporto distribuzione metriche di qualità multimediale in Skype for Business Server.'
ms.openlocfilehash: c39282ab2d5d6ce903affd807d22116a98de3620
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827806"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Il rapporto distribuzione metriche di qualità multimediale in Skype for Business Server 
 
**Riepilogo:** Informazioni sul rapporto distribuzione metriche di qualità multimediale in Skype for Business Server.
  
Il rapporto distribuzione metriche di qualità multimediale consente di visualizzare un grafico che mostra i valori di distribuzione per una metrica di qualità di esperienza, ad esempio instabilità o perdita di pacchetti. Si supponga, ad esempio, che gli utenti effettuino un totale di 10 chiamate telefoniche; tali 10 chiamate segnalano i seguenti tempi di andata e ritorno:
  
|**Numero di chiamata**|**Tempo di andata e ritorno (millisecondi)**|
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
|10   <br/> |50  <br/> |
   
La media di tali tempi di andata e ritorno è di 500 millisecondi (5000 diviso 10). 500 millisecondi è un tempo di andata e ritorno estremamente esteso; di conseguenza, è possibile che si verifichi un problema serio con la congestione della rete. (I tempi lunghi di andata e ritorno sono in genere il risultato delle reti di overload).
  
In realtà, ovviamente, il 90% delle chiamate ha avuto tempi di andata e ritorno eccellenti; si è avuta solo una cattiva chiamata che ha alterato i risultati complessivi. Se si esamina solo il tempo medio di andata e ritorno, è possibile passare a una conclusione molto sbagliata.
  
Il rapporto distribuzione metriche di qualità multimediale consente di evitare di saltare a conclusioni errate mostrando una distribuzione grafica di una metrica specificata, ad esempio il tempo di andata e ritorno. Questi grafici possono essere utili per chiarire che sono state riportate nove chiamate molto valide e una pessima chiamata. È possibile che si desideri continuare a indagare su una chiamata. Tuttavia, il fatto che 9 chiamate su 10 siano state molto valide suggerisce che non vi è alcun motivo per apportare modifiche drastiche alla rete, almeno non a questo punto nel tempo.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il rapporto distribuzione metriche di qualità multimediale.
  
**Filtri del rapporto distribuzione metriche di qualità multimediale**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Minimo nell'asse x** <br/> |Valore più basso da visualizzare sull'asse X del grafico.  <br/> |
|**Massimo nell'asse x** <br/> |Valore massimo da visualizzare sull'asse X del grafico.  <br/> |
|**Tipo di accesso** <br/> | Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Interno <br/>  Esterno <br/> |
|**VPN** <br/> | Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  VPN <br/>  Non VPN <br/> |
|**Tipo di rete** <br/> | Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Cablata <br/>  Wireless <br/> |
   

