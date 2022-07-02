---
title: Considerazioni sulla modalità Solo teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Amministrazione informazioni su come preparare l'aggiornamento alla modalità Solo Microsoft Teams nell'interfaccia di amministrazione di Microsoft Teams.
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
ms.openlocfilehash: b80a563d6d3938a597e57aab4ac93e41df976d32
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605865"
---
# <a name="teams-only-mode-considerations"></a>Considerazioni sulla modalità Solo teams

Gli amministratori di Microsoft 365 o Office 365 organizzazioni possono aggiornare singoli utenti o l'intero tenant alla modalità Solo teams.  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

L'aggiornamento alla modalità Solo Teams offre agli utenti tutti i vantaggi di Microsoft Teams, l'hub per il lavoro in team in Microsoft 365 o Office 365, tramite un'esperienza client singola. Gli utenti in modalità Solo Teams riceveranno tutte le chiamate e le chat in Teams, indipendentemente dal fatto che il mittente usi Skype for Business o Teams, e beneficeranno del supporto di interoperabilità e federazione.

Anche se migliaia di clienti hanno eseguito correttamente l'aggiornamento a Microsoft Teams, ci sono considerazioni che possono influenzare la sequenza temporale e l'esperienza utente dell'organizzazione lungo il percorso. Per un'esperienza utente ottimale, verificare che Teams soddisfi i requisiti interni di collaborazione e comunicazione, assicurarsi che la rete sia pronta per supportare Teams e implementare il piano di preparazione degli utenti prima di aggiornarli a Teams. 

> [!IMPORTANT]
> Se stai appena iniziando la pianificazione dell'aggiornamento, assicurati di consultare la guida [introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md) . 

**Considerazioni sulla coesistenza**: le organizzazioni che usano già Skype for Business Online e/o Skype for Business Server possono introdurre Teams nel proprio ambiente a un ritmo che soddisfi le loro esigenze. Le organizzazioni possono distribuire in modo incrementale Teams a un set di utenti desiderato in base alle esigenze e gli utenti che usano Teams possono comunicare con gli utenti che usano Skype for Business e viceversa. Per gestire questa esperienza, gli amministratori usano modalità di coesistenza, che definiscono l'esperienza client per l'utente finale, il comportamento di routing delle chat e delle chiamate in arrivo e se le nuove riunioni sono pianificate in Teams o Skype for Business. Gli utenti possono eseguire la federazione con utenti di altre organizzazioni se l'utente viene aggiornato a **Solo Teams**; tuttavia, l'esperienza migliore viene fornita quando entrambi gli utenti usano Teams. Gli utenti aggiornati a Solo Teams possono comunque partecipare a Skype for Business riunioni. 

> [!IMPORTANT]
> Per informazioni più dettagliate sulla coesistenza, vedere [Informazioni su Microsoft Teams e Skype for Business coesistenza e interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md). Per altre informazioni su Teams e Skype (consumer), vedi [Interoperabilità di Teams e Skype](teams-skype-interop.md).


**Considerazioni specifiche** dell'utente: alcuni scenari utente sono ancora in continua evoluzione e gli amministratori possono decidere di posticipare temporaneamente l'aggiornamento di alcuni utenti durante l'aggiornamento di altri utenti dell'organizzazione. In particolare, stiamo ancora lavorando agli scenari di risoluzione dei problemi per gli utenti il cui dispositivo principale è basato su VDI. Per gli annunci del sito, monitorare la [roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

> [!NOTE]
> Prima di passare alla modalità Solo Teams è necessario sostituire o aggiornare i dispositivi che non supportano Teams. 

> [!IMPORTANT]
> **Ricordare**: il passaggio a Teams è molto più di una migrazione tecnica. Un aggiornamento riuscito valuta sia la preparazione tecnica che la preparazione degli utenti finali. Per altre informazioni sulla pianificazione di un'implementazione dell'aggiornamento a Teams, consultare le [linee guida per l'aggiornamento](upgrade-framework.md) di Skype for Business a Teams.  
