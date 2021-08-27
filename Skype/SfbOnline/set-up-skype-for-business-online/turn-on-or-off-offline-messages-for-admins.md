---
title: Attivare o disattivare i messaggi offline per gli amministratori
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 8bab15dacbf888b36e1f243d52f540fd22f75c25
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581970"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Attivare o disattivare i messaggi offline per gli amministratori

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

È possibile inviare Skype for Business messaggi di posta elettronica ai contatti anche se non sono connessi. Questa funzione consente di far sapere ai contatti che si sta tentando di mettersi in contatto con loro. Non è necessario attendere che gli utenti siano online prima di inviare loro un messaggio.

Per i messaggi offline, è importante sapere:

- I messaggi offline non verranno archiviati nella cassetta postale dell'utente.

- I messaggi offline verranno inviati alla cassetta postale dell'utente e l'utente riceverà una notifica quando accede a Skype for Business.

- Se lo stato del destinatario  del messaggio è impostato su Non disturbare o **Presenta,** riceverà un messaggio perso inviato dal client Skype for Business destinatario.

Per altre informazioni, vedere [Usare la messaggistica offline in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Per iniziare

> [!NOTE]
> Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente. Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.
1. Installare il [Teams di PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .

## <a name="turning-on-or-off-offline-im"></a>Attivazione o disattivazione della messaggistica offline

> [!NOTE]
> I messaggi  offline sono disponibili solo nella versione più recente del client Skype for Business A scelta e non sono disponibili quando viene usato un Skype for Business A Skype for Business A scelta meno recente o se è stato usato un file *.msi per installare il client Skype for Business.

Per abilitare o disabilitare l'invio di messaggi offline per gli utenti dell'organizzazione, impostare  _EnableIMAutoArchiving_ su `True` o `False` . Per impostazione predefinita, è impostato su `True` .

Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Per abilitare o disabilitare l'invio di messaggi offline per un utente, impostare  _EnableIMAutoArchiving_ su `True` o `False` . Per impostazione predefinita, è impostato su  `True`. È possibile usare un criterio esistente o crearne uno come nell'esempio seguente.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più sulle Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
