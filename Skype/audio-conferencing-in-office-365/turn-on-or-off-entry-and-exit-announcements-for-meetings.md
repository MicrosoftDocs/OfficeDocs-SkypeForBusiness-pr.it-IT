---
title: Attivare o disattivare gli annunci di entrata e uscita per le riunioni
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Informazioni su come attivare la voce e uscire da attivare o disattivare gli annunci in Skype per riunioni Online Business con i Skype per interfaccia di amministrazione di Business. '
ms.openlocfilehash: 2298450d28ebb09acb87820b1f8a01cb9196708e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Attivare o disattivare gli annunci di entrata e uscita per le riunioni

Quando impostano audioconferenze con accesso esterno in Office 365, si otterrà un ponte per conferenze audio. Un ponte per conferenze può contenere uno o più numeri di telefono utilizzato per chiamare un Skype per riunione Business o Microsoft Teams persone. 
  
Bridge conferenza risponde a una chiamata di un utente che si collegano a una riunione utilizzando un telefono. Bridge conferenza risponde al chiamante di istruzioni vocali da un operatore automatico conferenza e quindi, a seconda delle impostazioni consentono di riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e impostato la protezione PIN. Un PIN viene assegnato a un Skype per Business o Microsoft Teams organizzatore della riunione e ha la possibilità di avviare una riunione, se non possono avviare una riunione utilizzando un Skype per applicazioni aziendali o Microsoft Teams. È possibile impostarla, tuttavia, in modo che non è richiesto un PIN per avviare una riunione.
  
## <a name="setting-meeting-join-options"></a>Impostazione di opzioni di partecipazione alla riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. In **esperienza di partecipazione alle riunioni**, selezionare o deselezionare **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**. Questa opzione è selezionata per impostazione predefinita. Se si deselezionare l'opzione, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.
    
5. In **tipo di annunci di entrata/uscita**, selezionare **i nomi o numeri di telefono** o **toni**.
    
6. Selezionare o deselezionare **Ask ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.
    
7. Dopo aver apportato le modifiche desiderate, fare clic su **Salva**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
-  Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Domande più comuni di servizi di conferenza audio](audio-conferencing-common-questions.md)

