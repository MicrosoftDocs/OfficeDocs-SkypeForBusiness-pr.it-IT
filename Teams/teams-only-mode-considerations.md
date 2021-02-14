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
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802376"
---
# <a name="teams-only-mode-considerations"></a>Considerazioni sulla modalità Solo teams

Se sei un amministratore nell'organizzazione di Microsoft 365 o Office 365, ora vedi l'opzione per passare alla modalità Solo teams nell'interfaccia di amministrazione di Microsoft Teams. Con questa funzionalità è possibile aggiornare singoli utenti oppure, in alternativa, l'intero tenant.  

L'aggiornamento alla modalità Solo teams offre agli utenti tutti i vantaggi di Microsoft Teams, l'hub per il lavoro in team in Microsoft 365 o Office 365, tramite un'unica esperienza client. Inoltre, gli utenti in modalità Solo teams riceveranno tutte le chiamate e le chat in Teams, indipendentemente dal fatto che il mittente utilizzi Skype for Business o Teams e trarre vantaggio dal supporto di interoperabilità e federazione.

Anche se migliaia di clienti hanno eseguito correttamente l'aggiornamento a Microsoft Teams, ci sono considerazioni che possono influire sulla sequenza temporale dell'aggiornamento e sull'esperienza utente dell'organizzazione. In particolare, avere l'opzione di aggiornamento non significa necessariamente che l'organizzazione è pronta per questa modifica. Per un'esperienza utente ottimale, verificare che Teams soddisfi i requisiti interni di collaborazione e comunicazione, assicurarsi che la rete sia pronta per supportare Teams e implementare il piano di preparazione degli utenti prima di aggiornarli a Teams. 

> [!IMPORTANT]
> Se si sta appena iniziando la pianificazione degli aggiornamenti, consultare la Guida introduttiva alla guida all'aggiornamento [a Microsoft Teams.](upgrade-start-here.md) 

**Considerazioni sulla** coesistenza: le organizzazioni che già usano Skype for Business online e/o Skype for Business Server possono introdurre Teams nel proprio ambiente con un ritmo che soddisfa le loro esigenze. Le organizzazioni possono implementare in modo incrementale Teams nel set desiderato di utenti, se necessario, e gli utenti che usano Teams possono comunicare con gli utenti che usano Skype for Business e viceversa. Per gestire questa esperienza, gli amministratori usano le modalità di coesistenza, che definiscono l'esperienza client dell'utente finale, il comportamento di instradamento delle chat e delle chiamate in arrivo, nonché la pianificazione di nuove riunioni in Teams o Skype for Business. Gli utenti possono eseguire la federazione con utenti di altre organizzazioni se l'utente viene aggiornato a **Solo Teams;** tuttavia, l'esperienza migliore viene fornita quando entrambi gli utenti usano Teams. Gli utenti aggiornati a Teams possono comunque partecipare alle riunioni Skype for Business. 

> [!IMPORTANT]
> Per informazioni più dettagliate sulla coesistenza, vedere Informazioni sulla coesistenza e l'interoperabilità di [Microsoft Teams e Skype for Business.](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Per ulteriori informazioni su Teams e Skype (Consumer), consulta [Teams e l'interoperabilità di Skype.](teams-skype-interop.md)

**Considerazioni a livello di tenant:** Stiamo lavorando all'abilitazione di Teams nei seguenti ambienti; tuttavia, per il momento, gli amministratori non devono aggiornare gli utenti dell'organizzazione se il tenant di Skype for Business è ospitato in uno dei seguenti ambienti:

 - Office 365 gestito da 21Vianet
 - Office 365 Germany
 - Il tenant di Skype for Business è ospitato in Corea del Sud **e** l'organizzazione richiede l'archiviazione dei dati di Teams in Corea del Sud. Attualmente, le organizzazioni con dati Skype for Business archiviati in Corea del Sud che ese aggiornano a Teams avranno i loro dati di Teams archiviati nell'area dati Asia, non nell'area geografica del data center della Corea del Sud.

**Considerazioni specifiche per gli** utenti: alcuni scenari utente sono ancora in evoluzione e gli amministratori possono decidere di posticipare temporaneamente l'aggiornamento di alcuni utenti durante l'aggiornamento di altri utenti nell'organizzazione. In particolare, stiamo ancora lavorando agli scenari di indirizzamento per gli utenti il cui dispositivo principale è basato su VDI. Monitorare il sito [della roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per gli annunci.

> [!NOTE]
> Prima di passare alla modalità Solo teams, devi sostituire o aggiornare i dispositivi che non supportano Teams. 

> [!IMPORTANT]
> **Ricorda:** il passaggio a Teams non è solo una migrazione tecnica. Un aggiornamento riuscito valuta sia la conformità tecnica che la conformità degli utenti finali. Consulta le nostre indicazioni per l'aggiornamento da Skype for Business [a](upgrade-framework.md) Teams per ulteriori informazioni sulla pianificazione di un aggiornamento a Teams.  
