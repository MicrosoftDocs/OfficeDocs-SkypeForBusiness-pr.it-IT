---
title: Consentire agli utenti di registrare il proprio nome quando partecipano a una riunione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 'Informazioni su come abilitare o disabilitare se gli utenti possono registrare i nomi quando partecipano a una riunione '
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>Consentire agli utenti di registrare il proprio nome quando partecipano a una riunione

Quando impostano audioconferenze con accesso esterno in Office 365, si riceverà i numeri di telefono e il processo definito un ponte per conferenze audio. Un ponte per conferenze può contenere uno o più numeri di telefono che possono essere un numero di telefono dedicate o condivise.
  
Bridge conferenza risponde a una chiamata di un utente che si collegano a una riunione utilizzando un telefono. Bridge conferenza risponde al chiamante di istruzioni vocali da un operatore automatico e quindi, a seconda delle loro impostazioni consentono di riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e impostato la protezione PIN per gli organizzatori delle riunioni. PIN assegnate agli organizzatori delle riunioni per consentire loro di avviare una riunione. Tuttavia, è possibile impostare tale in modo che non è richiesto un PIN per avviare una riunione.
  
## <a name="set-whether-callers-should-record-their-name"></a>Specificare se i chiamanti devono registrare il proprio nome

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. In **esperienza di partecipazione alle riunioni**, vedere la casella di controllo **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**.
    
  - **Selezionata** I chiamanti verranno richiesto di registrare il proprio nome prima di immettere la riunione. Questa opzione è selezionata per impostazione predefinita.
    
  - **Deselezionata** I chiamanti non verranno richiesto di registrare il proprio nome prima di immettere la riunione.
    
5. Dopo aver apportato le modifiche desiderate, fare clic su **Salva**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
-  Windows PowerShell è incentrato sulla gestione degli utenti e quali gli utenti possono eseguire. Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)

