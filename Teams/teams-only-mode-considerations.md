---
title: Considerazioni sulla modalità Solo teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: L'amministratore può imparare a preparare l'ambiente per un aggiornamento alla modalità Solo di Microsoft Teams nell'interfaccia di amministrazione di Microsoft Teams.
localization_priority: Normal
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
ms.openlocfilehash: 4a38967ffb80f59fab88006b5aad2e6ecb76395c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460996"
---
# <a name="teams-only-mode-considerations"></a>Considerazioni sulla modalità Solo teams

Gli amministratori delle organizzazioni Microsoft 365 o Office 365 possono passare alla modalità Solo Teams per singoli utenti o per l'intero tenant.  

L'aggiornamento alla modalità Solo teams offre agli utenti tutti i vantaggi di Microsoft Teams, l'hub per il lavoro in team in Microsoft 365 o Office 365, tramite un'unica esperienza client. Gli utenti in modalità Solo teams riceveranno tutte le chiamate e le chat in Teams, indipendentemente dal fatto che il mittente utilizzi Skype for Business o Teams e trarre vantaggio dal supporto di interoperabilità e federazione.

Anche se migliaia di clienti hanno eseguito correttamente l'aggiornamento a Microsoft Teams, ci sono considerazioni che possono influire sulla sequenza temporale dell'aggiornamento e sull'esperienza utente dell'organizzazione. Per un'esperienza utente ottimale, verificare che Teams soddisfi i requisiti interni di collaborazione e comunicazione, assicurarsi che la rete sia pronta per supportare Teams e implementare il piano di preparazione degli utenti prima di aggiornarli a Teams. 

> [!IMPORTANT]
> Se si sta appena iniziando la pianificazione degli aggiornamenti, consultare la Guida introduttiva alla guida all'aggiornamento [a Microsoft Teams.](upgrade-start-here.md) 

**Considerazioni sulla** coesistenza: le organizzazioni che già usano Skype for Business online e/o Skype for Business Server possono introdurre Teams nel proprio ambiente con un ritmo che soddisfa le loro esigenze. Le organizzazioni possono implementare in modo incrementale Teams nel set desiderato di utenti, se necessario, e gli utenti che usano Teams possono comunicare con gli utenti che usano Skype for Business e viceversa. Per gestire questa esperienza, gli amministratori usano le modalità di coesistenza, che definiscono l'esperienza client dell'utente finale, il comportamento di instradamento delle chat e delle chiamate in arrivo e se le nuove riunioni sono pianificate in Teams o Skype for Business. Gli utenti possono eseguire la federazione con utenti di altre organizzazioni se l'utente viene aggiornato a **Solo Teams;** tuttavia, l'esperienza migliore viene fornita quando entrambi gli utenti usano Teams. Gli utenti aggiornati a Teams possono comunque partecipare alle riunioni Skype for Business. 

> [!IMPORTANT]
> Per informazioni più dettagliate sulla coesistenza, vedere Informazioni sulla coesistenza e l'interoperabilità di [Microsoft Teams e Skype for Business.](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Per ulteriori informazioni su Teams e Skype (Consumer), consulta [Teams e l'interoperabilità di Skype.](teams-skype-interop.md)


**Considerazioni specifiche per gli** utenti: alcuni scenari di utenti sono ancora in evoluzione e gli amministratori possono decidere di posticipare temporaneamente l'aggiornamento di alcuni utenti durante l'aggiornamento di altri utenti nell'organizzazione. In particolare, stiamo ancora lavorando agli scenari di indirizzamento per gli utenti il cui dispositivo principale è basato su VDI. Per gli annunci di siti, monitorare la roadmap [di Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

> [!NOTE]
> Prima di passare alla modalità Solo teams, devi sostituire o aggiornare i dispositivi che non supportano Teams. 

> [!IMPORTANT]
> **Ricorda:** il passaggio a Teams non è solo una migrazione tecnica. Un aggiornamento riuscito valuta sia la conformità tecnica che la conformità degli utenti finali. Consulta le nostre indicazioni per l'aggiornamento da Skype for Business [a](upgrade-framework.md) Teams per ulteriori informazioni sulla pianificazione di un aggiornamento a Teams.  
