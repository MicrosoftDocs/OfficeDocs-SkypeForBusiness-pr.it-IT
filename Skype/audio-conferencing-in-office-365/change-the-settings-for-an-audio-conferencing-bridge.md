---
title: Modificare le impostazioni per un ponte per conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "È possibile ottenere la procedura che è necessario modificare le impostazioni per un bridge di componente aggiuntivo per conferenze Microsoft che consente di richiedere i chiamanti e raccogliere i nomi e i pin per gli organizzatori delle riunioni quando non sono in uso Skype per i client aziendali. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
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
    
  - **Abilitare questa impostazione voce relativa alla riunione e chiudere le notifiche per essere attivata** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.
    
    Quando si seleziona **Abilita voce relativa alla riunione e uscire da attivare le notifiche**, è possibile selezionare le opzioni nell'elenco **tipo di annunci di entrata/uscita** :
    
  - **I nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il numero di telefono verrà riprodotto quando partecipano a.
    
  - **Toni** Quando gli utenti accedono a una riunione, un tono di audio da riprodurre quando partecipano a.
    
    > [!NOTE]
    > Utilizzo **Tone** come tipo di annuncio è attualmente disponibile per tutti i clienti come una caratteristica di anteprima.
  
  - **Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.
    
5. Dopo aver apportato le modifiche desiderate, fare clic su **Salva**.
    
**Impostare la lunghezza del PIN per le riunioni**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. Nella sezione **protezione**della pagina **impostazioni di ponte Microsoft** immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.
    
    > [!IMPORTANT]
    > Il codice PIN deve essere compreso tra 4 e 12 cifre. 
  
**Selezionare questa opzione per inviare la posta elettronica per gli utenti**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. Nella pagina **impostazioni di ponte Microsoft** selezionare o deselezionare **automaticamente invia messaggi di posta elettronica agli utenti se viene modificata la relativa configurazione di conferenze audio**e quindi fare clic su **Salva**.
    
    Per ulteriori informazioni, vedere [messaggi di posta elettronica inviato automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare il processo, è possibile utilizzare il cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Windows PowerShell è incentrato sulla gestione degli utenti e quali utenti sono consentiti o non è autorizzati a eseguire. Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
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

