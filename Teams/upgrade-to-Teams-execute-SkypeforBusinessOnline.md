---
title: Eseguire l'aggiornamento da Skype for Business online a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione di Skype for Business Online.
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578259"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Eseguire l'aggiornamento da Skype for Business online a Teams

![Diagramma percorso di aggiornamento, enfatizzando distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità comprensibili di Skype for Business e Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Organizzazione preparata](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ha diretto un pilota](https://aka.ms/SkypeToTeams-Pilot)

Segui le indicazioni in questo articolo se hai distribuito completamente Skype for Business online e desideri aggiornare gli utenti da Skype for Business a Teams. È possibile aggiornare gli utenti in modo selettivo o all-in, in base al percorso di aggiornamento scelto dall'organizzazione, assegnando agli utenti la modalità di coesistenza e aggiornamento appropriata.

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per ottimizzare la realizzazione dei vantaggi e garantire alla tua organizzazione il tempo necessario per implementare il tuo aggiornamento, ti consigliamo di iniziare oggi stesso il tuo percorso verso Microsoft Teams. Ricorda che un aggiornamento riuscito allinea la preparazione tecnica e quella degli utenti, quindi assicurati di avvalerti delle indicazioni riportate qui mentre ti snavigare verso Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Assegnare la modalità di coesistenza e aggiornamento

Puoi aggiornare gli utenti alla modalità TeamsOnly assegnando l'istanza UpgradeToTeams di TeamsUpgradePolicy, che può essere eseguita utilizzando l'interfaccia di amministrazione di Microsoft Teams o una sessione di Windows PowerShell remota di Skype for Business. È possibile eseguire questa operazione a livello di utente o a livello di tenant se si vuole aggiornare l'intero tenant in un unico passaggio. 

Per altre informazioni, vedere Impostazione delle impostazioni di [coesistenza](https://aka.ms/SkypeToTeams-SetCoexistence) e aggiornamento [e TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Aggiornare tutti gli utenti a Teams contemporaneamente

Seguire questa procedura per aggiornare tutti gli utenti a Teams contemporaneamente.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Passaggio 1: Informare gli utenti della modifica (facoltativo)

1. Nell'interfaccia di amministrazione di Microsoft Teams, selezionare Impostazioni **a livello di organizzazione Aggiornamento** di  >  **Teams.**
2. In **modalità coesistenza,** imposta l'interruttore Informa gli utenti di Skype for Business che è disponibile un aggiornamento **a** **Teams.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Passaggio 2: Impostare la modalità di coesistenza su TeamsOnly per l'organizzazione

1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Impostazioni a livello di organizzazione.**
2. Selezionare **modalità Solo** teams nell'elenco a discesa Modalità di **coesistenza.**

## <a name="upgrade-users-in-stages"></a>Aggiornare gli utenti in più fasi

Seguire questa procedura se si vuole aggiornare gradualmente gli utenti a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Passaggio 1: Identificare i gruppi di utenti per l'aggiornamento

Spesso le organizzazioni possono scegliere di aggiornare la propria organizzazione in gruppi di utenti di successo.  È prima di tutto necessario identificare questi utenti in modo da poterli cercare facilmente nell'interfaccia di amministrazione di Microsoft Teams. In alternativa, è possibile usare PowerShell per eseguire questa operazione in modo più efficiente. Dopo aver identificato il set di utenti per una determinata ondata di aggiornamenti, continuare con i passaggi rimanenti.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Passaggio 2: Impostare la notifica per gli utenti nella fase di aggiornamento corrente (facoltativo)

Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare Utenti e trovare e selezionare più caselle di controllo per un massimo di 20 utenti da aggiornare. 
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco. 
3. Nel riquadro **Modifica impostazioni a** destra, in Aggiornamento **Teams,** modifica Informa l'utente **di Skype for Business** su **Attiva.** Nota: se il valore della modalità di coesistenza è "Usa impostazioni a livello di organizzazione", questo parametro non viene visualizzato, quindi è necessario prima impostare esplicitamente la modalità di coesistenza per questi utenti sul valore predefinito per l'organizzazione.

In alternativa, può risultare più facile abilitare le notifiche per gruppi di utenti contemporaneamente con PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Passaggio 3: Impostare la modalità di coesistenza per gli utenti solo su Teams

Quando si è pronti ad aggiornare gli utenti nella corrente per usare Teams come unica applicazione, impostare la modalità di coesistenza per gli utenti solo su Teams.

Se si usa l'interfaccia di amministrazione di Microsoft Teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti,** quindi selezionare la casella di controllo per un massimo di 20 utenti.
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra della visualizzazione elenco.
3. Nel riquadro **Modifica impostazioni a** destra, nella sezione aggiornamento di **Teams,** impostare la modalità di coesistenza su **Solo team** nell'elenco a discesa.

In alternativa, può risultare più semplice aggiornare gruppi di utenti contemporaneamente con PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Passaggio 4: Ripetere i passaggi da 1 a 3 per gruppi di utenti successivi

Quando si convalida l'aggiornamento alla modalità Solo Teams ed è pronto per l'espansione, ripetere i passaggi precedenti per applicare TeamsOnly a più utenti.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opzioni di connettività Sistema telefonico e PSTN

Sistema telefonico con Teams è supportato dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità Isole, il Sistema telefonico è supportato solo con Skype for Business.  

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), ci sono due scenari possibili quando si passa dalla modalità Skype for Business Online alla modalità TeamsOnly:

- Un utente in Skype for Business online, con un Piano per chiamate Microsoft. Al momento dell'aggiornamento, l'utente continuerà a disporre di un piano per le chiamate Microsoft. Questo è lo scenario più semplice che richiede solo un paio di passaggi. Per ulteriori informazioni, consulta [Da Skype for Business online con Piani per chiamate Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- Un utente in Skype for Business online, con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per garantire che l'utente TeamsOnly abbia funzionalità PSTN.  Per ulteriori informazioni, [vedere Da Skype for Business online con voce locale.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)


