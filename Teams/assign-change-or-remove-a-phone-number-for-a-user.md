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
description: Scopri come assegnare, modificare o rimuovere un numero di telefono dell'ufficio per il tuo Teams gli utenti in modo che aziende e clienti esterni possano chiamare.
ms.openlocfilehash: dc616425b4dce35a2a40179e0ee4a56d31bae12b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676488"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Assegnare, modificare o rimuovere il numero di telefono di un utente

Quando configuri Piani per chiamate o Connessione con operatore, assegni numeri di telefono agli utenti. In Microsoft Teams, il numero di telefono assegnato viene elencato quando un utente fa clic su **Chiamate**.

Questo articolo si applica ai Piani per chiamate e Connessione con operatore. Per informazioni sull'assegnazione, la modifica o la rimozione di un numero di telefono da un utente in uno scenario di routing diretto, vedere [Abilitare gli utenti per routing diretto, voce e segreteria telefonica](./direct-routing-enable-users.md).

Prima di assegnare un numero a un Piano per chiamate o a un utente Connessione con operatore, è necessario ottenere numeri per gli utenti. Per altre informazioni, vedere [Ottenere numeri per gli utenti del Piano per chiamate](getting-phone-numbers-for-your-users.md) o [Configurare numeri per Connessione con operatore utenti](operator-connect-configure.md#set-up-phone-numbers).

> [!NOTE]
> Un modo per verificare se a un utente è assegnata una licenza consiste nell'accedere all'interfaccia di amministrazione Microsoft Teams > **Utenti**. Se viene assegnata una licenza, verrà indicata nella pagina.  È anche possibile usare il interfaccia di amministrazione di Microsoft 365.

> [!NOTE]
> Questa nota si applica ai clienti che hanno una distribuzione ibrida con un Active Directory locale. Se si desidera assegnare un piano per chiamate o Connessione con operatore numero di telefono a un account utente o di risorsa, è necessario assicurarsi che qualsiasi numero di telefono archiviato nell'attributo msRTCSIP-Line nell'oggetto utente o account di risorsa nel Active Directory locale sia stato rimosso e che la modifica sia stata sincronizzata con Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Assegnare un numero di telefono a un utente

Quando assegni un numero di telefono a un utente, assicurati che il numero di telefono e la posizione di utilizzo dell'utente siano dello stesso paese.

Per assegnare un numero tramite l'interfaccia di amministrazione di Teams:

1. Nel riquadro di spostamento sinistro fare clic su **Numeri** >  **voce Telefono**.

2. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.

3. Nel riquadro **Modifica** , in **Assegnato a**, cercare l'utente per nome visualizzato o nome utente e quindi fare clic su **Assegna**.

4. Per assegnare o modificare la posizione per gli interventi di emergenza associata, in Posizione per gli **interventi di emergenza** cerca e seleziona la posizione.

   > [!NOTE]
   > Se stai assegnando numeri a Connessione con operatore utenti, potresti o non essere in grado di assegnare o modificare la posizione per gli interventi di emergenza associata. Questa funzionalità dipenderà dall'operatore. Per altre informazioni, contatta il tuo operatore.

5. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare **L'utente di posta elettronica con informazioni sul numero di telefono**. Per impostazione predefinita, questa opzione è attivata.
6. Fare clic su **Salva**.

Per assegnare numeri tramite PowerShell, usa il cmdlet [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) come segue:

Per i numeri del piano per chiamate:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Per i numeri di Connessione con operatore:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Ad esempio:

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
```

> [!NOTE]
> A causa della latenza tra Microsoft 365 e Teams, l'abilitazione degli utenti può richiedere fino a 24 ore. Se dopo 24 ore il numero di telefono non viene assegnato correttamente, vedi [Telefono Centro assistenza numeri](https://pstnsd.powerappsportals.com/).

## <a name="change-a-phone-number-for-a-user"></a>Modificare un numero di telefono per un utente

Per modificare un numero di telefono per un utente tramite l'interfaccia di amministrazione di Teams:

1. Nel riquadro di spostamento sinistro fare clic su **Utenti**, individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in **Informazioni generali** prendere nota del numero di telefono assegnato all'utente.

2. Nel riquadro di spostamento sinistro fare clic su Numeri **di Telefono** **vocali**\>.

3. Nella pagina **Telefono numeri** selezionare il numero identificato nel passaggio 1 e quindi fare clic su **Modifica**.

4. Nel riquadro **Modifica** , in **Assegnato a**, fare clic sulla **X** per rimuovere l'utente.

5. Fare clic su **Salva**.

6. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.

7. Nel riquadro **Modifica** , in **Assegnato a**, cercare l'utente per nome visualizzato o nome utente e quindi fare clic su **Assegna**.

8. Per assegnare o modificare la posizione per gli interventi di emergenza associata, in Posizione per gli **interventi di emergenza** cerca e seleziona la posizione.

      > [!NOTE]
      > Se modifichi i numeri per Connessione con operatore utenti, puoi assegnare o modificare la posizione per gli interventi di emergenza associata. Questa funzionalità dipenderà dall'operatore. Per altre informazioni, contatta il tuo operatore.

9. Fare clic su **Salva**.

Per un esempio di PowerShell, vedi [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Rimozione di un numero di telefono da un utente

Per rimuovere un numero di telefono tramite l'interfaccia di amministrazione di Teams:

1. Nel riquadro di spostamento sinistro fare clic su **Utenti**, individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in **Informazioni generali** prendere nota del numero di telefono assegnato all'utente.

2. Nel riquadro di spostamento sinistro fare clic su Numeri **di Telefono** **vocali**\>.

3. Nella pagina **Telefono numeri** selezionare il numero identificato nel passaggio 2 e quindi fare clic su **Modifica**.

4. Nel riquadro **Modifica** , in **Assegnato a**, fare clic sulla **X** per rimuovere l'utente.

5. Fare clic su **Salva**.

Per un esempio di PowerShell, vedi [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>Argomenti correlati

[Cos'è la convalida dell'indirizzo?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
