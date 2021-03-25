---
title: Visualizzare un elenco di numeri di telefono assegnati nell'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Informazioni su come usare l'interfaccia di amministrazione di Microsoft Teams per visualizzare un elenco di tutti i numeri di telefono dell'organizzazione e di tutti i numeri assegnati agli utenti o non assegnati.
ms.openlocfilehash: 41eceb3618fae61308b90a88165ce1935ad6b30b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117234"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Visualizzare un elenco di numeri di telefono assegnati nell'organizzazione

Esistono diversi tipi di numeri di telefono che è possibile assegnare agli utenti o ad altri servizi (numeri di servizio), ad esempio per le audioconferenze in Microsoft 365 o Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>Per visualizzare un elenco di tutti i numeri di telefono che hai per la tua organizzazione

![Icona che mostra il logo di Teams ](media/teams-logo-30x30.png) **Usando l'interfaccia di amministrazione di Microsoft Teams**

1. Passare **all'interfaccia di amministrazione di Microsoft Teams.**

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Skype  for Business, è necessario  prima acquistare almeno una licenza **Enterprise E5,** una licenza per il componente aggiuntivo Sistema telefonico o una licenza per i componenti aggiuntivi audioconferenza. 

3. Per visualizzare i numeri di telefono assegnati, vedere la **colonna** Stato.

4. Per filtrare la visualizzazione, fare clic sull'icona del filtro. Nel riquadro **Filtro** è possibile usare l'elenco a discesa per filtrare la visualizzazione in base a:

   - **Intervallo di** numeri impostato. È possibile eseguire la ricerca in base al numero più basso o al numero più alto.

   - Numeri che iniziano con un numero specificato dall'utente.

   - Stato **di attivazione dei numeri**.

   - Tipo **di numero**.

   - Stato del numero **di telefono**.

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>Per visualizzare tutti i numeri di telefono che vengono assegnati agli utenti

Quando si configurano gli utenti, è consigliabile visualizzare l'elenco dei numeri di telefono già assegnati agli utenti e i numeri di telefono disponibili per l'assegnazione.
  
![Icona che mostra il logo di Teams ](media/teams-logo-30x30.png) **Usando l'interfaccia di amministrazione di Microsoft Teams**

1. Passare **all'interfaccia di amministrazione di Microsoft Teams.**

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Microsoft  Teams, è necessario prima  acquistare almeno una licenza **Enterprise E5,** una licenza per il componente aggiuntivo Sistema telefonico o una licenza per i componenti aggiuntivi Audioconferenza. 

3. Per ordinare rapidamente i numeri in modo da vedere quali sono assegnati, fare clic **sull'intestazione di colonna** Stato. In caso contrario, è possibile fare clic sull'icona del filtro e quindi filtrare la visualizzazione per visualizzare i numeri di telefono già assegnati agli utenti o i numeri non assegnati che è possibile assegnare a un utente. È possibile filtrare per:

   - **Assegnato all'utente**

   - **Assegnato a bridge di conferenza** 

   - **Non assegnato**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>Per visualizzare i numeri di telefono assegnati agli utenti voce

Quando si configurano gli utenti dell'organizzazione per effettuare e ricevere chiamate telefoniche, è necessario prima ottenere i numeri di telefono e quindi assegnarli agli utenti. Dopo aver ottenuto i numeri di telefono, è consigliabile visualizzare lo stato di attivazione delle assegnazioni di numeri.

![Icona che mostra il logo di Teams ](media/teams-logo-30x30.png) **Usando l'interfaccia di amministrazione di Microsoft Teams** !
  
1. Passare **all'interfaccia di amministrazione di Microsoft Teams.**

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Microsoft  Teams, è necessario prima  acquistare almeno una licenza **Enterprise E5,** una licenza per il componente aggiuntivo Sistema telefonico o una licenza per i componenti aggiuntivi Audioconferenza. 

3. Fare clic sull'icona del filtro per filtrare la visualizzazione in **base allo stato di attivazione** È possibile filtrare in base a:

   - **Attivato**

   - **Attività in sospeso**

   - **Assegnazione non riuscita**

   - **Aggiornamento in sospeso**

   - **Aggiornamento non riuscito**

## <a name="using-the-teams-powershell-module"></a>Uso del modulo di PowerShell di Teams

È possibile usare il modulo PowerShell di Teams per ottenere le stesse informazioni dalle sezioni precedenti, ma è richiesta la versione 1.1.6 o successiva, che include l'integrazione del connettore Skype for Business Online. Per altre informazioni sul modulo, vedere Panoramica [di Microsoft Teams PowerShell.](teams-powershell-overview.md)

È possibile visualizzare un elenco di tutti i numeri di telefono disponibili per l'organizzazione usando il cmdlet [Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Ad esempio, è possibile eseguire il comando seguente per visualizzare ogni numero di telefono e il relativo stato:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

È possibile visualizzare tutti i numeri di telefono assegnati agli utenti usando il cmdlet [Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Ad esempio, è possibile eseguire il comando seguente per visualizzare tutti gli utenti a cui è assegnato un numero di telefono:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Etichetta di esclusione di responsabilità per chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)