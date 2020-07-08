---
title: Restrizioni delle chiamate in uscita-audioconferenza & chiamate PSTN
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
description: Gli amministratori possono controllare il tipo di audioconferenza e chiamate PSTN degli utenti finali che possono essere effettuate dagli utenti.
ms.openlocfilehash: fd7c30a7561c06dd237bb72b405c8fc5b7b68dcd
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077671"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente

Gli amministratori possono usare i controlli per le chiamate in uscita per limitare il tipo di audioconferenze e di chiamate PSTN che possono essere eseguite dagli utenti nell'organizzazione. 

I controlli delle chiamate in uscita possono essere applicati per ogni singolo utente e offrono i due controlli seguenti per limitare in modo indipendente ogni tipo di chiamata in uscita. Per impostazione predefinita, entrambi i controlli sono impostati per consentire chiamate in uscita internazionali e nazionali. 

|Controllo|Descrizione|Opzioni di controllo|
|:-----|:-----|:-----|
|Chiamate PSTN per servizi di audioconferenza|Limita il tipo di in uscita </br>chiamate consentite dall'interno </br>riunioni organizzate da un utente.|Qualsiasi destinazione (impostazione predefinita)</br>Nello stesso paese o area geografica di organizor </br> </br>Area solo paesi o aree geografiche </br>Non consentire|
|Chiamate PSTN degli utenti finali|Limita il tipo di chiamate </br>che possono essere eseguite da un utente.|Internazionali e nazionali (impostazione predefinita)</br>Nazionali</br>Nessuno|

Per scoprire quali paesi/aree geografiche sono considerate zone A, vedere [zone a paesi/aree geografiche](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).

   > [!NOTE]
   > Una chiamata è considerata domestica se il numero composto si trova nello stesso paese in cui è stato configurato Microsoft 365 o Office 365 per l'organizzatore della riunione (nel caso di servizi di audioconferenza) o per l'utente finale (nel caso di chiamate PSTN degli utenti finali). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Limitare le chiamate in uscita per i servizi di audioconferenza 

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. Accanto a servizi di **audioconferenza**fare clic su **modifica**.

4. In **autorizzazioni di accesso esterno da riunioni**selezionare l'opzione di restrizione della chiamata in uscita desiderata.

5. Fare clic su **Salva**. 

![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1.    Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, passa a utenti di servizi di **audioconferenza**  >  **Users**e quindi seleziona l'utente nell'elenco degli utenti disponibili.

2.    In the Action pane, click **Edit**.

3.    In **restrizioni ai dial-out delle riunioni di questo utente**selezionare l'opzione di restrizione chiamata in uscita desiderata.

    ![Le restrizioni alle opzioni per i dial-out](/Skype/SfbOnline/images/restrictions-to-dial-outs.png)

5. Fare clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utilizzo di PowerShell**

Le restrizioni delle chiamate in uscita sono controllate da un singolo criterio denominato OnlineDialOutPolicy che contiene un attributo di restrizione per ogni. I criteri non possono essere personalizzati, ma esistono istanze di criteri predefinite per ogni combinazione delle impostazioni. 

Puoi usare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e assegnarli agli utenti usando il cmdlet Grant-CSDialOutPolicy. Tieni presente che il cmdlet Grant non contiene la parola "online" come fa il cmdlet Get. 

La tabella seguente offre una panoramica di ogni criterio.

|||
|:-----|:-----|
|Identity =' Tag: DialoutCPCandPSTNInternational '    |    L'utente della conferenza può effettuare chiamate in uscita per i numeri nazionali e internazionali, e questo utente può anche eseguire una chiamata in uscita a numeri nazionali e internazionali.    |
|Identity =' Tag: DialoutCPCDomesticPSTNInternational '  |    L'utente nella conferenza può effettuare la chiamata solo ai numeri nazionali e questo utente può eseguire chiamate in uscita a numeri nazionali e internazionali.    |
|    Identity =' Tag: DialoutCPCDisabledPSTNInternational '    |    L'utente della conferenza non può effettuare una chiamata esterna. Questo utente può effettuare chiamate in uscita a numeri nazionali e internazionali.    |
|    Identity =' Tag: DialoutCPCInternationalPSTNDomestic '    |    L'utente della conferenza può effettuare una chiamata esterna a numeri nazionali e internazionali e questo utente può eseguire chiamate in uscita solo al numero PSTN nazionale.    |
|    Identity =' Tag: DialoutCPCInternationalPSTNDisabled '    |    L'utente della conferenza può effettuare una chiamata esterna a numeri nazionali e internazionali e questo utente non può eseguire chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity =' Tag: DialoutCPCandPSTNDomestic '    |    L'utente nella conferenza può effettuare la chiamata solo ai numeri nazionali e questo utente può eseguire solo chiamate in uscita ai numeri PSTN nazionali.    |
|    Identity =' Tag: DialoutCPCDomesticPSTNDisabled '    |    L'utente nella conferenza può effettuare la chiamata solo ai numeri nazionali e questo utente non può eseguire chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity =' Tag: DialoutCPCDisabledPSTNDomestic '    |    L'utente della conferenza non può effettuare chiamate in uscita e questo utente può solo effettuare una chiamata in uscita ai numeri PSTN nazionali.    |
|    Identity =' Tag: DialoutCPCandPSTNDisabled '    |    L'utente della conferenza non può effettuare chiamate in uscita e questo utente non può effettuare alcuna chiamata in uscita al numero PSTN oltre ai numeri di emergenza.    |
|    Identity =' Tag: DialoutCPCZoneAPSTNInternational '    |    L'utente nella conferenza può effettuare la chiamata solo per la zona di paesi e aree geografiche e questo utente può eseguire chiamate in uscita a numeri nazionali e internazionali.    |
|    Identity =' Tag: DialoutCPCZoneAPSTNDomestic '    |    L'utente nella conferenza può effettuare la chiamata solo per la zona di paesi e aree geografiche e questo utente può eseguire solo chiamate in uscita al numero PSTN nazionale.    |
|    Identity =' Tag: DialoutCPCZoneAPSTNDisabled '    |    L'utente nella conferenza può effettuare la chiamata solo per la zona di paesi e aree geografiche e questo utente non può eseguire chiamate in uscita al numero PSTN oltre ai numeri di emergenza.    |
