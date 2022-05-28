---
title: Come usare Microsoft Teams dispositivi con pannelli
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: Questo articolo fornisce indicazioni su come usare Teams dispositivi con pannelli.
ms.openlocfilehash: 00d2657179e35e2a5e43cbc0665a6d1533ec70d1
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760908"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Come usare i pannelli Microsoft Teams

Microsoft Teams pannelli sono dispositivi di visualizzazione digitale compatti montati direttamente all'esterno degli spazi delle riunioni, in genere accanto agli ingressi. Questi pannelli touchscreen sono dedicati Microsoft Teams dispositivi che offrono una visualizzazione immediata dell'area riunioni e della riunione pianificata. Con i vivaci indicatori led codificati a colori e schermata home, puoi determinare se lo spazio è disponibile o riservato da una distanza. È possibile usare Teams pannelli per prenotare uno spazio disponibile per una riunione ad hoc, sul posto.

I dispositivi con pannelli Teams sono preinstallati con Microsoft Teams e visualizzano i dettagli delle riunioni pianificati tramite calendari Outlook o Teams.

Questo articolo fornisce indicazioni su come usare i dispositivi dei pannelli di Teams sia per gli utenti finali che per gli amministratori. Fornisce inoltre le risposte alle [domande frequenti](#frequently-asked-questions) sull'uso di questi dispositivi.

Per una panoramica dei dispositivi con pannelli e le indicazioni su come pianificarli, recapitarli e gestirli nell'organizzazione, vedere [Distribuire Microsoft Teams pannelli](teams-panels.md).

Per una guida introduttiva, vedi [Attività iniziali con Teams pannelli](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Teams l'esperienza utente finale dei pannelli

Esplorare la [schermata home](#explore-teams-panels-home-screen) del dispositivo con pannelli Teams per visualizzare l'area riunioni e i dettagli della riunione. In alternativa, tocca e scorri il pannello touchscreen per eseguire altre azioni.

Usare i dispositivi Teams pannelli per:

- [Visualizzare i dettagli e la disponibilità dell'area riunioni, i dettagli della riunione, le prenotazioni imminenti](#explore-teams-panels-home-screen)
- [Prenotare un'area riunioni disponibile](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Segnala un problema](#report-a-problem)
- [Visualizzare o aggiornare l'impostazione di un dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Esplorare la schermata iniziale dei pannelli Teams

La schermata Home è l'interfaccia visiva principale del dispositivo con pannelli Teams.  

Dalla schermata Home è possibile visualizzare i dettagli del luogo e della riunione, prenotare uno spazio, visualizzare le prenotazioni imminenti e identificare lo stato di disponibilità corrente.

Lo screenshot seguente mostra diverse parti o riquadri nella schermata iniziale dei pannelli Teams:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Questa schermata mostra aree diverse nella schermata iniziale dei pannelli Teams.":::

Per una descrizione di ogni riquadro, vedere la tabella seguente:

Piastrelle | Descrizione
:---|:---
**1-Dettagli relativi a ora, giorno, data e spazio riunioni corrente** | Visualizza l'ora, il giorno, la data e il nome dell'area riunioni correnti. Il nome dell'area riunioni è il nome dell'account della risorsa che ha eseguito l'accesso ai pannelli.
**2-Disponibilità dell'area riunioni e dettagli della riunione** | Indica la disponibilità dell'area riunioni e visualizza i dettagli della riunione. Vedere [Il riquadro Disponibilità dell'area riunioni e dettagli della riunione](#meeting-space-availability-and-meeting-details-tile).
**3-Prossimo calendario** | Visualizza il calendario dell'area riunioni e la disponibilità per un massimo di 24 ore rispetto all'ora corrente. Scorrere verso l'alto o verso il basso per determinare quali fasce orarie sono disponibili e quali sono riservate.
**4 Impostazioni** | Visualizza l'icona **Impostazioni**. Toccalo per segnalare un problema o aggiornare le impostazioni del dispositivo disponibili.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Riquadro Disponibilità dell'area riunioni e dettagli della riunione

L'aspetto di questo riquadro e le sue funzionalità variano a seconda della disponibilità dell'area riunioni e del tipo di prenotazione.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>L'area riunioni è riservata a una riunione pianificata

Il riquadro viene visualizzato in viola per un'area riunioni riservata a una riunione pianificata (pianificata tramite Outlook o Teams). Mostra il titolo della riunione in un testo in evidenza, l'ora di inizio e di fine della riunione e il nome dell'organizzatore della riunione. Per una riunione Teams viene visualizzato anche il logo Teams. Con i dettagli della riunione in primo piano visualizzati, i partecipanti possono verificare facilmente di essere nell'area della riunione giusta, all'ora giusta e per la riunione giusta.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams pannelli Schermata iniziale che mostra che l'area riunioni è riservata a una riunione pianificata.":::

> [!NOTE]
>
> - Dopo aver pianificare una riunione, possono essere necessari fino a 90 secondi prima che il calendario venga sincronizzato e riflesso sullo schermo dei pannelli.
> - Per una [riunione pianificata contrassegnata come privata](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d), viene visualizzata la **riunione privata** al posto del titolo effettivo della riunione.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>L'area riunioni è riservata a una riunione ad hoc

Il riquadro viene visualizzato in viola per un'area riunioni [riservata per una riunione ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Viene visualizzato **Riservato** nel testo in evidenza insieme all'ora di inizio e di fine della riunione. Le riunioni ad hoc vengono pianificate automaticamente come riunioni Teams, quindi sullo schermo viene sempre visualizzato il logo Teams.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams riquadri Schermata iniziale che mostra che l'area riunioni è riservata per una riunione ad hoc.":::

#### <a name="meeting-space-is-available"></a>L'area riunioni è disponibile

Il riquadro viene visualizzato in verde per un'area riunioni disponibile. Viene visualizzato **Disponibile** in un testo in evidenza e viene anche visualizzato un pulsante **Prenota** che è possibile toccare per [prenotare l'area della riunione per una riunione ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). È possibile controllare il calendario imminente dell'area riunioni (riquadro in basso a destra) per decidere l'ora di fine della riunione ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Questa schermata mostra come viene visualizzata la schermata iniziale dei pannelli Teams quando è disponibile l'area riunioni.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Prenotare spazi per riunioni ad hoc

È possibile prenotare [un'area riunioni disponibile](#meeting-space-is-available) direttamente dai pannelli per una riunione ad hoc. Tutte le riunioni ad hoc vengono pianificate automaticamente come riunioni Teams. Tuttavia, una volta prenotata, non è possibile rilasciare o annullare la prenotazione dell'area riunioni tramite i pannelli. Solo gli amministratori dell'account delle risorse del dispositivo possono annullare la riunione ad hoc (tramite Outlook o Teams calendario) per annullare la prenotazione dello spazio.

Per le riunioni ad hoc prenotate direttamente dai pannelli:

- L'ora di inizio è sempre l'ora corrente e pertanto non è possibile pianificare per un orario futuro.
- L'ora di fine può essere fino alla successiva riunione pianificata o fino a 24 ore dall'ora corrente, a seconda di quale evento si verifichi prima. Controllare il riquadro **Calendario in scadenza** nella schermata home per determinare le fasce orarie durante le quali l'area della riunione è disponibile o prenotata.

Per prenotare un'area riunioni disponibile per una riunione ad hoc:

1. Nella schermata Home toccare il pulsante **Prenota** .
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams schermata iniziale dei pannelli con il pulsante Prenota.":::
2. Nella schermata **Riunione ad hoc** , esaminare le opzioni disponibili per l'ora di fine. È possibile usare le frecce a destra o a sinistra per esplorare le opzioni disponibili per l'ora di fine.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Schermata riunione ad hoc che mostra le fasce orarie di fine.":::

    > [!Note]
    >
    > - Le opzioni per l'ora di fine vengono visualizzate a intervalli di 15 minuti di un'ora.
    > - Per impostazione predefinita, l'ora di fine corrisponde all'intervallo di 15 minuti successivo, che è di almeno cinque minuti dopo l'ora corrente. Ad esempio, se l'ora corrente è 13.57, l'ora di fine predefinita viene visualizzata come 14.15 e non come 14.00. Questo impedisce agli utenti di prenotare lo spazio per cinque minuti o meno. Nello screenshot precedente, l'ora di fine predefinita viene visualizzata come 14.00, ovvero l'intervallo di 15 minuti successivo che è di almeno cinque minuti dopo l'ora corrente (13.53).
    > - Un'eccezione alla regola precedente è quando l'ora di inizio della riunione successiva è entro cinque minuti dall'ora corrente. In questi casi, è possibile prenotare lo spazio fino all'ora di inizio della riunione successiva. Ad esempio, se l'ora corrente è 13.57 e l'ora di inizio della riunione successiva è 14.00, alle 14.00 viene visualizzata l'unica opzione per l'ora di fine ed è possibile prenotare lo spazio per tre minuti.

3. Toccare l'intervallo di tempo di fine desiderato e quindi toccare **Prenota**.

    Viene visualizzata una finestra di conferma con un emoji pollice in su, l'ora di inizio e di fine della riunione e il nome dell'area riunioni.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Messaggio di conferma di una riunione ad hoc.":::
Il riquadro destro della schermata home ora viene visualizzato in viola e mostra il testo **riservato** e il logo Teams. Ciò indica che l'area riunioni è ora riservata per una riunione ad hoc Teams.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Schermata iniziale che mostra che l'area riunioni è riservata per una riunione ad hoc.":::

    > [!NOTE]
    > Se l'area riunioni è una sala Microsoft Teams, è possibile _partecipare a_ questa Teams riunione con la sala Microsoft Teams o i dispositivi Surface Hub.

### <a name="report-a-problem"></a>Segnala un problema

Per segnalare un problema con il dispositivo o l'area riunioni, richiedere un aggiornamento delle funzionalità o fornire feedback, usare l'icona **Impostazione** nella schermata iniziale.

1. Toccare l'icona **a** Impostazioni ingranaggio nella schermata home.

2. Toccare l'opzione **Segnala un problema** .

    La schermata **Invia feedback** viene visualizzata in formato modulo.
3. Nell'elenco a discesa **Tipo** selezionare il tipo di richiesta.
4. Nell'elenco a discesa **Problema** selezionare la categoria.
5. Nel campo di testo **Titolo** digitare il titolo usando il tastierino dei pannelli.
6. Nel campo di testo sotto **Titolo** digitare altri dettagli, se necessario.

    > [!NOTE]
    > Non includere informazioni personali.

7. Rivedere le voci e toccare **Invia**.

### <a name="view-or-update-a-device-setting"></a>Visualizzare o aggiornare l'impostazione di un dispositivo

Esistono diverse impostazioni del dispositivo, ad esempio informazioni su, accessibilità, riavvio e informativa sulla privacy che è possibile visualizzare o aggiornare direttamente dai pannelli. Le impostazioni disponibili per il dispositivo potrebbero variare in base all'OEM (Original Equipment Manufacturer) del dispositivo. Per informazioni sulle impostazioni specifiche del dispositivo, vedi la documentazione dell'OEM.

Per visualizzare o aggiornare l'impostazione di un dispositivo:

1. Toccare l'icona **Impostazioni** nella schermata home.
2. Nella **schermata Impostazioni** toccare **Impostazioni dispositivo**.
3. Nella schermata **Impostazioni dispositivo** toccare l'impostazione da visualizzare o aggiornare.
4. Seguire la richiesta visualizzata sullo schermo per visualizzare o aggiornare l'impostazione.

## <a name="teams-panels-admin-experience"></a>esperienza di amministrazione dei pannelli di Teams

Se si è l'amministratore [dell'account delle risorse di Pannello di Teams](teams-panels.md\#resource-account-provisioning), si è anche l'amministratore **dell'app Pannelli** nel dispositivo. L'amministratore **dell'app Panels** può eseguire tutte le funzioni menzionate nella sezione [dell'esperienza utente finale](#teams-panels-end-user-experience) , oltre a gestire le impostazioni **dell'app Pannelli** nel dispositivo.

I dispositivi pannelli forniscono due tipi di impostazioni di amministrazione. Per accedere alle impostazioni di amministrazione disponibili, è necessario essere un amministratore del dispositivo. Gli utenti finali non possono accedere a queste impostazioni.

- Amministrazione impostazioni specifiche del dispositivo, ad esempio schermo, data e ora, lingua, Bluetooth, WiFi e così via. Per altre informazioni su queste impostazioni, consulta la documentazione dell'OEM.
- Amministrazione impostazioni specifiche **dell'app Pannelli** nel dispositivo, ad esempio lo sfondo e il colore dell'indicatore LED. Solo un amministratore **dell'app Pannelli** può accedere a queste impostazioni. Poiché le impostazioni **dell'app Pannelli** sono disponibili nelle impostazioni di amministrazione, per accedere alle impostazioni **dell'app Pannelli** è necessario disporre delle credenziali di accesso dell'amministratore sia per il dispositivo che per **l'app Pannelli**.

> [!NOTE]
> Gli eventuali aggiornamenti alle impostazioni **dell'app Pannelli** eseguiti tramite il dispositivo sono applicabili solo a quel dispositivo specifico. Questi aggiornamenti non influiranno su altri dispositivi pannelli nell'organizzazione. Ad esempio, se si modifica l'immagine di sfondo della schermata iniziale dalle impostazioni **dell'app Pannelli** , l'immagine di sfondo verrà modificata solo per quel dispositivo specifico.

### <a name="access-panels-app-settings"></a>Impostazioni dell'app Pannelli di accesso

È possibile accedere alle impostazioni specifiche **dell'app Pannelli** usando **l'opzione Impostazioni app Pannelli** nelle impostazioni di amministrazione. La procedura per accedere **all'app Pannelli Impostazioni** potrebbe variare in base all'OEM del dispositivo.

Per accedere all'opzione **Impostazioni app Pannelli**:

1. Toccare l'icona **Impostazioni** nella schermata home.
2. Nella schermata **Impostazioni** toccare **Impostazioni dispositivo**.
3. Toccare il **Amministrazione Impostazioni**.

    > [!NOTE]
    > A seconda dell'OEM del dispositivo, potrebbe essere necessario immettere la password di amministratore del dispositivo subito o dopo il passaggio successivo.

4. Scorrere verso il basso per trovare l'opzione **Impostazioni app Pannelli**. Toccalo.
5. Toccare il pulsante **Impostazioni app Pannelli** sullo schermo destro.
    Viene visualizzata la schermata con le impostazioni **dell'app Pannelli** disponibili.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Questa schermata mostra lo schermo con le impostazioni dell'app Pannelli disponibili.":::

    Usare questa schermata per aggiornare le impostazioni **dell'app Pannelli** seguenti per il dispositivo:

    - [Sfondo](#update-the-wallpaper)
    - [Indicatore LED](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Associare un Pannello di Teams a una sala Microsoft Teams in Android

Per associare un Pannello di Teams e una sala Teams in Android, entrambi i dispositivi devono essere connessi allo stesso account della risorsa.

Nel Pannello di Teams accedere con le credenziali di amministratore.

1. Passare a **Impostazioni >'app Pannelli Impostazioni > Amministrazione Impostazioni > dispositivi Impostazioni > riunioni > l'associazione dei dispositivi.**

2. Un codice a sei cifre verrà visualizzato sulla Teams Rooms Android parte anteriore dello schermo della sala. Immettere il codice nel pannello Teams.  

#### <a name="meeting-check-in-and-room-release"></a>Check-in riunione e rilascio sala

Le impostazioni di check-in e di rilascio della sala consentono agli utenti di accedere a una riunione in Teams Pannelli nella sala prenotata all'inizio della riunione. Se un utente non esegue l'archiviazione entro un determinato periodo di tempo dopo l'ora di inizio della riunione, la sala viene rilasciata e diventa disponibile per la prenotazione da parte di altri utenti.

Quando Teams pannelli è associato a una sala Microsoft Teams in Android, le notifiche di archiviazione possono essere abilitate per essere visualizzate sullo schermo della sala quando le riunioni sono in ritardo.

Per abilitare il check-in e il rilascio della sala, vedere [Check-in e rilascio della sala nei pannelli Microsoft Teams](check-in-and-room-release.md).

#### <a name="room-capacity-warning"></a>Avviso sulla capacità della sala

Teams pannelli associati a una sala Teams in Android possibile visualizzare un messaggio di avviso quando una sala riunioni è al suo o alla sua capacità superiore. Per usare questa funzionalità, la Teams Room deve avere una fotocamera che supporti il conteggio delle persone. Teams Rooms su Android avvisi di capacità della sala di supporto senza Pannello di Teams.

Gli avvisi sulla capacità della sala sono disattivati per impostazione predefinita. Per attivare l'impostazione dal Pannello di Teams, [associare prima di tutto un Pannello di Teams a una sala Microsoft Teams Android](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android). Il pannello e il Teams Room devono essere connessi allo stesso account della risorsa.

 Passa quindi a **impostazioni Impostazioni > dispositivo > Amministrazione impostazioni > impostazioni dell'app Pannello**. Quindi, in **Riunioni**, attiva la **notifica sull'occupazione massima della sala**.

#### <a name="view-room-equipment"></a>Visualizzare l'attrezzatura della sala

Quando questa funzionalità è attivata, gli utenti finali possono visualizzare le apparecchiature disponibili in uno spazio di un Pannello di Teams.

Questa funzionalità è disattivata per impostazione predefinita e può essere abilitata per ogni dispositivo. Per attivarlo, usare [Imposta posizione](/powershell/module/exchange/set-place?view=exchange-ps) in PowerShell per configurare i nomi visualizzati per `AudioDeviceName`, `DisplayDeviceName`, `VideoDeviceName`, `Tags`e `IsWheelChairAccessible`.

In alternativa, è possibile abilitare questa caratteristica nell'interfaccia di amministrazione di Exchange. Per altre informazioni, vedere [Modificare una risorsa](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) .



#### <a name="update-the-wallpaper"></a>Aggiorna lo sfondo

Modificare l'immagine di sfondo Della schermata home.

1. [App **Pannelli** di accesso Impostazioni](#access-panels-app-settings).
2. Tocca **Sfondi**.
3. In **Scegli l'immagine** selezionare un'immagine da impostare come immagine di sfondo della schermata home. Visualizzare in anteprima l'immagine selezionata in **Sfondo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Questo screenshot mostra la schermata delle impostazioni dello sfondo.":::
4. Indietro alla schermata iniziale e verifica che lo sfondo sia aggiornato.

#### <a name="change-the-busy-state-led-color"></a>Cambiare il colore LED dello stato occupato

Gli amministratori possono scegliere il rosso o il viola come colore LED per indicare che lo spazio della riunione è occupato o riservato. Il colore LED per indicare uno spazio disponibile è sempre verde e non può essere modificato.

1. [App **Pannelli** di accesso Impostazioni](#access-panels-app-settings).
2. Tocca **Impostazioni LED**.
3. In **Scegli il colore LED** seleziona il colore desiderato.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Questa schermata mostra le impostazioni dello stato occupato del colore LED.":::
4. Indietro alla schermata iniziale e verifica che il colore LED per lo stato occupato sia aggiornato. Se l'area della riunione è attualmente disponibile, provare a pianificare una riunione di prova per verificare la modifica del colore LED per lo stato occupato.

## <a name="frequently-asked-questions"></a>Domande frequenti

Trova le risposte alle domande frequenti sui dispositivi con pannelli Teams.

**A quanto lontano nel futuro posso visualizzare i dettagli di pianificazione di un'area riunioni?**  
Nel riquadro **Calendario in scadenza** (in basso a destra) nella schermata iniziale è possibile visualizzare i dettagli di pianificazione di un'area riunioni per un massimo di 24 ore in futuro a partire dall'ora corrente.

**È possibile prenotare un'area riunioni per un periodo futuro dal dispositivo con pannelli Teams?**  
No, non è possibile prenotare un'area riunioni per un periodo futuro dai pannelli. L'ora di inizio è sempre l'ora corrente per una riunione ad hoc pianificata dai pannelli.

**Per quanto tempo è possibile prenotare un'area riunioni disponibile per una riunione ad hoc?**  
È possibile prenotare uno spazio disponibile per le riunioni a partire dall'ora corrente fino all'orario della riunione pianificata successivo oppure fino a un massimo di 24 ore dall'ora corrente, a seconda dell'orario precedente. Ad esempio, se l'ora corrente è le 10 e l'ora di inizio della riunione successiva è 14:00, è possibile prenotare l'area riunioni dalle 10:00 alle 14:00.
