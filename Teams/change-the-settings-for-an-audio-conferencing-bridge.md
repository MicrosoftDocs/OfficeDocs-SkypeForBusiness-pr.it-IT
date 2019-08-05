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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Ecco i passaggi necessari per modificare le impostazioni per un Bridge di conferenza usato per richiedere ai chiamanti e raccogliere nomi e pin per gli organizzatori della riunione quando non usano le app Skype for business o Microsoft teams. '
ms.openlocfilehash: 97c1439325e5a9a00cacfa26e97078d2c2a91014
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "36183793"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modificare le impostazioni per un bridge per audioconferenza

Quando si configurano i servizi di audioconferenza in Office 365, si riceveranno i numeri di telefono per gli utenti provenienti da un Bridge per audioconferenza. Un Bridge per i servizi di conferenza può contenere uno o più numeri di telefono. Questi numeri di telefono vengono usati quando i chiamanti accedono a una riunione. Il numero di telefono è incluso nella parte inferiore dell'invito alla riunione di Skype for business o Microsoft teams.
  
Il Bridge per i servizi di conferenza risponde a una chiamata e chiede al chiamante di ricevere le istruzioni vocali usando un operatore automatico della riunione e quindi, a seconda delle impostazioni, può riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN. I PIN vengono assegnati agli organizzatori della riunione per consentire loro di avviare una riunione quando non usano un'app Skype for business o Microsoft teams.

  > [!IMPORTANT]
  > Un PIN è necessario solo per l'organizzatore della riunione quando un utente dell'app Skype for business o Microsoft teams non ha già avviato la riunione. Se tutti gli utenti effettuano la chiamata alla riunione, è necessario che l'organizzatore della riunione avvii la riunione. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) Uso dell'interfaccia di amministrazione di Microsoft Teams

1. Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > . 

2. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** selezionare: 
   - **Notifiche di entrata e di uscita della riunione** Se si disattiva questa opzione, gli utenti che hanno già partecipato alla riunione non verranno informati quando qualcuno entra o esce dalla riunione.
    
     Quando si attivano le **notifiche di entrata e di uscita della riunione**, è possibile selezionare queste opzioni:
    
   - **Nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il loro numero di telefono viene riprodotto quando partecipano.
    
   - **Toni** Quando gli utenti accedono a una riunione, viene riprodotto un tono audio quando partecipano.
      
   - **Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, ai chiamanti non verrà chiesto di registrare il nome prima di partecipare a una riunione.

4. Per impostare la lunghezza del PIN per le riunioni, selezionare il numero di cifre desiderato per il PIN nell'elenco **lunghezza PIN** .

5. Per specificare se inviare messaggi di posta elettronica agli utenti, abilitare o disabilitare automaticamente l'invio di posta elettronica agli **utenti in caso di modifica della configurazione dei**servizi di audioconferenza.
    Vedere i [messaggi di posta elettronica inviati automaticamente agli utenti quando le impostazioni dei servizi di audioconferenza cambiano in Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o i [messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) per altre informazioni.
 
6. Fai clic su **Salva**. 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![Icona che mostra il logo di Skype for business](media/sfb-logo-30x30.png)  Utilizzo dell'interfaccia di amministrazione di Skype for Business

 **Impostare l'esperienza della riunione quando i chiamanti partecipano a una riunione**
    
1. Nell'interfaccia **di amministrazione di Skype for business**, nella barra di spostamento sinistra **** > , vai a**impostazioni di Microsoft Bridge**per audioconferenza.
    
2. Nella pagina **Impostazioni Bridge Microsoft** , in **esperienza di partecipazione a una riunione**, selezionare:
    
   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. Se si deseleziona la casella di controllo, gli utenti che hanno già partecipato alla riunione non verranno informati quando qualcuno entra o esce dalla riunione.
    
   - Quando si seleziona **Abilita l'attivazione delle notifiche di entrata e uscita della riunione**, è possibile selezionare queste opzioni nell'elenco **tipo di annuncio di entrata/uscita** :
    
   - **Nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il loro numero di telefono viene riprodotto quando partecipano.
    
   - **Toni** Quando gli utenti accedono a una riunione, viene riprodotto un tono audio quando partecipano.
  
   - **Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, ai chiamanti non verrà chiesto di registrare il nome prima di partecipare a una riunione.
    
3. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
**Impostare la lunghezza del PIN per le riunioni**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedere all'interfaccia di **Amministrazione** > di Microsoft 365**Skype for business**.
    
3. Nell'interfaccia **di amministrazione di Skype for business**, nella barra di spostamento sinistra, **** > Vai a**impostazioni di Microsoft Bridge**per audioconferenza.
    
4. Nella pagina **Impostazioni Bridge Microsoft** , in **sicurezza**, immettere il numero di cifre desiderato per il PIN nell'elenco **lunghezza PIN** e quindi fare clic su **Salva**.
    
    > [!IMPORTANT]
    > Il codice PIN deve essere compreso tra 4 e 12 cifre. 
  
**Selezionare se inviare messaggi di posta elettronica agli utenti**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedere all'interfaccia di **Amministrazione** > di Microsoft 365**Skype for business**.
    
3. Nell'interfaccia **di amministrazione di Skype for business**, nella barra di spostamento sinistra, **** > Vai a**impostazioni di Microsoft Bridge**per audioconferenza.
    
4. Nella pagina **Impostazioni Bridge Microsoft** selezionare o deselezionare **Invia automaticamente i messaggi di posta elettronica agli utenti se le informazioni di accesso esterno vengono modificate**e quindi fare clic su **Salva**.
    
    Vedere i [messaggi di posta elettronica inviati automaticamente agli utenti quando le impostazioni dei servizi di audioconferenza cambiano in Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o i [messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) per altre informazioni.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questo processo, puoi usare il cmdlet [set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare servizi di audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurare servizi di audioconferenza per Skype for business online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
