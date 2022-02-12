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
description: Informazioni su come usare l Microsoft Teams di amministrazione per visualizzare un elenco di tutti i numeri di telefono dell'organizzazione e di tutti i numeri assegnati agli utenti o non assegnati.
ms.openlocfilehash: 45d292ae1ba4ffd714f0c302fe140978968ba1c9
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763629"
---
# <a name="see-a-list-of-telephone-numbers"></a>Visualizzare un elenco di numeri di telefono 

Esistono diversi tipi di numeri di telefono che è possibile assegnare agli utenti o alle applicazioni vocali, ad esempio [audioconferenze](deploy-audio-conferencing-teams-landing-page.md) [o code di chiamata](plan-auto-attendant-call-queue.md). Per altre informazioni, vedere [Gestire i numeri di telefono per l'organizzazione](/microsoftteams/manage-phone-numbers-landing-page).

Questo articolo si applica ai Piani per chiamate e Connessione con operatore. Per informazioni su Routing diretto, vedere [Configurare il numero di telefono e abilitare voIP aziendale](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Per visualizzare tutti i numeri di telefono dell'organizzazione

Per visualizzare un elenco di tutti i numeri di telefono dell'organizzazione:

1. Passare **all'Microsoft Teams di amministrazione.**

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

3. Per visualizzare i numeri di telefono assegnati, vedere la colonna **Stato** assegnazione, che mostra anche il tipo di servizio a cui è assegnato il numero.

4. Per filtrare la visualizzazione, fare clic sull'icona del filtro. Nel riquadro **Filtro** è possibile usare l'elenco a discesa per filtrare la visualizzazione in base a:

   - **Intervallo di** numeri impostato. È possibile eseguire la ricerca in base al numero più basso o al numero più alto.

   - Numeri che iniziano con un numero specificato dall'utente.

   - Stato **di attivazione dei numeri**.

   - Tipo **di numero**.

   - Telefono stato **del numero**.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Per visualizzare tutti i numeri di telefono assegnati agli utenti

Quando si configurano gli utenti, è consigliabile visualizzare l'elenco dei numeri di telefono già assegnati agli utenti e i numeri di telefono disponibili per l'assegnazione.

1. Passare **all'Microsoft Teams di amministrazione.**

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione  Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Microsoft Teams, è necessario prima acquistare almeno una licenza **Enterprise E5**, una licenza per componenti aggiuntivi **Sistema telefonico** o una licenza per i componenti aggiuntivi per audioconferenze.

3. Per ordinare rapidamente i numeri in modo da vedere quali sono assegnati, fare clic **sull'intestazione di colonna Stato** assegnazione. In caso contrario, è possibile fare clic sull'icona del filtro e quindi filtrare la visualizzazione per visualizzare i numeri di telefono già assegnati agli utenti o i numeri non assegnati che è possibile assegnare a un utente. È possibile filtrare per:

   - **Assegnato all'utente**
   - **Assegnato a bridge di conferenza** 
   - **Assegnato all'app Vocale (Operatore automatico/Coda di chiamata)**
   - **Non assegnato**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Per visualizzare tutti i numeri di telefono assegnati agli utenti vocali

Quando si configurano gli utenti dell'organizzazione per effettuare e ricevere chiamate telefoniche, è necessario prima ottenere i numeri di telefono e quindi assegnarli agli utenti. Dopo aver ottenuto i numeri di telefono, potrebbe essere necessario visualizzare lo stato di attivazione delle assegnazioni di numeri.
  
1. Passare **all'Microsoft Teams di amministrazione.**

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

3. Fare clic sull'icona del filtro per filtrare la visualizzazione in base **allo stato di attivazione**. È possibile filtrare per:

   - **Attivato**
   - **Attività in sospeso**
   - **Assegnazione non riuscita**
   - **Aggiornamento in sospeso**
   - **Aggiornamento non riuscito**

## <a name="using-the-teams-powershell-module"></a>Uso del modulo Teams PowerShell

È possibile usare il modulo di PowerShell di Teams per ottenere le stesse informazioni dalle sezioni precedenti, ma è richiesta la versione 1.1.6 o successiva, che include l'integrazione del connettore Skype for Business Online. Per altre informazioni sul modulo, vedere panoramica Microsoft Teams [PowerShell](teams-powershell-overview.md).

Per visualizzare un elenco di tutti i numeri di telefono disponibili per l'organizzazione, usare il cmdlet [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) . Ad esempio, per visualizzare ogni numero di telefono e il relativo stato, eseguire il comando seguente:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Per visualizzare tutti i numeri di telefono assegnati agli utenti, usare il cmdlet [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) . Ad esempio, per visualizzare tutti gli utenti a cui è assegnato un numero di telefono, eseguire il comando seguente:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)