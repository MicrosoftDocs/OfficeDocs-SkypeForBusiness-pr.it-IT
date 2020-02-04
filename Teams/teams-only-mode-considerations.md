---
title: Considerazioni sulla modalità solo Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: Preparare l'aggiornamento alla modalità solo Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1.keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89aded4747bc0a3f41fd78ce1bdced7b3363775b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708312"
---
# <a name="teams-only-mode-considerations"></a>Considerazioni sulla modalità solo Teams

Se si è un amministratore del tenant di Office 365, si vedrà ora l'opzione per l'aggiornamento alla modalità solo teams nell'interfaccia di amministrazione di Microsoft teams. Con questa funzionalità è possibile aggiornare singoli utenti o, in alternativa, l'intero tenant.  

L'aggiornamento alla modalità solo teams offre agli utenti tutti i vantaggi di Microsoft teams, l'hub per il lavoro in team in Office 365, tramite una singola esperienza client. Inoltre, gli utenti in modalità solo team riceveranno tutte le chiamate e le chat in teams, indipendentemente dal fatto che il mittente usi Skype for business o teams e tragga vantaggio dal supporto per l'interoperabilità e la Federazione.

Mentre migliaia di clienti hanno eseguito l'aggiornamento a Microsoft teams, esistono considerazioni che possono influenzare la sequenza temporale dell'aggiornamento dell'organizzazione e l'esperienza utente lungo il percorso. In particolare, la possibilità di eseguire l'aggiornamento non significa necessariamente che l'organizzazione sia pronta per questa modifica. Per un'esperienza utente ottimale, verificare che Teams soddisfi i requisiti interni di collaborazione e comunicazione, assicurarsi che la rete sia pronta per supportare Teams e implementare il piano di preparazione degli utenti prima di aggiornarli a Teams. 

> [!IMPORTANT]
> Se si sta solo avviando la pianificazione dell'aggiornamento, assicurarsi di esaminare le risorse di pianificazione e le informazioni complete sull'aggiornamento. [Iniziare da qui](upgrade-start-here.md). 

**Considerazioni sulla coesistenza**: le organizzazioni che usano già Skype for business online e/o Skype for Business Server possono introdurre team nel proprio ambiente a un ritmo che soddisfi le proprie esigenze. Le organizzazioni possono distribuire in modo incrementale Teams a un set di utenti desiderato e gli utenti che usano i team possono comunicare con utenti che usano Skype for business e viceversa. Per gestire questa esperienza, gli amministratori usano le modalità di coesistenza, che definiscono l'esperienza dell'utente finale, il comportamento di routing delle chat e delle chiamate in arrivo, nonché la programmazione di nuove riunioni in teams o Skype for business. Gli utenti possono essere federati con utenti di altre organizzazioni se l'utente viene aggiornato **solo a teams**; Tuttavia, l'esperienza migliore viene fornita quando entrambi gli utenti usano teams. Gli utenti che hanno eseguito l'aggiornamento a teams possono ancora partecipare a riunioni Skype for business. 

> [!NOTE]
> Gli utenti che hanno eseguito l'aggiornamento a teams non possono comunicare solo con utenti che usano Skype for consumer.

> [!IMPORTANT]
> Per informazioni più dettagliate sulla coesistenza, vedere [comprendere Microsoft teams e la coesistenza e l'interoperabilità di Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Considerazioni a livello di tenant**: stiamo lavorando per abilitare teams negli ambienti seguenti; Tuttavia, per il momento, gli amministratori non dovrebbero aggiornare gli utenti dell'organizzazione se il tenant di Skype for business è ospitato in uno degli ambienti seguenti:

 - Nuvola di community governative High
 - Government community Cloud DoD
 - Office 365 gestito da 21Vianet
 - Office 365 Germania
 - Il tenant di Skype for business è ospitato in Corea del sud **e** l'organizzazione richiede che i dati dei team vengano archiviati in Corea del sud. Attualmente, le organizzazioni con i dati di Skype for business archiviati in Corea del sud che aggiornano a teams avranno i loro dati di team archiviati nell'area del datacenter Asia, non nell'area del centro dati della Corea del sud.

**Considerazioni specifiche dell'utente**: alcuni scenari degli utenti continuano a evolversi e gli amministratori possono decidere di posticipare temporaneamente l'aggiornamento di alcuni utenti durante l'aggiornamento di altri utenti nell'organizzazione. In particolare, stiamo ancora lavorando agli scenari di indirizzamento per gli utenti il cui dispositivo principale è basato su VDI. Monitorare il sito della [Roadmap di Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) per gli annunci.

> [!NOTE]
> Prima di procedere con la modalità solo teams, è necessario sostituire o aggiornare i dispositivi che non supportano team. 

> [!IMPORTANT]
> **Ricorda**: il passaggio a teams è più di una migrazione tecnica. Un aggiornamento corretto valuta sia la conformità tecnica che la disponibilità degli utenti finali. Esaminare le [linee guida](upgrade-framework.md) per l'aggiornamento di Skype for business a teams per altre informazioni sulla pianificazione di un'implementazione dell'aggiornamento a teams.  
