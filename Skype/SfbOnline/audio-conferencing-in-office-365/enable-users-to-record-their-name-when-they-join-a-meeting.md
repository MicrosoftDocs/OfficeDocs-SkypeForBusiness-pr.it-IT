---
title: Consentire agli utenti di registrare il proprio nome quando aderiscono a una riunione in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Scopri come abilitare o disabilitare la registrazione dei nomi degli utenti quando un utente partecipa a una riunione in Skype for Business online.
ms.openlocfilehash: d6bb98c2d3c6b12479aea4fbdfdc717491c9893e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164155"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Consentire agli utenti di registrare il proprio nome quando aderiscono a una riunione in Skype for Business online

> [!Note]
> Se desideri consentire agli utenti di registrare i nomi su Teams, consulta [Consentire agli utenti di registrare il proprio nome quando partecipano a una riunione su Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si riceveranno numeri di telefono e un bridge per audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono, dedicati o condivisi.
  
Il bridge di conferenza risponde alla chiamata di un utente che sta eseguendo l'accesso a una riunione con il telefono. Il bridge risponde con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, richiedere ai chiamanti di registrare il proprio nome e configurare le opzioni di sicurezza del PIN per gli organizzatori della riunione. I PIN sono assegnati a un organizzatore della riunione per consentire l'avvio della stessa. Puoi comunque configurarla in modo tale che non sia richiesto il PIN per l'avvio.

## <a name="set-whether-callers-should-record-their-name"></a>Impostare se i chiamanti devono registrare il proprio nome
    
1. **Nell'interfaccia di amministrazione di Skype for Business,** nella barra di spostamento sinistra, vai alle impostazioni bridge Microsoft per le   >  **audioconferenze.**
    
2. In **Esperienza di partecipazione a una** riunione, vedi la casella di controllo Consenti attivazione notifiche di accesso e uscita da una **riunione.**
    
   - Ai chiamanti **selezionati** viene chiesto di registrare il proprio nome prima di accedere alla riunione. Questa opzione è selezionata per impostazione predefinita.
    
   - Ai chiamanti **deselezionati** non viene chiesto di registrare il proprio nome prima di accedere alla riunione.
    
3. Dopo aver apportato le modifiche, fai clic su **Salva**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](https://go.microsoft.com/fwlink/?LinkId=715757)
    
- Windows PowerShell riguarda la gestione degli utenti e le operazioni che sono autorizzati a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
