---
title: Report di distribuzione delle metriche di qualità multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Riepilogo: informazioni sul report di distribuzione delle metriche di qualità multimediale in Skype for Business Server.'
ms.openlocfilehash: 0376f75ff94b1b189c15e53aa7259880da96554a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188786"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Report di distribuzione delle metriche di qualità multimediale in Skype for Business Server 
 
**Riepilogo:** Informazioni sul report di distribuzione delle metriche di qualità multimediale in Skype for Business Server.
  
Il report di distribuzione delle metriche di qualità multimediale consente di visualizzare un grafico che mostra i valori di distribuzione per una metrica di qualità dell'esperienza, ad esempio jitter o perdita di pacchetti. Supponiamo ad esempio che gli utenti facciano un totale di 10 telefonate; Queste 10 chiamate segnalano i tempi di andata e ritorno seguenti:
  
|**Numero chiamata**|**Tempo di andata e ritorno (millisecondi)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4  <br/> |50  <br/> |
|5  <br/> |50  <br/> |
|6  <br/> |50  <br/> |
|7  <br/> |50  <br/> |
|8  <br/> |4550  <br/> |
|9  <br/> |50  <br/> |
|10  <br/> |50  <br/> |
   
La media di questi tempi di andata e ritorno è di 500 millisecondi (5000 diviso 10). 500 millisecondi è un tempo di andata e ritorno estremamente grande; di conseguenza, potresti credere di avere un problema serio con la congestione della rete. (I lunghi tempi di andata e ritorno sono in genere il risultato delle reti di overload).
  
In realtà, naturalmente, il 90% delle chiamate ha avuto ottimi tempi di andata e ritorno; è stata semplicemente assegnata una chiamata errata che ha alterato i risultati complessivi. Se si osserva solo il tempo medio di andata e ritorno, è possibile passare a una conclusione molto sbagliata.
  
Il report di distribuzione delle metriche di qualità multimediale consente di evitare di saltare a conclusioni errate mostrando una distribuzione grafica di una metrica specificata, ad esempio il tempo di andata e ritorno. Questi grafici consentono di chiarire che sono state effettuate nove chiamate molto valide e una chiamata molto negativa. Certo, potresti voler ancora approfondire l'analisi di una chiamata; Tuttavia, il fatto che 9 delle 10 chiamate siano state molto valide suggerisce che non ci sono motivi per apportare modifiche drastiche alla rete, almeno non in questo momento.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report di distribuzione delle metriche di qualità multimediale.
  
**Filtri per i report di distribuzione delle metriche di qualità multimediale**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Minimo nell'asse x** <br/> |Valore più basso da visualizzare sull'asse X del grafico.  <br/> |
|**Massimo nell'asse x** <br/> |Valore massimo da visualizzare nell'asse X del grafico.  <br/> |
|**Tipo di accesso** <br/> | Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Interno <br/>  Esterno <br/> |
|**VPN** <br/> | Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  VPN <br/>  Non VPN <br/> |
|**Tipo di rete** <br/> | Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Cablata <br/>  Wireless <br/> |
   

