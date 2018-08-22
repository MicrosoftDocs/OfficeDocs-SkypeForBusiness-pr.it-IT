---
title: Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare il tipo di utente finale e servizi di conferenza PSTN le chiamate audio che possono essere effettuate dagli utenti.
ms.openlocfilehash: 6096816ef9fb98811ec3ebed5a56b90a90b58c29
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490576"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente

In qualità di amministratore, è possibile utilizzare i controlli delle chiamate in uscita per limitare il tipo di utente finale e servizi di conferenza PSTN le chiamate audio che possono essere effettuate dagli utenti nell'organizzazione. 

Controlli delle chiamate in uscita possono essere applicati a ogni utente e forniscono i seguenti due controlli per limitare in modo indipendente ogni tipo di chiamate in uscita. Per impostazione predefinita, entrambi i controlli sono impostati per consentire le chiamate in uscita nazionali e internazionali. 

|Controllo|Descrizione|Opzioni di controllo|
|:-----|:-----|:-----|
|Chiamate PSTN per conferenze audio|Consente di limitare il tipo di in uscita </br>chiamate a cui sono consentite dall'interno </br>riunioni organizzate dall'utente.|International e interno (impostazione predefinita)</br>Nazionale</br>Nessuno|
|Chiamate PSTN degli utenti finali|Consente di limitare il tipo di chiamate </br>che può essere effettuata da un utente.|International e interno (impostazione predefinita)</br>Nazionale</br>Nessuno|

   > [!NOTE]
   > Una chiamata è considerata interno se è il numero di telefono chiamato nello stesso paese del paese che è stato impostato in Office 365 per l'organizzatore della riunione (nel caso di conferenze audio) o l'utente finale (nel caso di chiamate PSTN degli utenti finali). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Limitare le chiamate in uscita audioconferenze con accesso esterno 

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**.

4. In **autorizzazioni di chiamata in uscita dalle riunioni**, selezionare l'opzione di chiamata esterna per una restrizione desiderato.

5. Fai clic su **Salva**. 

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1.  Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2.  In the Action pane, click **Edit**.

3.  In **restrizioni alla connessione-outs dalle riunioni dell'utente**, selezionare l'opzione di chiamata in uscita restrizione desiderato.

    ![Le restrizioni alle opzioni di chiamate](../images/restrictions-to-dial-outs.png)

5. Fai clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Utilizzo di PowerShell**

Limitazioni delle chiamate in uscita sono controllati da un singolo criterio denominato OnlineDialOutPolicy che ha un attributo di restrizione per ogni. Non è possibile personalizzare il criterio, bensì sono disponibili le istanze dei criteri predefiniti per ogni combinazione delle impostazioni. 

È possibile utilizzare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e assegnrli a utenti utilizzando il cmdlet Grant-CSDialOutPolicy. (Si noti che il cmdlet Grant non contiene la parola "Online" in modo analogo al cmdlet Get.) 

Nella tabella seguente viene fornita una panoramica di ogni criterio.

|||
|:-----|:-----|
|Identità = 'tag: DialoutCPCandPSTNInternational'    |    Utente nella conferenza effettuare chiamate ai numeri nazionali e internazionali e l'utente può inoltre effettuare chiamate in uscita per i numeri nazionali e internazionali.    |
|Identità = 'tag: DialoutCPCDomesticPSTNInternational'  |    Solo utente alla conferenza effettuare chiamate ai numeri nazionali e l'utente può effettuare chiamate in uscita per i numeri nazionali e internazionali.    |
|    Identità = 'tag: DialoutCPCDisabledPSTNInternational'    |    Utente alla conferenza non può effettuare qualsiasi dial out. L'utente può effettuare chiamate in uscita per i numeri nazionali e internazionali.    |
|    Identità = 'tag: DialoutCPCInternationalPSTNDomestic'    |    Utente nella conferenza effettuare chiamate ai numeri nazionali e internazionali e l'utente può effettuare solo chiamate in uscita a numero PSTN interna.    |
|    Identità = 'tag: DialoutCPCInternationalPSTNDisabled'    |    Utente nella conferenza effettuare chiamate ai numeri nazionali e internazionali e l'utente non può effettuare chiamate in uscita numero PSTN oltre ai numeri di emergenza.    |
|    Identità = 'tag: DialoutCPCandPSTNDomestic'    |    Solo utente alla conferenza effettuare chiamate ai numeri nazionali e l'utente può effettuare solo chiamate in uscita a numeri PSTN interne.    |
|    Identità = 'tag: DialoutCPCDomesticPSTNDisabled'    |    Solo utente alla conferenza effettuare chiamate ai numeri di interno e all'utente non può effettuare chiamate in uscita numero PSTN oltre ai numeri di emergenza.    |
|    Identità = 'tag: DialoutCPCDisabledPSTNDomestic'    |    Utente alla conferenza non può effettuare le chiamate in uscita e l'utente può effettuare solo chiamate in uscita a numeri PSTN interne.    |
|    Identità = 'tag: DialoutCPCandPSTNDisabled'    |    Utente alla conferenza non può effettuare le chiamate in uscita e l'utente non può effettuare chiamate in uscita numero PSTN oltre ai numeri di emergenza.    |
