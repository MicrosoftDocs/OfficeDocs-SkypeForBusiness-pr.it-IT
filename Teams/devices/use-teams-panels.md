---
title: Come usare i Microsoft Teams dispositivi
ms.author: czawideh
author: cazawideh
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
description: Questo articolo fornisce indicazioni su come usare i Teams dei pannelli.
ms.openlocfilehash: 2928bb64881cad5fb5c6615d26767e963f725dcd
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643040"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Come usare i Microsoft Teams di lavoro

Microsoft Teams sono dispositivi di visualizzazione digitali compatti che vengono installati all'esterno degli spazi riunioni, in genere accanto agli ingressi. Questi pannelli touchscreen sono Microsoft Teams dispositivi che offrono una visualizzazione a colpo d'occhio dell'area riunioni e della riunione pianificata. Con gli indicatori della schermata HOME e LED codificati a colori vivaci, è possibile determinare se lo spazio è disponibile o riservato a distanza. È possibile usare Teams per prenotare uno spazio riunioni disponibile per una riunione ad hoc, sul posto.

Teams i dispositivi dei pannelli vengono preinstallati con Microsoft Teams e visualizzano i dettagli della riunione pianificati tramite Outlook o Teams calendario.

Questo articolo fornisce indicazioni, sia per gli utenti finali che per gli amministratori, su come usare i Teams dei pannelli. Fornisce anche le risposte alle [domande frequenti sull'uso](#frequently-asked-questions) di questi dispositivi.

Per una panoramica dei dispositivi dei pannelli e per indicazioni su come pianificarli, gestirli e gestirli nell'organizzazione, vedere Distribuire Microsoft Teams [pannelli](teams-panels.md).

Per una guida introduttiva, vedere Attività iniziali [con Teams pannelli.](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

## <a name="teams-panels-end-user-experience"></a>Teams per l'utente finale dei pannelli

Esplorare la [schermata Home del](#explore-teams-panels-home-screen) dispositivo Teams per visualizzare l'area riunioni e i dettagli della riunione. In caso contrario, toccare e scorrere il riquadro del touchscreen per eseguire altre azioni.

Usare i Teams per:

- [Visualizzare i dettagli e la disponibilità dello spazio della riunione, i dettagli della riunione, le prenotazioni imminenti](#explore-teams-panels-home-screen)
- [Prenotare uno spazio disponibile per le riunioni](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Segnalare un problema](#report-a-problem)
- [Visualizzare o aggiornare un'impostazione del dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Esplorare Teams pannello Home

La schermata Home è l'interfaccia visiva principale del dispositivo Teams pannello.  

Nella schermata Home è possibile visualizzare i dettagli della posizione e della riunione, prenotare uno spazio, visualizzare le prenotazioni imminenti e identificare lo stato di disponibilità corrente.

Lo screenshot seguente mostra parti o riquadri diversi nella Teams home dei riquadri:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Questa schermata mostra diverse aree nella schermata Teams pannello Home.":::

Fare riferimento alla tabella seguente per una descrizione di ogni riquadro:

Riquadro | Descrizione
:---|:---
**1-Dettagli su ora corrente, giorno, data e spazio riunioni** | Visualizza l'ora corrente, il giorno, la data e il nome dell'area riunioni. Il nome dell'area riunioni è il nome dell'account della risorsa che ha eseguito l'accesso ai pannelli.
**Disponibilità dell'area riunioni 2 e dettagli della riunione** | Indica la disponibilità dello spazio della riunione e visualizza i dettagli della riunione. Vedere [La disponibilità dell'area riunioni e il riquadro dei dettagli della riunione](#meeting-space-availability-and-meeting-details-tile).
**3-Upcoming Calendar** | Visualizza il calendario dell'area riunioni e la disponibilità per un massimo di 24 ore dall'ora corrente. Scorrere verso l'alto o verso il basso per determinare quali fasce orarie sono disponibili e quali sono riservate.
**4 Impostazioni** | Visualizza **l'icona Impostazioni** testo. Toccarlo per segnalare un problema o aggiornare le impostazioni del dispositivo disponibili.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Riquadro Della disponibilità dell'area riunioni e dei dettagli della riunione

L'aspetto di questo riquadro e le relative funzionalità variano a seconda della disponibilità dello spazio della riunione e del tipo di prenotazione.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>Lo spazio riunioni è riservato a una riunione pianificata

Il riquadro viene visualizzato in viola per un'area riunioni riservata a una riunione pianificata (pianificata tramite Outlook o Teams). Mostra il titolo della riunione in testo prominente, l'ora di inizio e di fine della riunione e il nome dell'organizzatore della riunione. Per una Teams riunione, viene visualizzato Teams logo. Con i dettagli della riunione ben visibili, i partecipanti possono facilmente confermare di essere nella giusta area della riunione, al momento giusto e per la riunione giusta.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams pannello Home che mostra che lo spazio riunioni è riservato per una riunione pianificata.":::

> [!NOTE]
>
> - Dopo aver programmato una riunione, la sincronizzazione del calendario e la sua visualizzazione sullo schermo dei pannelli possono richiedere fino a 90 secondi.
> - Per una [riunione pianificata contrassegnata come privata](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)**, viene** visualizzata una riunione privata invece del titolo effettivo della riunione.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>Lo spazio riunioni è riservato per una riunione ad hoc

Il riquadro viene visualizzato in viola per un'area riunioni [riservata a una riunione ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Visualizza Riservato **in testo** prominente insieme all'ora di inizio e di fine della riunione. Le riunioni ad hoc vengono pianificate automaticamente Teams riunioni, quindi il logo Teams viene sempre visualizzato sullo schermo.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams pannello Home che mostra che lo spazio riunioni è riservato per una riunione ad hoc.":::

#### <a name="meeting-space-is-available"></a>L'area riunioni è disponibile

Il riquadro viene visualizzato in verde per un'area riunioni disponibile. Viene visualizzato **Disponibile** in testo prominente e viene  visualizzato anche un pulsante Prenota che è possibile toccare per prenotare lo spazio della riunione [per una riunione ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). È possibile controllare il calendario imminente dell'area della riunione (riquadro in basso a destra) per decidere l'ora di fine della riunione ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Questo screenshot mostra come viene visualizzata la Teams home dei pannelli quando l'area riunioni è disponibile.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Prenotare gli spazi delle riunioni per le riunioni ad hoc

È possibile prenotare uno [spazio riunioni disponibile](#meeting-space-is-available) direttamente dai pannelli per una riunione ad hoc. Tutte le riunioni ad hoc vengono pianificate automaticamente Teams riunioni. Tuttavia, una volta prenotato, non è possibile rilasciare o annullare la prenotazione dello spazio riunioni tramite i pannelli. Solo gli amministratori dell'account delle risorse del dispositivo possono annullare la riunione ad hoc (tramite Outlook o Teams calendario) per annullare la prenotazione dello spazio.

Per le riunioni ad hoc prenotate direttamente dai pannelli:

- L'ora di inizio è sempre l'ora corrente e di conseguenza non è possibile pianificarla per un'ora futura.
- L'ora di fine può essere fino alla riunione pianificata successiva o fino a 24 ore dall'ora corrente, a seconda della data precedente. Controllare il **riquadro Calendario imminente** nella schermata Home per determinare le fasce orarie durante le quali l'area della riunione è disponibile o prenotata.

Per prenotare una sala riunioni disponibile per una riunione ad hoc:

1. Nella schermata Home toccare il **pulsante** Riserva.
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams pannello Home con il pulsante Riserva.":::
2. Nella schermata **Riunione ad hoc** esaminare le opzioni disponibili per l'ora di fine. È possibile usare le frecce destra o sinistra per esplorare le opzioni disponibili per l'ora di fine.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Schermata della riunione ad hoc che mostra le fasce orarie di fine.":::

    > [!Note]
    >
    > - Le opzioni dell'ora di fine vengono visualizzate a intervalli di 15 minuti di un'ora.
    > - L'ora di fine viene impostata per impostazione predefinita sull'intervallo di 15 minuti successivo, che è almeno cinque minuti dopo l'ora corrente. Ad esempio, se l'ora corrente è 13:57, l'ora di fine predefinita viene visualizzata come 14.15 e non come 14.00. In questo modo gli utenti non potranno prenotare lo spazio per cinque minuti o meno. Nello screenshot precedente l'ora di fine predefinita viene visualizzata come 14.00, ovvero l'intervallo successivo di 15 minuti, ovvero almeno cinque minuti dopo l'ora corrente (13:53).
    > - Un'eccezione alla regola precedente è quando l'ora di inizio della riunione successiva è entro cinque minuti dall'ora corrente. In questi casi, è possibile prenotare lo spazio fino all'ora di inizio successiva della riunione. Ad esempio, se l'ora corrente è 13:57 e l'ora di inizio successiva della riunione è 14.00, le 14.00 verranno visualizzate come unica opzione di fine ed è possibile prenotare lo spazio per tre minuti.

3. Toccare l'intervallo di tempo di fine desiderato e quindi toccare **Prenota**.

    Viene visualizzata una finestra di conferma con un emoji con il pollice in su, l'ora di inizio e di fine della riunione e il nome dell'area della riunione.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Messaggio di conferma della riunione ad hoc.":::
Il riquadro destro nella schermata Home ora viene visualizzato in viola e visualizza il  testo riservato e il logo Teams testo. Questo indica che lo spazio della riunione è ora riservato per una riunione Teams riunione.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Schermata iniziale che mostra che lo spazio della riunione è riservato per una riunione ad hoc.":::

    > [!NOTE]
    > Se l'area della riunione è Microsoft Teams sala riunioni, è possibile  partecipare a questa riunione Teams con la sala Microsoft Teams sala o Surface Hub dispositivi.

### <a name="report-a-problem"></a>Segnalare un problema

Per segnalare un problema relativo al dispositivo o all'area riunioni, per richiedere un aggiornamento delle funzionalità o per inviare commenti e suggerimenti,  usare l'icona Impostazioni nella schermata Home.

1. Toccare l **Impostazioni'icona** a forma di ingranaggio nella schermata Home.

2. Toccare **l'opzione Segnala un** problema.

    La **schermata Invia feedback** viene visualizzata in formato modulo.
3. **Nell'elenco a** discesa Tipo selezionare il tipo di richiesta.
4. **Nell'elenco a** discesa Problema selezionare la categoria.
5. Nel campo **di** testo Titolo digitare il titolo usando il tastierino dei pannelli.
6. Nel campo di testo sotto **Titolo** digitare altri dettagli, se necessario.

    > [!NOTE]
    > Non includere informazioni personali.

7. Rivedere le voci e toccare **Invia**.

### <a name="view-or-update-a-device-setting"></a>Visualizzare o aggiornare un'impostazione del dispositivo

Sono disponibili diverse impostazioni del dispositivo, ad esempio informazioni su, accessibilità, riavvio e informativa sulla privacy, che è possibile visualizzare o aggiornare direttamente dai pannelli. Le impostazioni del dispositivo disponibili possono variare in base al produttore OEM (Original Equipment Manufacturer) del dispositivo. Per informazioni sulle impostazioni specifiche del dispositivo, vedere la documentazione OEM.

Per visualizzare o aggiornare un'impostazione del dispositivo:

1. Toccare **l'Impostazioni** nella schermata Home.
2. Nella schermata **Impostazioni**, toccare **Impostazioni dispositivo**.
3. Nella schermata **Impostazioni** dispositivo toccare l'impostazione che si vuole visualizzare o aggiornare.
4. Seguire la richiesta visualizzata per visualizzare o aggiornare l'impostazione.

## <a name="teams-panels-admin-experience"></a>Teams di amministrazione dei pannelli di lavoro

Se sei l'amministratore [dell'account](teams-panels.md\#resource-account-provisioning) delle risorse di Pannello di Teams, sei anche l'amministratore **dell'app Panels** nel dispositivo. **L'amministratore dell'app Panels** può eseguire tutte le funzioni menzionate nella sezione dell'esperienza utente finale, oltre a gestire le impostazioni [](#teams-panels-end-user-experience) **dell'app Panels** nel dispositivo.

I dispositivi dei pannelli forniscono due tipi di impostazioni di amministratore. Per accedere alle impostazioni di amministrazione disponibili, è necessario essere un amministratore del dispositivo. Gli utenti finali non possono accedere a queste impostazioni.

- Impostazioni di amministratore specifiche del dispositivo, ad esempio visualizzazione, ora e data, lingua, bluetooth, WiFi e così via. Per altre informazioni su queste impostazioni, vedere la documentazione OEM.
- Impostazioni di amministratore specifiche **dell'app Pannelli** nel dispositivo, ad esempio lo sfondo e il colore dell'indicatore LED. Solo un amministratore **dell'app Panels** può accedere a queste impostazioni. Poiché **le impostazioni dell'app** Pannelli sono disponibili come parte delle impostazioni di amministrazione, è necessario avere le credenziali di accesso dell'amministratore sia per il dispositivo che per **l'app Panels** per accedere **alle impostazioni dell'app** Panels.

> [!NOTE]
> Tutti gli aggiornamenti alle **impostazioni dell'app Panels** eseguite tramite il dispositivo sono applicabili solo a quel dispositivo specifico. Questi aggiornamenti non incideranno sugli altri dispositivi dei pannelli dell'organizzazione. Ad esempio, se si modifica l'immagine di sfondo della schermata Home dalle impostazioni **dell'app** Pannelli, l'immagine dello sfondo verrà cambiata solo per quel dispositivo specifico.

### <a name="access-panels-app-settings"></a>Impostazioni dell'app Pannelli di accesso

È possibile accedere **alle impostazioni specifiche dell'app Panels** usando l'opzione **Panels App Impostazioni** sotto le impostazioni di amministrazione. La procedura per accedere **all'app Impostazioni** pannello può variare in base all'OEM del dispositivo.

Per accedere **all'opzione Impostazioni** pannello:

1. Toccare **l'Impostazioni** nella schermata Home.
2. Nella schermata **Impostazioni** toccare **Impostazioni dispositivo**.
3. Toccare **l'icona Impostazioni**.

    > [!NOTE]
    > A seconda dell'OEM del dispositivo, potrebbe essere necessario immettere la password di amministratore del dispositivo ora o dopo il passaggio successivo.

4. Scorrere verso il basso per trovare **l'opzione Impostazioni** pannello. Toccarlo.
5. Toccare il **pulsante Impostazioni'app** Pannelli sullo schermo destro.
    Viene visualizzata la schermata con **le impostazioni dell'app** Pannelli disponibili.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Questa schermata mostra lo schermo con le impostazioni dell'app Pannelli disponibili.":::

    Usare questa schermata per aggiornare le impostazioni **dell'app** Pannelli seguenti per il dispositivo:

    - [Sfondo](#update-the-wallpaper)
    - [Indicatore LED](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Associare un Pannello di Teams a una Microsoft Teams room in Android

Per associare una Pannello di Teams e una Teams room in Android, entrambi i dispositivi devono essere connessi allo stesso account delle risorse.

Nella scheda Pannello di Teams accedere usando le credenziali di amministratore.

1. Passare a **Impostazioni > dispositivo Impostazioni >'app Impostazioni > pannello Impostazioni > Riunioni > dispositivo di associazione.**

2. Un codice a sei cifre verrà visualizzato nella parte Teams Rooms sulla parte anteriore android dello schermo della sala. Immettere il codice nel Teams pannello.  

#### <a name="meeting-check-in-and-room-release"></a>Check-in riunione e rilascio sala

Le impostazioni di check-in e rilascio sala consentono agli utenti di accedere a una riunione nei Teams nella sala che hanno prenotato all'inizio della riunione. Se un utente non archivia entro un periodo di tempo impostato dopo l'ora di inizio della riunione, la sala viene rilasciata e diventa disponibile per la prenotazione da parte di altri utenti.

Quando Teams pannelli sono associati a una sala Microsoft Teams su Android, le notifiche di archiviazione possono essere abilitate per essere visualizzate sullo schermo davanti alla sala quando le riunioni sono in ritardo.

Per abilitare il check-in e il rilascio delle chat room, vedere [Check-in](check-in-and-room-release.md) e rilascio sala Microsoft Teams pannelli.

#### <a name="room-capacity-warning"></a>Avviso relativo alla capacità della sala

Teams pannelli che sono abbinati a una sala Teams su Android può visualizzare un messaggio di avviso quando una sala riunioni ha una capacità superiore o superiore. Per usare questa funzionalità, la Teams room deve avere una fotocamera che supporta il conteggio delle persone. Teams Rooms avvisi sulla capacità della sala di supporto android senza Pannello di Teams.

Gli avvisi relativi alla capacità della sala sono disattivati per impostazione predefinita. Per attivare l'impostazione dal Pannello di Teams, associare prima un Pannello di Teams a una Microsoft Teams [room in Android](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android). Il pannello e la Teams room devono essere connessi allo stesso account delle risorse.

 Quindi, passare a Impostazioni **Impostazioni > dispositivo > impostazioni di amministrazione > impostazioni dell'app Pannello**. Quindi, in **Riunioni**, attivare la **notifica numero max di occupanze delle chat room**.

#### <a name="view-room-equipment"></a>Visualizzare l'attrezzatura della sala

Quando questa funzionalità è attivata, gli utenti finali possono visualizzare le apparecchiature disponibili in uno spazio in un Pannello di Teams.

Questa funzionalità è disattivata per impostazione predefinita e può essere abilitata per ogni dispositivo. Per attivarla, usare [Set-Place](/powershell/module/exchange/set-place?view=exchange-ps) in PowerShell per configurare i nomi visualizzati per `AudioDeviceName`, `DisplayDeviceName``VideoDeviceName`, , `Tags`e `IsWheelChairAccessible`.

In caso contrario, è possibile abilitare questa funzionalità nell'Exchange di amministrazione. Per [altre informazioni, vedere Modificare](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) una risorsa.



#### <a name="update-the-wallpaper"></a>Aggiornare lo sfondo

Modificare l'immagine dello sfondo della schermata Home.

1. [Pannello **di accesso Impostazioni**](#access-panels-app-settings).
2. Toccare **Sfondi**.
3. In **Scegli l'immagine** selezionare un'immagine da impostare come immagine di sfondo della schermata Home. Visualizzare in anteprima l'immagine **selezionata in Sfondo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Questa schermata mostra la schermata delle impostazioni dello sfondo.":::
4. Indietro nella schermata Home e verificare che lo sfondo sia aggiornato.

#### <a name="change-the-busy-state-led-color"></a>Cambiare il colore del LED dello stato occupato

Gli amministratori possono scegliere rosso o viola come colore LED per indicare che l'area riunioni è occupata o riservata. Il colore del LED per indicare che uno spazio disponibile è sempre verde e non può essere modificato.

1. [Pannello **di accesso Impostazioni**](#access-panels-app-settings).
2. Toccare **Led Impostazioni**.
3. In **Scegliere il colore del LED** selezionare il colore desiderato.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Questo screenshot mostra le impostazioni dello stato occupato del colore LED.":::
4. Indietro alla schermata Home e verificare che il colore DEL LED per lo stato occupato sia aggiornato. Se l'area della riunione è attualmente disponibile, provare a pianificare una riunione di prova per verificare la modifica del colore a LED per lo stato occupato.

## <a name="frequently-asked-questions"></a>Domande frequenti

Trovare le risposte alle domande frequenti sui Teams dei pannelli.

**Fino a che punto in futuro è possibile visualizzare i dettagli della pianificazione di un'area riunioni?**  
Nel riquadro **Calendario imminente** (in basso a destra) nella schermata Home è possibile visualizzare i dettagli della pianificazione di uno spazio riunioni per un massimo di 24 ore in futuro a partire dall'ora corrente.

**È possibile prenotare uno spazio per una riunione per un periodo di tempo futuro dal dispositivo Teams pannelli?**  
No, non è possibile prenotare uno spazio riunioni per un periodo futuro dai pannelli. L'ora di inizio è sempre l'ora corrente per una riunione ad hoc pianificata dai pannelli.

**Per quanto tempo è possibile prenotare un'area riunioni disponibile per una riunione ad hoc?**  
È possibile prenotare uno spazio disponibile per la riunione a partire dall'ora corrente fino all'ora pianificata successiva oppure fino a un massimo di 24 ore dall'ora corrente, a seconda di quale sia la data precedente. Ad esempio, se l'ora corrente è 10.00 e l'ora di inizio successiva della riunione è 14.00, è possibile prenotare lo spazio per la riunione dalle 10.00 alle 14.00.
