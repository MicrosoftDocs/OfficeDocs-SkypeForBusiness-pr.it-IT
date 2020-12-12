---
title: Licenze di Microsoft teams rooms
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Informazioni sulle licenze disponibili per diversi tipi di funzionalità di chiamata e riunione in Microsoft teams rooms.
ms.openlocfilehash: 37f47e9b89abd87837b02f8a67c3c82eaa9c7a5c
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662481"
---
# <a name="teams-meeting-room-licensing-update"></a>Aggiornamento delle licenze della sala riunioni Teams

## <a name="licensing-solutions-for-shared-communication-devices"></a>Soluzioni di gestione licenze per dispositivi di comunicazione condivisi

Microsoft ha un SKU dedicato per le riunioni di licenza e la chiamata su base per dispositivo per i dispositivi della sala riunioni, ad esempio Microsoft teams rooms, Microsoft Surface Hub e Collaboration bars per Microsoft teams.

||SKU sala riunioni |  
|:--- |:---: |
|Skype for Business |&#x2714;|
|Microsoft Teams|  &#x2714;|
|Sistema telefonico|  &#x2714;|
|Audioconferenza|&#x2714; &sup1;|
|Microsoft Intune|&#x2714;|  
|Disponibilità mondiale | &#x2714; &sup2;|
|Disponibilità del canale | EA, EAS, CSP, <br/>Web Direct |
| | | |

&sup1; La disponibilità e i minuti inclusi possono variare in base all'area geografica. Per verificare la disponibilità del servizio, fare riferimento alla  [disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans). Gli oneri per il consumo possono essere applicati per servizi aggiuntivi, ad esempio i minuti gratuiti per i piani nazionali e così via. I clienti possono disabilitare queste funzionalità per evitare ulteriori fatturazione.  

&sup2; Non disponibile in nubi sovrane  


> [!NOTE]
> Se attualmente si usano gli SKU E1, E3, E4, E5 con Skype for Business Plan 2 con servizi di audioconferenza o con il sistema telefonico Office 365 e un piano per le chiamate, questi continueranno a funzionare. Tuttavia, è consigliabile passare a un modello di licenza più semplice nella tabella precedente dopo la scadenza delle licenze correnti.

> [!IMPORTANT]
> Se si usa Skype for Business Plan 2, è possibile usare solo le sale di Microsoft teams in modalità solo Skype for business, quindi tutte le riunioni saranno riunioni Skype for business. Per abilitare la sala riunioni per le riunioni di Microsoft teams, ti consigliamo di acquistare la licenza della sala riunioni. 

La tabella seguente elenca le caratteristiche disponibili nelle sale di Microsoft teams e le licenze che è necessario acquistare per ottenerle.
  
> [!NOTE]
> È necessario che la sala configurata sia un oggetto utente e abbia le licenze assegnate.

|  | Si hanno Microsoft teams o Skype for business online <br/> Ecco cosa è necessario acquistare:   |Si ha Skype for Business Server 2015/2019 (locale o ibrido). <br/> Ecco cosa è necessario acquistare:|
|:-----|:-----|:-----|
|Partecipazione a una riunione programmata  | SKU sala riunioni  |Skype for Business Licenza CAL per server Standard  |
|Avviare una riunione ad hoc | SKU sala riunioni  |Skype for Business Licenza CAL per server Standard  <br/> Skype for Business Licenza CAL per server Enterprise|
|Avviare una riunione ad hoc e effettuare chiamate in uscita da una riunione a numeri di telefono |  SKU sala riunioni |Skype for Business Licenza CAL Standard  <br/> Skype for Business Licenza CAL per server Enterprise|
|Assegnare un numero di telefono alla sala e effettuare o ricevere chiamate dalla sala o partecipare a una conferenza audio usando un numero di telefono  | Con routing diretto: SKU sala riunioni<br/>Senza routing diretto: piano per chiamate nazionali o internazionali<br/>Microsoft 365 Business Voice  |Skype for Business Licenza CAL per server Standard  <br/> Skype for Business Licenza CAL per server Plus  |
|Gestire il dispositivo room con Microsoft Intune |SKU sala riunioni  |Abbonamento a Microsoft Intune con [MDM locale](https://docs.microsoft.com/configmgr/mdm/plan-design/plan-on-premises-mdm) |
| |||

> [!NOTE]
> Se sono state assegnate licenze esistenti per i sistemi room, queste continueranno a funzionare senza interruzioni. È consigliabile usare la nuova SKU della sala riunioni quando scadono le licenze esistenti.  

 **Usare la versione corretta di Windows 10**: per i clienti che desiderano distribuire immagini di Windows 10 nei propri dispositivi, vedere [configurare una console Microsoft teams Rooms](https://docs.microsoft.com/microsoftteams/room-systems/console). È possibile ottenere una copia dal [centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/).
