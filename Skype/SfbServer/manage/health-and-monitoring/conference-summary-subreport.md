---
title: Sottorapporto riepilogativo conferenze in Skype for Business Server
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
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 'Riepilogo: informazioni sul sottoreport riepilogativo conferenze in Skype for Business Server.'
ms.openlocfilehash: 9a42e16bc22f01f196274f1e25396d8516e26af2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826476"
---
# <a name="conference-summary-subreport-in-skype-for-business-server"></a>Sottorapporto riepilogativo conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni sul sottoreport riepilogativo conferenze in Skype for Business Server.
  
Il sottorapporto riepilogativo conferenze offre una visualizzazione generale delle sessioni di conferenza non riuscite. Tali sessioni vengono ulteriormente suddivise per tipo: sessioni Focus e sessioni MCU.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più appropriato, nonché visualizzare i dati restituiti in diversi modi. Nella tabella che segue sono elencati i filtri che è possibile usare con il sottorapporto riepilogativo conferenze.
  
**Filtri del sottorapporto riepilogativo conferenze**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su **[Tutto]** per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.<br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel sottoreport riepilogativo conferenze.
  
**Metriche del sottorapporto riepilogativo conferenze**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Totale conferenze** <br/> |No  <br/> |Numero totale di conferenze effettuate.  <br/> |
|**Totale sessioni conferenza** <br/> |No  <br/> |Numero totale di sessioni di conferenza. Una singola conferenza può includere più sessioni, ad esempio una sessione Focus e una sessione MCU.  <br/> |
|**Frequenza generale errori sessione** <br/> |No  <br/> |Percentuale di tutte le conferenze non riuscite.  <br/> |
|**Sessioni Focus** <br/> |No  <br/> |Numero totale di sessioni Focus.  <br/> |
|**Frequenza errori Focus** <br/> |No  <br/> |Percentuale di sessioni Focus non riuscite.  <br/> |
|Sessioni MCU  <br/> |No  <br/> |Numero totale di sessioni MCU.  <br/> |
|**Frequenza errori MCU** <br/> |No  <br/> |Percentuale di sessioni MCU non riuscite.  <br/> |
|**Sessioni MCU per modalità** <br/> |No  <br/> |Numero totale di sessioni MCU, raggruppate per modalità (ad esempio IM Conferencing).  <br/> |
|**Frequenza errori per modalità** <br/> |No  <br/> |Percentuale di sessioni MCU non riuscite, raggruppate per modalità (ad esempio IM Conferencing).  <br/> |
   

