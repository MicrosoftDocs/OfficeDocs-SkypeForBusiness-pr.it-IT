---
title: Configurare le impostazioni di aggiornamento e coesistenza
author: dstrome
ms.author: dstrome
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
ms.openlocfilehash: 489f5315df8c818fd674e30fdaef7c057e9a8ff3
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536497"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configurare le impostazioni di aggiornamento e coesistenza


Quando si aggiornano i Skype for Business utenti per usare Teams, sono disponibili diverse opzioni per semplificare il processo per gli utenti. È possibile apportare contemporaneamente le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione oppure apportare modifiche alle impostazioni per un singolo o un set di utenti dell'organizzazione. Tenere presente che le versioni precedenti Skype for Business client potrebbero non rispettare queste impostazioni. Per altre informazioni sulle Skype for Business client, passare alla pagina Skype for Business [download e aggiornamenti.](/skypeforbusiness/software-updates) 

Per una migliore comprensione delle modalità [disponibili,](teams-and-skypeforbusiness-coexistence-and-interoperability.md) vedere Comprendere Microsoft Teams e Skype for Business coesistenza e interoperabilità o [Coesistenza](coexistence-chat-calls-presence.md)con Skype for Business .  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Impostare le opzioni di aggiornamento per tutti gli utenti dell'organizzazione

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. [Nell'Microsoft Teams di amministrazione,](https://admin.teams.microsoft.com/)nel riquadro di spostamento sinistro, passare a **Impostazioni** a livello di organizzazione  >  **Teams aggiornamento.** 

2. Nella parte superiore della pagina **Teams di aggiornamento** modificare le opzioni seguenti nel modo desiderato.

    - Impostare la **modalità di coesistenza.**
        - **Isole:** usare questa impostazione se si vuole consentire agli utenti di usare contemporaneamente Skype for Business e Teams.
        - **Skype for Business: usare** questa impostazione se si vuole che gli utenti usino solo Skype for Business.
        - **Skype for Business con Teams** collaborazione: usare questa impostazione se si vuole che gli utenti usino Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
        - **Skype for Business** con Teams di collaborazione e riunioni: usare questa impostazione se si vuole che gli utenti usino Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali) e le riunioni Teams riunioni.
        - **Teams: usare** questa impostazione se si vuole che gli utenti usino solo Teams. Anche con questa impostazione, gli utenti possono comunque partecipare alle riunioni ospitate in Skype for Business.

          > [!IMPORTANT]
          > È possibile assegnare la modalità TeamsOnly all'intero tenant solo dopo aver completato entrambi i passaggi seguenti:
          >  - Tutti gli utenti locali sono stati spostati in Teams solo usando Move-CsUser nel set di strumenti Skype for Business Server locale.
          >  - Sono stati aggiornati tutti i record DNS Skype for Business in modo che puntino a Microsoft 365. 
          >
          > Per altre informazioni, vedere [Disabilitare la configurazione ibrida per completare la](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)migrazione a Teams solo .
        
    - Impostare **Avvisa Skype for Business utenti che Teams disponibili per l'aggiornamento**. Se si attiva questa opzione, gli utenti Skype for Business che presto verranno aggiornati all'app Teams.

    - Impostare **l'app Preferred per consentire agli utenti di partecipare a Skype for Business riunioni.** Questa impostazione determina quale app viene usata per partecipare a Skype for Business riunioni e viene rispettata indipendentemente dal valore della modalità di coesistenza.
      - **Skype App Riunioni**
      - **Skype for Business con funzionalità limitate**

    - Impostare se scaricare **l'app Teams in background per Skype for Business utenti**.  Questa impostazione scarica automaticamente l'app Teams per gli utenti che eseguono Skype for Business in Windows. Viene rispettato solo se la modalità di coesistenza per l'utente Teams solo o se le notifiche di aggiornamento in sospeso sono abilitate in Skype for Business.

3. Fare **clic su** Salva dopo aver apportato le modifiche.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Impostare le opzioni di aggiornamento per un singolo utente dell'organizzazione

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro passare a **Utenti** e quindi selezionare l'utente nell'elenco. 
2. Nella scheda **Account** per l'utente, in **Teams,** fare clic su **Modifica.**
3. È possibile impostare la **modalità di coesistenza.** Le modalità diverse da Teams possono essere applicate solo agli utenti ospitati in Skype for Business Server locale e, al contrario, solo gli utenti ospitati nel cloud possono avere la modalità TeamsOnly.  Scegliere una delle opzioni seguenti:
     - **Usa impostazioni a livello di organizzazione:** usare questa impostazione se si vuole che l'utente usi le impostazioni nelle **impostazioni a livello di** organizzazione. 
     - **Isole:** usare questa impostazione se si vuole che l'utente sia in grado di usare sia Skype for Business che Teams. 
     - **Skype for Business: usare** questa impostazione se si vuole che l'utente usi Skype for Business.
     - **Skype for Business con Teams** collaborazione: usare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
      - **Skype for Business** con Teams e riunioni: usare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali) e le riunioni Teams riunioni.
     - **Teams: usare** questa impostazione se si vuole che l'utente usi solo Teams. L'utente potrà comunque partecipare a Skype for Business riunioni.
4. Se si seleziona una modalità di **coesistenza** diversa da Usa impostazioni a livello di **organizzazione,** è possibile abilitare le notifiche nell'app Skype for Business dell'utente che esegue l'aggiornamento a Teams sarà disponibile a breve. È possibile abilitare questa notifica per l'utente attivando l'opzione Notifica **Skype for Business'utente.**
5. Fare **clic su** Salva dopo aver apportato le modifiche.

### <a name="related-topics"></a>Argomenti correlati
[Pianificare il viaggio](upgrade-plan-journey.md)

[Comprendere il percorso di coesistenza e aggiornamento per Skype for Business e Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Rimuovere le autorizzazioni dell'ambiente Skype for Business locale](/skypeforbusiness/hybrid/decommission-on-prem-overview)
