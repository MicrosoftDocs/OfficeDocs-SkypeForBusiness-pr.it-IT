---
title: Aggiornare Skype for business online a Microsoft Teams | Distribuire
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da un deployement di Skype for business online.
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
ms.openlocfilehash: 70700e0a05fb3d647fb8c0b26e0d15ecb8371671
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940506"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Eseguire l'aggiornamento da Skype for business online a teams

![Aggiornare il diagramma di viaggio, enfatizzando la distribuzione e l'implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)
- [Scelto il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparare l'organizzazione](https://aka.ms/SkypeToTeams-UserReadiness)
- [Condotto un pilota](https://aka.ms/SkypeToTeams-Pilot)

Seguire le indicazioni di questo articolo se si è completamente distribuito Skype for business online e si vuole aggiornare gli utenti da Skype for business a teams. È possibile aggiornare gli utenti in modo selettivo o all-in, in base al percorso di aggiornamento scelto dall'organizzazione, assegnando la modalità di coesistenza e l'aggiornamento appropriata agli utenti.

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams. Tieni presente che un aggiornamento corretto allinea la disponibilità tecnica e degli utenti, quindi assicurati di sfruttare le linee guida qui mentre navighi in Microsoft teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Assegnare la modalità di coesistenza e aggiornamento

Puoi aggiornare gli utenti alla modalità TeamsOnly assegnando l'istanza di UpgradeToTeams di TeamsUpgradePolicy, che può essere eseguita usando l'interfaccia di amministrazione di Microsoft teams o una sessione remota di Windows PowerShell per Skype for business. Puoi eseguire questa operazione per ogni utente o in base a un tenant, se vuoi aggiornare l'intero tenant in un solo passaggio. 

Per altre informazioni, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: gestione della migrazione e della coesistenza](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Aggiornare tutti gli utenti a teams in una sola volta

Seguire questa procedura per aggiornare tutti gli utenti ai team contemporaneamente.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Passaggio 1: notificare agli utenti la modifica (facoltativo)

1. Nell'interfaccia di amministrazione di Microsoft teams selezionare l'aggiornamento dei team di **impostazioni a livello di organizzazione**  >  **Teams upgrade**.
2. In **modalità di coesistenza**cambiare gli **utenti di Notify Skype for business che è disponibile un aggiornamento a teams** **su**attivato.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Passaggio 2: impostare la modalità di coesistenza su TeamsOnly per l'organizzazione

1. Nell'interfaccia di amministrazione di Microsoft teams selezionare **impostazioni a livello di organizzazione**.
2. Selezionare modalità **solo teams** nell'elenco a discesa **modalità di coesistenza** .

## <a name="upgrade-users-in-stages"></a>Aggiornare gli utenti in fasi

Seguire questa procedura se si vuole aggiornare gradualmente gli utenti a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Passaggio 1: identificare i gruppi di utenti per l'aggiornamento

Spesso le organizzazioni possono scegliere di aggiornare le loro organizzazioni in ondate di successo degli utenti.  È consigliabile identificare prima di tutto questi utenti, in modo da poterli cercare facilmente nell'interfaccia di amministrazione di Microsoft teams. In alternativa, è consigliabile usare PowerShell per eseguire questa operazione in modo più efficiente. Dopo aver identificato il set di utenti per una determinata onda di aggiornamento, continuare con i passaggi rimanenti.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Passaggio 2: impostare la notifica per gli utenti nell'onda di aggiornamento corrente (facoltativo)

Se si usa l'interfaccia di amministrazione di Microsoft teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft teams seleziona **utenti**e trova e seleziona la casella di controllo per un massimo di 20 utenti che devono essere aggiornati. 
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra del controllo ListView. 
3. Nel riquadro **Modifica impostazioni** a destra, in **aggiornamento teams**, cambia **notifica l'opzione utente Skype for business** su **attiva**. Nota: se il valore della modalità di coesistenza è "Usa impostazioni a livello di organizzazione", non vedrai questo interruttore, quindi dovrai prima impostare esplicitamente la modalità di coesistenza per questi utenti in qualsiasi valore predefinito sia per l'organizzazione.

In alternativa, è possibile che sia più facile abilitare le notifiche per i gruppi di utenti contemporaneamente usando PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Passaggio 3: impostare la modalità di coesistenza per gli utenti solo per i team

Quando si è pronti per aggiornare gli utenti nell'onda corrente per usare teams come unica applicazione, impostare la modalità di coesistenza per gli utenti solo per i team.

Se si usa l'interfaccia di amministrazione di Microsoft teams, è possibile configurare TeamsUpgradePolicy per un massimo di 20 utenti contemporaneamente:
1. Nell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**e quindi selezionare la casella di controllo per un massimo di 20 utenti.
2. Selezionare **Modifica impostazioni** nell'angolo in alto a sinistra del controllo ListView.
3. Nel riquadro **Modifica impostazioni** a destra, in sezione **aggiornamento teams** , impostare la modalità di coesistenza su **Teams only** nell'elenco a discesa.

In alternativa, è possibile che sia più facile aggiornare i gruppi di utenti contemporaneamente usando PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Passaggio 4: ripetere i passaggi 1-3 per le onde successive degli utenti

Quando si convalida l'aggiornamento alla modalità solo teams e si è pronti per espandersi, ripetere i passaggi precedenti per applicare TeamsOnly a più utenti.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefonico e opzioni di connettività PSTN

Il sistema telefonico con teams è supportato dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità isole, il sistema telefonico è supportato solo con Skype for business.  

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si considerano le opzioni di connettività PSTN (Public Switched Telephone Network), è possibile passare da Skype for business online alla modalità TeamsOnly in due scenari:

- Un utente in Skype for business online con un piano di chiamata Microsoft. Dopo l'aggiornamento, questo utente continuerà ad avere un piano per le chiamate Microsoft. Questo è lo scenario più semplice che richiede solo un paio di passaggi. Per altre informazioni, Vedi [da Skype for business online con i piani per le chiamate Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Un utente in Skype for business online con funzionalità vocali locali tramite Skype for business locale o Cloud Connector Edition. L'aggiornamento dell'utente ai team deve essere coordinato con la migrazione dell'utente per indirizzare il routing per garantire che l'utente di TeamsOnly abbia funzionalità PSTN.  Per altre informazioni, vedere [da Skype for business online con la voce locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).


