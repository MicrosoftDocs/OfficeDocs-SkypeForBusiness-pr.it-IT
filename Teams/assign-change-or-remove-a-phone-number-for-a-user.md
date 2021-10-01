---
title: Assegnare, modificare o rimuovere il numero di telefono di un utente
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Informazioni su come assegnare, modificare o rimuovere un numero di telefono dell'ufficio per gli utenti Teams in modo che le aziende e i clienti esterni possano chiamare.
ms.openlocfilehash: a6e2c8075134817b61d99366633f29140599b447
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046182"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Assegnare, modificare o rimuovere il numero di telefono di un utente

Quando si configuraNo piani per chiamate **o Connessione con operatore**, si assegnano numeri di telefono agli utenti. In Microsoft Teams, il numero di telefono assegnato viene elencato quando un utente fa clic su **Chiamate**. 

**Questo articolo si applica a Piani per chiamate e Connessione con operatore.** Per informazioni sull'assegnazione, la modifica o la rimozione di un numero di telefono da un utente in uno scenario di routing diretto, vedere Abilitare gli utenti per il routing diretto, la voce e la [segreteria telefonica.](./direct-routing-enable-users.md)

**Prima di assegnare un numero per un piano per chiamate o un Connessione con operatore utente, è necessario ottenere i numeri per gli utenti. Per altre informazioni, vedere [Ottenere numeri per gli utenti del](getting-phone-numbers-for-your-users.md) piano per chiamate o Configurare i numeri per Connessione con operatore [utenti](operator-connect-configure.md#set-up-phone-numbers).**

  
> [!NOTE]
> Un modo per vedere se a un utente è assegnata una licenza è accedere all'Microsoft Teams di amministrazione > **utenti**. Se viene assegnata una licenza, verrà indicata nella pagina.  È anche possibile usare il interfaccia di amministrazione di Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Assegnare un numero di telefono a un utente

Per assegnare un numero usando l'interfaccia Teams di amministrazione:
    
1. Nel riquadro di spostamento sinistro fare clic **su Numeri**  >  **Telefono vocali**.

2. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.  

3. Nel riquadro **Modifica,** in **Assegnato a,** cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna.**

4. Per assegnare o modificare la posizione di emergenza associata, in **Posizione di** emergenza cercare e selezionare la posizione.

   > [!NOTE]
   > **Se si assegnano numeri a Connessione con operatore utenti, potrebbe essere possibile assegnare o modificare la posizione di emergenza associata. Questa funzionalità dipende dall'operatore. Per altre informazioni, contattare l'operatore.**

5. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare l'utente di posta elettronica **con informazioni sul numero di telefono.** Per impostazione predefinita, questa opzione è impostata su . 

6. Fare clic su **Salva**.

Per assegnare numeri tramite PowerShell, usare il cmdlet [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser) nel modo seguente:


''PowerShell Set-CsOnlineVoiceUser -Identity <user>   -TelephoneNumber <phone number> 
```

For example:

```PowerShell
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

> [!NOTE]
> A causa della latenza tra Microsoft 365 e Teams, possono essere necessario fino a 24 ore prima che gli utenti siano abilitati. Se il numero di telefono non viene assegnato correttamente dopo 24 ore, vedere Telefono [Numero di servizio](https://pstnsd.powerappsportals.com/). 

  
## <a name="change-a-phone-number-for-a-user"></a>Modificare un numero di telefono per un utente

Per modificare un numero di telefono per un utente usando l'interfaccia Teams di amministrazione:
    
1. Nel riquadro di spostamento sinistro fare clic su Utenti **,** individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in Informazioni generali prendere nota del numero di telefono assegnato all'utente.

2. Nel riquadro di spostamento sinistro fare clic **su Numeri**  >  **Telefono vocali**.

3. Nella pagina **Telefono numeri** selezionare il numero identificato nel passaggio 1 e quindi fare clic su **Modifica**.  

4. Nel riquadro **Modifica,** in **Assegnato a,** fare clic sulla **X** per rimuovere l'utente.

5. Fare clic su **Salva**.

6. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.  

7. Nel riquadro **Modifica,** in **Assegnato a,** cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna.**

8. Per assegnare o modificare la posizione di emergenza associata, in **Posizione di** emergenza cercare e selezionare la posizione.

      > [!NOTE]
      > **Se si modificano i numeri Connessione con operatore utenti, potrebbe essere possibile assegnare o modificare la posizione di emergenza associata. Questa funzionalità dipende dall'operatore. Per altre informazioni, contattare l'operatore.**

9. Fare clic su **Salva**.

Per un esempio di PowerShell, [vedere Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

## <a name="remove-a-phone-number-from-a-user"></a>Rimozione di un numero di telefono da un utente

Per rimuovere un numero di telefono usando l'Teams di amministrazione:

1. Nel riquadro di spostamento sinistro fare clic su Utenti **,** individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in Informazioni generali prendere nota del numero di telefono assegnato all'utente.

2. Nel riquadro di spostamento sinistro fare clic **su Numeri**  >  **Telefono vocali**.

3. Nella pagina **Telefono numeri** selezionare il numero identificato nel passaggio 2 e quindi fare clic su **Modifica**.  

4. Nel riquadro **Modifica,** in **Assegnato a,** fare clic sulla **X** per rimuovere l'utente.

5. Fare clic su **Salva**.

Per un esempio di PowerShell, [vedere Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

## <a name="related-topics"></a>Argomenti correlati

[Cos'è la convalida dell'indirizzo?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

