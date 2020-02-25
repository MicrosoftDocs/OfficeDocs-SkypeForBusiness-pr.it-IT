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
description: Informazioni su come usare l'interfaccia di amministrazione di Microsoft teams per visualizzare un elenco di tutti i numeri di telefono dell'organizzazione e tutti i numeri assegnati agli utenti o non assegnati.
ms.openlocfilehash: 029f5f15e4d414ed2f6bc4e06d39b3456b32ee62
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236856"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Visualizzare un elenco di numeri di telefono assegnati nell'organizzazione

Esistono diversi tipi di numeri di telefono che è possibile assegnare a utenti o altri servizi (numeri di servizio), ad esempio per le Conferenze Audio in Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>Per visualizzare un elenco di tutti i numeri di telefono che hai per la tua organizzazione

![Icona che mostra il logo](media/teams-logo-30x30.png) teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Accedere all'interfaccia di **amministrazione di Microsoft teams**.

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione **Voice** nella barra di spostamento sinistra nell'interfaccia di amministrazione di Skype for business, è necessario prima acquistare almeno una licenza **Enterprise E5**, una licenza per il componente aggiuntivo per il **sistema telefonico** o una licenza per il componente aggiuntivo per i servizi di **audioconferenza** .

3. Per visualizzare i numeri di telefono assegnati, vedere la colonna **stato** .

4. Per filtrare la visualizzazione, fare clic sull'icona filtro. Nel riquadro **filtro** è possibile usare l'elenco a discesa per filtrare la visualizzazione in base a:

   - **Intervallo di numeri** impostato. È possibile eseguire una ricerca in base al numero più basso o al numero più alto.

   - Numeri che iniziano con un numero specificato.

   - **Stato attivazione**numero.

   - **Tipo**di numero.

   - **Stato**numero di telefono.

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>Per visualizzare tutti i numeri di telefono che vengono assegnati agli utenti

Quando si configurano gli utenti, è possibile visualizzare l'elenco dei numeri di telefono già assegnati agli utenti e quali sono i numeri di telefono disponibili per l'assegnazione.
  
![Icona che mostra il logo](media/teams-logo-30x30.png) teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Accedere all'interfaccia di **amministrazione di Microsoft teams**.

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione **Voice** nella barra di spostamento sinistra nell'interfaccia di amministrazione di Microsoft teams, è necessario prima acquistare almeno una licenza **Enterprise E5**, una licenza per il componente aggiuntivo per il **sistema telefonico** o una licenza per il componente aggiuntivo per i servizi di **audioconferenza** .

3. Per ordinare rapidamente i numeri per vedere quali sono assegnati, fare clic sull'intestazione della colonna **stato** . In alternativa, è possibile fare clic sull'icona del filtro e quindi filtrare la visualizzazione per visualizzare i numeri di telefono già assegnati agli utenti o ai numeri non assegnati che è possibile assegnare a un utente. È possibile filtrare per:

   - **Assegnato all'utente**

   - **Assegnato a Bridge conferenza** 

   - **Nessuno**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>Per visualizzare i numeri di telefono assegnati agli utenti voce

Quando si configurano gli utenti dell'organizzazione per effettuare e ricevere chiamate telefoniche, è necessario prima di tutto ottenere i numeri di telefono e quindi assegnarli agli utenti. Dopo aver ottenuto i numeri di telefono, è possibile che si voglia vedere lo stato di attivazione delle assegnazioni numeriche.

![Icona che mostra il logo](media/teams-logo-30x30.png) teams **con l'interfaccia di amministrazione di Microsoft teams** .
  
1. Accedere all'interfaccia di **amministrazione di Microsoft teams**.

2. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione **Voice** nella barra di spostamento sinistra nell'interfaccia di amministrazione di Microsoft teams, è necessario prima acquistare almeno una licenza **Enterprise E5**, una licenza per il componente aggiuntivo per il **sistema telefonico** o una licenza per il componente aggiuntivo per i servizi di **audioconferenza** .

3. Fare clic sull'icona del filtro per filtrare la visualizzazione in base **allo stato di attivazione** in cui è possibile filtrare:

   - **Attivato**

   - **Assegnazione in sospeso**

   - **Assegnazione non riuscita**

   - **Aggiornamento in sospeso**

   - **Aggiornamento non riuscito**

## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber)
  
 
