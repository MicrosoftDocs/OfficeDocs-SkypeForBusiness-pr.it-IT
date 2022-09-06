---
title: Visualizzare un elenco di numeri di telefono nell'organizzazione
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Informazioni su come usare l'interfaccia di amministrazione di Microsoft Teams per visualizzare un elenco di tutti i numeri di telefono dell'organizzazione e di tutti i numeri assegnati agli utenti o non assegnati.
ms.openlocfilehash: ac7c63515b34b8c199f8050933b6c3ccbc6f8d33
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606075"
---
# <a name="see-a-list-of-telephone-numbers"></a>Visualizzare un elenco di numeri di telefono 

Esistono diversi tipi di numeri di telefono che è possibile assegnare agli utenti o ad applicazioni vocali come [Audioconferenze](deploy-audio-conferencing-teams-landing-page.md) o [Code di chiamata](plan-auto-attendant-call-queue.md). Per altre informazioni, vedere [Gestire i numeri di telefono per l'organizzazione](/microsoftteams/manage-phone-numbers-landing-page).

Questo articolo si applica ai Piani per chiamate, Operator Connect e Connessione con operatore di telefonia mobile (versione di anteprima pubblica). Per informazioni sull'instradamento diretto, vedere [Configurare il numero di telefono e abilitare la voce aziendale](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Per visualizzare tutti i numeri di telefono dell'organizzazione

Per visualizzare un elenco di tutti i numeri di telefono dell'organizzazione:

1. Passare **all'interfaccia di amministrazione di Microsoft Teams**.

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

3. Per visualizzare i numeri di telefono assegnati, vedere la colonna **Stato assegnazione** , che mostra anche il tipo di servizio a cui è assegnato il numero.

4. Per filtrare la visualizzazione, fare clic sull'icona del filtro. Nel riquadro **Filtro** è possibile usare l'elenco a discesa per filtrare la visualizzazione in base a:

   - **Intervallo di numeri** impostato. È possibile eseguire la ricerca in base al numero più basso o al numero più alto.

   - Numeri che iniziano con un numero specificato dall'utente.

   - Stato **di attivazione** del numero.

   - **Tipo di numero**.

   - **Stato** del numero di telefono.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Per visualizzare tutti i numeri di telefono assegnati agli utenti

Quando si configurano gli utenti, è sufficiente visualizzare l'elenco dei numeri di telefono già assegnati agli utenti e i numeri di telefono disponibili per l'assegnazione.

1. Passare **all'interfaccia di amministrazione di Microsoft Teams**.

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione **Voce** nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Microsoft Teams, è necessario acquistare almeno una **licenza Enterprise E5**, una licenza per il componente aggiuntivo **Sistema telefonico** o una licenza per i componenti aggiuntivi **di Audioconferenza** .

3. Per ordinare rapidamente i numeri in modo da vedere quali sono assegnati, fare clic sull'intestazione della colonna **Stato assegnazione** . In alternativa, è possibile fare clic sull'icona del filtro e quindi filtrare la visualizzazione per visualizzare i numeri di telefono già assegnati agli utenti o i numeri non assegnati che è possibile assegnare a un utente. È possibile filtrare per:

   - **Assegnato all'utente**
   - **Assegnato a bridge di conferenza** 
   - **Assegnato all'app Voce (Operatore automatico/Coda di chiamata)**
   - **Nessuno**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Per visualizzare tutti i numeri di telefono assegnati agli utenti vocali

Quando si impostano gli utenti dell'organizzazione per effettuare e ricevere chiamate telefoniche, è necessario ottenere i numeri di telefono e quindi assegnarli agli utenti. Dopo aver ottenuto i numeri di telefono, potresti voler visualizzare lo stato di attivazione delle assegnazioni dei numeri.
  
1. Passare **all'interfaccia di amministrazione di Microsoft Teams**.

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

3. Fare clic sull'icona del filtro per filtrare la visualizzazione in base **allo stato di attivazione**. È possibile filtrare per:

   - **Attivato**
   - **Attività in sospeso**
   - **Assegnazione non riuscita**
   - **Aggiornamento in sospeso**
   - **Aggiornamento non riuscito**

## <a name="using-the-teams-powershell-module"></a>Uso del modulo di Teams PowerShell

È possibile usare il modulo PowerShell di Teams per ottenere le stesse informazioni dalle sezioni precedenti, ma è necessaria la versione 1.1.6 o successiva, che include l'integrazione del connettore online Skype for Business. Per altre informazioni sul modulo, vedere [Panoramica di PowerShell di Microsoft Teams](teams-powershell-overview.md).

Per visualizzare un elenco di tutti i numeri di telefono disponibili per l'organizzazione, usa il cmdlet [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) . Ad esempio, per visualizzare ogni numero di telefono, il relativo tipo e lo stato, eseguire il comando seguente:

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

Per visualizzare tutti i numeri di telefono assegnati agli utenti, utilizza il cmdlet [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) . Ad esempio, per visualizzare tutti gli utenti a cui è assegnato un numero di telefono, eseguire il comando seguente:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
