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
description: Informazioni su come configurare le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione contemporaneamente oppure per un singolo o set di utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2dbeb4d93273aab848f1b4436b46e6b22e08e53
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397571"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configurare le impostazioni di aggiornamento e coesistenza


Quando si esegue l'aggiornamento agli utenti di Skype for Business per l'uso di Teams, sono disponibili diverse opzioni che consentono di semplificare il processo per gli utenti. È possibile apportare contemporaneamente impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione oppure apportare modifiche alle impostazioni per un singolo o set di utenti dell'organizzazione. Si noti che le versioni precedenti dei client Skype for Business potrebbero non rispettare queste impostazioni. Per ulteriori informazioni sulle versioni client di Skype for Business, visita la pagina di [download e aggiornamenti di Skype for Business.](https://docs.microsoft.com/skypeforbusiness/software-updates) 

Per una migliore comprensione delle modalità disponibili, vedere Informazioni sulla coesistenza e l'interoperabilità o la coesistenza di Microsoft Teams e [Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) con Skype for [Business.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Impostare le opzioni di aggiornamento per tutti gli utenti dell'organizzazione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. [Nell'interfaccia di amministrazione di Microsoft Teams,](https://admin.teams.microsoft.com/)nella barra di spostamento sinistra, passa a Impostazioni a livello di **organizzazione** Aggiornamento  >  **di Teams.** 

2. Nella parte superiore della pagina di **aggiornamento di Teams,** modificare le opzioni seguenti nel modo desiderato.
    - Impostare la **modalità di coesistenza.**
        - **Isole** : utilizzare questa impostazione se si vuole consentire agli utenti di usare sia Skype for Business che Teams contemporaneamente.
        - **Solo Skype for Business-** Utilizzare questa impostazione se si desidera che gli utenti usino solo Skype for Business.
        - **Collaborazione di Skype for Business** con Teams - Utilizzare questa impostazione se si vuole che gli utenti usino Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
        - **Skype for Business con** la collaborazione e le riunioni di Teams - Utilizzare questa impostazione se si vuole che gli utenti usino Skype for Business oltre a usare Teams per la collaborazione (canali) di gruppo e le riunioni di Teams.
        - **Solo Teams:** usare questa impostazione se si vuole che gli utenti usino solo Teams. Anche con questa impostazione, gli utenti possono comunque partecipare alle riunioni ospitate in Skype for Business.
        
    - Impostare **Avvisa gli utenti di Skype for Business che Teams è disponibile per l'aggiornamento.** Se attivi questa opzione, gli utenti di Skype for Business saranno presto aggiornati all'app Teams.
    - Impostare **l'app preferita per consentire agli utenti di partecipare alle riunioni Skype for Business.** Questa impostazione determina quale app viene usata per partecipare alle riunioni Skype for Business e viene rispettata indipendentemente dal valore della modalità di coesistenza.
      - **App Riunioni Skype**
      - **Skype for Business con funzionalità limitate**
    - Consente di scegliere **se scaricare l'app Teams in background per gli utenti di Skype for Business.**  Questa impostazione scarica automaticamente l'app Teams per gli utenti che eseguono Skype for Business su Windows. Viene rispettata solo se la modalità di coesistenza per l'utente è solo Teams o se le notifiche di aggiornamento in sospeso sono abilitate in Skype for Business.
3. Dopo **aver** apportato le modifiche, fare clic su Salva.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Impostare le opzioni di aggiornamento per un singolo utente dell'organizzazione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro passare **a Utenti** e quindi selezionare l'utente nell'elenco. 
2. Nella scheda **Account** dell'utente, in Aggiornamento **di Teams,** fare clic su **Modifica.**
3. È possibile impostare la **modalità di coesistenza.** Scegliere una delle opzioni seguenti:
     - **Usare le impostazioni a livello di** organizzazione: usare questa impostazione se si desidera che l'utente usi le impostazioni delle impostazioni a livello **di** organizzazione. 
     - **Isole** : utilizzare questa impostazione se si vuole che l'utente possa utilizzare sia Skype for Business che Teams. 
     - **Solo Skype for Business:** utilizzare questa impostazione se si desidera che l'utente utilizzi Skype for Business.
     - **Skype for Business con la** collaborazione di Teams - Utilizzare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
      - **Skype for Business con** la collaborazione e le riunioni di Teams - Utilizzare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali) e le riunioni di Teams.
     - **Solo Teams:** usare questa impostazione se si vuole che l'utente usi solo Teams. L'utente potrà comunque partecipare alle riunioni Skype for Business.
4. Se si  seleziona una modalità di coesistenza diversa da Usa impostazioni a livello di **organizzazione,** è possibile abilitare le notifiche nell'app Skype for Business dell'utente che l'aggiornamento a Teams sarà disponibile a breve. Puoi abilitare questa notifica per l'utente attivando l'opzione Avvisa l'utente **Skype for Business.**
5. Dopo **aver** apportato le modifiche, fare clic su Salva.

### <a name="related-topics"></a>Argomenti correlati
[Pianificare il viaggio](upgrade-plan-journey.md)

[Comprendere il percorso di coesistenza e aggiornamento di Skype for Business e Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)
