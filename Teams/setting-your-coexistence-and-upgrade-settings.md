---
title: Configurare le impostazioni di aggiornamento e coesistenza
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Informazioni su come impostare le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione contemporaneamente o per un singolo o set di utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52e035f3940237309a1a8bab0211ccaad243b004
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117074"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configurare le impostazioni di aggiornamento e coesistenza


Quando si aggiornano gli utenti di Skype for Business per l'uso di Teams, sono disponibili diverse opzioni per semplificare il processo per gli utenti. È possibile apportare contemporaneamente le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione oppure apportare modifiche alle impostazioni per un singolo o set di utenti dell'organizzazione. Tieni presente che le versioni precedenti dei client Skype for Business potrebbero non rispettare queste impostazioni. Per altre informazioni sulle versioni client di Skype for Business, vai alla pagina [download e aggiornamenti di Skype for Business.](/skypeforbusiness/software-updates) 

Per una migliore comprensione delle modalità disponibili, vedere Informazioni sulla coesistenza e l'interoperabilità di Microsoft Teams e [Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) o [Coesistenza con Skype for Business.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Impostare le opzioni di aggiornamento per tutti gli utenti dell'organizzazione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. [Nell'interfaccia di amministrazione di Microsoft Teams,](https://admin.teams.microsoft.com/)nel riquadro di spostamento sinistro, passare a **Impostazioni** a livello di organizzazione Aggiornamento  >  **di Teams.** 

2. Nella parte superiore della pagina **di aggiornamento di Teams** modificare le opzioni seguenti nel modo desiderato.
    - Impostare la **modalità di coesistenza.**
        - **Isole:** usare questa impostazione se si vuole che gli utenti possano usare contemporaneamente Sia Skype for Business che Teams.
        - **Solo Skype for Business:** usare questa impostazione se si vuole che gli utenti usino solo Skype for Business.
        - **Collaborazione di Skype for Business con Teams:** usare questa impostazione se si vuole che gli utenti usino Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
        - Collaborazione e riunioni di Skype for Business con **Teams:** usare questa impostazione se si vuole che gli utenti usino Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali) e le riunioni di Teams.
        - **Solo Teams:** usare questa impostazione se si vuole che gli utenti usino solo Teams. Anche con questa impostazione, gli utenti possono comunque partecipare alle riunioni ospitate in Skype for Business.
        
    - Impostare **Avvisa gli utenti di Skype for Business che Teams è disponibile per l'aggiornamento.** Se attivi questa opzione, gli utenti di Skype for Business riceveranno l'aggiornamento all'app Teams.
    - Impostare **l'app Preferred per consentire agli utenti di partecipare alle riunioni Skype for Business.** Questa impostazione determina quale app viene usata per partecipare alle riunioni Skype for Business e viene rispettata indipendentemente dal valore della modalità di coesistenza.
      - **App Riunioni Skype**
      - **Skype for Business con funzionalità limitate**
    - Impostare se scaricare **l'app Teams in background per gli utenti di Skype for Business.**  Questa impostazione scarica automaticamente l'app Teams per gli utenti che eseguono Skype for Business in Windows. Viene rispettato solo se la modalità di coesistenza per l'utente è Solo Teams o se le notifiche di aggiornamento in sospeso sono abilitate in Skype for Business.
3. Fare **clic su** Salva dopo aver apportato le modifiche.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Impostare le opzioni di aggiornamento per un singolo utente dell'organizzazione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro passare a **Utenti** e quindi selezionare l'utente nell'elenco. 
2. Nella scheda **Account per** l'utente, in Aggiornamento **di Teams,** fare clic su **Modifica.**
3. È possibile impostare la **modalità di coesistenza.** Scegliere una delle opzioni seguenti:
     - **Usa impostazioni a livello di organizzazione:** usare questa impostazione se si vuole che l'utente usi le impostazioni nelle **impostazioni a livello di** organizzazione. 
     - **Isole:** usare questa impostazione se si vuole che l'utente sia in grado di usare sia Skype for Business che Teams. 
     - **Solo Skype for Business:** usare questa impostazione se si vuole che l'utente usi Skype for Business.
     - **Collaborazione di Skype for Business con Teams:** usare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
      - Collaborazione e riunioni di Skype for Business con **Teams:** usare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali) e le riunioni di Teams.
     - **Solo Teams:** usare questa impostazione se si vuole che l'utente usi solo Teams. L'utente potrà comunque partecipare alle riunioni Skype for Business.
4. Se si seleziona una modalità di **coesistenza** diversa da Usa impostazioni a livello di **organizzazione,** è possibile abilitare le notifiche nell'app Skype for Business dell'utente che l'aggiornamento a Teams sarà disponibile a breve. È possibile abilitare questa notifica per l'utente attivando l'opzione Notifica all'utente **Skype for Business.**
5. Fare **clic su** Salva dopo aver apportato le modifiche.

### <a name="related-topics"></a>Argomenti correlati
[Pianificare il viaggio](upgrade-plan-journey.md)

[Comprendere il percorso di coesistenza e aggiornamento per Skype for Business e Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)