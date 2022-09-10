---
title: Restrizioni alle chiamate in uscita - Audioconferenza & chiamate PSTN
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.topic: article
ms.service: msteams
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Gli amministratori possono controllare il tipo di audioconferenza e chiamate PSTN per l'utente finale che possono essere effettuate dagli utenti.
ms.openlocfilehash: 67c138db8522ec6eee1f384e182f5c8d01ea40fd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641767"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente

Gli amministratori possono usare i controlli delle chiamate in uscita per limitare il tipo di audioconferenza e chiamate PSTN (Public Switched Telephone Network) per utente finale che possono essere effettuate dagli utenti dell'organizzazione.

I controlli delle chiamate in uscita possono essere applicati in base all'utente o a un tenant e fornire i due controlli seguenti per limitare in modo indipendente ogni tipo di chiamata in uscita. Per impostazione predefinita, entrambi i controlli sono impostati per consentire chiamate in uscita internazionali e nazionali.

|Controllo|Descrizione|Opzioni di controllo|
|:-----|:-----|:-----|
|Chiamate PSTN dei servizi di audioconferenza|Limita il tipo di connessioni in uscita </br>chiamate consentite dall'interno </br>riunioni organizzate da un utente.|Qualsiasi destinazione (impostazione predefinita)</br>Nello stesso paese o area geografica dell'organizzatore </br> [Solo paesi o aree geografiche dell'area A](audio-conferencing-zones.md) </br>Non consentire|
|Chiamate PSTN per utente finale|Limita il tipo di chiamata </br>che può essere effettuata da un utente.|Internazionale e Nazionale (impostazione predefinita)</br>Domestico</br>Nessuno|

Per scoprire quali paesi e aree geografiche sono considerati Zona A, vedi [Paesi e aree geografiche per i servizi di audioconferenza](audio-conferencing-zones.md).

   > [!NOTE]
   > Una chiamata viene considerata nazionale se il numero composto si trova nello stesso paese in cui Microsoft 365 o Office 365 è stato configurato per l'organizzatore della riunione (nel caso delle audioconferenze) o l'utente finale (nel caso di chiamate PSTN dell'utente finale).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Limitare le chiamate in uscita per i servizi di audioconferenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro selezionare **Utenti** e quindi selezionare il nome visualizzato dell'utente nell'elenco degli utenti disponibili.

2. Passa quindi a **Audioconferenza**, seleziona **Modifica**.

3. In **Chiamata in uscita dalle riunioni** selezionare l'opzione di restrizione della chiamata in uscita desiderata.

4. Selezionare **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Le restrizioni delle chiamate in uscita sono controllate da un singolo criterio denominato OnlineDialOutPolicy, che ha un attributo di restrizione per ognuno di essi. Il criterio non può essere personalizzato, ma sono presenti istanze di criteri predefinite per ogni combinazione di impostazioni.

È possibile usare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e usare il comando seguente per la configurazione.

**Impostare il criterio a livello di utente con il cmdlet seguente**. Il cmdlet Grant non contiene la parola "Online" come fa il cmdlet Get.

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Impostare il criterio a livello di tenant con il cmdlet seguente**.

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

Questo criterio verrà assegnato a tutti gli utenti del tenant a cui non sono assegnati criteri di chiamata. Gli altri utenti mantengono i criteri correnti.

**Controllare il criterio corrente a livello di tenant con il cmdlet seguente**.

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

La tabella seguente fornisce una panoramica di ogni criterio.

|Cmdlet di PowerShell|Descrizione|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    L'utente che partecipa alla conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e può anche effettuare chiamate in uscita verso numeri nazionali e internazionali.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    L'utente nella conferenza può effettuare chiamate in uscita solo a numeri nazionali e questo utente può effettuare chiamate in uscita a numeri nazionali e internazionali.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    L'utente che partecipa alla conferenza non può effettuare chiamate in uscita. Questo utente può effettuare chiamate in uscita a numeri internazionali e nazionali.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    Gli utenti della conferenza possono effettuare chiamate in uscita verso numeri internazionali e nazionali e questo utente può effettuare chiamate in uscita solo a numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    L'utente che partecipa alla conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    L'utente che partecipa alla conferenza può effettuare chiamate in uscita solo a numeri nazionali e può effettuare chiamate in uscita solo a numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    L'utente che partecipa alla conferenza può effettuare chiamate in uscita solo a numeri nazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    L'utente nella conferenza non può effettuare chiamate in uscita e questo utente può effettuare chiamate in uscita solo a numeri PSTN nazionali.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    L'utente nella conferenza non può effettuare chiamate in uscita e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    L'utente che partecipa alla conferenza può effettuare chiamate in uscita solo nei [paesi e nelle aree geografiche della Zona A](audio-conferencing-zones.md) e può effettuare chiamate in uscita a numeri nazionali e internazionali.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    Gli utenti della conferenza possono effettuare chiamate in uscita solo verso i [paesi e le aree geografiche della zona A](audio-conferencing-zones.md) e questo utente può effettuare chiamate in uscita solo al numero PSTN nazionale.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    L'utente che partecipa alla conferenza può effettuare chiamate in uscita solo nei [paesi e nelle aree geografiche della Zona A](audio-conferencing-zones.md) e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
