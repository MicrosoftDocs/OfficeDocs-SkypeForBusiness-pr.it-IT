---
title: Modificare le impostazioni per un ponte per conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'È possibile ottenere la procedura che è necessario modificare le impostazioni per un ponte per conferenze che consente di richiedere i chiamanti e raccogliere i nomi e i pin per gli organizzatori delle riunioni quando non sono in uso Skype per le applicazioni aziendali o Microsoft Teams. '
ms.openlocfilehash: c58c1b3031da9e9ebe8408568bed0fd4b8c9ae9b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modificare le impostazioni per un ponte per conferenze Audio

Quando impostano audioconferenze con accesso esterno in Office 365, si riceverà i numeri di telefono per gli utenti da quello che viene definito un ponte per conferenze audio. Un ponte per conferenze può contenere uno o più numeri di telefono. Questi numeri di telefono vengono utilizzati quando i chiamanti effettua la chiamata a una riunione. Il numero di telefono è incluso nella parte inferiore della Skype di invito alla riunione Business o Microsoft Teams.
  
Bridging risponde a una chiamata e viene richiesto il chiamante con istruzioni vocali utilizzando un automatico riunione attendant e quindi, a seconda delle impostazioni riprodurre le notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN. PIN assegnate agli organizzatori della riunione per consentire il per avviare una riunione quando si trovano non sono tramite un Skype per applicazioni aziendali o Microsoft Teams.

  > [!IMPORTANT]
  > Un PIN è solo necessario per l'organizzatore della riunione quando Skype per utente app aziendali o Teams Microsoft non ha già avviato la riunione. Se tutti gli utenti è accedono alla riunione, il PIN è obbligatorio per l'organizzatore della riunione avviare la riunione. 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngimagesteams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![30x30.png di logo del team](../images/teams-logo-30x30.png) Utilizzo del team di Microsoft e Skype for Business Admin Center

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Nella parte superiore della pagina **ponti di conferenza** , fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** selezionare: 
  - **Voce della riunione e chiudere le notifiche** Se si disattiva questa opzione, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.
    
    Quando si attiva **le notifiche di entrata e uscita delle riunioni**, è possibile selezionare queste opzioni:
    
  - **I nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il numero di telefono verrà riprodotto quando partecipano a.
    
  - **Toni** Quando gli utenti accedono a una riunione, un tono di audio da riprodurre quando partecipano a.
      
  - **Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.

4. Per impostare la lunghezza del PIN per le riunioni, selezionare il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** .

5. Per specificare se inviare posta elettronica per gli utenti, abilitare o disabilitare **l'invio automatico di messaggi di posta elettronica agli utenti se viene modificata la relativa configurazione di audioconferenze con accesso esterno**.
    Per ulteriori informazioni, vedere [messaggi di posta elettronica inviato automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md) .
 
6. Fare clic su **Applica**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png)  Utilizzo dell'interfaccia di amministrazione di Skype for Business

 **Configurare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**
    
1. In **Skype per interfaccia di amministrazione di Business**, nel riquadro sinistro passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
2. Nella pagina **impostazioni di bridge di Microsoft** , in **esperienza di partecipazione alle riunioni**, selezionare:
    
  - **Enable meeting entry and exit notifications to be turned on** This is selected by default. Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione non vengono informati quando un utente si unisce o abbandona la riunione.
    
    Quando si seleziona **Abilita voce relativa alla riunione e uscire da attivare le notifiche**, è possibile selezionare le opzioni nell'elenco **tipo di annunci di entrata/uscita** :
    
  - **I nomi o numeri di telefono** Quando gli utenti accedono a una riunione, il numero di telefono verrà riprodotto quando partecipano a.
    
  - **Toni** Quando gli utenti accedono a una riunione, un tono di audio da riprodurre quando partecipano a.
  
  - **Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.
    
3. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
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
    
4. Nella pagina **impostazioni di ponte Microsoft** selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se cambiano le informazioni di accesso esterno**e quindi fare clic su **Salva**.
    
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

[Configurare l’audioconferenza](set-up-audio-conferencing.md)
