---
title: Restrizioni per le chiamate in uscita - Servizi di audioconferenza & chiamate PSTN
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Gli amministratori possono controllare il tipo di audioconferenza e le chiamate PSTN degli utenti finali che possono essere effettuate dagli utenti.
ms.openlocfilehash: bbe2641cfd642e4ffd0cf6af901df059190740bf60ddbb8dfc5d82ba58c98380
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332548"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente

Gli amministratori possono usare i controlli delle chiamate in uscita per limitare il tipo di audioconferenza e le chiamate PSTN (Public Switched Telephone Network) degli utenti finali che possono essere effettuate dagli utenti dell'organizzazione.

I controlli delle chiamate in uscita possono essere applicati in base all'utente o al tenant e forniscono i due controlli seguenti per limitare in modo indipendente ogni tipo di chiamata in uscita. Per impostazione predefinita, entrambi i controlli sono impostati per consentire chiamate in uscita nazionali e internazionali.

|Controllo|Descrizione|Opzioni di controllo|
|:-----|:-----|:-----|
|Chiamate PSTN per servizi di audioconferenza|Limita il tipo di messaggi in uscita </br>chiamate consentite dall'interno </br>riunioni organizzate da un utente.|Qualsiasi destinazione (impostazione predefinita)</br>Nello stesso paese o area geografica dell'organizzatore </br> [Solo paesi o aree geografiche dell'area A](audio-conferencing-zones.md) </br>Non consentire|
|Chiamate PSTN per l'utente finale|Limita il tipo di chiamata </br>che può essere effettuata da un utente.|Internazionale e Nazionale (impostazione predefinita)</br>Nazionale</br>Nessuno|

Per scoprire quali paesi e aree geografiche sono considerati zona A, vedere Aree geografiche per [audioconferenze.](audio-conferencing-zones.md)

   > [!NOTE]
   > Una chiamata è considerata nazionale se il numero composto si trova nello stesso paese in cui è stato configurato Microsoft 365 o Office 365 per l'organizzatore della riunione (nel caso delle audioconferenze) o per l'utente finale (nel caso di chiamate PSTN dell'utente finale).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Limitare le chiamate in uscita per le audioconferenze

![logo Microsoft Teams logo ](media/teams-logo-30x30.png) **Con l'interfaccia Microsoft Teams di amministrazione**

1. Nel riquadro di spostamento sinistro selezionare **Utenti** e quindi selezionare il nome visualizzato dell'utente nell'elenco degli utenti disponibili.

3. Accanto a **Audioconferenza** selezionare **Modifica.**

4. In **Uscita da riunioni** selezionare l'opzione di restrizione della chiamata in uscita desiderata.

5. Selezionare **Salva**.

![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Utenti di **audioconferenza** e quindi selezionare l'utente nell'elenco degli  >  utenti disponibili.

2. Nel riquadro Azioni selezionare **Modifica.**

3.  In **Restrizioni alle chiamate in uscita** dalle riunioni di questo utente selezionare l'opzione di restrizione della chiamata in uscita desiderata.

      ![Opzioni Restrizioni per le chiamate in uscita](media/restrictions-to-dial-outs.png)

4. Selezionare **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utilizzo di PowerShell**

Le restrizioni per le chiamate in uscita sono controllate da un singolo criterio denominato OnlineDialOutPolicy, che ha un attributo di restrizione per ogni criterio. Il criterio non può essere personalizzato, ma esistono istanze dei criteri predefinite per ogni combinazione di impostazioni.

È possibile usare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e usare il comando seguente per la configurazione.

**Impostare i criteri a livello di utente con il cmdlet seguente.** Il cmdlet Grant non contiene la parola "Online" come fa il cmdlet Get.

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Impostare i criteri a livello di tenant con il cmdlet seguente.**

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

Tutti gli utenti del tenant a cui non è assegnato alcun criterio di accesso remoto riceveranno questo criterio. Gli altri utenti rimangono con i criteri correnti.

La tabella seguente fornisce una panoramica di ogni criterio.

|Cmdlet di PowerShell|Descrizione|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    L'utente della conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e può anche effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    L'utente della conferenza può effettuare chiamate in uscita solo con numeri nazionali e può effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    L'utente della conferenza non può effettuare chiamate in uscita. Questo utente può effettuare chiamate in uscita verso numeri internazionali e nazionali.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    L'utente della conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e può effettuare solo chiamate in uscita verso numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    L'utente della conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e non può effettuare chiamate in uscita verso numeri PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    L'utente della conferenza può effettuare chiamate in uscita solo con numeri nazionali e può effettuare solo chiamate in uscita verso numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    L'utente della conferenza può effettuare chiamate in uscita solo con numeri nazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    L'utente alla conferenza non può effettuare chiamate in uscita e può effettuare solo chiamate in uscita verso numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    L'utente alla conferenza non può effettuare chiamate in uscita e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    L'utente della conferenza può effettuare chiamate in uscita solo nei paesi e nelle aree geografiche dell'area [A](audio-conferencing-zones.md)e può effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    L'utente della conferenza può effettuare chiamate in uscita solo nei paesi e nelle aree geografiche dell'area [A](audio-conferencing-zones.md)e può effettuare solo chiamate in uscita verso il numero PSTN nazionale.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    L'utente della conferenza può effettuare chiamate in uscita solo nei paesi e nelle aree geografiche dell'area [A](audio-conferencing-zones.md)e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
