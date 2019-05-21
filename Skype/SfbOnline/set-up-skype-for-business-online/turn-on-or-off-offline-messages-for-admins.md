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
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 9f7786e636ba49d6327486a11683e26799c01cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284935"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Attivare o disattivare i messaggi offline per gli amministratori

È possibile inviare messaggi istantanei di Skype for business ai contatti anche se non sono stati registrati. Questa funzione consente di far sapere ai contatti che si sta tentando di mettersi in contatto con loro. Non è necessario attendere che gli utenti siano online prima di inviare loro un messaggio.

Per i messaggi offline, è importante sapere:

- I messaggi offline non verranno archiviati nella cassetta postale dell'utente.

- I messaggi offline verranno inviati alla cassetta postale dell'utente e l'utente riceverà una notifica quando accederà a Skype for business.

- Se lo stato del destinatario del messaggio è impostato su **non disturbare** o **presentare**, riceverà un messaggio perso inviato dal client Skype for business del destinatario.

Per altre informazioni, vedere [usare la messaggistica offline in Skype for business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Per iniziare

## #

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**

1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.

2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.

3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.

4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.

Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).

## #

 **Avviare una sessione di Windows PowerShell**

1. Fare clic sul pulsante **Start** > **Windows PowerShell**.

2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:

    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Attivazione o disattivazione della messaggistica offline

> [!NOTE]
> I messaggi offline sono disponibili **solo** nella versione più recente del client Skype for business a portata di clic e non sono disponibili quando viene usato un file *. msi o un vecchio click-to-Run per installare il client Skype for business.

Per abilitare o disabilitare i messaggi offline, inviare messaggi offline per gli utenti dell'organizzazione __ , impostare `True` EnableIMAutoArchiving `False`su or. Per impostazione predefinita, questa opzione è `True`impostata su.

Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Per abilitare o disabilitare i messaggi offline, inviare messaggi offline per un utente __ , impostare `True` EnableIMAutoArchiving `False`su or. Per impostazione predefinita, è impostato su  `True`. Puoi usare un criterio esistente o crearne uno simile all'esempio seguente.


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:

  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usare Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)


