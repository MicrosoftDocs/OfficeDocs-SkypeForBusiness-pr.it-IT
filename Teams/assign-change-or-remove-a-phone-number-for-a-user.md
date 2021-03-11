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
description: Informazioni su come assegnare, modificare o rimuovere il numero di telefono dell'ufficio per gli utenti di Teams in modo che le aziende e i clienti esterni possano accedere tramite telefono.
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589620"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Assegnare, modificare o rimuovere il numero di telefono di un utente (Piani per chiamate)

Quando si configurano i Piani per chiamate, i numeri di telefono vengono assegnati agli utenti. In Microsoft Teams, il numero di telefono assegnato viene elencato quando un utente fa clic su **Chiamate.** Per istruzioni sull'assegnazione, la modifica o la rimozione di un numero di telefono da un utente in uno scenario di instradamento diretto, vedere Abilitare gli utenti per il routing diretto, la voce e [la segreteria telefonica.](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)

![Numero di telefono dell'utente visualizzato in Teams.](media/teams-phone-number.png)

Quando si configurano gli utenti in modo che possano effettuare e ricevere telefonate, è necessario innanzitutto utilizzare l'interfaccia di amministrazione di Microsoft Teams e assegnare un numero di telefono. Se necessario, puoi modificare o rimuovere il numero di telefono.
  
Per informazioni su come ottenere i piani per chiamate in Teams e sul loro costo, consulta Licenze [per i componenti aggiuntivi di Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
> [!NOTE]
> Un modo per vedere se un utente ha una licenza assegnata è accedere all'interfaccia di amministrazione di Microsoft Teams > **utenti.** Se viene assegnata una licenza, verrà indicata nella pagina.  È anche possibile usare l'interfaccia di amministrazione di Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Assegnare un numero di telefono a un utente
 
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**
    
1. Nella barra di spostamento sinistra fare clic **su Numeri** di  >  **telefono voce.**
2. Nella pagina **Numeri di telefono** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica.**  
3. Nel riquadro **Modifica,** in **Assegnata a,** cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna.**
4. Per assegnare o modificare la posizione per gli interventi di emergenza associata, in Posizione **di** emergenza, cerca e seleziona la posizione.
5. A seconda che si voglia inviare un messaggio di posta elettronica con le informazioni sul numero di telefono all'utente, disattivare o attivare l'invio di un messaggio di posta elettronica con informazioni **sul numero di telefono.** Per impostazione predefinita, questa opzione è on. 
6. Fare clic su **Salva**.

Per un esempio di PowerShell, [vedi Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Modificare il numero di telefono di un utente
 
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**
    
1. Nel riquadro di spostamento sinistro fare clic su **Utenti,** individuare l'utente desiderato e fare doppio clic su dirlo, fare clic su **Account,** quindi in Informazioni generali prendere nota del numero di telefono assegnato all'utente.
2. Nella barra di spostamento sinistra fare clic **su Numeri** di  >  **telefono voce.**
3. Nella pagina **Numeri di** telefono selezionare il numero identificato al passaggio 1 e quindi fare clic su **Modifica.**  
4. Nel riquadro **Modifica,** in **Assegnata a,** fare clic sulla **X** per rimuovere l'utente.
5. Fare clic su **Salva**.
6. Nella pagina **Numeri di telefono** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica.**  
7. Nel riquadro **Modifica,** in **Assegnata a,** cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna.**
8. Per assegnare o modificare la posizione per gli interventi di emergenza associata, in Posizione **di** emergenza, cerca e seleziona la posizione.
9. Fare clic su **Salva**.

Per un esempio di PowerShell, vedi [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="remove-a-phone-number-from-a-user"></a>Rimozione di un numero di telefono da un utente
 
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic su **Utenti,** individuare l'utente desiderato e fare doppio clic su dirlo, fare clic su **Account,** quindi in Informazioni generali prendere nota del numero di telefono assegnato all'utente.
2. Nella barra di spostamento sinistra fare clic **su Numeri** di  >  **telefono voce.**
3. Nella pagina **Numeri di** telefono selezionare il numero identificato nel passaggio 2 e quindi fare clic su **Modifica.**  
4. Nel riquadro **Modifica,** in **Assegnata a,** fare clic sulla **X** per rimuovere l'utente.
5. Fare clic su **Salva**.

Per un esempio di PowerShell, vedi [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="related-topics"></a>Argomenti correlati

[Cos'è la convalida dell'indirizzo?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Etichetta della dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Piani per chiamate per Microsoft 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
