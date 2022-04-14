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
description: Informazioni su come impostare le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione contemporaneamente o per uno o più utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 474c5fc55476e664ba03b9dd82608d8c244b7982
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839187"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Configurare le impostazioni di aggiornamento e coesistenza


Quando si aggiorna il Skype for Business gli utenti a usare Teams, sono disponibili diverse opzioni per semplificare il processo per gli utenti. È possibile impostare le impostazioni di coesistenza e aggiornamento per tutti gli utenti dell'organizzazione contemporaneamente oppure apportare modifiche alle impostazioni per uno o più utenti dell'organizzazione. Si noti che le versioni precedenti dei client Skype for Business potrebbero non rispettare queste impostazioni. Per altre informazioni su Skype for Business versioni client, vai alla [pagina download e aggiornamenti di Skype for Business](/skypeforbusiness/software-updates). 

È possibile comprendere meglio le modalità disponibili leggendo [Comprendere Microsoft Teams e Skype for Business coesistenza e interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) o [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Impostare le opzioni di aggiornamento per tutti gli utenti dell'organizzazione

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro [dell'interfaccia](https://admin.teams.microsoft.com/) di amministrazione di Microsoft Teams passare a **Teams** >  **Teams impostazioni di aggiornamento**. 

2. Nella parte superiore della pagina **di aggiornamento Teams** modificare le opzioni seguenti in base alle esigenze.

    - Impostare la modalità **di coesistenza** .
        - **Isole**: usare questa impostazione se si vuole consentire agli utenti di usare sia Skype for Business che Teams contemporaneamente.
        - **solo Skype for Business**: usare questa impostazione se si vuole che gli utenti usno solo Skype for Business.
        - **Skype for Business con Teams collaborazione**: usare questa impostazione se si vuole che gli utenti usno Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
        - **Skype for Business con Teams collaborazione e riunioni**: usare questa impostazione se si vuole che gli utenti usno Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali) e le riunioni Teams.
        - **solo Teams**: usare questa impostazione se si vuole che gli utenti usno solo Teams. Anche con questa impostazione, gli utenti possono comunque partecipare a riunioni ospitate in Skype for Business.

          > [!IMPORTANT]
          > È possibile assegnare la modalità TeamsOnly all'intero tenant solo dopo aver completato entrambi i passaggi seguenti:
          >  - Tutti gli utenti locali sono stati spostati in Teams Solo usando Move-CsUser nel set di strumenti Skype for Business Server locale.
          >  - Tutti i record DNS Skype for Business sono stati aggiornati in modo che puntino a Microsoft 365. 
          >
          > Per altre informazioni, vedere [Disabilitare la configurazione ibrida per completare la migrazione a solo Teams](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
        
    - Impostare **Notifica Skype for Business utenti che Teams è disponibile per l'aggiornamento**. Se si attiva questa opzione, gli utenti Skype for Business indicheranno agli utenti che presto verranno aggiornati all'app Teams.

    - Impostare **l'app Preferita per consentire agli utenti di partecipare Skype for Business riunioni**. Questa impostazione determina quale app viene usata per partecipare a Skype for Business riunioni e viene rispettata indipendentemente dal valore della modalità di coesistenza.
      - **app Riunioni Skype**
      - **Skype for Business con funzionalità limitate**

    - Imposta se **scaricare l'app Teams in background per Skype for Business utenti**. Questa impostazione scarica automaticamente l'app Teams per gli utenti che eseguono Skype for Business in Windows. Viene applicato solo se la modalità di coesistenza per l'utente è Teams solo o se le notifiche di aggiornamento in sospeso sono abilitate in Skype for Business.

3. Dopo aver apportato le modifiche, fare clic su **Salva** .

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Impostare le opzioni di aggiornamento per un singolo utente dell'organizzazione

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro passare a **UtentiGesti** >  utenti e quindi selezionare l'utente nell'elenco. 
2. Nella scheda **Account** per l'utente, in **Teams aggionamento**, fare clic su **Modifica**.
3. È possibile impostare la **modalità coesistenza**. Le modalità diverse da Teams Solo possono essere applicate solo agli utenti ospitati in Skype for Business Server locale e viceversa solo gli utenti ospitati nel cloud possono avere la modalità TeamsOnly.  Scegli una delle opzioni seguenti:
     - **Usare le impostazioni a livello di organizzazione** : usare questa impostazione se si vuole che l'utente usi le impostazioni nelle impostazioni **a livello di organizzazione** . 
     - **Isole**: usare questa impostazione se si vuole che l'utente possa usare sia Skype for Business che Teams. 
     - **solo Skype for Business**: usare questa impostazione se si vuole che l'utente usi Skype for Business.
     - **Skype for Business con Teams collaborazione**: usare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali).
      - **Skype for Business con Teams collaborazione e riunioni** - Usare questa impostazione se si vuole che l'utente usi Skype for Business oltre a usare Teams per la collaborazione di gruppo (canali) e Teams riunioni.
     - **solo Teams**: usare questa impostazione se si vuole che l'utente usi solo Teams. L'utente potrà comunque partecipare a Skype for Business riunioni.
4. Se si seleziona una **modalità di coesistenza** diversa da **Usa impostazioni a livello di organizzazione**, è possibile abilitare le notifiche nell'app Skype for Business dell'utente che verranno aggiornate a Teams sarà presto disponibile. È possibile abilitare questa notifica per l'utente attivando l'opzione **Notifica all'utente Skype for Business**.
5. Dopo aver apportato le modifiche, fare clic su **Salva** .

### <a name="related-topics"></a>Argomenti correlati
[Pianificare il viaggio](upgrade-plan-journey.md)

[Comprendere il percorso di coesistenza e aggiornamento per Skype for Business e Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Rimuovere l'ambiente di Skype for Business locale](/skypeforbusiness/hybrid/decommission-on-prem-overview)
