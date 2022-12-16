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
description: Informazioni su come assegnare, modificare o rimuovere un numero di telefono aziendale per gli utenti di Teams in modo che aziende e clienti esterni possano chiamare.
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414684"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Assegnare, modificare o rimuovere il numero di telefono di un utente

Quando configuri Piani per chiamate, Operator Connect o Teams Phone Mobile, assegni numeri di telefono agli utenti. In Microsoft Teams, il numero di telefono assegnato viene elencato quando un utente fa clic su **Chiamate**.

Questo articolo si applica a Piani per chiamate, Operator Connect e Teams Phone Mobile. Per informazioni sull'assegnazione, la modifica o la rimozione di un numero di telefono da un utente in uno scenario di routing diretto, vedere [Abilitare gli utenti per routing diretto, voce e segreteria telefonica](./direct-routing-enable-users.md).

Prima di assegnare un numero a un piano per chiamate, a Operator Connect o a Teams Phone Mobile, è necessario ottenere numeri per gli utenti. Per altre informazioni, vedere [Ottenere numeri per gli utenti del piano per chiamate](getting-phone-numbers-for-your-users.md), [Configurare i numeri per gli utenti operator Connect](operator-connect-configure.md#set-up-phone-numbers) o [Configurare i numeri per gli utenti di Teams Phone Mobile](operator-connect-mobile-configure.md).

> [!NOTE]
> Un modo per verificare se a un utente è assegnata una licenza consiste nell'accedere all'interfaccia di amministrazione di Microsoft Teams > **Utenti**. Se viene assegnata una licenza, verrà indicata nella pagina.  È anche possibile usare il interfaccia di amministrazione di Microsoft 365.

> [!NOTE]
> Questa nota si applica ai clienti che hanno una distribuzione ibrida con un Active Directory locale. Se si desidera assegnare un numero di telefono per un piano di chiamata o un numero di telefono Operator Connect a un account utente o di risorsa, è necessario assicurarsi che qualsiasi numero di telefono archiviato nell'attributo msRTCSIP-Line nell'oggetto dell'account utente o della risorsa nel Active Directory locale sia stato rimosso e che la modifica sia stata sincronizzata con Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Assegnare un numero di telefono a un utente

Quando assegni un numero di telefono a un utente, assicurati che il numero di telefono e la posizione di utilizzo dell'utente siano dello stesso paese.

Per assegnare un numero usando l'interfaccia di amministrazione di Teams:

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Per assegnare numeri tramite PowerShell, usa il cmdlet [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) come segue:

Per i numeri del piano per chiamate:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Per i numeri Operator Connect:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Per i numeri di Teams Phone Mobile:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

Ad esempio:

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```

> [!NOTE]
> A causa della latenza tra Microsoft 365 e Teams, l'abilitazione degli utenti può richiedere fino a 24 ore. Se il numero di telefono non viene assegnato correttamente dopo 24 ore, vedi [Centro assistenza numeri di](https://pstnsd.powerappsportals.com/) telefono.

> [!NOTE]
> Quando si assegna un numero di telefono, il contrassegno EnterpriseVoiceEnabled viene impostato automaticamente su True.

## <a name="change-a-phone-number-for-a-user"></a>Modificare un numero di telefono per un utente

Per modificare un numero di telefono per un utente usando l'interfaccia di amministrazione di Teams:

1. Nel riquadro di spostamento sinistro fare clic su **Utenti**, individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in **Informazioni generali** prendere nota del numero di telefono assegnato all'utente.

2. Nel riquadro di spostamento sinistro fai clic su **Numeri di telefono** **vocale**\>.

3. Nella pagina **Numeri di telefono** selezionare il numero identificato nel passaggio 1 e quindi fare clic su **Modifica**.

4. Nel riquadro **Modifica** , in **Assegnato a**, fare clic sulla **X** per rimuovere l'utente.

5. Fare clic su **Salva**.

6. Nella pagina **Numeri di telefono** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.

7. Nel riquadro **Modifica** , in **Assegnato a**, cercare l'utente per nome visualizzato o nome utente e quindi fare clic su **Assegna**.

8. Per assegnare o modificare la posizione per gli interventi di emergenza associata, in Posizione per gli **interventi di emergenza** cerca e seleziona la posizione.

      > [!NOTE]
      > Se modifichi i numeri per gli utenti di Operator Connect o Teams Phone Mobile, potresti o meno assegnare o modificare la posizione per gli interventi di emergenza associata. Questa funzionalità dipenderà dall'operatore. Per altre informazioni, contatta il tuo operatore.

9. Fare clic su **Salva**.

Per un esempio di PowerShell, vedi [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Rimozione di un numero di telefono da un utente

Per rimuovere un numero di telefono tramite l'interfaccia di amministrazione di Teams:

1. Nel riquadro di spostamento sinistro fare clic su **Utenti**, individuare e fare doppio clic sull'utente desiderato, fare clic su **Account** e quindi in **Informazioni generali** prendere nota del numero di telefono assegnato all'utente.

2. Nel riquadro di spostamento sinistro fai clic su **Numeri di telefono** **vocale**\>.

3. Nella pagina **Numeri di telefono** selezionare il numero identificato nel passaggio 2 e quindi fare clic su **Modifica**.

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
