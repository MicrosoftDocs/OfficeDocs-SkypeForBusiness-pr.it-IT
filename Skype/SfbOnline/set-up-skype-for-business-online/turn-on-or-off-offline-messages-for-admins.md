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
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814605"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Attivare o disattivare i messaggi offline per gli amministratori

È possibile inviare messaggi automatici di Skype for Business ai propri contatti anche se non hanno eseguito l'accesso. Questa funzione consente di far sapere ai contatti che si sta tentando di raggiungerli. Non è necessario aspettare che un utente sia online prima di inviarle un messaggio.

Per i messaggi offline, è importante sapere:

- I messaggi offline non verranno archiviati nella cassetta postale dell'utente.

- I messaggi offline verranno inviati alla cassetta postale dell'utente e l'utente riceverà una notifica quando accede a Skype for Business.

- Se lo stato del destinatario  del messaggio è impostato su Non disturbare o Presentazione **in** corso, riceverà un messaggio perso inviato dal client Skype for Business del destinatario.

Per ulteriori informazioni, consulta [Utilizzare la messaggistica offline in Skype for Business.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>Per iniziare

## #

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**

1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.

2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.

3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0. Quando richiesto, riavviare il computer.

4. Dovrai inoltre installare il modulo Windows PowerShell per Teams che ti consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online.

Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

## #

 **Avviare una sessione di Windows PowerShell**

1. Fare clic sul pulsante **Start** > **Windows PowerShell**.

2. Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:

   > [!NOTE]
   > Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
   >
   > Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
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

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)


