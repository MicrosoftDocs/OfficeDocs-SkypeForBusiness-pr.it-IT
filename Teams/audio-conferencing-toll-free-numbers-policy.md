---
title: Criteri per i numeri verdi per i servizi di audioconferenza
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: Scopri come i servizi di audioconferenza in Microsoft 365 o Office 365 consentono agli utenti di accedere alle riunioni tramite telefono.
ms.openlocfilehash: 11e1e493db38b5e830b3334f659d23f86b6b56ba
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2022
ms.locfileid: "65017000"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>Impostazioni dei criteri per i servizi di audioconferenza per i numeri verdi e a pagamento

## <a name="teams-audio-conferencing-policy"></a>criteri di audioconferenza di Teams

Usare i criteri per i servizi di audioconferenza per gestire i numeri verdi e a pagamento per i servizi di audioconferenza da visualizzare negli inviti alle riunioni creati dagli utenti all'interno dell'organizzazione. È possibile usare uno dei due criteri creati automaticamente oppure creare e assegnare criteri personalizzati. I due criteri creati automaticamente sono globali (impostazione predefinita a livello di organizzazione) e AllowTollFreeDialinFalse (assegnati a tutti gli utenti esistenti all'interno dell'organizzazione che non sono abilitati per i numeri verdi di accesso esterno). I criteri per i servizi di audioconferenza vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams o tramite [PowerShell](teams-powershell-overview.md).

- L'impostazione per AllowTollFreeDialin non può più essere gestita per un singolo utente tramite Teams'interfaccia di amministrazione o PowerShell. Gli amministratori tenant potranno gestire questa impostazione solo tramite i nuovi criteri per i servizi di audioconferenza.
- I criteri globali non possono essere modificati dall'interfaccia di amministrazione di Teams.

Quando un criterio di audioconferenza di Teams è abilitato nel tenant, nel tenant saranno disponibili due criteri creati automaticamente. I due criteri creati automaticamente e le relative impostazioni predefinite sono:

### <a name="global-org-wide-default"></a>Globale (impostazione predefinita a livello di organizzazione)

In questo criterio il valore di **AllowTollfreedialin** sarà impostato su ON e non ci saranno numeri di telefono definiti nel criterio. Questo sarà il criterio predefinito per tutti gli utenti del tenant che al momento del lancio hanno **AllowTollfreedialin** impostato su **Attivato**.
Poiché i criteri non hanno numeri di telefono definiti, quando gli utenti di questo criterio creano una riunione Teams, i numeri di telefono disponibili nella riunione saranno gli stessi numeri di telefono degli utenti che avevano prima del criterio. Questi numeri di telefono in genere vengono impostati come predefiniti per il paese/sede dell'utente, a meno che non siano stati modificati dall'amministratore del tenant per i singoli utenti.

Ad esempio, se a un utente con sede in Germania erano assegnati numeri verdi e a pagamento germania prima del lancio dei criteri per le audioconferenze, all'utente al momento dell'avvio verranno assegnati i criteri globali e i numeri di telefono che continueranno a visualizzare nell'invito alla riunione saranno gli stessi di prima dell'applicazione dei criteri, ovvero  numeri verdi e a pagamento tedeschi). Un utente finale non vedrà alcuna modifica all'avvio del criterio. Se, tuttavia, un amministratore tenant modifica i criteri globali e include numeri di telefono specifici nei criteri diversi da prima, tutti gli utenti del criterio vedranno solo i numeri di telefono inclusi nei criteri in tutte le riunioni pianificate.

> [!NOTE]
> Se invece di Modificare il criterio globale un amministratore tenant crea un criterio personalizzato e lo applica agli utenti, le impostazioni definite nel criterio personalizzato saranno ciò che gli utenti finali vedranno negli inviti alle riunioni.

Ad esempio, se il criterio personalizzato ha "AllowTollFreeDialinFalse" e non ha numeri di telefono definiti, gli utenti di questo criterio non saranno in grado di avere numeri verdi verdi e poiché non sono definiti numeri di telefono nel criterio il numero di telefono a pagamento che verrà utilizzato negli inviti alle riunioni creati da tali utenti sarà gli stessi numeri di telefono che gli utenti avevano prima del criterio. Questi numeri di telefono in genere vengono impostati come predefiniti per il paese/sede dell'utente, a meno che non siano stati modificati dall'amministratore del tenant per i singoli utenti.

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

In questo criterio il valore di **AllowTollfreedialin** verrà impostato su **Disattivato** e non saranno definiti numeri di telefono nel criterio. Questo sarà il criterio predefinito per tutti gli utenti del tenant che, al momento del lancio, hanno **AllowTollfreedialin** impostato su **Disattivato**.

Poiché i criteri non hanno numeri di telefono definiti, quando gli utenti di questo criterio creano una riunione del team, i numeri di telefono che saranno disponibili nella riunione saranno gli stessi numeri di telefono che avevano gli utenti prima del criterio. Questi numeri di telefono in genere vengono impostati come predefiniti per il paese, l'area geografica o la posizione dell'utente, a meno che non sia stato modificato dall'amministratore del tenant per i singoli utenti.

Ad esempio, se a un utente con sede in Germania era assegnato un numero di telefono a pagamento Germania prima del lancio di un criterio di audioconferenza, all'utente al momento dell'avvio verranno assegnati i criteri "AllowTollfreedialinFalse" e i numeri di telefono che continueranno a visualizzare nell'invito alla riunione saranno gli stessi di prima (vale a dire, il numero a pagamento Germania). Un utente finale non vedrà alcuna modifica all'avvio del criterio. Se, tuttavia, un amministratore tenant modifica il criterio **AllowTollfreedialinFalse** e include numeri di telefono specifici nel criterio, tutti gli utenti dei criteri vedranno solo i numeri di telefono inclusi nei criteri in tutte le riunioni pianificate.

## <a name="create-a-custom-audio-conferencing-policy"></a>Creare criteri personalizzati per i servizi di audioconferenza

Panoramica dei passaggi:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams vai a Riunioni > Audioconferenza.
1. Selezionare Aggiungi.
1. Immettere il nome e la descrizione del criterio. Il nome non può contenere caratteri speciali o più di 64 caratteri.
1. Scegliere le impostazioni desiderate.
1. Selezionare Salva.

Ad esempio, è possibile che un gruppo di utenti abbia regolarmente riunioni con partecipanti provenienti da più paesi. Nel nostro esempio, i partecipanti provengono da Canada, Provider e Singapore e vogliono tutti partecipare alla riunione tramite audioconferenza componendo un numero di telefono. È possibile creare un nuovo criterio personalizzato denominato "Canada Singapore" e selezionare i numeri di telefono di questi tre paesi da includere nel criterio tramite l'opzione **Aggiungi un numero di telefono** e salvare questo criterio. È quindi possibile assegnare questo criterio agli utenti necessari.

In questo modo i numeri di telefono selezionati per Canada, Fruit e Singapore verranno inclusi negli inviti alle riunioni creati dagli utenti di questo criterio.

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>Istruzioni dettagliate sulla creazione di criteri personalizzati basati sull'esempio

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **RiunioniConferenze** >  audio.
2. Selezionare **Aggiungi**.
3. Immettere il nome e la descrizione del criterio. Il nome non può contenere caratteri speciali o più di 64 caratteri.
4. Scegliere se includere o meno i numeri verdi nelle riunioni create dagli utenti di questo criterio. Impostando questa opzione **su Attivato** potrai aggiungere numeri verdi in questo criterio.
5. Seleziona Aggiungi un numero di telefono.
6. Verrà aperto un riquadro a destra dello schermo, contenente la casella **Cerca in base alla posizione** .
7. Immettere Canada e selezionare un numero di telefono canadese nei risultati.
8. Selezionare **Aggiungi**.
9. Ripetere i passaggi 6 e 7 allo stesso modo per cercare e aggiungere numeri di telefono di Singapore e Dio.
10. Seleziona i numeri verdi se hai attivato l'impostazione **Includi numeri verdi nelle riunioni create dagli utenti di questo criterio** nel passaggio 4.
11. Selezionare **Aggiungi** nell'angolo in basso a destra del riquadro. Verranno elencati i numeri di telefono dei tre paesi selezionati.
12. È presente una colonna di classificazione che determina l'ordine in cui i numeri di telefono verranno visualizzati negli inviti alle riunioni creati dagli utenti di questo criterio. Puoi modificare l'ordine selezionando un numero di telefono e spostandolo verso l'alto o verso il basso usando rispettivamente i pulsanti **Sposta su** e **Sposta giù** .
13. Dopo aver inserito i numeri di telefono nell'ordine preferito, seleziona **Salva**.
14. Viene creato il criterio personalizzato denominato "Canada Singapore Singapore".
15. Al termine della creazione, è possibile assegnare questo criterio agli utenti.

## <a name="edit-a-meeting-policy"></a>Modificare un criterio di riunione

È possibile modificare i criteri personalizzati creati. Nota: i criteri globali non possono essere modificati dall'interfaccia di amministrazione di Teams

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **RiunioniConferenze** >  audio.
1. Scegliere il criterio da modificare selezionando a sinistra del nome del criterio e quindi selezionando **Modifica**.
1. Apportare modifiche.
1. Selezionare **Salva**.

> [!NOTE]
> Non è possibile eliminare un criterio a cui sono utenti. Sarà necessario assegnare criteri diversi a tutti gli utenti interessati e quindi eliminare il criterio originale.

## <a name="assign-a-meeting-policy-to-users"></a>Assegnare un criterio riunione agli utenti

> [!IMPORTANT]
> Dopo l'applicazione di un nuovo criterio di audioconferenza a un utente, i numeri di telefono definiti nel criterio saranno disponibili solo nelle nuove riunioni create dall'utente con questo criterio. Tutte le riunioni vecchie e ricorrenti pianificate prima del criterio continueranno a mostrare le impostazioni precedenti, ad esempio un numero a pagamento e un numero verde (se è stato abilitato il numero verde per l'utente). Uno scenario potrebbe essere che un utente abbia attivato **l'opzione Consenti numero verde** e abbia assegnato un numero verde e abbia creato riunioni ricorrenti per il futuro. In questo scenario, se si crea un criterio personalizzato con AllowTollfreeDialIn **disattivato** e lo si applica a questo utente, tutte le nuove riunioni create da questo utente non includeranno numeri verdi, ma le riunioni precedenti e ricorrenti continueranno a mostrare numeri verdi. Quindi, se i chiamanti chiamano questo numero verde per partecipare alla riunione, la chiamata non riuscirà perché il numero verde è ora disabilitato per questo utente a causa dei criteri. Per evitare questo tipo di problemi, è possibile eseguire la migrazione delle riunioni precedenti degli utenti dopo aver assegnato loro i nuovi criteri per le audioconferenze. Consultare [Uso del servizio MMS (Meeting Migration Service).](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

È possibile assegnare un criterio direttamente agli utenti o a un gruppo di cui gli utenti sono membri (se supportato per il tipo di criterio), singolarmente o in numeri più grandi tramite un'assegnazione batch (se supportata per il tipo di criterio).

Per informazioni sui diversi modi in cui è possibile assegnare criteri agli utenti, vedere [Assegnare criteri a utenti e gruppi](assign-policies-users-and-groups.md).

> [!NOTE]
> A un utente può essere assegnato un solo criterio di audioconferenza alla volta.

### <a name="known-issue"></a>Problema noto

Quando si avvia una riunione usando l'opzione **Riunione immediata** da Microsoft Teams > Calendario > Riunione immediata, se si selezionano i puntini di sospensione ... e quindi Info riunione, si verifica un problema con la parte inferiore della sezione **in Chiamata in (solo audio).** Verranno visualizzati tutti i numeri di telefono definiti nel criterio, ma l'allineamento dei numeri rende difficile la lettura.
