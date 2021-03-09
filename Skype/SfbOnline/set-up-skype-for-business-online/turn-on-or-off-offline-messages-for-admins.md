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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568756"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Attivare o disattivare i messaggi offline per gli amministratori

È possibile inviare messaggi automatici di Skype for Business ai propri contatti anche se non hanno effettuato l'accesso. Questa funzione consente di far sapere ai contatti che si sta tentando di mettersi in contatto con loro. Non è necessario attendere che gli utenti siano online prima di inviare loro un messaggio.

Per i messaggi offline, è importante sapere:

- I messaggi offline non verranno archiviati nella cassetta postale dell'utente.

- I messaggi offline verranno inviati alla cassetta postale dell'utente e l'utente riceverà una notifica quando accede a Skype for Business.

- Se lo stato del destinatario  del messaggio è impostato su Non disturbare o Presentazione **in** corso, riceverà un messaggio perso inviato dal client Skype for Business del destinatario.

Per ulteriori informazioni, consulta [Utilizzare la messaggistica offline in Skype for Business.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>Per iniziare

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams. Se si usa la versione pubblica più recente di Teams PowerShell, non è necessario installare Skype for Business Online Connector.
1. Installare il [modulo Teams di PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Aprire un Windows PowerShell comando ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell o configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell.

## <a name="turning-on-or-off-offline-im"></a>Attivazione o disattivazione della messaggistica offline

> [!NOTE]
> I messaggi  offline sono disponibili solo nell'ultima versione del client Skype for Business A scelta e non sono disponibili quando si usa una versione precedente di Skype for Business A scelta o se è stato usato un file *.msi per installare il client Skype for Business.

Per abilitare o disabilitare l'invio di messaggi offline per gli utenti dell'organizzazione, impostare  _EnableIMAutoArchiving_ su `True` o `False` . Per impostazione predefinita, è impostato su `True` .

Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Per abilitare o disabilitare l'invio di messaggi offline per un utente, impostare  _EnableIMAutoArchiving_ su `True` o `False` . Per impostazione predefinita, è impostato su  `True`. È possibile usare criteri esistenti o crearne uno come nell'esempio seguente.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
