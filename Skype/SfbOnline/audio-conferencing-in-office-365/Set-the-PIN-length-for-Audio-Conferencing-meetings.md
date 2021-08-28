---
title: Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Informazioni sui parametri per la lunghezza e i requisiti di un PIN, e su come impostare la lunghezza delle riunioni in Skype for Business.
ms.openlocfilehash: ecd0ef071f790e000aff00820fcd1c5a04403f23
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598290"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> Per informazioni su come impostare la lunghezza del PIN in Microsoft Teams, consulta [Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams) .

Quando imposti un'audioconferenza per Skype for Business, ottieni un ponte per audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono. Il numero di telefono impostato verrà incluso negli inviti alla riunione per l'app Skype for Business.
  
Il bridge di conferenza risponde a una chiamata di un utente che partecipa a una riunione utilizzando un telefono. Risponde al chiamante con le istruzioni vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre le notifiche e chiedere ai chiamanti di registrare il proprio nome. **Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni. Gli organizzatori della riunione utilizzano i PIN per avviare le riunioni quando non riescono a partecipare utilizzando l'app Skype for Business.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Impostazione della lunghezza del PIN
 
1. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Impostazioni bridge Microsoft **per audioconferenze.**  >  
    
2. In **Lunghezza** PIN di sicurezza selezionare il numero di cifre desiderato per il PIN e quindi fare clic su  >   **Salva.**
    
> [!NOTE]
> Un PIN è diverso da un ID conferenza. Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione. Vengono utilizzati per identificare la riunione. Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione. 

## <a name="want-to-know-more-about-pin-settings"></a>Vuoi saperne di più sulle impostazioni del PIN?

- I PIN possono essere da 4 a 12 cifre. il valore predefinito è 5. Solo i numeri vengono utilizati quando si creano dei PIN. Lettere e caratteri speciali non vengono utilizzati.
    
- L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione. L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.
    
- Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft. Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)
    
- Per impostare a 8 il numero di cifre del PIN:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto solo all'uso del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>Vedere anche

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
