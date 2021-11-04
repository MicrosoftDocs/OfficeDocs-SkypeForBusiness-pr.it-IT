---
title: Teams Considerazioni solo sulla modalità
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: L'amministratore può imparare a preparare un aggiornamento alla modalità Microsoft Teams solo nell'Microsoft Teams di amministrazione.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93c45670207729cbfcf42620aa235803b3c50e02
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774336"
---
# <a name="teams-only-mode-considerations"></a>Teams Considerazioni solo sulla modalità

Gli amministratori di Microsoft 365 o Office 365 possono aggiornare i singoli utenti o l'intero tenant alla Teams Solo utenti.  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

L'aggiornamento alla modalità solo Teams offre agli utenti tutti i vantaggi di Microsoft Teams, l'hub per il lavoro in team in Microsoft 365 o Office 365, tramite un'unica esperienza client. Gli utenti in modalità solo Teams riceveranno tutte le chiamate e le chat in Teams, indipendentemente dal fatto che il mittente utilizzi Skype for Business o Teams e trarranno vantaggio dal supporto per l'interoperabilità e la federazione.

Anche se migliaia di clienti hanno eseguito correttamente l'aggiornamento a Microsoft Teams, esistono considerazioni che possono influire sulla sequenza temporale di aggiornamento e sull'esperienza utente dell'organizzazione. Per un'esperienza utente ottimale, verificare che Teams soddisfi i requisiti interni di collaborazione e comunicazione, assicurarsi che la rete sia pronta per supportare Teams e implementare il piano di preparazione degli utenti prima di aggiornarli a Teams. 

> [!IMPORTANT]
> Se si sta appena avviando la pianificazione dell'aggiornamento, leggere la guida introduttiva [Microsoft Teams'aggiornamento.](upgrade-start-here.md) 

**Considerazioni sulla** coesistenza: le organizzazioni che usano già Skype for Business Online e/o Skype for Business Server possono introdurre Teams nell'ambiente a un ritmo che soddisfi le proprie esigenze. Le organizzazioni possono implementare Teams a un set di utenti desiderato in base alle esigenze e gli utenti che usano Teams possono comunicare con gli utenti che usano Skype for Business e viceversa. Per gestire questa esperienza, gli amministratori usano le modalità di coesistenza, che definiscono l'esperienza client dell'utente finale, il comportamento di routing delle chat e delle chiamate in arrivo e se le nuove riunioni sono pianificate in Teams o Skype for Business. Gli utenti possono eseguire la federazione con utenti di altre organizzazioni se l'utente viene aggiornato a **Teams solo;** Tuttavia, l'esperienza migliore viene fornita quando entrambi gli utenti usano Teams. Gli utenti aggiornati a Teams possono comunque partecipare alle Skype for Business riunioni. 

> [!IMPORTANT]
> Per informazioni più dettagliate sulla coesistenza, vedere Informazioni sulla coesistenza Microsoft Teams e [Skype for Business e sull'interoperabilità.](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Per altre informazioni sull'Teams e Skype (consumer), vedere Teams [e Skype interoperabilità.](teams-skype-interop.md)


**Considerazioni specifiche per gli** utenti: alcuni scenari utente sono ancora in evoluzione e gli amministratori possono decidere di posticipare temporaneamente l'aggiornamento di determinati utenti durante l'aggiornamento di altri utenti dell'organizzazione. In particolare, stiamo ancora lavorando agli scenari di indirizzamento per gli utenti il cui dispositivo principale è basato su VDI. Per gli annunci del sito, monitorare la roadmap [Microsoft 365 sito](https://www.microsoft.com/microsoft-365/roadmap).

> [!NOTE]
> Prima di passare alla modalità Teams è necessario sostituire o aggiornare i dispositivi che non supportano Teams. 

> [!IMPORTANT]
> **Tenere** presente che il passaggio a Teams è più di una migrazione tecnica. Un aggiornamento riuscito valuta sia la conformità tecnica che la conformità degli utenti finali. Per altre informazioni sulla pianificazione [](upgrade-framework.md) dell'implementazione dell'aggiornamento Skype for Business a Teams, vedere le indicazioni per Teams per l'aggiornamento.  
