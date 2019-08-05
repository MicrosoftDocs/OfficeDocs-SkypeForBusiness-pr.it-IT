---
title: Gestire le impostazioni dei servizi di audioconferenza per l'organizzazione in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Per assegnare una licenza di conferenza telefonica con accesso esterno a un utente e molte altre impostazioni per i servizi di conferenza telefonica con accesso esterno, vedere la procedura Microsoft teams. '
ms.openlocfilehash: d5b3b616d8e3a42f5084d8de424c3fd557271b1d
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "36184936"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gestire le impostazioni dei servizi di audioconferenza per l'organizzazione in Microsoft Teams

Potrebbe essere più semplice visualizzare tutte le impostazioni di audioconferenza per Microsoft teams in un'unica posizione. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di audioconferenza

> [!NOTE]
> Non è possibile assegnare licenze con teams. È necessario usare l'interfaccia di amministrazione di Microsoft 365. Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](assign-teams-licenses.md). 
  
 **Per assegnare una licenza per un utente**
  
1. Accedere a Microsoft 365 con l'account di lavoro o dell'Istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di **amministrazione di Microsoft 365**, **** > accedere a utenti**attivi**degli utenti e quindi selezionare l'utente o gli utenti dall'elenco degli utenti disponibili.
    
    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.  
  
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**. 
    
4. Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**. Per altre informazioni sulle licenze, vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Dopo aver assegnato la licenza, Microsoft potrebbe non essere visualizzata inizialmente nell'elenco come provider di servizi di audioconferenza. In questo caso, disconnettersi dall'interfaccia di amministrazione oppure premere CTRL + F5 per aggiornare la finestra del browser. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Abilitare o disabilitare i messaggi di posta elettronica inviati agli utenti di servizi di audioconferenza

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > . 

2. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** abilitare o disabilitare **Invia automaticamente i messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso**esterno.

4. Fai clic su **Salva**.

    
**Uso di Windows PowerShell**
  
Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
  
## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

![Icona che mostra il logo](media/teams-logo-30x30.png) teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. In **audioconferenza**fare clic su **Reimposta ID conferenza**.  

3. Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**. Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati. Questa impostazione è abilitata in modo predefinito

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, potrebbero esserci momenti in cui un utente non vuole usarlo e si vuole impostarlo su un certo numero o se gli utenti non ricordano o hanno perso l'ID conferenza. 

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. In **audioconferenza**fare clic su **Reimposta PIN**e quindi su **Reimposta**. 
  
Gli utenti riceveranno un messaggio di posta elettronica con il PIN quando saranno abilitati per i servizi di audioconferenza o quando il PIN verrà reimpostato. Ma se si è disabilitato l'invio automatico di messaggi di posta elettronica, non verrà inviato un messaggio di reimpostazione del PIN e sarà necessario inviare manualmente il PIN all'utente. The PIN will only be shown once after it has been reset. Dopo averla visualizzata subito dopo la reimpostazione, il PIN non verrà più visualizzato sulle proprietà degli utenti; verrà invece visualizzato * * * * *. 
  
Vedere [reimpostare il pin per la conferenza audio](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni per i servizi di audioconferenza a un utente

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**. 

    > [!NOTE]
    > Quando si esegue questa operazione, il PIN per audioconferenza non viene inviato all'utente. 

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Impostare i numeri di telefono inclusi negli inviti

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Accanto a servizi di **audioconferenza**fare clic su **modifica**.
 
3. Nel riquadro **audioconferenza** è possibile impostare il numero verde e **** , se consentito, il **numero verde**.

4. Fai clic su **Salva**.
    
Vedere [impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Scegliere le impostazioni di Bridge per audioconferenza

**Impostare l'esperienza della riunione quando i chiamanti partecipano a una riunione**

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > . 

2. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** abilitare o disabilitare le **notifiche di entrata e uscita delle riunioni**.

    Questa opzione è abilitata per impostazione predefinita. Se si disattiva questa opzione, gli utenti che hanno già partecipato alla riunione per impostazione predefinita non verranno informati quando qualcuno entra o esce dalla riunione.

4. In **tipo di annuncio di entrata/uscita**scegliere **toni** o **nomi o numeri di telefono**. 

    Se si scelgono **i nomi o i numeri di telefono**, è anche possibile scegliere di abilitare o disabilitare i **chiamanti per registrare il nome prima di partecipare alla riunione**. 

5. Fai clic su **Salva**.

    
Vedere [modificare le impostazioni per un Bridge di audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Impostare la lunghezza del PIN per le riunioni**

1. Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > . 

2. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** immettere il numero di cifre desiderato per il PIN nell'elenco **lunghezza PIN** e quindi fare clic su **Salva**.

    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.

    
Vedere [modificare le impostazioni per un Bridge di audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti audio**

1. Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > . 

2. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** abilitare o disabilitare **l'invio automatico di messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di conferenza audio**.

4. Fai clic su **Salva**. 
 
    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza, passando alle proprietà dei servizi di audioconferenza dell'utente e facendo clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare le lingue primarie (predefinite) e secondarie (Alternate) in un Bridge di audioconferenza

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > . 

2. Selezionare un numero di telefono nell'elenco e fare clic su **modifica**.

3. Scegliere le lingue desiderate in **lingua predefinita** e **lingue alternative (facoltativo)**.

4. Fai clic su **Salva**.


See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Visualizzare i numeri di accesso esterno per i servizi di audioconferenza

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > . 

2. Selezionare un numero di telefono nell'elenco e fare clic su **modifica**. Qui puoi:
    
   - Visualizzare i numeri di telefono impostati da Office 365 per l'uso di servizi di audioconferenza. 
    
   - Visualizzare la posizione e la lingua principale che verrà usata dall'operatore automatico di audioconferenza.

  
Vedere [visualizzare un elenco di numeri di conferenza audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.
  
    
## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


