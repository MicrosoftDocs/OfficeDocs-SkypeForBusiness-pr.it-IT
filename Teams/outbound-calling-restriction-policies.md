---
title: Restrizioni alle chiamate in uscita - Audioconferenza & chiamate PSTN
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
description: Gli amministratori possono controllare il tipo di audioconferenza e di chiamate PSTN degli utenti finali che possono essere effettuate dagli utenti.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908655"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente

Gli amministratori possono usare i controlli per le chiamate in uscita per limitare il tipo di audioconferenze e di chiamate PSTN che possono essere eseguite dagli utenti nell'organizzazione. 

I controlli delle chiamate in uscita possono essere applicati per utente e forniscono i due controlli seguenti per limitare in modo indipendente ogni tipo di chiamata in uscita. Per impostazione predefinita, entrambi i controlli sono impostati per consentire chiamate in uscita nazionali e internazionali. 

|Controllo|Descrizione|Opzioni di controllo|
|:-----|:-----|:-----|
|Chiamate PSTN per audioconferenze|Limita il tipo di connessioni in uscita </br>chiamate consentite dall'interno </br>riunioni organizzate da un utente.|Qualsiasi destinazione (impostazione predefinita)</br>Nello stesso paese o area geografica dell'organizzatore </br> [Solo paesi o aree geografiche dell'area A](audio-conferencing-zones.md) </br>Non consentire|
|Chiamate PSTN dell'utente finale|Limita il tipo di chiamata </br>che può essere effettuata da un utente.|Internazionale e nazionale (impostazione predefinita)</br>Nazionale</br>Nessuno|

Per sapere quali paesi e aree geografiche sono considerati Area A, consulta Paese e aree [geografiche per le audioconferenze.](audio-conferencing-zones.md)

   > [!NOTE]
   > Una chiamata è considerata nazionale se il numero composto si trova nello stesso paese in cui Microsoft 365 o Office 365 è stato configurato per l'organizzatore della riunione (nel caso dei servizi di audioconferenza) o per l'utente finale (nel caso delle chiamate PSTN dell'utente finale). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Limitare le chiamate in uscita per i servizi di audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi sul nome visualizzato dell'utente nell'elenco di utenti disponibili.

3. Accanto a **Audioconferenza,** fai clic **su Modifica.**

4. In **Chiamata in uscita dalle riunioni** selezionare l'opzione di restrizione per la chiamata in uscita desiderata.

5. Fare clic su **Salva**. 

![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. **Nell'interfaccia di amministrazione di Skype for Business,** nella barra di spostamento sinistra, accedi a Utenti di **audioconferenza** e quindi seleziona l'utente dall'elenco  >  degli utenti disponibili.

2. In the Action pane, click **Edit**.

3.  In **Restrizioni alle chiamate in** uscita dalle riunioni di questo utente, selezionare l'opzione di restrizione per la chiamata in uscita desiderata.

      ![Restrizioni alle opzioni di chiamata in uscita](media/restrictions-to-dial-outs.png)
      

4. Fare clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utilizzo di PowerShell**

Le limitazioni delle chiamate in uscita sono controllate da un singolo criterio denominato OnlineDialOutPolicy, che ha un attributo di restrizione per ognuno di essi. Il criterio non può essere personalizzato, ma esistono istanze di criteri predefinite per ogni combinazione di impostazioni. 

È possibile usare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e assegnarli agli utenti usando Grant-CSDialOutPolicy cmdlet. Tenere presente che il cmdlet Grant non contiene la parola "Online" come fa il cmdlet Get. 

La tabella seguente fornisce una panoramica di ogni criterio.

|||
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    L'utente che è presente alla conferenza può effettuare chiamate in uscita verso numeri nazionali e internazionali e può effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    L'utente alla conferenza può effettuare chiamate in uscita solo a numeri nazionali e può effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    L'utente che è in conferenza non può effettuare chiamate in uscita. Questo utente può effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    L'utente che è in conferenza può effettuare chiamate in uscita verso numeri nazionali e internazionali e può effettuare chiamate in uscita solo verso numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    L'utente alla conferenza può effettuare chiamate in uscita verso numeri nazionali e internazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    L'utente che è in conferenza può effettuare chiamate in uscita solo a numeri nazionali e può effettuare chiamate in uscita solo su numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    L'utente alla conferenza può effettuare chiamate in uscita solo a numeri nazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    L'utente che è in conferenza non può effettuare chiamate in uscita e può effettuare chiamate in uscita solo verso numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    L'utente alla conferenza non può effettuare chiamate in uscita e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    L'utente alla conferenza può effettuare chiamate in uscita solo verso i paesi e le aree geografiche dell'Area [A](audio-conferencing-zones.md)e può effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    L'utente alla conferenza può effettuare chiamate in uscita solo verso i paesi e le aree geografiche dell'Area [A](audio-conferencing-zones.md)e può effettuare chiamate in uscita solo verso numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    L'utente alla conferenza può effettuare chiamate in uscita solo verso i paesi e le aree geografiche dell'Area [A](audio-conferencing-zones.md)e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
