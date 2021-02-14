---
title: Licenze Microsoft Teams Rooms
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
description: Informazioni sulle licenze disponibili per i diversi tipi di funzionalità di chiamata e riunione disponibili nelle sale di Microsoft Teams.
ms.openlocfilehash: 37f47e9b89abd87837b02f8a67c3c82eaa9c7a5c
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662481"
---
# <a name="teams-meeting-room-licensing-update"></a>Aggiornamento delle licenze per le sale riunioni di Teams

## <a name="licensing-solutions-for-shared-communication-devices"></a>Soluzioni di gestione delle licenze per dispositivi di comunicazione condivisa

Microsoft ha uno SKU dedicato per le licenze per le riunioni e le chiamate per ogni dispositivo per i dispositivi della sala riunioni (come le sale di Microsoft Teams, Microsoft Surface Hub e le barre di collaborazione per Microsoft Teams).

||SKU sala riunioni |  
|:--- |:---: |
|Skype for Business |&#x2714;|
|Microsoft Teams|  &#x2714;|
|Phone System|  &#x2714;|
|Audioconferenza|&#x2714; &sup1;|
|Microsoft Intune|&#x2714;|  
|Disponibilità in tutto il mondo | &#x2714; &sup2;|
|Disponibilità dei canali | EA, EAS, CSP, <br/>Web Direct |
| | | |

&sup1; La disponibilità e i minuti inclusi possono variare in base all'area geografica. Per verificare la disponibilità del servizio, consulta la disponibilità [del Paese e dell'area geografica per Audioconferenza e Piani per chiamate.](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans) I costi a consumo possono essere applicati per servizi aggiuntivi, come numeri verde, minuti di chiamate internazionali per piani nazionali e così via. I clienti possono disabilitare queste funzionalità per evitare la fatturazione aggiuntiva.  

&sup2; Non disponibile nei cloud sovereign  


> [!NOTE]
> Se attualmente utilizzi SKU E1, E3, E4, E5 con Skype for Business Piano 2 con Audioconferenza o con Il Sistema telefonico Office 365 e un Piano per chiamate, questi continueranno a funzionare. Tuttavia, è consigliabile passare a un modello di gestione delle licenze più semplice nella tabella precedente dopo la scadenza delle licenze correnti.

> [!IMPORTANT]
> Se si usa Skype for Business Piano 2, è possibile utilizzare le sale di Microsoft Teams solo in modalità Solo Skype for Business, il che significa che tutte le riunioni saranno riunioni Skype for Business. Per abilitare la sala riunioni per le riunioni di Microsoft Teams, è consigliabile acquistare la licenza per la sala riunioni. 

La tabella seguente elenca le funzionalità disponibili nelle sale di Microsoft Teams e le licenze che è necessario acquistare per ottenerle.
  
> [!NOTE]
> È necessario che la sala configurata sia un oggetto utente e abbia le licenze assegnate.

|  | Si dispone di Microsoft Teams o Skype for Business online <br/> Ecco cosa occorre acquistare:   |Si dispone di Skype for Business Server 2015/2019 (locale o ibrido). <br/> Ecco cosa occorre acquistare:|
|:-----|:-----|:-----|
|Partecipazione a una riunione programmata  | SKU sala riunioni  |Skype for Business Licenza CAL per server Standard  |
|Avviare una riunione ad hoc | SKU sala riunioni  |Skype for Business Licenza CAL per server Standard  <br/> Skype for Business Licenza CAL per server Enterprise|
|Avviare una riunione ad hoc ed effettuare chiamate in uscita da una riunione a numeri di telefono |  SKU sala riunioni |Skype for Business Licenza CAL Standard  <br/> Skype for Business Licenza CAL per server Enterprise|
|Assegnare un numero di telefono alla sala ed effettuare o ricevere chiamate dalla sala oppure partecipare a un'audioconferenza utilizzando un numero di telefono  | Con routing diretto: SKU sala riunioni<br/>Senza routing diretto: piano per chiamate nazionali o internazionali<br/>Microsoft 365 Business Voice  |Skype for Business Licenza CAL per server Standard  <br/> Skype for Business Licenza CAL per server Plus  |
|Gestire il dispositivo della sala con Microsoft Intune |SKU sala riunioni  |Abbonamento a Microsoft Intune [con MDM locale](https://docs.microsoft.com/configmgr/mdm/plan-design/plan-on-premises-mdm) |
| |||

> [!NOTE]
> Se ai sistemi di sala sono state assegnate licenze esistenti, queste continueranno a funzionare senza interruzioni. È consigliabile passare all'uso del nuovo SKU Sala riunioni quando le licenze esistenti scadono.  

 **Usare la versione corretta di Windows 10:** per i clienti che vogliono distribuire le immagini di Windows 10 nei propri dispositivi, vedere [Configurare una console Di Microsoft Teams Room.](https://docs.microsoft.com/microsoftteams/room-systems/console) È possibile ottenerne una copia dal [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/)
