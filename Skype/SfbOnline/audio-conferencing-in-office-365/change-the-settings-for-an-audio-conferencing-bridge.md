---
title: Modificare le impostazioni per un ponte per conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "È possibile ottenere la procedura che è necessario modificare le impostazioni per un bridge di componente aggiuntivo per conferenze Microsoft che consente di richiedere i chiamanti e raccogliere i nomi e i pin per gli organizzatori delle riunioni quando non sono in uso Skype per i client aziendali. "
ms.openlocfilehash: f37af15b4ab66eb5765cccbdba63b3bb6bb14597
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modificare le impostazioni per un ponte per conferenze Audio

Quando impostano audioconferenze con accesso esterno in Office 365, si riceverà i numeri di telefono per gli utenti da quello che viene definito un ponte per conferenze audio. Un ponte per conferenze può contenere uno o più numeri di telefono. Questi numeri di telefono vengono utilizzati quando i chiamanti effettua la chiamata a una riunione. Il numero di telefono è incluso nella parte inferiore della Skype di invito alla riunione Business o Microsoft Teams.
  
Bridging risponde a una chiamata e viene richiesto il chiamante con istruzioni vocali utilizzando un automatico riunione attendant e quindi, a seconda delle impostazioni riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN. PIN assegnate agli organizzatori della riunione per consentire il per avviare una riunione quando si trovano non sono tramite un Skype per applicazioni aziendali o Microsoft Teams.

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modificare le impostazioni per un ponte per conferenze audio

 **Configurare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. In **Skype per interfaccia di amministrazione di Business**, nel riquadro sinistro passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. Nella pagina **impostazioni di bridge di Microsoft** , in **esperienza di partecipazione alle riunioni**, selezionare:
    
  - **Enable meeting entry and exit notifications to be turned on** This is selected by default. Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.
    
    Quando si seleziona **Abilita voce relativa alla riunione e uscire da attivare le notifiche**, è possibile selezionare le opzioni nell'elenco **tipo di annunci di entrata/uscita** :
    
  - **I nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il numero di telefono verrà riprodotto quando partecipano a.
    
  - **Toni** Quando gli utenti accedono a una riunione, un tono di audio da riprodurre quando partecipano a.
    
    > [!NOTE]
    > Utilizzo **Tone** come tipo di annuncio è attualmente disponibile per tutti i clienti come una caratteristica di anteprima.
  
  - **Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.
    
5. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
**Impostare la lunghezza del PIN per le riunioni**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
4. Nella sezione **protezione**della pagina **impostazioni di ponte Microsoft** immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.
    
    > [!IMPORTANT]
    > Il codice PIN deve essere compreso tra 4 e 12 cifre. 
  
**Selezionare questa opzione per inviare la posta elettronica per gli utenti**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
4. Nella pagina **impostazioni di ponte Microsoft** selezionare o deselezionare **automaticamente invia messaggi di posta elettronica agli utenti se viene modificata la relativa configurazione di conferenze audio**e quindi fare clic su **Salva**.
    
    Per ulteriori informazioni, vedere [messaggi di posta elettronica inviato automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare il processo, è possibile utilizzare il cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Servizi di conferenza telefonica con accesso esterno in Office 365](set-up-audio-conferencing.md)

