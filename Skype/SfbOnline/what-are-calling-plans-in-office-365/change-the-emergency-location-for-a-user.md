---
title: Assegnare o modificare la posizione di emergenza per un utente
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Informazioni su come modificare la posizione di emergenza per gli utenti. Con un numero illimitato di posizioni, è possibile modificare le posizioni di emergenza quando i dipendenti si spostano su altri piani o edifici. '
ms.openlocfilehash: 9e583cf7882b5a269378dd69dbda37311ad08e28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233209"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a>Assegnare o modificare la posizione di emergenza per un utente

Ogni numero di telefono attivo deve avere un indirizzo di emergenza associato quando si assegna il numero di telefono a un utente. (Viene associato all'indirizzo quando si ricevono un numero di telefono in Office 365 o quando si trasferisce un numero di telefono). Quando si associa il numero a un indirizzo di emergenza, è inoltre possibile aggiungere un percorso di emergenza per fornire una posizione più preciso all'interno di una posizione fisica. La posizione per gli interventi di emergenza può corrispondere al piano, all'ala dell'edificio o al numero dell'ufficio in cui si trova l'utente. È possibile avere un numero illimitato di posizioni per un determinato indirizzo di emergenza ed è possibile modificare la posizione di emergenza se l'utente passa a un altro ufficio o edificio, ad esempio, se l'utente si sposta dal 34° al 35° piano.
  
Per informazioni su come ottenere Piani di chiamata in Office 365 e il relativo costo, consulta [Licenze per componenti aggiuntivi per Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="assign-or-change-the-emergency-location"></a>Assegnare o modificare il percorso di emergenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di team Microsoft che** > **portale Legacy**.
    
3. Nel riquadro sinistro passare a **Voice** > **agli utenti di VoIP**.
    
    > [!IMPORTANT]
    > Per poter visualizzare l'opzione **vocale** nel riquadro di spostamento sinistra in Skype per interfaccia di amministrazione di Business, è necessario acquistare una licenza di componente aggiuntivo **Per conferenze Audio** , una licenza di componente aggiuntivo di **Sistema telefonico** o almeno una **licenza Enterprise E5**.
    
4. Nella pagina **Utenti voce**, individua e seleziona l'utente a cui desideri modificare l'indirizzo di emergenza.
    
5. Nel riquadro Azioni, in **Posizione per gli interventi di emergenza**, fai clic su **Modifica**.
    
6. Nella pagina **Assegna numero**, fai clic su **Cambia posizione**. 
    
7. **Cambia indirizzo di emergenza per**immettere il nome della città nella casella e fare clic su **Cerca**.

8. Selezionare **ricerca dalla posizione** nell'elenco a discesa, immettere una parte del nome del percorso (ad esempio, immettere **la base**), quindi fare clic su **Cerca**. 
    
8. Selezionare il percorso di emergenza nell'elenco e quindi fare clic su **Salva**.
    
    Se si desidera aggiungere un nuovo percorso di emergenza che verrà visualizzato nell'elenco, vedere [aggiungere, modificare o rimuovere un percorso di emergenza per l'organizzazione](add-change-or-remove-an-emergency-location-for-your-organization.md).
    
## <a name="related-topics"></a>Argomenti correlati

[Assegnare una risposta all'emergenza percorsi tramite powershell](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[Aggiungere o rimuovere un indirizzo di emergenza per l'organizzazione](add-or-remove-an-emergency-address-for-your-organization.md)

[Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-or-remove-an-emergency-location-for-your-organization.md)

[Cos'è la convalida dell'indirizzo?](what-is-address-validation.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Cmdlet Set-CsOnlineVoiceUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

  
 
