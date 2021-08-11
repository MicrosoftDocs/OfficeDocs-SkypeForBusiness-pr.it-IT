---
title: Gestire le impostazioni di audioconferenza
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
description: 'Vedere Microsoft Teams procedura per assegnare una licenza e un ID conferenza telefonica con accesso esterno a un utente e molte altre impostazioni per i servizi di conferenza telefonica con accesso esterno. '
ms.openlocfilehash: 24d779a0740e5f0a8c0b305e4b441c01b628571f9ddf3292a1d92cd6c2d3ecb3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276412"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gestire le impostazioni di audioconferenza per l'organizzazione in Microsoft Teams

Potrebbe essere più facile visualizzare tutte le impostazioni di audioconferenza Microsoft Teams in un'unica posizione. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di audioconferenza

> [!NOTE]
> Non è possibile assegnare licenze usando Teams. È necessario usare il interfaccia di amministrazione di Microsoft 365. Vedere [Assegnare Microsoft Teams licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **Per assegnare una licenza per un utente**
  
1. Accedere a Microsoft 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro del **interfaccia di amministrazione di Microsoft 365**, passare a **Utenti** utenti attivi e quindi selezionare l'utente o gli utenti nell'elenco  >  degli utenti disponibili.
    
    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.  
  
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**. 
    
4. Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**. Per altre informazioni sulle licenze, [Microsoft Teams licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
   > [!NOTE]
   > Dopo aver assegnato la licenza, Microsoft potrebbe non comparire inizialmente nell'elenco come provider di servizi di audioconferenza. In questo caso, disconnettersi dall'interfaccia di amministrazione o premere CTRL+F5 per aggiornare la finestra del browser. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Abilitare o disabilitare i messaggi di posta elettronica inviati agli utenti di servizi di audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**. 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge** abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di accesso **remoto cambiano.**

4. Fare clic su **Salva**.

    
**Uso di Windows PowerShell**
  
Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)
  
## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

![Icona che mostra il logo Teams ](media/teams-logo-30x30.png) **con l'interfaccia Microsoft Teams di amministrazione**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. In **Audioconferenza** fare clic **su Reimposta ID conferenza.**  

3. Nella finestra **Reimposta ID conferenza?** fare clic su **Reimposta**. Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati. Questa impostazione è abilitata in modo predefinito

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente non vuole usarlo e si vuole impostarlo su un determinato numero oppure gli utenti non ricordano o non hanno perso l'ID conferenza. 

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. In **Audioconferenza** fare clic **su Reimposta PIN** e quindi su **Reimposta.** 
  
Gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per le audioconferenze o quando il PIN viene reimpostato. Se però l'invio automatico dei messaggi di posta elettronica è stato disabilitato, non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN e sarà necessario inviare manualmente il PIN all'utente. The PIN will only be shown once after it has been reset. Dopo essere stato visualizzato subito dopo la reimpostazione, il PIN non verrà più visualizzato nelle proprietà dell'utente. verrà invece visualizzato ******. 
  
Vedere [Reimpostare il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni sui servizi di audioconferenza a un utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**. 

    > [!NOTE]
    > In questo caso, il PIN dei servizi di audioconferenza non viene inviato all'utente. 

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Impostare i numeri di telefono inclusi negli inviti

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Accanto a **Audioconferenza** fare clic su **Modifica.**
 
3. Nel riquadro **Audioconferenza** è possibile impostare il **numero** a pedaggio e, se consentito, il **numero verde.**

4. Fare clic su **Salva**.
    
Vedere [Impostare i numeri di telefono inclusi per gli inviti.](set-the-phone-numbers-included-on-invites-in-teams.md)
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Scegliere le impostazioni del bridge di audioconferenza

**Impostare l'esperienza della riunione quando i chiamanti aderiscono a una riunione**

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**. 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge**, abilitare o disabilitare **Notifiche di entrata e di uscita per le riunioni**.

    Questa opzione è abilitata per impostazione predefinita. Se si disabilita questa opzione, gli utenti che hanno già partecipato alla riunione per impostazione predefinita non verranno avvisati quando un utente entra o esce dalla riunione.

4. In **Tipo annuncio di entrata/uscita** scegliere **Toni** o **Nomi o numeri di telefono.** 

    Se si sceglie **Nomi o** numeri di telefono, è anche possibile scegliere di abilitare o disabilitare Chiedi ai chiamanti di registrare il nome prima di partecipare **alla riunione.** 
    > [!NOTE]
    > Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti che hanno eseguito l'accesso tramite telefono. Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams.


5. Fare clic su **Salva**.

    
Vedere [Modificare le impostazioni per un bridge di audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Impostare la lunghezza del PIN per le riunioni**

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**. 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge** immettere il numero di cifre desiderato per il PIN nell'elenco Lunghezza **PIN** e quindi fare clic su **Salva.**

    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.

    
Vedere [Modificare le impostazioni per un bridge di audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Abilitare o disabilitare l'invio di posta elettronica agli utenti audio**

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**. 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge** abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni **di audioconferenza cambiano.**

4. Fare clic su **Salva**. 
 
    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza, accedere alle proprietà dei servizi di audioconferenza dell'utente e fare clic su Invia informazioni conferenza **tramite posta elettronica.**
    
    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare le lingue principale (predefinita) e secondaria (alternativa) in un bridge di audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**. 

2. Selezionare un numero di telefono nell'elenco e fare clic su **Modifica.**

3. Scegliere le lingue desiderate in **Lingua predefinita** e Lingue **alternative (facoltativo).**

4. Fare clic su **Salva**.


See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Visualizzare i numeri di accesso esterno per i servizi di audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**. 

2. Selezionare un numero di telefono nell'elenco e fare clic su **Modifica.** Qui puoi:
    
   - Visualizzare i numeri di telefono da usare per le audioconferenze. 
    
   - Visualizzare la posizione e la lingua principale che verranno usate dall'operatore automatico di audioconferenza.

  
Vedere [Visualizzare un elenco di numeri di audioconferenza.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)