---
title: Eseguire l'aggiornamento da Skype for Business Online a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione di Skype for Business Online.
ms.localizationpriority: medium
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
ms.openlocfilehash: 49376910ce9ca0f777533e950600a19bd440c27f
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846555"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Eseguire l'aggiornamento da Skype for Business Online a Teams

![Diagramma percorso di aggiornamento, enfatizzando la distribuzione e l'implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Ha raggruppato gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definito l'ambito del progetto](./upgrade-define-project-scope.md)
- [Coesistenza e interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Scelta del percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Seguire le istruzioni in questo articolo se si è distribuito interamente Skype for Business Online e si vuole aggiornare gli utenti da Skype for Business a Teams. È possibile aggiornare gli utenti in modo selettivo o automatico, in base al percorso di aggiornamento scelto dall'organizzazione, assegnando agli utenti la modalità di coesistenza e aggiornamento appropriata.

> [!IMPORTANT]
> Skype for Business Online è stato ritirato il 31 luglio 2021. Per massimizzare la realizzazione dei vantaggi e garantire che la tua organizzazione abbia il tempo giusto per implementare il tuo aggiornamento, ti invitiamo a iniziare il tuo viaggio verso Microsoft Teams oggi stesso. Ricorda che un aggiornamento riuscito allinea la preparazione tecnica e dell'utente, quindi assicurati di sfruttare le indicazioni qui riportate mentre ti sposti nel tuo percorso verso Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Assegnare la coesistenza e la modalità di aggiornamento

È possibile aggiornare gli utenti alla modalità TeamsOnly assegnando l'istanza UpgradeToTeams di TeamsUpgradePolicy, che può essere eseguita usando l'interfaccia di amministrazione di Microsoft Teams o un Skype for Business sessione di Windows PowerShell remota. È possibile eseguire questa operazione in base all'utente o a livello di tenant se si vuole aggiornare l'intero tenant in un unico passaggio. 

Per altre informazioni, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md) e [TeamsUpgradePolicy: gestione della migrazione e coesistenza](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Aggiornare tutti gli utenti a Teams contemporaneamente

Seguire questa procedura per aggiornare tutti gli utenti a Teams contemporaneamente.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Passaggio 1: Informare gli utenti della modifica (facoltativo)

1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Teams** >  **Teams impostazioni di aggiornamento**.
2. In **Modalità coesistenza** impostare l'interruttore **Notifica agli utenti Skype for Business che è disponibile un aggiornamento a Teams** su **Attivato**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Passaggio 2: Impostare la modalità di coesistenza su TeamsOnly per l'organizzazione

1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Teams** >  **Teams impostazioni di aggiornamento**.
2. Selezionare **Teams modalità Solo** nell'elenco a discesa **Modalità coesistenza**.

## <a name="upgrade-users-in-stages"></a>Aggiornare gli utenti in più fasi

Seguire questa procedura se si vuole aggiornare gradualmente gli utenti a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Passaggio 1: Identificare i gruppi di utenti per l'aggiornamento

Spesso le organizzazioni possono scegliere di eseguire l'aggiornamento nelle onde di successo degli utenti.  È consigliabile identificare prima questi utenti in modo da poterli cercare facilmente nell'interfaccia di amministrazione di Microsoft Teams. In alternativa, è consigliabile usare PowerShell per eseguire questa operazione in modo più efficiente. Dopo aver identificato il set di utenti per una determinata fase di aggiornamento, continuare con i passaggi rimanenti.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Passaggio 2: Impostare la notifica per gli utenti nell'attuale fase di aggiornamento (facoltativo)

Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti**, quindi trovare e selezionare la casella di controllo per un massimo di 20 utenti che devono essere aggiornati. 
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco. 
3. Nel riquadro **Modifica impostazioni** a destra, in **Teams aggiornamento**, impostare **Notifica all'utente Skype for Business** su **Attivato**. Nota: se il valore della modalità coesistenza è "Usa impostazioni a livello di organizzazione", l'opzione non verrà visualizzata, quindi è necessario impostare in modo esplicito la modalità di coesistenza per questi utenti su qualsiasi valore predefinito per l'organizzazione.

In alternativa, potrebbe risultare più facile abilitare le notifiche per gruppi di utenti contemporaneamente usando PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Passaggio 3: Impostare la modalità di coesistenza per gli utenti su solo Teams

Quando si è pronti per aggiornare gli utenti nella fase corrente in modo da usare Teams come unica applicazione, impostare la modalità di coesistenza per gli utenti su Teams Solo.

Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti** e quindi selezionare la casella di controllo per un massimo di 20 utenti.
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco.
3. Nel riquadro **Modifica impostazioni** a destra, in **Teams sezione aggiornamento**, impostare la modalità di coesistenza **su Teams Solo** nell'elenco a discesa.

In alternativa, potrebbe risultare più facile aggiornare gruppi di utenti contemporaneamente usando PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Passaggio 4: Ripetere i passaggi da 1 a 3 per le successive onde di utenti

Quando si convalida l'aggiornamento alla modalità solo Teams e si è pronti per l'espansione, ripetere i passaggi precedenti per applicare TeamsOnly a più utenti.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opzioni di connettività Sistema telefonico e PSTN

Sistema telefonico con Teams è supportata dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità Isole, Sistema telefonico è supportato solo con Skype for Business.  

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), ci sono due possibili scenari quando si passa da Skype for Business Online alla modalità TeamsOnly:

- Un utente in Skype for Business Online, con un piano per chiamate Microsoft. Al momento dell'aggiornamento, l'utente continuerà ad avere un piano per le chiamate Microsoft. Questo è lo scenario più semplice che richiede solo un paio di passaggi. Per ulteriori informazioni, vedi [Da Skype for Business Online con Piani per chiamate Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Un utente in Skype for Business Online, con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per garantire che l'utente TeamsOnly disponga di funzionalità PSTN.  Per altre informazioni, vedere [Da Skype for Business Online con la voce locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).
