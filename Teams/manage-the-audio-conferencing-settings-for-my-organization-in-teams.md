---
title: Gestire le impostazioni dei servizi di audioconferenza
ms.author: heidip
author: MicrosoftHeidi
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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Consulta i passaggi di Microsoft Teams per assegnare una licenza per i servizi di conferenza telefonica con accesso esterno e un ID conferenza a un utente e a molte altre impostazioni di conferenza telefonica con accesso esterno.
ms.openlocfilehash: 4bfb813b6e7b472ad7a9ab58e6403b92f60fd039
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271221"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gestire le impostazioni di audioconferenza per l'organizzazione in Microsoft Teams

Potrebbe essere più facile visualizzare tutte le impostazioni dei servizi di audioconferenza per Microsoft Teams in un'unica posizione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza per i servizi di audioconferenza

> [!NOTE]
> Non è possibile assegnare licenze con Teams. È necessario usare il interfaccia di amministrazione di Microsoft 365. Vedere [Assegnare licenze per i componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="to-assign-a-license-for-a-user"></a>To assign a license for a user

1. Accedere a Microsoft 365 con l'account aziendale o dell'istituto di istruzione.

2. Nel riquadro di spostamento sinistro del **interfaccia di amministrazione di Microsoft 365** passare a **Utenti** > **attivi** e quindi selezionare uno o più utenti dall'elenco degli utenti disponibili.

    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.  
  
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.

4. Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**. Per altre informazioni sulle licenze, vedere Licenze per i [componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

   > [!NOTE]
   > Dopo aver assegnato la licenza, Microsoft potrebbe non comparire inizialmente nell'elenco come provider di servizi di audioconferenza. In questo caso, disconnettersi dall'interfaccia di amministrazione o premere CTRL+F5 per aggiornare la finestra del browser.
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Abilitare o disabilitare i messaggi di posta elettronica inviati agli utenti dei servizi di audioconferenza

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>Abilitare o disabilitare l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Conference Bridge** fare clic su **Impostazioni bridge**.

3. Nel riquadro **Impostazioni bridge** abilitare o disabilitare **l'opzione Invia automaticamente messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso**.

4. Fare clic su **Salva**.

### <a name="enable-or-disable-using-windows-powershell"></a>Abilitare o disabilitare l'uso di Windows PowerShell

Per altre informazioni, vedere le [informazioni di riferimento su PowerShell di Microsoft Teams](/powershell/module/teams/?view=teams-ps) .
  
## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>Reimpostare l'ID conferenza della riunione usando l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro fare clic su **Utenti** e quindi selezionare l'utente dall'elenco di utenti disponibili.

2. In **Audioconferenza** fai clic su **Reimposta ID conferenza**.  

3. Nella finestra **Reimposta ID conferenza?** fai clic su **Reimposta**. Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati. Questa impostazione è abilitata in modo predefinito

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, in alcuni casi l'utente potrebbe non voler usare questo ID e vuoi impostarlo su un determinato numero oppure gli utenti non riescono a ricordare o hanno perso l'ID conferenza.

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>Reimpostare il PIN di un organizzatore di conferenze usando l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro fare clic su **Utenti** e quindi selezionare l'utente dall'elenco di utenti disponibili.

2. In **Audioconferenza** fai clic su **Reimposta PIN** e quindi su **Reimposta**.
  
Gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per i servizi di audioconferenza o quando il PIN viene reimpostato. Tuttavia, se hai disabilitato l'invio automatico dei messaggi di posta elettronica, non verrà inviato un messaggio e-mail di reimpostazione del PIN e dovrai inviare manualmente il PIN all'utente. The PIN will only be shown once after it has been reset. Dopo essere stato visualizzato subito dopo la reimpostazione, il PIN non verrà più visualizzato nelle proprietà dell'utente; verrà visualizzato **** al suo posto.
  
Vedi [Reimpostare il PIN dei servizi di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni sui servizi di audioconferenza a un utente

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>Inviare un messaggio di posta elettronica usando l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro fare clic su **Utenti** e quindi selezionare l'utente dall'elenco di utenti disponibili.

2. Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**.

    > [!NOTE]
    > Quando esegui questa operazione, il PIN dei servizi di audioconferenza non viene inviato all'utente.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Impostare i numeri di telefono inclusi negli inviti

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>Impostare i numeri di telefono di invito tramite l'interfaccia di amministrazione di Microsoft Teams

Vedere [Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> È anche possibile impostare i numeri di telefono aggiungendoli al *criterio TeamsAudioconferencing* e assegnando il criterio agli utenti. I numeri verdi e a tariffa aggiunti ai criteri hanno la precedenza sui numeri di telefono impostati singolarmente per gli utenti tramite il riquadro delle impostazioni dei servizi di audioconferenza. Se non vengono aggiunti numeri di telefono al *criterio Teamsaudioconferencing*, il numero di telefono impostato singolarmente per gli utenti tramite il riquadro delle impostazioni dei servizi di audioconferenza verrà visualizzato nelle convocazioni di riunione di Microsoft Teams. Ulteriori informazioni sono disponibili [nelle impostazioni dei criteri per i servizi di audioconferenza per i numeri verdi e a pagamento](audio-conferencing-toll-free-numbers-policy.md).

## <a name="choose-audio-conferencing-bridge-settings"></a>Scegli le impostazioni del bridge per i servizi di audioconferenza

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>Impostare l'esperienza della riunione quando i chiamanti partecipano a una riunione usando l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Conference Bridge** fare clic su **Impostazioni bridge**.

3. Nel riquadro **Impostazioni bridge**, abilitare o disabilitare **Notifiche di entrata e di uscita per le riunioni**.

    Questa funzionalità è abilitata per impostazione predefinita. Se si disabilita questa opzione, gli utenti che hanno già eseguito l'accesso alla riunione per impostazione predefinita non riceveranno una notifica quando qualcuno entra o esce dalla riunione.

4. In **Tipo di annuncio entrata/uscita** scegliere **Toni** o **Nomi o numeri di telefono**.

    Se si sceglie **Nomi o numeri di telefono**, è anche possibile scegliere di abilitare o disabilitare **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.
    > [!NOTE]
    > Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti che hanno eseguito l'accesso tramite telefono. Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams.
5. Fare clic su **Salva**.

Vedi [Modificare le impostazioni per un bridge di audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).
  
### <a name="set-the-pin-length-for-meetings"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Conference Bridge** fare clic su **Impostazioni bridge**.

3. Nel riquadro **Impostazioni bridge** immetti il numero di cifre desiderato per il PIN nell'elenco **Lunghezza PIN** e quindi fai clic su **Salva**.

    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.

Vedi [Modificare le impostazioni per un bridge di audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>Abilitare o disabilitare l'invio di posta elettronica agli utenti audio

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Conference Bridge** fare clic su **Impostazioni bridge**.

3. Nel riquadro **Impostazioni bridge** abilita o disabilita **l'invio automatico di messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni dei servizi di audioconferenza**.

4. Fare clic su **Salva**.

    Puoi anche inviare un messaggio e-mail all'utente con le impostazioni dei servizi di audioconferenza, accedendo alle proprietà dei servizi di audioconferenza dell'utente e facendo clic su **Invia le informazioni sulla conferenza tramite posta elettronica**.

    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare le lingue primaria (predefinita) e secondaria (alternativa) in un bridge di audioconferenza

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>Visualizzare le lingue primaria e secondaria con l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Selezionare un numero di telefono nell'elenco e fare clic su **Modifica**.

3. Scegliere le lingue desiderate in **Lingua predefinita** e **Lingue alternative (facoltativo).**

4. Fare clic su **Salva**.

See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>Visualizzare i numeri di accesso esterno per i servizi di audioconferenza tramite l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Selezionare un numero di telefono nell'elenco e fare clic su **Modifica**. Qui puoi:

   - Visualizza i numeri di telefono da utilizzare per le audioconferenze.

   - Visualizza la posizione e la lingua principale che verranno utilizzate dall'operatore automatico di audioconferenza.

Vedi [Visualizzare un elenco dei numeri dei servizi di audioconferenza](see-a-list-of-audio-conferencing-numbers-in-teams.md).

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
