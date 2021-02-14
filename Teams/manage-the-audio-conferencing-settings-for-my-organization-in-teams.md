---
title: Gestire le impostazioni delle audioconferenze
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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Vedi i passaggi di Microsoft Teams per assegnare una licenza per le conferenze telefoniche con accesso esterno e un ID conferenza a un utente e molte altre impostazioni per i servizi di conferenza telefonica con accesso esterno. '
ms.openlocfilehash: f2d056ffd2c3b40b8e39f6d4727859b45e675ebf
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031802"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gestire le impostazioni di audioconferenza per l'organizzazione in Microsoft Teams

Potrebbe essere più facile visualizzare tutte le impostazioni di audioconferenza per Microsoft Teams in un'unica posizione. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza per i servizi di audioconferenza

> [!NOTE]
> Non è possibile assegnare licenze con Teams. È necessario usare l'interfaccia di amministrazione di Microsoft 365. Vedi [Assegnare le licenze per i componenti aggiuntivi di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 
  
 **Per assegnare una licenza a un utente**
  
1. Accedere a Microsoft 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di **Microsoft 365** passare a Utenti attivi e quindi selezionare uno o più utenti nell'elenco di  >  utenti disponibili.
    
    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.  
  
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**. 
    
4. Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**. Per altre informazioni sulle licenze, vedere [l'articolo sulle licenze per i componenti aggiuntivi di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
    
   > [!NOTE]
   > Dopo l'assegnazione della licenza, Microsoft potrebbe non comparire inizialmente nell'elenco come provider di servizi di audioconferenza. In questo caso, disconnettersi dall'interfaccia di amministrazione o premere CTRL+F5 per aggiornare la finestra del browser. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Abilitare o disabilitare i messaggi di posta elettronica inviati agli utenti dei servizi di audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.** 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge abilitare o** disabilitare l'invio automatico dei messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso **remoto.**

4. Fare clic su **Salva**.

    
**Uso Windows PowerShell**
  
Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
  
## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

![Icona che mostra il logo di Teams ](media/teams-logo-30x30.png) **tramite l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. In **Audioconferenza** fare clic **su Reimposta ID conferenza.**  

3. Nella finestra **Reimposta ID conferenza?** fai clic su **Reimposta.** Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati. Questa impostazione è abilitata in modo predefinito

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente potrebbe non volerlo usare e impostare un numero specifico oppure potrebbe non ricordarsi più il suo ID conferenza. 

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. In **Audioconferenza** fare clic **su Reimposta PIN** e quindi su **Reimposta.** 
  
Gli utenti riceveranno un messaggio di posta elettronica con il PIN quando vengono abilitati per i servizi di audioconferenza o quando il PIN viene reimpostato. Se invece hai disabilitato l'invio automatico dei messaggi di posta elettronica, non verrà inviato un messaggio e-mail di reimpostazione del PIN e dovrai inviare manualmente il PIN all'utente. The PIN will only be shown once after it has been reset. Dopo la reimpostazione, il PIN non verrà più visualizzato nelle proprietà utente; verrà invece visualizzato *****.. 
  
Consulta [Reimpostare il PIN di audioconferenza.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni sulle audioconferenze a un utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**. 

    > [!NOTE]
    > In questo caso, il PIN di audioconferenza non viene inviato all'utente. 

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Impostare i numeri di telefono inclusi negli inviti

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. Accanto a **Audioconferenza,** fai clic **su Modifica.**
 
3. Nel riquadro **Audioconferenza** puoi  impostare il numero a numero verde e, se consentito, il numero **verde.**

4. Fare clic su **Salva**.
    
Consulta [Impostare i numeri di telefono inclusi per gli inviti.](set-the-phone-numbers-included-on-invites-in-teams.md)
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Scegliere le impostazioni del bridge per i servizi di audioconferenza

**Impostare l'esperienza della riunione quando i chiamanti a partecipare a una riunione**

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.** 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge abilitare o** disabilitare le notifiche di accesso e uscita da una **riunione.**

    Questa funzionalità è abilitata per impostazione predefinita. Se si disabilita questa opzione, gli utenti che hanno già partecipato alla riunione per impostazione predefinita non vengono avvisati quando qualcuno entra o esce dalla riunione.

4. In **Tipo di annuncio entrata/uscita** scegliere **Toni** o **Nomi o numeri di telefono.** 

    Se si sceglie **Nomi o** numeri di telefono, è anche possibile scegliere di abilitare o disabilitare l'opzione Chiedi ai chiamanti di registrare il proprio nome prima di partecipare **alla riunione.** 
    > [!NOTE]
    > Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti con accesso esterno. Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams.


5. Fare clic su **Salva**.

    
Vedi [Modificare le impostazioni per un bridge per audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Impostare la lunghezza del PIN per le riunioni**

1. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.** 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge** immettere il numero di cifre desiderato per il PIN nell'elenco di lunghezza **del PIN** e quindi fare clic su **Salva.**

    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.

    
Vedi [Modificare le impostazioni per un bridge per audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Abilitare o disabilitare l'invio di posta elettronica agli utenti audio**

1. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.** 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge abilitare o** disabilitare l'invio automatico di messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni delle **audioconferenze.**

4. Fare clic su **Salva**. 
 
    Puoi anche inviare messaggi di posta elettronica all'utente con le impostazioni per i servizi di audioconferenza e facendo clic su Invia informazioni sulla conferenza **tramite posta elettronica.**
    
    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare le lingue principali (predefinite) e secondarie (alternative) in un bridge per audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.** 

2. Seleziona un numero di telefono nell'elenco e fai clic su **Modifica.**

3. Scegliere le lingue desiderate in **Lingua predefinita** e Lingue **alternative (facoltativo).**

4. Fare clic su **Salva**.


See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Visualizzare i numeri di accesso esterno per i servizi di audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.** 

2. Seleziona un numero di telefono nell'elenco e fai clic su **Modifica.** Qui puoi:
    
   - Visualizzare i numeri di telefono da utilizzare per le audioconferenze. 
    
   - Visualizza la posizione e la lingua principale che verrà utilizzata dall'operatore automatico di Audioconferenza.

  
Visualizza [un elenco di numeri per i servizi di audioconferenza.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
  
    
## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


