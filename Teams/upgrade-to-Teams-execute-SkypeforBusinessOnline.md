---
title: Eseguire l'aggiornamento da Skype for Business online a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Scopri come aggiornare la tua organizzazione a Microsoft Teams da una distribuzione skype for business online.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104012"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Eseguire l'aggiornamento da Skype for Business Online a Teams

![Diagramma del percorso di aggiornamento, enfatizzando la distribuzione e l'implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
- [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Segui le indicazioni di questo articolo se hai completamente distribuito Skype for Business online e desideri aggiornare gli utenti da Skype for Business a Teams. È possibile aggiornare gli utenti in modo selettivo o all-in, in base al percorso di aggiornamento scelto dall'organizzazione, assegnando la modalità di coesistenza e aggiornamento appropriata agli utenti.

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti consigliamo di iniziare il tuo viaggio verso Microsoft Teams oggi stesso. Tenere presente che un aggiornamento riuscito allinea la conformità tecnica e quella dell'utente, quindi assicurarsi di usare le indicazioni qui riportate mentre ci si sposta verso Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Assegnare la modalità di coesistenza e aggiornamento

È possibile aggiornare gli utenti alla modalità TeamsOnly assegnando l'istanza UpgradeToTeams di TeamsUpgradePolicy, che può essere eseguita usando l'interfaccia di amministrazione di Microsoft Teams o una sessione di Windows PowerShell remota di Skype for Business. È possibile eseguire questa operazione in base all'utente o a livello di tenant se si vuole aggiornare l'intero tenant in un unico passaggio. 

Per altre informazioni, vedere Impostazione delle impostazioni di [coesistenza](./setting-your-coexistence-and-upgrade-settings.md) e aggiornamento e [TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Aggiornare tutti gli utenti a Teams contemporaneamente

Seguire questa procedura per aggiornare tutti gli utenti a Teams contemporaneamente.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Passaggio 1: Informare gli utenti della modifica (facoltativo)

1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Impostazioni a livello di organizzazione Aggiornamento** di  >  **Teams**.
2. In **Modalità di coesistenza** cambiare l'opzione Notifica agli utenti **di Skype for Business** che è disponibile un aggiornamento a Teams su **Attivata.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Passaggio 2: Impostare la modalità di coesistenza su TeamsOnly per l'organizzazione

1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Impostazioni a livello di organizzazione.**
2. Selezionare **Modalità solo** Teams nell'elenco a discesa Modalità di **coesistenza.**

## <a name="upgrade-users-in-stages"></a>Aggiornare gli utenti a fasi

Seguire questa procedura se si vuole aggiornare gradualmente gli utenti a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Passaggio 1: Identificare gruppi di utenti per l'aggiornamento

Spesso le organizzazioni possono scegliere di aggiornare le proprie organizzazioni in gruppi di utenti di successo.  È necessario identificare prima questi utenti in modo da poterli cercare facilmente nell'interfaccia di amministrazione di Microsoft Teams. In alternativa, è possibile usare PowerShell per eseguire questa operazione in modo più efficiente. Dopo aver identificato il set di utenti per una determinata ondata di aggiornamento, continuare con i passaggi rimanenti.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Passaggio 2: Impostare la notifica per gli utenti nell'ondata di aggiornamento corrente (facoltativo)

Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti** e trovare e selezionare la casella di controllo per un massimo di 20 utenti da aggiornare. 
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco. 
3. Nel riquadro **Modifica impostazioni a** destra, in Aggiornamento di **Teams,** impostare Notifica all'utente **di Skype for Business** su **Attivata.** Nota: se il valore della modalità di coesistenza è "Usa impostazioni a livello di organizzazione", questa opzione non verrà visualizzata, quindi sarà necessario prima impostare esplicitamente la modalità di coesistenza per questi utenti su qualsiasi valore predefinito sia per l'organizzazione.

In alternativa, può risultare più facile abilitare le notifiche per gruppi di utenti contemporaneamente usando PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Passaggio 3: Impostare la modalità di coesistenza per gli utenti su Solo Teams

Quando si è pronti per aggiornare gli utenti nell'ondata corrente per usare Teams come unica applicazione, impostare la modalità di coesistenza per gli utenti su Solo Teams.

Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti** e quindi selezionare la casella di controllo per un massimo di 20 utenti.
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco.
3. Nel riquadro **Modifica impostazioni a** destra, nella sezione Aggiornamento di **Teams,** impostare la modalità di coesistenza su Solo **Teams** nell'elenco a discesa.

In alternativa, può risultare più semplice aggiornare gruppi di utenti contemporaneamente usando PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Passaggio 4: Ripetere i passaggi da 1 a 3 per le successive ondate di utenti

Quando si convalida l'aggiornamento alla modalità Solo Teams e si è pronti per l'espansione, ripetere i passaggi precedenti per applicare TeamsOnly ad altri utenti.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opzioni di connettività sistema telefonico e PSTN

Sistema telefonico con Teams è supportato dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità Isole, Sistema telefonico è supportato solo con Skype for Business.  

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), è possibile passare dalla modalità Skype for Business Online alla modalità TeamsOnly in due scenari:

- Un utente in Skype for Business online, con un piano per chiamate Microsoft. Al momento dell'aggiornamento, questo utente continuerà a avere un piano Per chiamate Microsoft. Questo è lo scenario più semplice che richiede solo un paio di passaggi. Per altre informazioni, consulta [Da Skype for Business online con piani per chiamate Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- Un utente in Skype for Business online, con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per assicurarsi che l'utente TeamsOnly abbia la funzionalità PSTN.  Per altre informazioni, vedere Da Skype for Business online con voce [locale.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)