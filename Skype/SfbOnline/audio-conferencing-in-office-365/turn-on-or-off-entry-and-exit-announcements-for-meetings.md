---
title: Attivare o disattivare voce e chiudere gli annunci per le riunioni in Skype Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informazioni su come attivare la voce e uscire da attivare o disattivare gli annunci in Skype per riunioni Online Business con i Skype per interfaccia di amministrazione di Business. '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490486"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Attivare o disattivare voce e chiudere gli annunci per le riunioni in Skype Business online

> [!Note]
> Per informazioni sugli annunci di entrata e uscita nel Teams Microsoft, vedere [attivazione o disattivazione di annunci di entrata e uscita per le riunioni nel team di Microsoft](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Quando impostano audioconferenze con accesso esterno in Office 365, si otterrà un ponte per conferenze audio. Un ponte per conferenze può contenere uno o più numeri di telefono utilizzato per chiamare un Skype per le riunioni aziendali persone. 
  
Bridge conferenza risponde a una chiamata di un utente che si collegano a una riunione utilizzando un telefono. Bridge conferenza risponde al chiamante di istruzioni vocali da un operatore automatico conferenza e quindi, a seconda delle impostazioni consentono di riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e impostato la protezione PIN. Un PIN viene assegnato a un Skype per l'organizzatore della riunione di Business e ha la possibilità di avviare una riunione, se non possono avviare una riunione utilizzando il Skype per applicazioni aziendali. È possibile impostarla, tuttavia, in modo che non è richiesto un PIN per avviare una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Impostazione di opzioni di partecipazione alla riunione
    
1. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
2. In **esperienza di partecipazione alle riunioni**, selezionare o deselezionare **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**. Questa opzione è selezionata per impostazione predefinita. Se si deselezionare l'opzione, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.
    
3. In **tipo di annunci di entrata/uscita**, selezionare **i nomi o numeri di telefono** o **toni**.
    
4. Selezionare o deselezionare **Ask ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.
    
5. Dopo aver apportato le modifiche, fai clic su **Salva**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) .
    
-  Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
