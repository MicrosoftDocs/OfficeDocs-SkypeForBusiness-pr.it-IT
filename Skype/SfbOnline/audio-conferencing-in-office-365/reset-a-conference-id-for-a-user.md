---
title: Reimpostare un ID conferenza per un utente in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni sulla procedura per reimpostare l'ID conferenza di una riunione di un utente in Skype for Business Online e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni. "
ms.openlocfilehash: b2f816cf423a25016a67176d6b1479f585ee14e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586134"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Reimpostare un ID conferenza per un utente in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Un ID conferenza dinamico è incluso nella parte inferiore degli inviti alle riunioni insieme ai numeri di telefono di accesso esterno che possono essere usati dai chiamanti per accedere a una riunione. Quando l'utente compone il numero di telefono, l'operatore automatico della riunione chiederà al chiamante di immettere questo ID conferenza in modo che possa partecipare alla riunione.
  
> [!NOTE]
> Se il provider di conferenza è Microsoft, gli ID conferenza degli utenti sono impostati su Solo dinamico. Non è possibile modificare questa impostazione. Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Skype for Business abilitati per Audioconferenza. 

## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostazione dell'ID conferenza per un utente
   
1. **Nell'Skype for Business di amministrazione fare** clic su Utenti di **audioconferenza,** selezionare un utente e quindi nel riquadro Azioni in ID conferenza fare clic su  >   **Reimposta.** 
    
2. Nella finestra **Reimposta ID conferenza?** fare clic su **Sì.** A conference ID will be automatically created and an email sent to the user with the new conference ID. Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma possono essere disattivati.
    
> [!NOTE]
> Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio di posta elettronica verrà inviato all'indirizzo di posta elettronica principale, in molti casi, Microsoft 365 o Office 365 cassetta postale. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio  di posta elettronica che include l'ID conferenza e i numeri di telefono di accesso esterno facendo clic su Invia informazioni conferenza tramite posta elettronica per l'utente nel riquadro Azioni. Il PIN non è incluso.
    
- Un ID conferenza conterrà 7 cifre e non è possibile modificarne la lunghezza nell'interfaccia di amministrazione di Skype for Business o usando Windows PowerShell.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- L'ID conferenza di un utente per le audioconferenze può essere visualizzato nella parte inferiore del riquadro Azioni in **Audioconferenza** quando si seleziona l'utente nella **pagina** Utenti.
    
- Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono usare lo Skype for Business riunione per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire lo strumento di aggiornamento Skype for Business riunione, vedere:
    
  - [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin.md)
