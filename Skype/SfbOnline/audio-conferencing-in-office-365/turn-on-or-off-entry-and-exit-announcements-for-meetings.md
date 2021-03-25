---
title: Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: "Informazioni su come attivare gli annunci di entrata e uscita per le riunioni in Skype for Business Online tramite l'interfaccia di amministrazione di Skype for Business. "
ms.openlocfilehash: 5165facfdc4de040b24b199cd99a1bb42565a76b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111932"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Skype for Business online

> [!Note]
> Per informazioni sugli annunci di entrata e uscita in Microsof Teamst, consulta [Attivazione o disattivazione degli annunci di entrata e uscita per le riunioni in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Quando viene impostata Audioconferenza in Microsoft 365 o Office 365, si ottieni un bridge di audioconferenza. Un ponte per audioconferenze può contenere uno o più numeri di telefono che le persone possono utilizzare per partecipare a una riunione su Skype for Business. 
  
Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono. Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza. Viene assegnato un PIN a un organizzatore della riunione su Skype for Business, il quale permette di avviare la riunione se i partecipanti non sono in grado di farlo tramite l'app di Skype for Business. È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Impostazione delle opzioni di partecipazione alla riunione
    
1. **Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro di spostamento sinistro, vai a Impostazioni bridge Microsoft per   >  **audioconferenze.**
    
2. Su **Esperienza di partecipazione alle riunioni**, seleziona o deseleziona **Abilita l'attivazione di annunci di entrata e uscita per la riunione**. Questa opzione è selezionata per impostazione predefinita. Se si deseleziona l’opzione, gli utenti che partecipano alla riunione non verranno avvisati quando un utente entra o esce dalla riunione.
    
3. Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.
    
4. Seleziona o deseleziona **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.
    
5. Dopo aver apportato le modifiche, fai clic su **Salva**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)
    
- Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto solo all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sulle audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions)