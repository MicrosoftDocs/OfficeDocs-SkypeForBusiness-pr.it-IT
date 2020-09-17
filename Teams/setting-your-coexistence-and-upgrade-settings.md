---
title: Configurare le impostazioni di aggiornamento e coesistenza
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Informazioni su come impostare le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione contemporaneamente o per un singolo o un set di utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a20e8c355df4103980dc9da460d003382c721800
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940606"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configurare le impostazioni di aggiornamento e coesistenza


Quando si aggiornano gli utenti di Skype for business per usare teams, sono disponibili diverse opzioni che consentono di semplificare il processo per gli utenti. Si ha la possibilità di apportare le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione contemporaneamente oppure di apportare modifiche alle impostazioni per un singolo o un set di utenti dell'organizzazione. Tieni presente che le versioni precedenti dei client Skype for business potrebbero non rispettare queste impostazioni. Per altre informazioni sulle versioni client Skype for business, vedere la [pagina download e aggiornamenti di Skype for business](https://docs.microsoft.com/skypeforbusiness/software-updates). 

Puoi comprendere meglio le modalità disponibili leggendo [Microsoft teams e la coesistenza di Skype for business e l'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) o la [coesistenza con Skype for business](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Impostare le opzioni di aggiornamento per tutti gli utenti dell'organizzazione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/), nella barra di spostamento sinistra, passa a aggiornamento a **livello di organizzazione**di  >  **Teams**. 

2. Nella parte superiore della pagina **upgrade teams** modificare le opzioni seguenti come desiderato.
    - Impostare la modalità di **coesistenza** .
        - **Islands** : usare questa impostazione se si vuole che gli utenti possano usare contemporaneamente Skype for business e teams.
        - **Solo Skype for business** -usare questa impostazione se si vuole che gli utenti usino solo Skype for business.
        - **Skype for business con teams Collaboration** -usare questa impostazione se si vuole che gli utenti usino Skype for business, oltre a usare team per la collaborazione di gruppo (canali).
        - **Skype for business con teams Collaboration and Meetings** -usare questa impostazione se si vuole che gli utenti usino Skype for business, oltre a usare team per la collaborazione di gruppo (canali) e le riunioni di team.
        - **Solo teams** : usare questa impostazione se si vuole che gli utenti usino solo team. Tieni presente che anche con questa impostazione, gli utenti possono ancora partecipare alle riunioni ospitate in Skype for business.
        
    - Impostare **informa gli utenti di Skype for business che i team sono disponibili per l'aggiornamento**. Se si attiva questa opzione, gli utenti di Skype for business verranno avvisati che presto verranno aggiornati all'app teams.
    - Imposta l' **app preferita per gli utenti che partecipano a riunioni Skype for business**. Questa impostazione determina quale app viene usata per partecipare a riunioni Skype for business e viene rispettata indipendentemente dal valore della modalità di coesistenza.
      - **App riunioni Skype**
      - **Skype for business con funzionalità limitate**
    - Imposta se **scaricare l'app teams in background per gli utenti di Skype for business**.  Questa impostazione Scarica automaticamente l'app teams per gli utenti che utilizzano Skype for business in Windows. Viene rispettato solo se la modalità di coesistenza per l'utente è solo teams o se le notifiche di aggiornamento in sospeso sono abilitate in Skype for business.
3. Dopo avere apportato le modifiche, fare clic su **Salva** .

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Impostare le opzioni di aggiornamento per un singolo utente dell'organizzazione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra passa a **utenti**e quindi seleziona l'utente nell'elenco. 
2. Nella scheda **account** per l'utente, in **aggiornamento Team**, fare clic su **modifica**.
3. Puoi impostare la **modalità di coesistenza**. Scegliere una delle opzioni seguenti:
     - **Usare le impostazioni a livello di organizzazione** : usare questa impostazione se si vuole che l'utente usi le impostazioni nelle impostazioni a **livello di organizzazione** . 
     - **Islands** : usare questa impostazione se si vuole che l'utente possa usare sia Skype for business che teams. 
     - **Solo Skype for business** -usare questa impostazione se si vuole che l'utente usi Skype for business.
     - **Skype for business con teams Collaboration** -usare questa impostazione se si vuole che l'utente usi Skype for business, oltre a usare team per la collaborazione di gruppo (canali).
      - **Skype for business con teams Collaboration and Meetings** -usare questa impostazione se si vuole che l'utente usi Skype for business, oltre a usare team per la collaborazione di gruppo (canali) e le riunioni di teams.
     - **Solo teams** : usare questa impostazione se si vuole che l'utente usi solo team. L'utente sarà comunque in grado di partecipare a riunioni Skype for business.
4. Se si seleziona una **modalità di coesistenza** diversa dall' **uso delle impostazioni a livello di organizzazione**, è possibile abilitare le notifiche nell'app Skype for business dell'utente che l'aggiornamento a teams sarà disponibile a breve. Puoi abilitare questa notifica per l'utente attivando l'opzione **avvisa l'utente di Skype for business** .
5. Dopo avere apportato le modifiche, fare clic su **Salva** .

### <a name="related-topics"></a>Argomenti correlati
[Eseguire l'aggiornamento da Skype for business a teams — per gli amministratori IT](upgrade-to-teams-on-prem-overview.md)

[Pianificare il viaggio](upgrade-plan-journey.md)

[Comprendere il viaggio di coesistenza e di aggiornamento per Skype for business e teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md)
