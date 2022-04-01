---
title: Usare la procedura guidata connettore Turni per connettere Turni a Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare la procedura guidata connettore Turni per integrare turni in Teams con Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593667"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Usare la procedura guidata connettore Turni per connettere Turni a Blue Yonder Workforce Management

## <a name="overview"></a>Panoramica

La procedura guidata connettore Turni nella interfaccia di amministrazione di Microsoft 365 consente di integrare l'app Turni in Microsoft Teams con il sistema WFM (Workforce Management). Dopo aver configurato una connessione, i dipendenti in prima linea possono visualizzare e gestire facilmente le pianificazioni nel sistema WFM dall'interno dei turni.

La procedura guidata configura il connettore Turni, crea una connessione al sistema WFM e applica le impostazioni di sincronizzazione e i mapping del team che si sceglie. Le impostazioni di sincronizzazione determinano le informazioni sulla pianificazione sincronizzate tra il sistema WFM e i turni. I mapping dei team definiscono la relazione di sincronizzazione tra i siti WFM e i team in Teams. È possibile eseguire il mapping a team esistenti e nuovi team.

È possibile configurare più connessioni, ognuna con impostazioni di sincronizzazione diverse. Ad esempio, se l'organizzazione ha più posizioni con requisiti di pianificazione diversi, creare una connessione con impostazioni di sincronizzazione univoche per ogni posizione. Tenere presente che un sito WFM può essere mappato a un solo team alla volta. Se un sito WFM è già mappato a un team, non può essere mappato a un altro team.

Con il sistema WFM come sistema di registrazione, i dipendenti in prima linea possono vedere e scambiare turni, gestire la loro disponibilità e richiedere un turno nei turni sui loro dispositivi. I responsabili in prima linea possono continuare a usare il sistema WFM per configurare le pianificazioni.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrare turni con Blue Yonder Workforce Management

Attualmente, la procedura guidata supporta il [connettore Microsoft Teams Turni per Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Questo connettore consente di integrare Turni con Blue Yonder Workforce Management (Blue Yonder WFM) per gestire le pianificazioni e mantenerle aggiornate. In questo articolo viene illustrato come eseguire la procedura guidata per configurare una connessione a Blue Yonder WFM tramite il connettore.

> [!NOTE]
> È anche possibile usare PowerShell per integrare Turni con Blue Yonder WFM. Per altre informazioni, vedere [Usare PowerShell per connettere Turni a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Prima di iniziare

Per eseguire la procedura guidata è Microsoft 365 amministratore globale.

### <a name="prerequisites"></a>Prerequisiti
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- I team da mappare non hanno pianificazioni. Se un team ha una pianificazione esistente, [rimuovere](#remove-schedules-from-teams-you-want-to-map) la pianificazione dal team prima di mappare un sito WFM Blue Yonder a esso. In caso contrario, verranno visualizzati i turni duplicati.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Rimuovere le pianificazioni dai team di cui si vuole eseguire il mapping
<a name="remove_schedules"> </a>

> [!NOTE]
> Completare questo passaggio se si sta mappando i siti WFM Blue Yonder a team esistenti con pianificazioni. Se si esegue il mapping a team che non hanno pianificazioni o se si stanno creando nuovi team a cui eseguire il mapping, è possibile ignorare questo passaggio.

Usare PowerShell per rimuovere le pianificazioni dai team.

1. Prima di tutto, è necessario installare i moduli di PowerShell e configurarlo. Seguire i passaggi per [configurare l'ambiente](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Eseguire il comando seguente:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Per ottenere un elenco di scenari per il `EntityType` parametro, eseguire [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps). I dati di pianificazione verranno rimossi per l'intervallo di data e ora specificato.

Per altre informazioni, vedere [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Eseguire la procedura guidata

### <a name="get-started"></a>Per iniziare

1. Nel riquadro di spostamento sinistro del [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) scegliere **Configurazione** e quindi passare alla **sezione App e posta** elettronica.
1. Selezionare Connessione **sistema di gestione della forza lavoro**. Qui è possibile ottenere altre informazioni sui connettori Turni e sull'esperienza di lavoro e manager in prima linea quando si connettono Turni al sistema WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Screenshot della pagina dei dettagli per la procedura guidata connettore Turni nella interfaccia di amministrazione di Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Al termine, **selezionare Attività iniziali.**
1. Selezionare **Avanti** per creare una connessione WFM Blue Yonder.

### <a name="enter-connection-details"></a>Immettere i dettagli della connessione
<a name="connection_details"> </a>

1. Nella pagina Dettagli connessione assegnare un nome univoco alla connessione. Non può essere più lungo di 128 caratteri o contenere caratteri speciali.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Screenshot della pagina Dettagli connessione della procedura guidata che mostra le impostazioni di connessione." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Immettere il nome dell'account del servizio Blue Yonder WFM e la password e gli URL del servizio.
1. Al termine, selezionare Avanti **per** verificare la connessione con le impostazioni immesse.

### <a name="choose-sync-settings"></a>Scegliere le impostazioni di sincronizzazione
<a name="sync"> </a>

Nella pagina Impostazioni di sincronizzazione è possibile scegliere le informazioni da sincronizzare da Blue Yonder WFM a Turni, la frequenza di sincronizzazione e se gli utenti di Turni possono apportare modifiche ai dati.

1. Immettere l'Microsoft 365 di sistema.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Screenshot della pagina Impostazioni di sincronizzazione della procedura guidata che mostra le impostazioni di sincronizzazione." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. In **Destinatari notifica tramite posta elettronica** scegliere chi riceve le notifiche tramite posta elettronica sulla connessione. È possibile aggiungere singoli utenti e gruppi. Le notifiche tramite posta elettronica contengono informazioni sullo stato di configurazione della connessione e su eventuali problemi o errori che possono verificarsi dopo la configurazione della connessione.
1. Scegliere le impostazioni di sincronizzazione:
    1. In **Pianifica e turni** scegliere i dati WFM Blue Yonder che gli utenti possono visualizzare o modificare e quindi impostare la frequenza di sincronizzazione.
    2. In **Richieste** scegliere i tipi di richieste che gli utenti possono visualizzare e creare.

    > [!IMPORTANT]
    > Se si sceglie una delle opzioni seguenti per disabilitare i turni aperti, le richieste di turni aperti, le richieste di scambio o le richieste di tempo libero, è necessario eseguire un altro passaggio per nascondere la funzionalità in Turni.
    >
    > - Turni aperti: **gli utenti turni non vedono i dati WFM Blue Yonder**
    > - Richieste di scambio: **caratteristica disabilitata per tutti gli utenti**
    > - Richieste di tempo libero: **la caratteristica è disabilitata per tutti gli utenti**
    >
    > Dopo aver eseguito la procedura guidata, assicurarsi di seguire i passaggi della sezione Disabilitare turni aperti, richieste di turni aperti [,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) richieste di scambio e richieste di tempo libero più avanti in questo articolo.
 
1. Dopo aver scelto le impostazioni, selezionare **Crea connessione**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Mappare i siti di gestione della forza lavoro Blue Yonder ai team
<a name="sites"> </a>

Scegliere i siti WFM Blue Yonder da connettere ai turni. È possibile selezionare fino a 100 siti.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Screenshot della procedura guidata che mostra l'elenco dei siti WFM Blue Yonder." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Eseguire quindi il mapping di ogni sito WFM Blue Yonder selezionato a un team in Teams. È possibile mappare un sito a un team esistente oppure creare un nuovo team.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Screenshot del riquadro che mostra l'opzione del team di ricerca e crea una nuova opzione del team." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>Per mappare un sito a un team esistente

1. Selezionare il nome del sito.
2. Nel riquadro cercare il team e quindi selezionarlo. Tenere presente che i team già mappati a un sito in questa connessione non vengono visualizzati nella ricerca.
3. Scegliere il fuso orario e la città più vicina.
4. Selezionare **Salva** e quindi **Avanti**.

#### <a name="to-map-a-site-to-a-new-team"></a>Per mappare un sito a un nuovo team

1. Selezionare il nome del sito.
2. Nel riquadro scegliere **Crea un nuovo team**. Verrà creata una nuova scheda nel browser in cui è possibile creare un nuovo team nel interfaccia di amministrazione di Microsoft 365.
    1. Immettere un nome e una descrizione facoltativa per il team.
    1. Aggiungere uno o più proprietari del team. Assicurarsi di aggiungere l'account Microsoft 365 di sistema come proprietario.
    1. Aggiungere membri del team.
    1. Aggiungere un indirizzo di posta elettronica del team e scegliere un'impostazione di privacy.
    1. Rivedere le impostazioni e quindi scegliere **Aggiungi team**. Dopo la creazione del team, scegliere **Chiudi**.
3. Indietro alla procedura guidata, cercare e quindi selezionare il nuovo team creato.
4. Scegliere il fuso orario e la città più vicina.
5. Selezionare **Salva** e quindi **Avanti**.

### <a name="review-and-finish"></a>Revisione e fine

Rivedere le impostazioni. Se è necessario apportare modifiche ai mapping del team, scegliere **Modifica** per farlo. Al termine, selezionare **Fine**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Screenshot della pagina Revisione della procedura guidata che mostra i mapping." lightbox="../../media/shifts-connector-wizard-review.png":::

Verrà visualizzato un messaggio per confermare che la richiesta è stata ricevuta insieme a un ID operazione. Prendere nota dell'ID operazione. Sarà necessario per controllare lo stato di configurazione della connessione.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Screenshot della pagina della procedura guidata che mostra il messaggio di conferma e l'ID operazione." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

La procedura guidata avvia il processo per configurare la connessione e mappare i siti ai team selezionati. Il completamento di questo processo potrebbe richiedere del tempo. I destinatari scelti riceveranno notifiche tramite posta elettronica sullo stato della configurazione.

Selezionare **Fine per** uscire dalla procedura guidata.

Stai arrivando, ma non hai ancora finito! Assicurati di controllare la tua e-mail. Riceverai una conferma che abbiamo ricevuto la tua richiesta insieme a un [collegamento](shifts-connector-powershell-manage.md#check-connection-setup-status) a come puoi controllare lo stato di configurazione.

> [!NOTE]
> Se si verifica un problema o un errore in una connessione dopo la configurazione, si otterrà una notifica tramite posta elettronica. Seguire le istruzioni nel messaggio di posta elettronica per risolvere il problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Disabilitare i turni aperti, le richieste di turni aperti, le richieste di scambio e le richieste di tempo libero

> [!IMPORTANT]
> Seguire questa procedura solo se si sceglie una delle opzioni seguenti per disabilitare i turni aperti, le richieste di turni aperti, le richieste di scambio o le richieste di tempo libero nella procedura guidata. Il completamento di questo passaggio nasconde la funzionalità in Turni.
>
> - Turni aperti: **gli utenti turni non vedono i dati WFM Blue Yonder**
> - Richieste di scambio: **caratteristica disabilitata per tutti gli utenti**
> - Richieste di tempo libero: **la caratteristica è disabilitata per tutti gli utenti**
>
> Senza questo secondo passaggio, gli utenti potranno comunque vedere la funzionalità in Turni e riceveranno un messaggio di errore "Operazione non supportata" se provano a usarla.

Per nascondere turni aperti, richieste di scambio e richieste di tempo [libero in](/graph/api/resources/schedule?view=graph-rest-1.0) Turni, usare il tipo di risorsa pianificazione API Graph per impostare i parametri seguenti su per ogni team mappato a ```false``` un sito WFM Blue Yonder:

- Turni aperti: ```openShiftsEnabled```
- Richieste di scambio:  ```swapShiftsRequestsEnabled```
- Richieste di tempo libero: ```timeOffRequestsEnabled```

Per nascondere le richieste di turni aperti in Turni, passare a **Impostazioni in** Turni e quindi disattivare l'impostazione **Apri turni**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Se è necessario apportare modifiche a una connessione
<a name="update_connection"> </a>

Dopo aver configurato una connessione, usare PowerShell per apportarvi modifiche. Ad esempio, è possibile aggiornare le impostazioni di sincronizzazione, i mapping del team e disabilitare la sincronizzazione per una connessione. Per istruzioni dettagliate, vedere Usare PowerShell per gestire la connessione [Turni a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Articoli correlati

- [Turni connettori](shifts-connectors.md)
- [Usare PowerShell per gestire la connessione Turni a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Gestire l'app Turni in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
