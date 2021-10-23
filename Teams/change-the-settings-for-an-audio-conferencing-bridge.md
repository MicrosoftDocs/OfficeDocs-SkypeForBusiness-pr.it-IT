---
title: Modificare le impostazioni per un bridge per audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modificare le impostazioni del bridge di audioconferenza, incluse le notifiche di entrata e uscita, riprodurre nomi o numeri di telefono, toni e chiedere ai chiamanti di registrare il proprio nome.
ms.openlocfilehash: 0c64fa8c8717ae7fd401c4476896e6e52e833769
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537047"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modificare le impostazioni per un bridge per audioconferenza

Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si riceveranno numeri di telefono per gli utenti da quello che viene chiamato bridge di audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono. Questi numeri di telefono vengono usati quando i chiamanti a una riunione con accesso esterno. Il numero di telefono è incluso nella parte inferiore dell'invito Skype for Business o Microsoft Teams riunione.
  
Il bridge di conferenza risponde a una chiamata e chiede al chiamante di usare un operatore automatico della riunione e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN. I PIN vengono dati agli organizzatori della riunione per consentire loro di avviare una riunione quando non usano un'app Skype for Business o Microsoft Teams.

  > [!IMPORTANT]
  > Un PIN è necessario per l'organizzatore della riunione solo quando un Skype for Business o Microsoft Teams'app non ha ancora avviato la riunione. Se tutti gli utenti stanno per accedere alla riunione, il PIN è necessario per l'organizzatore della riunione per avviare la riunione. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

##  <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Ponti**  >  **conferenza riunioni**. 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge** selezionare: 
   - **Notifiche di entrata e uscita dalla riunione** Se si disattiva questa opzione, gli utenti che hanno già partecipato alla riunione non verranno avvisati quando un utente entra o esce dalla riunione.
    
     Quando si attivano le **notifiche di entrata e uscita dalla** riunione, è possibile selezionare queste opzioni:
    
   - **Nomi o numeri di telefono** Quando gli utenti aderiscono a una riunione, il loro numero di telefono verrà riprodotto al momento dell'accesso.
    
   - **Toni** Quando gli utenti aderiscono a una riunione, viene riprodotto un segnale audio quando aderiscono a una riunione.
      
   - **Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, ai chiamanti non verrà chiesto di registrare il nome prima di partecipare a una riunione.

4. Per impostare la lunghezza del PIN per le riunioni, selezionare il numero di cifre desiderato per il PIN **nell'elenco Lunghezza PIN.**

5. Per specificare se inviare messaggi di posta elettronica agli utenti, abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se la configurazione delle **audioconferenze cambia.**
    Per altre [informazioni,](emails-sent-to-users-when-their-settings-change-in-teams.md) vedere Messaggi di posta elettronica inviati automaticamente agli utenti quando le impostazioni di audioconferenza cambiano in Microsoft Teams o Messaggi inviati agli utenti quando le impostazioni cambiano [in Skype for Business Online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)
 
6. Fare clic su **Salva**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questo processo, è possibile usare il cmdlet [Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)
    
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare Audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurare le audioconferenze per Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)