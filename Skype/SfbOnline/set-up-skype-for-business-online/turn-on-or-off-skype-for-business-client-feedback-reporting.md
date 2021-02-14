---
title: Attivare o disattivare i report di feedback client di Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: È possibile consentire agli utenti di Skype for Business di utilizzare lo strumento di feedback app Skype for Business integrato per consentire agli utenti di segnalare problemi e inviare feedback direttamente a Microsoft sulla loro esperienza.
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814185"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Attivare o disattivare i report di feedback client di Skype for Business

È possibile consentire agli utenti di Skype for Business online di utilizzare lo strumento di feedback app Skype for Business integrato per consentire agli utenti di segnalare problemi e fornire feedback direttamente a Microsoft sulla loro esperienza. 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
Usando questo strumento, un utente può copiare i log dall'app nel proprio dispositivo per consentire a Microsoft di analizzare meglio e risolvere i problemi che potrebbe avere. 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Puoi anche utilizzare l'impostazione  _EnableOnlineFeedbackScreenshot_ in modo che gli utenti possano includere una schermata del proprio dispositivo nel loro feedback.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> I log raccolti dallo strumento di feedback dell'app verranno archiviati per un massimo di 90 giorni negli Stati Uniti durante l'analisi del problema. Per questo motivo, non abilitare questo strumento di feedback se questo viola i criteri di protezione dati dell'organizzazione. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0. Quando richiesto, riavviare il computer.
    
4. Dovrai inoltre installare il modulo Windows PowerShell per Teams che ti consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online. 
    
Per altre informazioni, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in un'unica Windows PowerShell singola.](https://technet.microsoft.com/library/dn568015.aspx)
    
- **Avviare una sessione di Windows PowerShell**
    
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
   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell oppure Configurare il computer per[Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>Attiva i report di feedback dell'applicazione client per tutti gli utenti dell'organizzazione

Per abilitare la creazione di report di feedback per gli utenti dell'organizzazione e consentire loro di inviare schermate del dispositivo, esegui:
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
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

  
 
