---
title: Assegnare, modificare o rimuovere il numero di telefono di un utente
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Informazioni su come assegnare, modificare o rimuovere un numero di telefono dell'ufficio per gli utenti Teams in modo che le aziende e i clienti esterni possano chiamare.
ms.openlocfilehash: 443fdb5833e657c3f45c0f53d1d4ce6744bd67b0b83247e72084e3d29f6c1bc7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320029"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Assegnare, modificare o rimuovere un numero di telefono per un utente (Piani per chiamate)

Quando si configuraNo i Piani per chiamate, si assegnano numeri di telefono agli utenti. In Microsoft Teams, il numero di telefono assegnato viene elencato quando un utente fa clic su **Chiamate**. Per istruzioni sull'assegnazione, la modifica o la rimozione di un numero di telefono da un utente in uno scenario di routing diretto, vedere Abilitare gli utenti per routing diretto, voce e [segreteria telefonica.](./direct-routing-enable-users.md)

![Numero di telefono dell'utente visualizzato in Teams.](media/teams-phone-number.png)

Quando si configurano gli utenti in modo che possano effettuare e ricevere chiamate telefoniche, è necessario prima di tutto usare l'interfaccia di amministrazione di Microsoft Teams e assegnare un numero di telefono. Se necessario, è possibile modificare o rimuovere il numero di telefono.
  
Per informazioni su come ottenere piani per chiamate in Teams e quanto costano, vedere Teams [licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
> [!NOTE]
> Un modo per verificare se a un utente è assegnata una licenza è accedere all'Microsoft Teams di amministrazione > **utenti**. Se viene assegnata una licenza, verrà indicata nella pagina.  È anche possibile usare il interfaccia di amministrazione di Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Assegnare un numero di telefono a un utente
 
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**
    
1. Nel riquadro di spostamento sinistro fare clic su  >  **Numeri Telefono vocali**.
2. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.  
3. Nel riquadro **Modifica,** in **Assegnato a,** cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna.**
4. Per assegnare o modificare la posizione di emergenza associata, in **Posizione di** emergenza cercare e selezionare la posizione.
5. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare l'utente di posta elettronica **con informazioni sul numero di telefono.** Per impostazione predefinita, questa opzione è impostata su . 
6. Fare clic su **Salva**.

Per un esempio di PowerShell, [vedere Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Modificare un numero di telefono per un utente
 
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**
    
1. Nel riquadro di spostamento sinistro fare clic su Utenti **,** individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in Informazioni generali prendere nota del numero di telefono assegnato all'utente.
2. Nel riquadro di spostamento sinistro fare clic su  >  **Numeri Telefono vocali**.
3. Nella pagina **Telefono numeri** selezionare il numero identificato nel passaggio 1 e quindi fare clic su **Modifica**.  
4. Nel riquadro **Modifica,** in **Assegnato a,** fare clic sulla **X** per rimuovere l'utente.
5. Fare clic su **Salva**.
6. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.  
7. Nel riquadro **Modifica,** in **Assegnato a,** cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna.**
8. Per assegnare o modificare la posizione di emergenza associata, in **Posizione di** emergenza cercare e selezionare la posizione.
9. Fare clic su **Salva**.

Per un esempio di PowerShell, vedere [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="remove-a-phone-number-from-a-user"></a>Rimozione di un numero di telefono da un utente
 
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic su Utenti **,** individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in Informazioni generali prendere nota del numero di telefono assegnato all'utente.
2. Nel riquadro di spostamento sinistro fare clic su  >  **Numeri Telefono vocali**.
3. Nella pagina **Telefono numeri** di telefono selezionare il numero identificato nel passaggio 2 e quindi fare clic su **Modifica**.  
4. Nel riquadro **Modifica,** in **Assegnato a,** fare clic sulla **X** per rimuovere l'utente.
5. Fare clic su **Salva**.

Per un esempio di PowerShell, vedere [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="related-topics"></a>Argomenti correlati

[Cos'è la convalida dell'indirizzo?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Piani per chiamate per Microsoft 365](./calling-plans-for-office-365.md)