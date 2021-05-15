---
title: Dati di diagnostica necessari per dispositivo mobile di Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Elenco delle proprietà e degli eventi per dispositivo mobile per i controlli dei criteri di Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c54a38a547708b78f652096cdad577088283c5b
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469648"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Dati di diagnostica necessari per dispositivo mobile di Microsoft Teams

Questo articolo contiene un elenco degli eventi per dispositivo mobile di Microsoft Teams e gli elenchi delle proprietà raccolte da ciascun evento.

## <a name="events"></a>Eventi

> [!NOTE]
> Ci sono proprietà comuni per tutti gli eventi elencati di seguito. Per rivederle, vedere [Proprietà inviate per tutti gli eventi](#properties-sent-with-all-events).

### <a name="panelaction"></a>PanelAction

> [!NOTE]
> Per informazioni sulle proprietà degli eventiPanelAction, vedere [Proprietà inviate con gli eventi panelaction](#properties-sent-with-panelaction-events).

- **accessibilityUserConfiguration**: quando un utente attiva o disattiva una funzionalità di accessibilità.
- **acknowledgeSettingChange**: conferma un aggiornamento nella finestra di dialogo abbiamo aggiornato un'impostazione di notifica. Questa è una metrica di successo della funzionalità usata per confermare le notifiche di aggiornamento e per determinare l'affidabilità complessiva delle notifiche.
- **actionComposeMenu**
  - Utilizzo dell’estensione creazione messaggio.
  - Utilizzo dell'estensione messaggio d’azione.
- **active_session_banner_dismissed**: il banner di promemoria attivo per la condivisione della posizione è stato eliminato.
- **activityChatClicked**: si attiva quando viene selezionata una chat non live nella scheda **Attività** o viene mostrata una Doppia visualizzazione.
- **activityContextMenu**: azioni di overflow nel feed attività.
- **activityFeedClick**: viene toccato un elemento del feed attività e ci si sposta in chatbot.
- **activityFeedLongPress**: acquisisce gesti di pressione prolungati sugli elementi del feed.
- **activityFeedSwipe**: acquisisce i gesti di scorrimento sugli elementi del feed.
- **activityFilterClick**: acquisisce l'utilizzo del filtro attività.
- **activityFilterOptionsClick**: acquisisce l'utilizzo del filtro attività.
- **activityFilterOptionsClicked**: acquisisce l'utilizzo del filtro attività.
- **activityLiveChatClicked**: si attiva quando la chat viene selezionata da una riunione live nella scheda **Attività**.
- **activityLiveDetailsClicked**: si attiva quando si seleziona **Dettagli** da una riunione live nella scheda **Attività**.
- **activityTabClicked** consente di determinare se:
  - viene visualizzata la scheda **Attività**.
  - Teams acquisisce un evento della scheda **Attività**.
- **activityTypeDropdown**: acquisisce l'utilizzo del filtro attività per passare da **Le mie attività** a **Feed**.
- **addChannel**: aggiunta di un canale. Questo elemento fornisce dati sulla creazione corretta di un canale.
- **addMember**: si attiva quando il pulsante **Invita persone** è selezionato nel menu **Altro**.
- **addMembers**: aggiunge membri a un team o a un canale privato.
- **addToCalendar**: seleziona il pulsante **Aggiungi al calendario** per gli eventi del calendario mancanti nel calendario privato.
- **addToList**: un contatto viene aggiunto a un elenco di contatti.
- **addToMeeting**: seleziona il pulsante **Aggiungi alla riunione** nell'elenco dei partecipanti per una riunione, per i partecipanti che fanno parte della chat.
- **addUserAsContact**: è possibile aggiungere un contatto selezionando l'icona **Aggiungi contatto** dalla scheda del profilo del contatto.
- **admitAll**: il numero di volte in cui il pulsante **Ammetti tutti** è selezionato dalla sala di attesa.
- **admitParticipant**: il numero di volte in cui una persona è ammessa a una riunione dall'elenco dei partecipanti alla riunione.
- **alertsNavAlert**: toccare un elemento del feed.
- **Android: null**: attiva o disattiva l'audio di una chatbot. Questo migliora l’esistente telemetria delle chat e aggiunge solo le informazioni sull'applicazione.
- **anonymousMeetingJoin** - **Partecipa a una riunione** è selezionato in una pagina di aggiunta anonima nella quale si deve fornire un nome, oppure viene selezionato **OK** nella finestra di dialogo nome.
- **anonymousMeetingJoinWelcome** - **Partecipa come ospite** è selezionato in una pagina di destinazione anonima di una riunione.
- **anonymousMeetingPostMeetingChat**: il numero di visualizzazioni utente della chat dalla schermata di fine chiamata.
- **anonymousMeetingPostMeetingRejoin**: il numero di volte in cui un utente anonimo tenta partecipare di nuovo a una riunione.
- **anonymousMeetingSignIn**: il numero di volte in cui un utente è passato nella schermata di accesso dalla schermata di input del nome.
- **anonymousMeetingJoinWelcome**: l’opzione **Accedi e partecipa** è selezionata in una pagina di destinazione anonima di una riunione.
- **anonymousMeetingToggleMuted**: il numero di volte in cui è stato selezionato l’interruttore per disattivare l'audio.
- **anonymousMeetingToggleVideo**: il numero di volte in cui è stato selezionato l’interruttore per il video.
- **appKilled**: l'applicazione viene chiusa.
- **approveTimeOffRequest**: quando un manager di un operatore sul campo approva una richiesta di permesso di un operatore sul campo.
- **assigneeChange**: si attiva quando un nuovo assegnatario viene aggiunto a un elemento dell'attività.
- **assignmentPickerClicked**: il pulsante **Assegna a** è selezionato, aprendo la pagina di selezione di un assegnatario.
- **assignmentRemoved**: si attiva quando un assegnatario viene rimosso da un elemento dell'attività selezionando la **x** (che è l'unico modo per rimuovere un assegnatario).
- **attachmentAdded**: conferma che è stato aggiunto un allegato in un'attività.
- **attachmentDeleted**: conferma che è stato eliminato un allegato in un'attività.
- **attachmentUpdated**: conferma che è stato aggiornato un allegato in un'attività.
- **audioOnlyLowBatteryBanner**: l'opzione **Solo audio** è selezionata a causa di un banner di notifica di batteria scarica.
- **audioOnlyPoorNetworkBanner**: l'opzione **Video disattivato** è selezionata a causa di un banner di notifica di connessione scadente.
- **audioUserDoubleTap**: effettuare un doppio tocco sull’audio di un partecipante.
- **autoReconnectCallmebackCallDrop**: il numero di volte in cui è stato selezionato il pulsante **Richiamami** in una schermata di fine chiamata.
- **autoReconnectDialIn**
  - Il pulsante **Componi numero** è selezionato nell'UFD di riconnessione.
  - Il numero di volte in cui è stato selezionato il pulsate **Componi numero** nel corso di una di una riconnessione.
- **autoReconnectDialInonCallDrop**: il pulsante **Componi numero** viene selezionato sull'UFD di disconnessione dalla chiamata.
- **autoReconnectDialOut**: il pulsante **Richiamami** è selezionato nell'UFD di riconnessione.
- **autoReconnectRejoinonCallDrop**: il numero di volte in cui è stato selezionato il pulsante **Torna a partecipare** o **Ricomponi** nella schermata di fine chiamata.
- **backFromCallMePSTN**. Il flusso del numero PSTN di richiamata non è stato completato.
- **backToPhotoShare**: ritornare a una fotocamera.
- **backToStageFromWhiteboard**: ritornare a una schermata di chiamate da una lavagna.
- **backToWhiteboardFromStage**: passare a una lavagna da una schermata di chiamata.
- **blockAnonymous** quando:
  - abilita le impostazioni chiamate di bloccare le chiamate senza l'ID del chiamante dalle impostazioni.
  - disabilita le impostazioni chiamate di bloccare le chiamate senza l'ID del chiamante dalle impostazioni.
  - abilita le impostazioni chiamate di bloccare le chiamate senza l'ID del chiamante dal foglio di azione.
  - disabilita le impostazioni chiamate di bloccare le chiamate senza l'ID del chiamante dal foglio di azione.
- **blockCaller** blocca:
  - un numero e un contatto dal nuovo foglio di azione chiamate di iOS.
  - un contatto e un numero dalla scheda contatto.
  - numeri dalle impostazioni.
- **blockChat**: blocco di una chatbot. Questo migliora l’esistente telemetria delle chat e aggiunge solo le informazioni sull'applicazione.
- **botClickCardAction**: utilizzo della scheda del connettore.
- **brbFeedback**: relativa alle prestazioni del modulo di feedback BRB.
- **brbFormCancelled**: un evento inviato quando il modulo di feedback BRB viene annullato e l'utente torna all'app.
- **brbFormOpened**: un evento inviato all'apertura del modulo BRB.
- **brbFormSubmit**: un evento inviato quando l'utente seleziona **Invia** nel modulo di feedback.
- **breakStartEndClicked**: nella schermata di registrazione dell’orario in entrata, il pulsate **Inizia** o **Termina pausa** viene selezionato.
- **breakStartEndTriggered**: registra le scelte dell’utente sull’utilizzo di inizio o fine pausa.
- **bucketSelected**: conferma che un contenitore è stato selezionato.
- **bucketUnselected**: conferma che un contenitore è stato deselezionato.
- **bucketPickerClicked**: conferma che il selettore di contenitori è stato avviato correttamente.
- **BYOELiveEventJoin**: un utente si unisce a un evento live BYOE (trasmetti il tuo evento).
- **calendarLiveChatClicked**: chat dalla riunione live nella scheda **Pianificazione**.
- **calendarMeetingJoin** - Il pulsante **Partecipa riunione** selezionato da un calendario.
- **calendarTab**: selezionare la scheda **Riunioni** nella barra di scorrimento in basso. È utile per comprendere l'uso del calendario e confrontarlo con altre app sulla barra di scorrimento, o determinare se si è verificato un errore durante il rendering del post del calendario dopo aver selezionato la barra di scorrimento.
- **calendarTabClicked**: nelle circostanze elencate di seguito, questo mostrerà l'uso del calendario e consentirà di confrontarlo con altre app della barra di spostamento nella barra di scorrimento inferiore. È possibile usare questa funzione per determinare se si è verificato un errore quando:
  - viene mostrata la scheda **Pianifica**.
  - la barra **Riunioni** viene selezionata nella barra di scorrimento inferiore.
- **calendarUpcomingChatClicked**: chat da una riunione imminente nella scheda **Pianificazione**.
- **callAccepted**: chiamata accettata.
- **callAcceptedSFB**: chiamata accettata.
- **callAppPreference**: viene selezionata un'app di chiamata preferita.
- **callControlsManualDismiss**: i controlli chiamata vengono ignorati manualmente.
- **callControlsManualInvoke**: i controlli chiamata vengono richiamati manualmente.
- **callHistoryItemExpand**: elemento della cronologia chiamate espanso.
- **callHistoryTab** -  la scheda **CallHistory** viene selezionata in Chiamate.
- **callInProgressShown**: viene mostrato il banner di notifica **_Chiamata in corso_*.
- **callMePSTNConnected** - **Chiamami** è andato a buon fine.
- **callOrMeetUpAddParticipants** si attiva quando:
  - si tocca il pulsante Aggiungi partecipante sulla schermata di una chiamata 1:1.
  - si seleziona una persona (VoIP) in Aggiungi partecipanti.
  - si seleziona PSTN in Aggiungi partecipanti.
  - si aggiungono persone in una riunione privata live.
  - si seleziona un PSTN in una riunione privata live.
  - si seleziona un contatto aziendale in una riunione privata live.
  - si seleziona un contatto del dispositivo in una riunione privata live.
  - i partecipanti sono stati aggiunti in una riunione privata live.
  - su aggiungi persone in una riunione di canale live.
  - si seleziona un PSTN in una riunione di canale live.
  - si seleziona membri del team in una riunione di canale live.
  - si seleziona un contatto del dispositivo in una riunione di canale live.
  - i partecipanti sono stati aggiunti in una riunione di canale live.
- **callOrMeetUpAddParticipantsDone**: un utente finalizza l'aggiunta dei partecipante.
- **callOrMeetUpAddRoom** si attiva quando:
  - viene selezionato **Aggiungi gruppo di lavoro** in un elenco partecipanti.
  - viene selezionato un risultato di ricerca in Aggiungi gruppo di lavoro.
  - viene selezionato **Ignora** al posto di Nelle vicinanze.
  - viene selezionato **Abilita BT** o **Posizione** al posto di Nelle Vicinanze.
  - viene selezionato un risultato di una stanza nelle vicinanze in Aggiungi gruppo di lavoro.
  - viene selezionato un risultato di una stanza consigliata in Aggiungi gruppo di lavoro.
  - viene selezionato **Fatto** in Aggiungi gruppo di lavoro.
- **callOrMeetUpAudioOffSwitch**: inverte il pulsante **Audio disattivato** durante la partecipazione nella modalità companion in una chiamata live o una riunione.
- **callOrMeetUpAutoReconnect**: le scarse prestazioni di rete fanno entrare il dispositivo di un utente in modalità Autoreconnect.
- **callOrMeetUpCallAccepted** si attiva quando:
  - È stata accettata una chiamata.
  - È stata accettata una chiamata PSTN.
- **callOrMeetUpCallended** si attiva quando:
  - viene premuto il pulsante **Termina chiamata**.
  - viene premuto il pulsante **Chiamata terminata** durante callOrMeetupLive.
  - viene premuto il pulsante **Chiamata terminata** durate la schermata di blocco.
  - viene premuto il pulsante **Chiamata terminata** durate una notifica.
  - viene premuto il pulsante **Chiamata terminata** mentre si è all’interno dell’app.
  - viene premuto il pulsante **Chiamata terminata** mentre si è in callKit.
  - viene premuto il pulsante **Chiamata terminata** per il PSTN.
- **callOrMeetUpChatWithParticipants**: interruttore chat durante una riunione live o una chiamata.
- **callOrMeetUpDeviceAudioSwitch** si attiva quando:
  - cambia la sorgente audio all’altoparlante.
  - cambia la sorgente audio al dispositivo.
  - cambia la sorgente audio al Bluetooth.
  - cambia la sorgente audio disattivando l’audio.
  - cambia l’altoparlante durante una riunione live o una chiamata.
  - viene disattivato l’audio dell’altoparlante durante una riunione live o una chiamata.
  - si inverte il pulsante **Audio disattivato** durante la partecipazione nella modalità companion in una chiamata live o una riunione.
  - il dispositivo audio cambia mentre si è in PSTN.
- **callOrMeetUpEnterDriveMode**: passa manualmente da modalità guida dal menu **...**.
- **callOrMeetupExitDriveMode** - viene premuto il pulsante **Esci dalla modalità guida**.
- **callOrMeetUpAddRoom** si attiva quando:
  - si tocca il pulsante **In attesa** durante una riunione live o una chiamata.
  - la chiamata è in attesa in PSTN.
- **callOrMeetUpIncomingVideoSwitch**: disattiva IncomingVideo durante una riunione live o una chiamata.
- **callOrMeetUpInvitedParticipants** si attiva quando:
  - si fa clic su **Vedi tutti** nella parte inferiore dell’opzione **Altri invitati** di un gruppo di partecipanti durante una riunione privata live.
  - si fa clic su **Vedi tutti** nella parte inferiore dell’opzione **Altri invitati** di un gruppo di partecipanti durante una riunione di canale live.
- **callOrMeetUpJoinedParticipants** si attiva quando:
  - si fa clic su **Vedi tutti** nella parte inferiore dell’opzione **Nella riunione** di un gruppo di partecipanti durante una riunione privata live.
  - si fa clic su **Vedi tutti** nella parte inferiore dell’opzione **Nella riunione** di un gruppo di partecipanti durante una riunione di canale live.
- **callOrMeetUpLobbyParticipants** si attiva quando:
  - si fa clic su **Vedi tutti** nella parte inferiore dell’opzione **Sala di attesa** di un gruppo di partecipanti durante una riunione privata live.
  - si fa clic su **Vedi tutti** nella parte inferiore dell’opzione **Sala di attesa** di un gruppo di partecipanti durante una riunione di canale live.
- **callOrMeetUpMicrophoneSwitch** si attiva quando:
  - si accende il microfono.
  - si spegne il microfono.
  - si seleziona il pulsante **Microfono** durante una riunione live o una chiamata.
  - si cambia il microfono mentre si è in PSTN.
- **callOrMeetUpMuteParticipant**: viene disattivato l’audio di un partecipante da remoto.
- **callOrMeetUpMuteParticipants**: viene disattivato l'audio di tutti i partecipanti durante una riunione live o una chiamata.
- **callOrMeetUpMuteParticipants**: si alternano i partecipanti durante una riunione live o una chiamata.
- **callOrMeetUpRemoteMuteUFD**: è stato disattivato l’audio per UFD.
- **callOrMeetUpResume** si attiva quando:
  - si seleziona il pulsante **Riprendi** durante una riunione live o una chiamata.
  - si riprende una chiamata in PSTN.
- **callOrMeetUpSearchParticipants** si attiva quando:
  - si fa clic su **Cerca** nei partecipanti alla riunione durante una riunione live privata.
  - si fa clic su **Cerca** dopo aver visualizzato il gruppo di partecipanti nella **Sala di attesa** durante una riunione privata.
  - si fa clic su **Cerca** dopo aver visualizzato il gruppo di partecipanti nell’opzione **Nella riunione** durante una riunione privata.
  - si fa clic su **Cerca** dopo aver visualizzato il gruppo di partecipanti nell’opzione **Altri invitati** durante una riunione privata.
  - si fa clic su **Cerca** nei partecipanti alla riunione durante una riunione di canale live.
  - si fa clic su **Cerca** dopo aver visualizzato il gruppo di partecipanti nella **Sala di attesa** durante una riunione di canale live.
  - si fa clic su **Cerca** dopo aver visualizzato il gruppo di partecipanti nell’opzione **Nella riunione** durante una riunione di canale live.
  - si fa clic su **Cerca** dopo aver visualizzato il gruppo di partecipanti nell’opzione **Altri invitati** durante una riunione di canale live.
- **callOrMeetUpVideoSwitch** si attiva quando:
  - si attiva il video.
  - si disattiva il video.
  - viene selezionato il pulsante Video durante una riunione live o una chiamata.
- **callPark** si attiva quando:
  - viene selezionato **Parcheggia chiamata** nel menu **...**.
  - viene selezionato il pulsante **Riprendi**.
  - viene selezionato **Rispondi** nella finestra di dialogo Riprendi.
  - viene selezionato **Annulla** nella finestra di dialogo Riprendi.
- **callPreferenceSetting**: impostazione preferenze di chiamata dell'app.
- **callsTabNewCall** - viene selezionato **Nuova chiamata** nella scheda **Chiamate**.
- **callTransfer**: viene avviato un trasferimento di chiamata.
- **callVoicemailTab** - viene selezionata la scheda **messaggio vocale** in Chiamate.
- **cameraPermissionCancel** - viene selezionato **Annulla** nella finestra di dialogo di autorizzazione della fotocamera.
- **cameraPermissionGoToSettings** - si accede alle **Impostazioni** dalla finestra di dialogo delle autorizzazioni della fotocamera.
- **cancelEditMeeting**: viene selezionato il pulsante **Chiudi** nella pagina di pianificazione delle riunioni, dopo aver selezionato **Modifica riunione**. Registra quando un utente abbandona la selezione Modifica riunione.
- **cancelFileShare** - viene selezionato **Annulla** nella finestra di dialogo di conferma.
- **cancelFileUpload** - viene selezionato **x** nella finestra di dialogo di caricamento.
- **cancelMeeting**: viene selezionato **Annulla evento** dalla pagina dei dettagli della riunione. Viene usato per ottenere dati aggregati sul numero di riunioni annullate.
- **cancelNavigationToLink**: è stato scelto Annulla Spostamento.
- **cancelRequestToJoinTeam**: annulla la richiesta di partecipazione a un team.
- **cancelRequestToJoinTeamError**: errore di annullamento della richiesta di partecipazione.
- **cancelNewMeeting** per registrare le selezioni abbandonate di Crea riunioni e verificare quali sono le cause quando:
  - viene selezionato il pulsante **Chiudi** nella pagina programmazione riunioni.
  - viene selezionato il pulsante **Chiudi** nella pagina programmazione riunioni dopo aver selezionato **Modifica riunione**.
- **cardView - Nessun AS assegnato**: visualizzazione scheda e rendering della scheda. Le schede sono costrutti chiave della piattaforma e misurare il loro utilizzo e modello è necessario per comprendere l'uso della piattaforma e tenere d'occhio potenziali problemi dal lato client. Questo elemento è necessario per misurare qualsiasi errore con l'aggiunta di un team.
- **castPpt** l’evento si genera quando:
  - viene selezionata un’opzione di PowerPoint.
  - viene selezionato uno specifico PowerPoint.
  - vengono selezionate le cartelle di Teams e Canali nella pagina Seleziona file.
  - viene selezionata una cartella di OneDrive nella pagina Seleziona file.
  - viene interrotta la sessione di trasmissione.
  - si tocca sul PiP multitasking.
  - viene selezionata un'opzione di visualizzazione da visualizzazione file.
- **castScreen** fa riferimento a:
  - toccare l'opzione Condividi schermata.
  - interrompere l'opzione Condividi schermata.
  - selezionare l'opzione Condividi schermata.
- **center_on_team_clicked**: un utente allineare al centro la mappa sui gruppi.
- **channelFollow**: attiva le notifiche per un canale.
- **channelUnfollow**: diattiva le notifiche per un canale.
- **channelsActiveSetting**: modifica le impostazioni di notifica di **Avvisami quando sono attivo sul desktop**.
- **chatCreation**: creazione chat riuscita.
- **changeIsActiveSetting**: modifica le notifiche basate sull'attività del desktop.
- **Canale**: pulsante Nuovo messaggio o casella di testo nella chat.
- **channelDetails** informazioni di spostamento nel canale quando:
  - viene selezionata un'intestazione di canale.
  - si accede alla pagina dei dettagli del canale.
- **channelFollow/channelUnfollow**: seguire o non seguire più un canale.
- **channelNav**: accesso a un canale ovunque ci si trovi.
- **channelNavTab**: fornisce dati su successo e reperibilità per i file in Teams quando:
  - viene selezionata la scheda **File** nel canale.
  - c’è una risposta della scheda connettore.
- **channelNotificationSettings** si attiva quando:
  - viene selezionata la finestra di dialogo **Nuove impostazioni di notifica**.
  - viene selezionato il pulsante Impostazioni di notifica canali in visualizzazione canale.
  - viene selezionata l’impostazione notifica canale.
- **channelSelected**: conferma che un canale è stato selezionato per un nuovo piano.
- **channelSendMessage** si attiva quando:
  - viene inviato un messaggio di canale.
  - un bot viene @menzionato in una casella di composizione.
- **channelTabOverflow**: seleziona la scheda **Altro** in un canale.
- **chat** si riferisce a:
  - un pulsante Nuovo messaggio o casella di testo nella chat.
  - una chat tra due persone o un elemento callHistory.
  - una selezione di chat tra due persone da un elenco chiamate.
- **chat - Nessun AS assegnato** visualizzazione della chat non letta o modifica dell'elenco delle chat, in particolare:
  - selezionando il pulsante **Fatto** quando si aggiunge un utente a una chat.
  - viene selezionato un filtro dell'elenco chat, per filtrare per non letti.
- **chatAddChat**: toccare il pulsante Aggiungi un membro alla chat (sarà lo stesso per la chat tra due persone e la chat di gruppo).
- **chatAllowJoinViaLink**: attiva o disattiva le funzionalità del collegamento Partecipa nella pagina Dettagli chat.
- **chatAvatarEdit**: tiene traccia del numero di gruppi che cambiano il loro avatar dalla pagina Dettagli della chat.
- **chatAvatarEditCamera**: si attiva quando un utente modifica l'avatar da un feed live di una videocamera.
- **chatAvatarEditCamera**: si attiva quando un utente modifica l'avatar da un feed live dalla galleria del telefono.
- **chatAvatarEditView**: si attiva quando un utente visualizza l'immagine avatar esistente.
- **chatListNavConversations**: quando un utente tocca un elemento dell'elenco chat.
- **chatCancelAudioCall**: annulla la finestra di dialogo Annulla una chiamata audio di gruppo.
- **chatCancelVideoCall**: annullare la finestra di dialogo Annulla una chiamata video di gruppo.
- **chatCM_CopyText**: tocca **Copia testo** nel menu di scelta rapida della chat.
- **chatCM_DeleteMessage**: tocca **Elimina messaggio** nel menu di scelta rapida della chat.
- **chatCM_edit**: tocca **Modifica** nel menu di scelta rapida della chat.
- **chatCM_Forward**: tocca **Inoltra** nel menu di scelta rapida della chat.
- **chatCM_Forward**: tocca **Segna come da leggere** nel menu di scelta rapida della chat.
- **chatCM_save**: tocca **Salva** nel menu di scelta rapida della chat.
- **chatCM_SeenBy**: tocca **Visto** nel menu di scelta rapida della chat. Conferme di lettura, ad esempio letto da (readby).
- **chatContactsEnter**: viene immessa la scheda **Contatti chat**.
- **chatDetails** fornisce dati su successo e reperebilità per una pagina dei dettagli della chat quando:
  - viene selezionata un'intestazione di chat.
  - si accede a una pagina di dettagli della chat.
- **chatRecentEnter**: viene immessa la scheda **Chat recenti**.
- **chatSendMessage**: invia un messaggio chat.
- **chatShareLink**: tiene traccia del numero di utenti che inviano un collegamento di invito al gruppo.
- **chatStartAudioCall** viene attivato quando:
  - viene toccato il pulsante di chiamata audio 1:1.
  - viene toccato il pulsante **Audio** nei risultati della ricerca.
  - viene toccato il pulsante sulla destra **Avvia chiamata**.
  - viene toccato chiamata audio 1:1 da un elemento di callHistory.
  - viene toccato chiamata audio 1:1 da un elemento della segreteria telefonica.
  - viene inserita una finestra di dialogo di conferma di una chiamata audio di gruppo.
- **chatStartAudioCallOnBehalfOf**: un delegato avvia una chiamata da un foglio di azione come Capo.
- **chatStartAudioCallOnBehalfOfMyself**: un delegato avvia una chiamata da un foglio di azione come Io.
- **chatStartAudioCallSFB**: viene selezionato il pulsante chiamata audio 1:1.
- **chatStartVideoCall** viene attivato quando:
  - viene toccato il pulsante Chiamata video 1:1.
  - viene toccato il pulsante Video nei risultati di ricerca.
  - viene toccato chiamata video 1:1 da un elemento di callHistory.
  - viene inserita una finestra di dialogo di conferma di una chiamata video di gruppo.
- **chatStartVideoCallSFB**: viene selezionato il pulsante chiamata video 1:1.
- **chatWithMeetingParticipants**: seleziona la scheda **Chat** dalla pagina Dettagli riunione.
- **checkListAddClicked** -  viene selezionato **Aggiungi un elemento** nella visualizzazione dei dettagli dell'attività per la sezione Elenco di controllo.
- **checkListItemAdded**: viene creata una voce di elenco di controllo per un'attività.
- **checkListItemDeleted**: viene eliminata una voce di elenco di controllo per un'attività.
- **checkListItemUpdated**: viene aggiornata una voce di elenco di controllo per un'attività.
- **channelPickerClicked**: conferma che il selettore di canali è stato avviato correttamente.
- **checklistSeeAllClicked**: quando viene selezionato il pulsante **Visualizza tutto** all'interno dei dettagli dell'attività per visualizzare tutti gli elementi dell'elenco di controllo.
- **chicletExpand**: permette di comprendere come le schede vengono visualizzate in anteprima sui dispositivi mobili e il comportamento di chiusura dell'anteprima.
- **clearFilter**: quando tutti i filtri vengono deselezionati durante la visualizzazione di un elenco di attività.
- **clickPhotoOfficeLens**: selezionare **Scatta foto** - Avvia fotocamera (solo per Android).
- **clockInEntryTeamSelectionShown**: un utente seleziona un team per il marcatempo senza aver registrato l’orario di entrata.
- **clockInOutClicked**: nella schermata di registrazione di orario di uscita, viene selezionato il pulsante **Registra entrata** o **Registra uscita**.
- **clockInOutTriggered**: registra l’entrata e l’uscita di un utente. Questo non si attiverà finché non sarà controllata la posizione, supponendo che sia richiesta.
- **closedBannerMessage**: viene attivato alla chiusura del messaggio banner di una notifica.
- **closeLobbyBanner**: numero di volte in cui l’avviso popup delle sala di attesa viene chiuso usando il pulsante **Chiudi**.
- **commentAdded**: conferma che è stato aggiunto un commento a un'attività.
- **commentsClicked**: conferma che la visualizzazione commenti è stata avviata correttamente.
- **commentUpdated**: conferma che è stato aggiornato un commento in un'attività.
- **companionBannerJoin**: selezionare **Partecipa** nel banner principale.
- **companionDismiss**: ignorare il banner complementario.
- **companionDismissProximity**: ignorare il banner complementario.
- **companionJoin**: viene selezionata l’opzione dal foglio Partecipare con dispositivo complementare.
- **companionJoinProximity**: aggiunto attraverso il banner complementario.
- **completionStateChange**: si attiva quando un interruttore del filtro completato o incompleto viene selezionato nella visualizzazione del filtro dall'elenco delle attività.
- **composeExpandComposer** -  viene toccato il pulsante **Formato**.
- **composeFilePick**: selezione file nativo avviata.
- **composeImagePicker** -  viene toccato il pulsante **Immagine**.
- **composeLocation** -  viene toccato il pulsante **Posizione**.
- **composeMention** - @menzione.
- **composeOpenEmoticonPicker**: viene toccata la selezione emoticon.
- **composeOpenFunPicker**: viene toccata la selezione Divertimenti.
- **composeParticipantAdded**: quando si aggiunge un partecipante all'app Turni.
- **composeSearchResult**: selezione del risultato dell'estensione messaggio, utile per comprendere la pertinenza dei risultati di ricerca dell'app. Inoltre, migliora la telemetria di invio dei messaggi con i dati dell'app.
- **composeSelectExtension**: toccare un’app ME.
- **composeSendSmartReply**: si fa clic su un elemento di risposta intelligente.
- **composeSendMessage**: migliora la telemetria di invio dei messaggi con i dati dell'app.
- **confirmAudioOn**: un utente conferma che vuole attivare l'audio.
- **confirmlFileShare** - viene selezionato **Condividi** nella finestra di dialogo di conferma.
- **consultTransfer** si attiva quando:
  - si seleziona **Trasferisci** > **Consulta prima**
  - la destinazione di trasferimento è impostata su Persona.
  - la destinazione di trasferimento è impostata su Numero di telefono.
- **consultTransferCall** si attiva quando:
  - viene avviata una chiamata di consultazione.
  - conferma è selezionato nella finestra di dialogo di conferma del trasferimento.
  - annulla è selezionato nella finestra di dialogo di conferma del trasferimento.
  - Viene selezionato il pulsante **Trasferimento banner**.
  - Viene selezionato il pulsante **Ripristino banner**.
- **consultTransferChat** si attiva quando:
  - viene avviata una chat di consultazione.
  - conferma è selezionato nella finestra di dialogo di conferma del trasferimento.
  - conferma è selezionato nella finestra di dialogo di conferma del trasferimento.
  - è selezionato il pulsante **Trasferimento banner** o **Ripristino banner**.
- **consumeVoiceMessage**: viene riprodotto un messaggio vocale.
- **ContactCard_SeeMoreOOF**: visualizzare di più su un lungo messaggio OOF.
- **contactOrganizer**: viene selezionato **Contatta organizzatore**.
- **conversazione, schede**: scheda selezionata.
- **copyLink**: copia un collegamento a un post di canale.
- **contactActivity**: quando viene selezionato il pulsante per visualizzare l'attività di un utente dalla scheda contatto.
- **conversazione**: quando un utente accede alla scheda **Chat** o **Post**.
- **createChannel** fornisce dati di successo sulla creazione o sull'azione di scarto per la creazione di un nuovo canale, quando:
  - il pulsante **Fatto** viene selezionato nella pagina **Crea canale**.
  - il pulsante **Annulla** viene selezionato nella pagina **Crea canale**.
- **createComposeExtension**: crea l'utilizzo dell'estensione messaggio o l'azione ME.
- **createConversationClicked**: quando si crea una conversazione con altri dipendenti.
- **createDefaultPlannerPlan**: un elenco condiviso viene creato automaticamente quando l'app Attività viene aperta per la prima volta da chiunque in quel gruppo, controlla l'elenco automatico creato con il servizio Planner. Conferma che l'elenco delle attività condivise predefinito è stato creato correttamente in Planner la prima volta che un utente tenta di creare un elenco di attività condivise.
- **createOrJoinTeam**: viene selezionato il pulsante **+** per creare o unirsi a un team.
- **createPersonalPlan**: viene creato un elenco personale, che consente di controllare l'elenco creato con il servizio ToDo. Conferma la creazione di un nuovo elenco attività personale in ToDo.
- **createPersonalSubtask**: conferma che è stata creata correttamente una sottoattività personale.
- **createPersonalTask**: conferma che è stata creata correttamente un’attività personale.
- **createPlan**: conferma che un elenco attività condiviso è stato creato correttamente. Conferma che un piano condiviso è stato creato con successo tramite il livello intermedio.
- **createPlannerPlan**: viene creato un elenco condiviso, che controlla l'elenco creato con il servizio Planner. Conferma la creazione di un nuovo elenco attività condiviso in Planner.
- **createPlannerTask**: verifica una chiamata al servizio Planner. Conferma che un'attività è stata creata correttamente in un elenco di attività condivise.
- **createShiftClicked**: quando un manager seleziona **Crea un turno**.
- **createShiftOrTimeOffClicked**: si attiva se si seleziona **Crea un turno** oppure **Permesso**.
- **createTask**: viene usato quando l'azione di creazione non riesce, controlla la chiamata al servizio Planner. Conferma che un'operazione di creazione dell'attività non è riuscita.
- **createTaskList**: quando un utente accede alla visualizzazione Crea piano dalla visualizzazione Home.
- **createTeam** fornisce dati di successo sulla creazione o sull'azione di scarto per la creazione di un nuovo team, quando:
  - il pulsante **Fatto** viene selezionato nella pagina **Crea team**.
  - il pulsante **Annulla** viene selezionato nella pagina **Crea team**.
- **createTeam, createChannel** fornisce i dati relativi all'aggiunta con successo di membri in un team e la creazione con successo di un nuovo team quando:
  - viene selezionato il pulsante **Ignora** nella pagina **Aggiungi membri** (verificare quelli già esistenti).
  - viene selezionato il pulsante **Fatto** nella pagina **Aggiungi membri** (verificare quelli già esistenti).
  - mostra il riconoscimento della creazione del team o del canale.
- **crossCloudDialogCancel** -  viene selezionato **Annulla** per la finestra di dialogo tra cloud.
- **crossCloudDialogJoin** -  viene selezionato **Partecipa come guest** per la finestra di dialogo tra cloud.
- **dashboardNav**: un utente passa a una sezione nel dashboard della chat.
- **dateChanged**: un utente ha modificato una data del turno.
- **datePickerLaunch**: conferma che la selezione data è stata avviata correttamente.
- **dayClicked**: selezionare la visualizzazione giorno quando gli utenti vedono il loro turno.
- **daySaved**: un utente salva la disponibilità e i turni del giorno.
- **declineTimeOffRequest**: quando un utente rifiuta la richiesta di permesso di lavoro. Si tratta di una funzionalità chiave per i manager, per rifiutare le richieste di permessi.
- **deleteClicked**: quando viene selezionato **Elimina** nei dettagli delle attività, facendo apparire la finestra di dialogo di conferma.
- **deleteContact**: un utente elimina un contatto privato esistente.
- **deleteMeeting**: selezionare il pulsante **Elimina** nella pagina dei dettagli della riunione.
- **deletePersonalTask**: conferma che è stata eliminata correttamente un’attività personale.
- **deletePersonalSubtask**: conferma che è stata eliminata correttamente una sottoattività personale.
- **deletePlannerTask**: conferma che un'operazione di eliminazione di un'attività condivisa è stata completata correttamente.
- **deleteShift**: eliminazione turni.
- **duration_picker_dismissed**: quando viene ignorata la selezione della durata.
- **deleteTask**: verifica con il servizio Planner se un'azione di eliminazione è riuscita o meno. Conferma che l'eliminazione di un'attività non è riuscita, ossia che l'eliminazione di un'attività non ha avuto successo.
- **deleteVoicemail**: viene toccato Elmina l’elemento della segreteria telefonica.
- **demotedToAttendee**: un utente abbassa di livello di un relatore. Pulsante **Cambia** nella finestra di dialogo.
- **denyParticipant**: numero di volte in cui un utente rifiuta l'immissione di una persona dall'elenco.
- **descriptionChanged**: conferma una descrizione dell'attività condivisa che è stata cambiata correttamente.
- **descriptionClicked**: quando un utente seleziona **Visualizza descrizione** dai dettagli dell'attività.
- **detailsTabClicked**: viene selezionata la scheda **Dettagli** nella riunione.
- **deviceAddressBookSync**: generato quando la sincronizzazione della Rubrica è attivata dalla pagina impostazioni.
- **deviceAddressBookUnsync**: generato quando la sincronizzazione della Rubrica è disattivataattivata dalla pagina impostazioni.
- **dialIn**: un utente decide di connettersi telefonicamente a una riunione (varie posizioni).
- **dialInBadNetworkBanner** -  viene selezionata l’opzione **Componi numero** per un banner di connessione scadente.
- **dialInBadNetworkBannerCancel**: l’opzione **Componi numero** viene annullata nella finestra di dialogo nativa.
- **dialInBadNetworkBannerConfirm**: l’opzione **Componi numero** viene confermata nella finestra di dialogo nativa.
- **dialInCall** -  viene selezionato **Chiama** dalla finestra di popup **Componi numero**.
- **dialInCancel** -  viene selezionato **Annulla** dalla finestra di popup di **Componi numero**.
- **dialOutCall** si attiva quando un utente:
  - si unisce in Modalità guida.
  - Seleziona **Chiama** nella finestra popup **Richiamami**.
- **dialOutCallAAD**: quando si seleziona un numero da **I miei numeri** nel foglio di azione.
- **dialOutCallRecent**: quando si seleziona un numero dai numeri precedenti recenti nel foglio di azione.
- **dialOutCancel** -  viene selezionato **Annulla** nella finestra popup **Richiamami**.
- **dialOutDialog** -  viene selezionato **Nuovo numero** nel foglio di lavoro.
- **dialOutFailRetry** - viene selezionato **Riprova** da un banner di errore.
- **DialPad**: il pulsante **Tastiera** viene selezionato dall’elenco chiamate.
- **disableCategory**: disabilita un tipo di notifica o disattiva le notifiche di chiamate in arrivo.
- **disabled** -  viene selezionato **Ignora notifiche** in First-run experience (FRE). Fornisce i dati di successo chiave per ignorare la notifica nel flusso FRE.
- **disableQuietDays**: giorni in modalità non interattiva disabilitato. Funzionalità di telemetria di successo per giorni in modalità non interattiva.
- **disableQuietHours**: ore in modalità non interattiva disabilitato.
- **discoverTeams**: passare alla pagina Sfoglia e Partecipa a Teams.
- **Dismiss_earlycancelledCQF**: Il modulo di chiamata annullato anticipatamente CQF viene ignorato.
- **Dismiss_ratemycallCQF**: il tasso CQF del modulo Mie chiamate viene ignorato.
- **Dismiss_ratemyliveeventCQF**: il tasso CQF del modulo evento live viene ignorato.
- **dismissBadNetworkBanner** -  viene selezionata l’opzione **Ignora** per un banner di connessione scadente.
- **dismissFlyout** -  viene selezionato il pulsante **Ignora**.
- **dismissModality**: si uscirà dalla selezione modalità senza condividere.
- **dismissModalityPicker**: viene selezionato il pulsante **Selezione modalità**.
- **dismissReadReceiptsNotice** -  viene selezionato **OK** da un avviso di funzionalità.
- **dismissStartRecording**: ignorare l'errore all'avvio della registrazione.
- **dismissStopRecording**: ignorare l'errore all'interruzione della registrazione.
- **dismissUseWifiForVideoBanner** si attiva quando un utente ignora un banner:
  - che indica all'utente che il video dei partecipanti da remoto è bloccato e che gli utenti devono passare alla modalità Wi-Fi per vederlo.
  - che indica all'utente che gli utenti devono passare a una rete Wi-Fi per condividere il video.
- **DLPDelete**: un utente ha eliminato un messaggio bloccato.
- **DLPEdit**: un utente ha modificato un messaggio bloccato.
- **DLPOverride**: un utente ha eseguito l’override di un messaggio bloccato.
- **DLPOverrideReport**: un utente ha segnalato un falso positivo e ha eseguito l’override del messaggio.
- **DLPReport**: un utente ha segnalato un falso positivo.
- **DLPResolve**: un utente ha provato a risolvere un messaggio di prevenzione della perdita dei dati.
- **DLPSeeOriginal**: un utente ha toccato per visualizzare un messaggio originale.
- **downloadFile** consente di:
  - determinare se è stata avviata un'operazione di download.
  - determinare se un file è stato scaricato con successo.
- **dragDatePickerHandle**
- **dtmfPSTNCall**: viene toccato il pulsante DTMF sulla tastiera.
- **dueDateChanged**: si attiva quando un utente assegna una scadenza a un’attività.
- **dueDatePickerClicked**: si attiva quando il pulsante **Scadenza** è selezionato nei dettagli dell'attività, aprendo la pagina di selezione delle date.
- **dueDateSelected**: si attiva quando un utente seleziona un filtro per scadenza durante la visualizzazione di un elenco di attività.
- **dueDateUnselected**: si attiva quando un utente non seleziona un filtro per scadenza durante la visualizzazione di un elenco di attività.
- **edit** -  pulsante **Modifica** in un messaggio di chat.
- **editChannel**: un utente seleziona un pulsante che consente di modificare un canale di cui è proprietario o amministratore.
- **editContact**: un utente modifica un contatto privato esistente e può essere eseguito passando alla scheda contatto.
- **editMeetingResponse**: modifica una risposta di una riunione dalla pagina dei dettagli della riunione.
- **editNavigation** -  viene selezionato **Riordina** nel menu **Altro** per modificare l'ordine delle app nella barra inferiore.
- **editRsvpMeetingOptions**: selezionare **conferma di partecipazione** per cambiare la selezione precedente.
- **editShiftClicked**: modificare un turno.
- **editSmartReply**: viene modificato un elemento di risposta intelligente.
- **editTeam**: un utente tocca un pulsante per la modifica di un team di cui è proprietario o amministratore.
- **editTeam, editChannel** è relativo all'aggiunta con succeso di membri in un team e alla creazione con successo di un team esistente quando:
  - viene selezionato il pulsante **Annulla** nella pagina **Aggiungi membri** (membro o team esistente).
  - viene selezionato il pulsante **Fatto** nella pagina **Aggiungi membri** (membro o team esistente).
- **emergencyCall**: chiamata di emergenza effettuata con un piano per chiamate.
- **emergencyCallDirectRouting**: chiamata di emergenza effettuata in routing diretto.
- **emergencyCallLocationPolicyBased**: DialEmergency con tastiera.
- **emergencycallSecurityDeskNotify**: chiamata di emergenza effettuata, desk sicurezza informato.
- **enableCategory** relativo alle impostazioni di notifica per l'abilitazione:
  - un tipo di notifica.
  - notifiche di chiamata in arrivo.
- **enabled** è relativo all'abilitazione della notifica nel flusso first-run experience (FRE):
  - viene selezionato **Abilita notifiche** in first-run experience (FRE).
  - viene selezionato Abilita in un promemoria.
- **enabled/disabled**: autorizzazioni di chiamata o autorizzazioni di contatto (solo Android).
- **enabled, notNow**: pulsante **Accetta** del prompt delle autorizzazioni delle notifiche, autorizzazione di notifiche per first-run experience (iOS). Acquisisce il numero di persone che hanno abilitato la caratteristica di notifica e forniscono informazioni.
- **enablediOSPrompt**: un utente abilita le notifiche nel prompt delle autorizzazioni delle notifiche iOS. Vengono fornite informazioni sugli utenti che effettivamente abilitano le notifiche in iOS dal prompt delle autorizzazioni delle notifiche.
- **enabledQuietDays**: giorni in modalità non interattiva abilitati.
- **enableLocationPermission**: quando un utente abilita le autorizzazioni di posizione per la funzionalità di condivisione della posizione.
- **enableQuietDays**: un utente abilita giorni in modalità non interattiva.
- **enableQuietHours**: ore in modalità non interattiva abilitato.
- **endEditing** -  pulsante **Salva** premuto.
- **endFileShare** -  viene selezionato **Indietro** in una finestra di dialogo di condivisione file.
- **endMyShift**: numero di dispositivi in modalità condivisa o numero di disconnessioni.
- **endPhotoShare** - **x** per uscire dalla condivisione foto.
- **entryPointClicked**: selezione di **Richieste** nella scheda **Pianifica**. Le richieste si riferiscono a quando un operatore sul campo richiede un turno di lavoro, ecc.
- **endPSTNCallSelected**: un utente termina un PSTN e una chiamata di contenuto.
- **endPSTNCallShown**: agli utenti viene chiesto di terminare una chiamata PSTN o una chiamata di contenuto.
- **endVideoShare** - **x** per uscire dalla condivisione video.
- **errorShown**: viene visualizzato un messaggio di errore.
- **expand/collapse**: sezione contatti dispositivo o contatti aziendali.
- **expandCollapseSection** : toccare un'intestazione di sezione per espandere o comprimere una sezione.
- **Previsto: atMention - Android: chatSendMessage - iOS: sendMsg**: @menzionare un bot in una casella di composizione.
- **Previsto: botClickCardAction - Android: showCard - iOS: missing**: toccare i pulsanti della scheda. Le schede sono costrutti principali della piattaforma e la misura dell'utilizzo e dello schema è necessaria per comprendere l'utilizzo della piattaforma e tenere traccia dei potenziali problemi sul lato client.
- **Previsto: chatSendMessage - iOS: composeSendMessage**: toccare **Rispondi** e rispondere a una chat bot in un canale.
- **Previsto: composeSendMessage - Android: replyChannel - iOS: mancante**: toccare **Rispondi** e rispondere a una chat bot in un canale.
- **Previsto: messageLike - Android: reactLike_CM**: mettere mi piace su un messaggio bot.
- **Previsto: messageUnread - Android: markAsLastUnread**: opzioni di menu di scelta rapida per un messaggio di bot.
- **federatedUpgradeNewChat**: legacy chat viene aggiornata a native.
- **file**:tiene traccia se l'elenco dei file è stato eseguito correttamente nella chat e nella scheda dei file di canale.
- **fileselected**: viene selezionata una presentazione di PowerPoint.
- **fileThumbnailPreviewDownloaded**: consente di identificare se una anteprima è stata renderizzata correttamente per un file.
- **fileThumbnailPreviewFromCache**: acquisisce se le anteprime vengono visualizzate dalla cache con esito positivo e consente di identificare se l'anteprima di un file è riuscita.
- **fileThumbnailPreviewNotAvailable**: consente di identificare se una anteprima è stata renderizzata correttamente per un file.
- **fillFrameVideo**: riempimento frame dal foglio di lavoro.
- **firstTimeSignedIn** evento di accesso o di iscrizione generato da:
  - accesso riuscito.
  - primo accesso riuscito.
  - gli errori di accesso vengono visualizzati da un utente.
  - registra la telemetria sui criteri MAM/MDM implementata per il primo accesso.
  - registra i parametri del referrer per l'installazione dell'app dopo il primo accesso riuscito.
- **fitToFrameVideo**: adattamento frame dal foglio di lavoro.
- **flipCamera**: capovolge camera.
- **forcedUpdateAccept**: un utente accetta di aggiornare la versione dell'app nella finestra di dialogo Forza aggiornamento.
- **forcedUpdateExit**: un utente chiude l'app anziché aggiornare la versione dell'app nella finestra di dialogo Forza aggiornamento.
- **forcedUpdatePrompt**: usato in situazioni in cui è necessario raggiungere gli utenti con versioni precedenti, che potrebbero non disporre delle ultime correzioni per la sicurezza e la privacy.
- **formattingBold**: un utente seleziona la formattazione in grassetto.
- **formattingHighlight**: un utente seleziona la formattazione dell'evidenziazione.
- **formattingImportant**: un utente seleziona importanza.
- **formattingItatlics**: un utente seleziona il corsivo.
- **formattingTextColor**: un utente seleziona la formattazione del colore del testo.
- **formattingUnderline**: un utente seleziona sottolineato.
- **FRE - Nessun AS Assegnato**: registra dati di telemetria sui criteri MAM / MDM all'avvio dell'app. Telemetria per l'integrazione di Intune per MAM e MDM. Fornisce dati di successo sull'errore durante il first-run experience (FRE).
- **freActionClicked** -  **Inizia**, **Prova più tardi**, o **Chiudi** (GPS) viene selezionato nel First-run experience (FRE).
- **freDone**: viene eseguito il First-run experience (FRE).
- **freTriggered**: un utente visualizza il marcatempo nel First-run experience (FRE).
- **funSearchQueryEntered**: query Giphy immessa. Dati di successo relativi alla funzionalità di allegato Giphy in Teams.
- **funSelectItem**: immagine Giphy selezionata. Dati di successo relativi alla funzionalità di allegato Giphy in Teams.
- **galleryImage**: immagine caricata - galleria.
- **get_directions_clicked**: viene selezionato il pulsante **Ottieni indicazioni**.
- **goToNotificationSettings**: andare alla pagina delle impostazioni di notifica dalla finestra di dialogo **Abbiamo aggiornato le impostazioni di notifica**.
- **GPSPromptClicked**: viene selezionata l'opzione **Consenti** o **Non consentire** in una richiesta del sistema operativo, consentendo o meno la funzione GPS.
- **group_map_closed**: un utente apre una visualizzazione mappa da una chat.
- **group_map_open**: un utente chiude una visualizzazione mappa.
- **groupCallJoin**: un utente partecipa a una chiamata di gruppo.
- **groupClicked**: tiene traccia di quando un utente seleziona il turno del gruppo.
- **guideMe**: gli utenti selezionano un banner che li informa su un'app di terze parti che blocca le notifiche e offre una guida alla risoluzione dei problemi.
- **hamburgerMenu**: passare al menu hamburger. Il menu contiene azioni importanti, come il cambio di account, le impostazioni di notifica, l'impostazione dei dati e le impostazioni del profilo.
- **handoffComplete**: una riunione o una chiamata è stata trasferita su questo dispositivo.
- **handoffJoi**: viene selezionata un’opzione di trasferimento nel foglio di lavoro.
- **hardwareAudioOff**: disattiva l'audio tramite i pulsanti hardware.
- **hardwareAudioOn**: attiva l'audio tramite i pulsanti hardware.
- **hide**: nasconde chat.
- **hideChannel**: nasconde un canale dall'elenco di team e canali.
- **image**: immagine.
- **immediateCallForward**: viene impostato l’inoltro di chiamata immediato o l'attivazione dell'inoltro di chiamata immediato (Ricevo io le chiamate è disabilitato).
- **importanceToggleClicked**: si attiva quando il campo **!** è attivato o disattivato all'interno dei dettagli dell'elemento dell'attività.
- **importantMessage_select**: un utente seleziona un messaggio importante dal menu contestuale di priorità.
- **importantMessageSend**: un utente invia un messaggio importante.
- **inCallDialOut**: un utente seleziona il pulsante **Richiamami** da altre opzioni durante la chiamata.
- **initiatePhotoShare**: avvia la condivisione foto.
- **initiateVideoShare** : avvia la condivisione di video.
- **install**: installa o installa evento.
- **installReferrer**: registra i parametri del referrer per l'installazione dell'app dopo la prima installazione.
- **invisionWhiteboardClicked** la lavagna Invision viene selezionata:
  - la scheda **File di canale**.
  - la scheda di riunione **File di chat**.
- **inviteFreemium**: toccare il pulsante **+** nella schermata invita.
- **inviteGuest**: toccare il pulsante **+** nella schermata invita.
- **joinFromDeeplinkInTeams**: un utente è stato aggiunto tramite un deeplink dall'app di Teams.
- **joinFromDeeplinkInTeams**: un utente è stato aggiunto tramite un deeplink dall'app di Teams.
- **joinFromJoinLauncher**: un utente è stato aggiunto da un Join Launcher.
- **joinFromNudge**: un utente è stato aggiunto da un suggerimento.
- **joinFromStore**: un utente è stato aggiunto dopo aver scaricato l’app dall’App Store.
- **joinMeeting** rileva l'esito positivo o negativo dell'iscrizione alle riunioni dai calendari nei casi seguenti:
  - si partecipa alla riunione tramite Componi numero.
  - si partecipa alla riunione tramite Richiamami.
  - si partecipa solo al contenuto della riunione.
  - si seleziona il pulsante **Partecipa riunione** dalla visualizzazione agenda.
- **joinOptionsEdu**: un utente EDU seleziona le opzioni per partecipare a una riunione pianificata e gli vendono mostrate le opzioni corrette.
- **joinTeam**: viene premuto il pulsante **Partecipa**.
- **joinViaCode**: un utente partecipa a una riunione con un codice.
- **labelPickerClicked**: conferma che la selezione etichette è stato avviato correttamente.
- **labelSelected**: conferma che un’etichetta è stata selezionata.
- **labelUnselected**: conferma che un’etichetta è stata deselezionata.
- **launchLinksGallery**: quando un utente accede alla raccolta collegamenti nel dashboard.
- **Sorgente di avvio come diretta, collegamento, appShortcut**: si avvia direttamente o tramite collegamento (registrando la telemetria Mobile Application Management (MAM) o Gestione dispositivi mobili (MDM) all'avvio dell'app per raccogliere dati per gli utenti attivi).
- **leaveChat**: conferma che si esce dalla chat.
- **legacyChatLink**: viene selezionato un collegamento a una chat legacy.
- **likeAppDismiss**: quando il prompt che chiede se a un utente piace o meno l'app viene ignorato senza una risposta.
- **likeAppNo**: quando il prompt che chiede se all'utente piace l'app riceve una risposta negativa.
- **likeAppYes**: quando il prompt che chiede se all'utente piace l'app riceve una risposta positiva.
- **likeMsg**: selezionare **Mi piace**.
- **linkPreviewCancel**: comprendere il comportamento della chiusura di anteprima.
- **listUserClicked**: quando un utente seleziona un utente Al lavoro adesso.
- **liveCaptions**: le didascalie live sono attivate o disattivate.
- **liveEventAdditonalLink**: viene selezionato un altro collegamento.
- **liveEventInfo**: viene selezionato il pulsante **Info**.
- **liveEventJoin**: un utente partecipa a un evento live.
- **liveEventLeave**: viene premuto il pulsante **Abbandona**.
- **liveEventPresenterJoin**: un relatore si aggiunge a un evento live.
- **liveEventPresenterJoinAsAttendee**: il relatore di un evento si aggiunge come partecipante.
- **liveEventQnA**: viene selezionata l’icona **Domande e risposte**.
- **liveEventYammer**: viene selezionata l'icona **Yammer**.
- **liveMeetingPushNotificationClicked**: viene selezionata una notifica push.
- **liveMeetingToastClicked**: viene selezionato un avviso popup in-app.
- **live_location_in_chats_from_profile_clicked** -  viene selezionato in visualizzazione profilo **Posizioni live**.
- **lobbyPickAudio**: numero di volte in cui un utente cambia l'uscita audio dalla lobby.
- **lobbyToggleMuted**: numero di volte in cui un utente ha attivato o disattivato il microfono dalla sala di attesa.
- **lobbyToggleVideo**: numero di volte in cui un utente ha attivato o disattivato il video dalla sala di attesa.
- **logOutClicked**: quando un utente si disconnette.
- **location_active_tracking**: il dispositivo di un utente passa a verifica attiva.
- **locationCard**: seleziona una scheda di posizione.
- **location_family_sync**: mostra i membri di un gruppo famiglia che sono stati creati nell'app per famiglie MSA. Conferma che vengono visualizzati tutti i membri della famiglia a cui può essere dato il consenso.
- **location_group_map_sync**: viene aperta la visualizzare mappa.
- **location_map_load**: carica la visualizzazione mappa.
- **location_map_markers_load**: viene caricata la visualizzazione della mappa. Conferma che gli indicatori di posizione per tutti gli utenti che condividono attivamente sono visualizzati correttamente nella visualizzazione della mappa.
- **location_message_send**: un utente avvia una sessione di condivisione della posizione.
- **location_data_use_privacy_denied**: un utente ignora o seleziona **Non ora** in un popup che spiega come usare i dati di una posizione per TFL.
- **location_data_use_privacy_granted**: un utente seleziona **Consenti** in un popup che spiega come usare i dati di una posizione per TFL.
- **location_settings_open**: un utente apre le impostazioni di posizione.
- **location_sharing_start**: un utente condivide la posizione live in una chat.
- **location_sharing_start**: un utente interrompe la condivisione della posizione live in una chat.
- **loginFailed**: l’utente non ha potuto eseguire l'accesso.
- **loginSuccess**: l’utente ha potuto eseguire l'accesso.
- **manageBlockedNumbers**: accedere a numeri bloccati tramite impostazioni.
- **manualSendMessage** - viene inviato un messaggio manualmente.
- **mapAppPicker**: quando un utente seleziona l'app di mapping da usare quando tocca una scheda di percorso.
- **markAsRead**: segnare come già letto.
- **markAsUnread**: segnare come da leggere.
- **markChannelRead**: un utente contrassegna il canale come già letto.
- **messageBookmarkMessage**: salva scheda connettore. Usa la telemetria esistente con i dati specifici dell'app. Oppure salva un messaggio di bot.
- **markAsLastUnread**: menu di scelta rapida della scheda del connettore.
- **maskCallerId**: un utente abilita o disabilita l'opzione chiamata per nascondere l'ID chiamante.
- **meetingDetailCalendarList**: pagina Dettagli riunione selezionata dall'elenco dei calendari o selezionare la scheda **Dettagli** nella pagina dei dettagli della riunione.
- **meetingDetailChatWithParticipants**: chattare con i partecipanti dalla pagina dei dettagli della riunione.
- **meetingDetailDeleteMeetingforSelf**: eliminare una riunione dalla pagina dei dettagli della riunione.
- **meetingDetailJoin**: viene selezionato il pulsante **Partecipa riunione** dalla pagina dei dettagli della riunione.
- **meetingDetailParticipants**: vedere tutti i partecipanti dalla pagina dei dettagli della riunione.
- **meetingDetailScheduledMeeting**: pagina dei dettagli della riunione selezionata dall'oggetto della riunione pianificata (**…**) oppure selezionare la scheda **Dettagli** di una riunione pianificata.
- **meetingDetailSearchParticipants**: viene selezionata l’opzione **Cerca** nei partecipanti alla riunione all’interno della pianificazione della riunione.
- **meetingJoinLeave**: lasciare premuto **x** dopo che viene toccato il pulsante **Partecipa**.
- **meetingJoinNow** - **Partecipa ora per VOIP** selezionato.
- **meetingJoinNowWithCallMe**: un utente partecipa a una riunione tramite **Chiamami**.
- **meetingJoinNowWithPSTN**: un utente partecipa a una riunione tramite Componi numero.
- **meetingLeaveChat**: abbandonare la chat.
- **meetingMuteChat**: disattivare l'audio della chat.
- **meetingNotesCreatedInChatLink**: viene selezionato il chiclet **Note della riunione create** in una chat di una riunione privata o in una chat di una riunione di canale.
- **meetingNotesMentionCharLink**: viene selezionato il collegamento @menziona in chat di una riunione privata.
- **meetingNotesMentionCharLink**: viene selezionato il collegamento @menziona in chat di una riunione di canale.
- **meetingNotesTabEntryPoint**: la scheda **Note della riunione** viene selezionata in riunione privata o in un canale.
- **meetingNotificationSettingsAccepted**: l’opzione impostazioni di notifica è stata modificata in Solo accettata.
- **meetingNotificationSettingsAll**: l’opzione impostazioni di notifica è stato modificata in Tutti.
- **meetingNotificationSettingsNone**: l’opzione impostazioni di notifica è stata modificata in Nessuno.
- **messagePriority_select**: è selezionato un punto di ingresso priorità messaggio.
- **messageSeeOriginal**: un utente ripristina un messaggio tradotto nella lingua originale.
- **meetingSeeParticipantsChatDetails**: vedere tutti i partecipanti.
- **memberListLoadMore**: scorrere verso il basso per caricare altro.
- **messagedEditMessage**: un utente modifica un messaggio.
- **messageShareMessage**: condividere un messaggio.
- **messageTranslate**: un utente traduce un messaggio.
- **messageUnabletoEdit**: un utente non riesce a modificare un messaggio.
- **meetingUserAnonB2B**: un utente B2B anonimo si è unito alla riunione.
- **meetingUserAnonB2C**: un utente B2C anonimo si è unito alla riunione.
- **meetingUserDialIn**: un utente PSTN (Componi numero) si è unito alla riunione.
- **meetingUserDialOut**: un utente PSTN (Richiamami) si è unito alla riunione.
- **meetingUserFederated**: un utente federato si è unito alla riunione.
- **meetingUserFreemium**: un utente freemium si è unito alla riunione.
- **meetingUserGuest**: un utente guest si è unito alla riunione.
- **meetingUserTenant**: un utente interno al tenant si è unito alla riunione.
- **messageCopyMessage**: copiare messaggio.
- **messageDelete**: eliminare messaggio.
- **messageEditMessage**: modificare messaggio.
- **messageForwardMessage**: Un utente seleziona un punto di ingresso Inoltra dal menu contestuale del messaggio.
- **messageLike/messageUnlike**: messaggio Mi piace o Non mi piace.
- **messageMuteSender**: disattivare o attivare l'audio del mittente.
- **messageLike**: Mi piace sulla scheda del connettore. Usa la telemetria esistente con i dati specifici dell'app.
- **messageScheduledMeeting**: oggetto riunione nel canale selezionato (non solo quelli programmati).
- **messageTriggered**: quando viene attivata una notifica per un messaggio.
- **micPermissionCancel** - viene selezionato **Annulla** nella finestra di dialogo di autorizzazione del microfono.
- **micPermissionGoToSettings**: un utente passa a impostazioni dalla finestra di dialogo autorizzazioni microfono.
- **MicrosoftWhiteboardClicked**: la lavagna Microsoft è selezionata nella scheda **File canale** o nella scheda **File della chat della riunione**.
- **moreOptionsClicked**: si attiva quando il menu **...** in alto a destra è selezionato nella schermata dell'editor degli elementi dell'attività.
- **moveTaskClicked**: opzione all’interno dell’elenco altre opzioni di un elemento di attività.
- **multiCallEndFromUFD**: numero di volte in cui un utente termina la conversazione in uno scenario con più chiamate.
- **multiCallResumeFromUFD**: numero di volte in cui un utente sceglie di riprendere una conversazione in attesa.
- **multiCallSwitch**: numero di volte in cui un utente seleziona un'opzione che consente di cambiare la chiamata e l'elenco delle chiamate in attesa.
- **multipleAccounts**: numeri di account per utente.
- **multipleTenants**: numero di tenant per account.
- **mute**: disattivare l'audio di una chat.
- **muteOnWhiteboard** : un utente disattiva o attiva l’audio nella schermata di una lavagna.
- **muteParticipant**: disattivare l’audio di un partecipante (passare al foglio di lavoro).
- **my_location_button_clicked**: l'utente centra la mappa sulla propria posizione selezionando il pulsante **La mia posizione**.
- **my_location_clicked**: l'utente centra la mappa sulla propria posizione selezionando il **punto blu** sulla mappa.
- **myShiftPickerClicked**: viene registrato solo se la richiesta inviata è uno scambio o un'offerta. Viene selezionata l'opzione **Il mio turno**.
- **nameGroupChat**: nome chat di gruppo.
- **nativeTimeClockBreak**: un pausa sul marcatempo.
- **nativeChatLink**: viene selezionato un collegamento alla chat nativa.
- **navActivity**: passare alla pagina feed di attività.

- **navBookmark**: un utente accede alla scheda **Salvato** o all'app nella barra inferiore o nella barra delle applicazioni.
- **navCalendar**: misura se un utente accede a un calendario.
- **navCallingSettings**: un utente passa alle impostazioni delle chiamate.
- **navCalls** -  la scheda **Chiamate** viene premuta.
- **navCamera**: un utente accede alla scheda **Fotocamera** o all'app nella barra inferiore o nella barra delle applicazioni.
- **navChat**: un utente accede alla scheda **Chat** o all'app nella barra inferiore o nella barra delle applicazioni.
- **navContacts**: un utente accede alla scheda **Contatti** o alla scheda **Persone** o all'app nella barra inferiore o nella barra delle applicazioni.
- **navDashboardTab**: un utente accede alla scheda **Dashboard** all'interno di una conversazione.
- **navDynamics365**: viene attivato all'apertura dell'app Dynamics365.
- **navFiles**: l'app File è selezionata, tiene traccia se un utente può avviare l'app File nella barra delle applicazioni (iOS).
- **navFilesTab**: l'app File è selezionata, tiene traccia se un utente può avviare l'app File nella barra di spostamento inferiore (iOS).
- **navMeetings** -  viene toccato l’opzione **Calendario**.
- **navNotes**: si attiva quando l’app Note viene aperta.
- **navOrganization**: si attiva quando l’app Organizzazione viene aperta.
- **navOrgChart**: si attiva quando l’app Orgchart viene aperta.
- **navPeople**: un evento viene generato quando si apre l'app Contatti.
- **navPeopleSettings**: si attiva quando si passa alla categoria **Persone** nel menu delle impostazioni.
- **navPersonalFiles**: l'app File è selezionata, tiene traccia se un utente può avviare l'app File nella barra di spostamento inferiore (Android).
- **navPhotoTab** -  scheda **Foto**.
- **navSaved**: un utente accede alla scheda **Salvato** o all'app nella barra inferiore o nella barra delle applicazioni.
- **navSelectPlan**: quando un utente seleziona un piano condiviso a cui passare dalla visualizzazione Home.
- **navSelectPersonalList**: quando un utente seleziona un piano personale a cui passare dalla visualizzazione Home.
- **navSelectPlan**: quando un utente seleziona un piano Smart in cui passare dalla visualizzazione Home.
- **navNotes**: si attiva quando l’app Attività viene aperta.
- **navTeams**: toccare **Vedi tutti**.
- **navVideocamera**: un utente accede alla scheda **Fotocamera** o all'app nella barra inferiore o nella barra delle applicazioni.
- **navVideoTab** -  scheda **Video**.
- **navVoicemail**: un utente accede alla pagina della segreteria telefonica.
- **navWalkieTalkie**: un utente ha aperto l'app walkie talkie.
- **navWiki**: si attiva quando l’app Wiki viene aperta.
- **newChat**: un utente crea una chat.
- **newCall**: si tocca il pulsante **Nuova chiamata**.
- **newCallDialPad**: si tocca il pulsante **Tastiera** sulla scheda.
- **newCallPeople**: si tocca il pulsante **Persone** sulla scheda.
- **noBGActivityDetected**: supera la soglia relativa ai guasti delle attività in background.
- **notBlockedDevice**: un utente non raggiunge la soglia degli errori di attività in background in 30 giorni.
- **notNow** -  viene selezionato **Non ora** in promemoria.
- **notNowUpdate**: aggiornamento posticipato.
- **notificationNavChannelConversation**: avviare l'app usando una notifica per una conversazione nel canale.
- **notificationNavChannelThreadConversation**: avviare l'app usando una notifica per un determinato messaggio in una conversazione nel canale.
- **notificationSettingTurnedOff**: disattivare le notifiche push per l'app per i dispositivi Android.
- **notificationNavPreCall** : un utente riceve una notifica di inizio riunione che li fa passare alla schermata di prechiamata nella selezione.
- **ocvFeedback**: relativa alle prestazioni del modulo di feedback OCV.
- **ocvFormCancelled**: un evento inviato quando il modulo di feedback OCV viene annullato e l'utente torna all'app.
- **ocvFormOpened**: un evento inviato all'apertura del modulo OCV.
- **ocvFormSubmit**: un evento inviato quando l'utente seleziona Invi nel modulo di feedback OCV.
- **offerRecipientClicked**: viene registrato soltanto se la richiesta di invio è un'offerta. L'utente immette la selezione del membro del team per offrire un turno. Offrire significa offrire un turno di riposo.
- **offerSwapShiftFromL1**: il tipo di turno che un utente cerca di offrire o scambiare da un elenco di turni. L’azione su iOS è **SwipedRight** mentre su Android **LongPressed**.
- **offerSwapShiftFromL1Triggered**: un utente offre il cambio di turno a un altro utente.
- **officeLens** viene generato quando l'app avvia la funzionalità fotocamera officeLens, se:
  - un utente tenta di allegare una foto al messaggio.
  - un utente prova a scattare una foto e a caricarla direttamente nella raccolta.
- **officeLens o cameraImage**: immagine della fotocamera selezionata - fotocamera standard o officeLens.
- **onBackClicked**: ogni volta che si seleziona la freccia indietro per spostarsi indietro di una pagina.
- **oneNote**: quando un utente apre l'app OneNote.
- **open**: toccare Impostazioni notifica.
- **open edit**: telemetria d’utilizzo di Wiki - selezionata dall'utente per modificare il Wiki.
- **openApp**: apertura di un'app personale.
- **openAppDrawer** -  viene selezionato **Altro** nella parte inferiore della barra per aprire l’icona di avvio delle app.
- **openEditMeetingForm**: il pulsante **Modifica** viene selezionato nella pagina dei dettagli della riunione.
- **openFile** consente di:
  - identificare un file è stato possibile aprire correttamente nella chat.
  - identificare un file è stato possibile aprire da un elenco di file.
  - verificare se i file possono essere aperti da un elenco di OneDrive.
  - identificare i file aperti può essere aperto da un elenco di canali.
  - determinare se i file possono essere aperti dalle chat di gruppo.
  - determinare se un file può essere aperto correttamente dall'app File.
  - determinare se un file di messaggio può essere aperto con successo dal quadratino.
  - determinare se i file dall'elenco recente possono essere aperti correttamente.
  - determinare se un file dall'elenco dei file può essere aperto correttamente.
  - determinare se un file può essere aperto da un quadratino di file di messaggi.
  - determinare se i file possono essere aperti correttamente da un elenco di file.
- **openInAppClicked**: opzione all'interno dell’elenco elemento attività Altre opzioni, disponibile solo per le attività personali.
- **opensCalendarView**: toccare su **Turni aperti** dalla scheda **Pianifica**.
- **openContactCard**: un utente tocca l’icona **Contatto** o un contatto nell'app Contatti per avviare la scheda del profilo del contatto.
- **openContactCard_ReactionSummary**: passare alla scheda contatto nella pagina Riepilogo reazioni.
- **openFileInApp**: consente di identificare se l'utente ha scelto di aprire file all'esterno di Teams rispetto che all’interno.
- **openHamburgerMenu**: l'icona **Hamburger** (in alto a sinistra) viene selezionata per aprire il menu laterale per l'accesso alle impostazioni, presenza e cambio tenant.
- **openInStream**: aprire un video in Stream.
- **openMeetingDetails**: aprire i dettagli della riunione o la pagina dei dettagli della riunione aperta di una riunione specifica.
- **openModalityPicker**: X = ChatsAndChannels per le chat e i canali.
- **openNewMeetingForm**: conferma che è stata aggiornata correttamente una sottoattività personale.
- **openNewMeetingForm**: aprire l'utilità di programmazione durante la configurazione di una nuova riunione.
- **openPhotoLibrary**: selezionare una raccolta foto.
- **openQuietDays**: passare alla pagina Giorni in modalità non interattiva.
- **openQuietHours**: passare alla pagina Ore in modalità non interattiva.
- **openReactionHoverBubble**: premere il pulsante **Aggiungi reazione** nella pagina Riepilogo reazioni.
- **openReactionSummary**: richiama il cassetto di riepilogo delle reazioni.
- **openSettingsSetUpInstructions**: aprire **Impostazioni** dalle istruzioni.
- **openSharedLink**: quando un utente apre un collegamento dal riquadro collegamenti del dashboard o dalla raccolta collegamenti.
- **openShiftsClicked**: il numero di persone che toccano l'icona **Calendario**.
- **orgChart - Nessun AS assegnato**: telemetria di utilizzo di base per l'organigramma.
- **pageEntered**: un utente ha immesso una pagina.
- **parental_consent_grant**: un utente concede l'autorizzazione a un minorenne nella propria MSFamily per usare la funzione di localizzazione live in TFL.
- **parental_consent_remove**: un utente rimuove l'autorizzazione a un minorenne nella propria MSFamily per usare la funzione di localizzazione live in TFL.
- **pauseVoicemail** -  viene toccato **Sospndi** su un elemento della segreteria telefonica.
- **peoplePickerInvoked** la Selezione persone viene usata in sette posizioni in Teams per dispositivo mobile, incluso, ma non limitati a:
  - selezione nuova chat.
  - inoltrare un messaggio.
  - aggiungere un partecipante a una riunione.
- **personalAppNavBotChat**: passare al bot nell'app personale.
- **personalAppNavTab**: passare alle schede nell'app personale.
- **photoLibraryPicker** - **Apri raccolta foto** toccato in selezione immagini.
- **pickGalleryPhoto**: scegliere una foto dalla raccolta.
- **pickParticipantChatDetails**: scegliere un utente dall'elenco.
- **pickRecentPhoto**: scegliere un'immagine recente da condividere.
- **pinChannel**: aggiungere un canale per visualizzarlo al di sopra dell'elenco di Teams e Canali.
- **pinSelf**: aggiungere se stessi dal foglio di lavoro.
- **pinUser**: aggiungere un utente dal foglio di lavoro.
- **play**: riprodurre la registrazione.
- **playVoicemail** - **Riproduci** toccato in un elemento della segreteria telefonica.
- **plusButtonClicked**: selezionare il **pulsante più** (**+**).
- **pptNextSlide**: diapositiva successiva come presentatore o in visione privata.
- **pptPreviousSlide**: diapositiva precedente come presentatore o in visione privata.
- **pptReturnToPresenter**: passare alla diapositiva **Live** (quella su cui si trovano il presentatore e tutti gli altri).
- **pptStopPresenting**: interrompere presentazione.
- **pptTakeControl**: prendere il controllo.
- **preJoinAddRoom**: il pulsante **Aggiungi una sala** viene selezionato nell'elenco a discesa prima della partecipazione, viene selezionato **Partecipa** nello scenario **Aggiungi una stanza**.
- **preJoinAudioOff**: il pulsante **Audio disattivato** è selezionato nell'elenco a discesa pre-partecipa.
- **preJoinAutoAddRoom** - **Partecipa ora** viene selezionato quando un gruppo è nelle vicinanze.
- **preJoinBack** -  pulsante **Indietro** o **Chiudi** selezionato.
- **preJoinDenied**: un utente non è in grado di partecipare a una riunione.
- **preJoinDeviceAudio** - **Partecipa con l'audio del dispositivo** viene selezionato dall'elenco a discesa.
- **preJoinDialIn**: il pulsante **Componi numero** viene selezionato nel menu a discesa prima della partecipazione.
- **preJoinDialInCall**: un utente conferma la richiesta **Componi numero** prima della partecipazione.
- **preJoinDialInCancel**: un utente annulla la richiesta **Componi numero** prima della partecipazione.
- **preJoinDialOut**: viene selezionato il pulsante **Richiamami** nel menu a discesa prima della partecipazione.
- **preJoinDialOutCall**: un utente conferma la richiesta **Richiamami** prima della partecipazione.
- **preJoinDialOutCancel**: un utente annulla la richiesta **Richiamami** prima della partecipazione.
- **preJoinPSTNOptions**: un utente seleziona il menu a discesa per altre opzioni di partecipazione.
- **priorityChange**: si attiva quando il filtro di priorità viene applicato durante la visualizzazione di un elenco di attività.
- **priorityPickerClicked**: si attiva quando un utente passa a una selezione di filtri di priorità dalla schermata del filtro dell'elenco delle attività.
- **privateMeetingJoin** -  viene toccato il pulsante **Partecipa riunione** da una chat della riunione privata.
- **processInBG**: processo di notifica in arrivo sullo sfondo(Android).
- **processInFG**: processo di notifica in arrivo in primo piano (Android).
- **progressItemClicked**: conferma che un utente ha aperto correttamente la selezione dello stato di avanzamento di un'attività.
- **promotedToPresenter**: un utente promuove un partecipante - pulsante **Cambia** della finestra di dialogo.
- **provideFeedbackDismiss**: ignora il messaggio che chiede se l'utente desidera inviare un feedback sul motivo per cui non gli è piaciuta l'app.
- **provideFeedbackNo**: risponde no al messaggio che chiede se l'utente desidera inviare un feedback sul motivo per cui non gli è piaciuta l'app.
- **provideFeedbackYes**: risponde sì al messaggio che chiede se l'utente desidera inviare un feedback sul motivo per cui non gli è piaciuta l'app.
- **provideRatingDismiss**: ignora il messaggio che chiede se l'utente desidera valutarci nell'app store dopo aver detto che gli è piaciuta l'app.
- **provideRatingNo**: risponde no al messaggio che chiede se l'utente desidera valutarci nell'app store dopo aver detto che gli è piaciuta l'app.
- **provideRatingYes**: risponde sì al messaggio che chiede se l'utente desidera valutarci nell'app store dopo aver detto che gli è piaciuta l'app.
- **proximityPermissionDismissed**: il banner di autorizzazione viene ignorato.
- **proximityPermissionGranted**: l'autorizzazione viene assegnata nella finestra popup.
- **proximityPermissionViewed**: il banner di autorizzazione viene toccato.
- **pushNotification** gli eventi che l’attivano sono:
  - l’avvio tramite notifica.
  - selezionare una notifica push.
  - toccare riconnessione della notifica push.
  - **Reconnect failed**: viene toccata una notifica push.
- **quickNotificationAction**: quando un utente interagisce con una delle risposte di azione rapida a una notifica, ad esempio la possibilità di mettere mi piace su un messaggio direttamente dalla notifica push.
- **quickSelectImagePicker**: selezione rapida.
- **quickStartLiveEventJoin**: un utente partecipa a un evento live in avvio rapido.
- **quietHoursValues**: cattura lo stato ore in modalità non interattiva durante la navigazione con il pulsante Indietro.
- **quotedReplySent**: un utente ha inviato un messaggio di risposta con il tipo di contesto.
- **reactAngry_CM**: reazione arrabbiata dal menu di scelta rapida.
- **reactAngry_HB**: reazione arrabbiata dalla bolla al passaggio del mouse.
- **reactHeart_CM**: reazione con cuore dal menu di scelta rapida.
- **reactHeart_HB**: reazione con cuore dalla bolla al passaggio del mouse.
- **reactLaugh_CM**: reazione con risata dal menu di scelta rapida.
- **reactLaugh_HB**: reazione con risata dalla bolla al passaggio del mouse.
- **reactLike_CM**: reazione con Mi piace dal menu di scelta rapida o Mi piace a un messaggio bot.
- **reactLike_doubleTap**: reazione Mi piace con doppio tocco.
- **reactLike_HB**: reazione con Mi piace dalla bolla al passaggio del mouse.
- **reactSad_CM**: reazione Triste dal menu di scelta rapida.
- **reactSad_HB**: reazione con Triste dalla bolla al passaggio del mouse.
- **reactSurprised_CM**: reazione Sorpresa dal menu di scelta rapida.
- **reactSurprised_HB**: reazione Sorpresa dalla bolla al passaggio del mouse.
- **reactRemoved_HB**: quando un utente rimuove una reazione tramite la pagina di riepilogo della reazione.
- **readReceipts**: caratteristica abilitata dall'utente.
- **redeemInvite**: riscatto all’interno dell’app.
- **refreshCalendarList**: trascinare verso il basso per aggiornare la visualizzazione dell’agenda.
- **refreshLinksGallery**: quando un utente scorre verso il basso per aggiornare la raccolta collegamenti.
- **removeAssignee**: conferma che un assegnatario viene rimosso dalla visualizzazione selezione assegnazione, anziché *assignmentRemoved* che viene attivato selezionando **x** all'esterno della visualizzazione selezione assegnazione.
- **removeMeeting**: selezionare **Rimuovi dal calendario** dalla pagina dei dettagli della riunione di una riunione annullata.
- **removeParticipantFromEditMeeting**: rimuovere un partecipante dopo aver selezionato **Modifica riunione** dalla pagina dei dettagli della riunione.
- **removeParticipantFromNewMeeting**: rimuovere un partecipante dalla pagina dell'utilità di programmazione durante la configurazione di una nuova riunione.
- **removeReplyObject**: un utente ha rimosso l'oggetto della risposta da comporre.
- **removeUser**: conferma che un assegnatario viene rimosso dalla visualizzazione selezione assegnazione, anziché *assignmentRemoved* che viene attivato selezionando **x** all'esterno della visualizzazione selezione assegnazione.
- **removeUser_CM**: quando un utente rimuove qualcuno con l'elenco dei partecipanti alla chat.
- **removeUserConfirm**: un utente ha confermato una finestra di dialogo Rimuovi utente.
- **removeUserContextMenu**: un utente ha rimosso un partecipante tramite il menu di scelta rapida.
- **removeUserSwipe**: un utente ha rimosso un partecipante tramite scorrimento rapido.
- **reorderChannelItem**: un utente riordina i canali aggiunti.
- **reportAbuseConfirmation**: quando un utente seleziona il pulsante **Fatto** nella schermata di conferma.
- **reportAbuseOpen**: il numero di volte in cui viene selezionato il pulsante **Segnala un problema** nel menu di scelta rapida.
- **reportAbuseSend**: quando un utente seleziona il pulsante **Segnala**, la telemetria deve archiviare il tipo di report selezionato.
- **replyChain**: pulsante o casella di testo **Nuovo messaggio** selezionato nella catena di risposte (thread).
- **replyChannel**: pulsante **Rispondi** selezionato in tutti i canali.
- **replyNavigation**: l'oggetto Rispondi è stato selezionato per passare al post di riferimento.
- **replySendMessage**: inviare una risposta al canale.
- **replyViaMsgOptions**: l’utente ha avviato la risposta tramite il menu contestuale.
- **replyViaSwipe**: l’utente ha avviato la risposta tramite scorrimento rapido.
- **requestActedOn**: si attiva quando un manager agisce su richieste di turni aperte.
- **requestActionClicked**: quando un utente richiede un'azione, ad esempio quando è selezionata la richiesta per un turno, che sia la visualizzazione del responsabile degli operatori sul campo oppure gli operatori sul campo.
- **requestDetailsClicked**: quando è selezionata la richiesta per un turno, che sia la visualizzazione del responsabile degli operatori sul campo oppure gli operatori sul campo.
- **requestJoinTeam** -  pulsante **Richiedi** premuto.
- **requestSent**: registra se è stata inviata una richiesta.
- **requestToJoinTeam**: richiesta di unirsi al team (pubblico o privato).
- **requestToJoinTeamError**: errore con la richiesta di partecipazione.
- **requestTypeClicked**: determinare il tipo di richiesta che le persone scelgono nella selezione richieste.
- **resolveIssue** - **Resolvi** viene selezionato nel riquadro a comparsa di risoluzione dei problemi di notifica per passare all'app di blocco.
- **responseClicked**: un utente seleziona una pagina di risposta.
- **retryButtonClicked**: viene selezionato il pulsante **Riprova**.
- **returnToMessage**: il pulsante **Ritorna** viene selezionato per tornare al messaggio.
- **runningLate**: l'utente è in ritardo.
- **safeLink**: collegamento verificato come attendibile.
- **saveEditMeeting**: viene selezionato il pulsante **Salva** nella pagina di pianificazione delle riunioni, dopo aver aggiornato una riunione.
- **saveNewMeeting**: viene selezionato il pulsante **Salva** nella pagina di pianificazione delle riunioni. Per registrare le riunioni salvate con successo e la percentuale di riunioni che non sono state create a causa di un errore lato client o di servizio.
- **savePlanClicked**: **Crea** viene selezionato nel nuovo autore del piano dall'apertura predefinita dell'app.
- **scheduledMeetingJoin**: il pulsante **Partecipa riunione** viene selezionato dall’oggetto riunione pianificata.
- **scrollCalendarList**: misura il numero di volte che si scorre nel calendario.
- **scrollDatePicker**: scorrere nel controllo selezione data calendario.
- **searchAbandoned**: determina se la ricerca è stata abbandonata.
- **searchCancelled** determina se:
  - la ricerca ha avuto esito positivo o se l'utente ha abbandonato la ricerca.
  - una query di ricerca ha avuto esito positivo.
- **searchContacts**: eseguire una ricerca dall'elenco chiamate.
- **searchIcon** determina:
  - se la ricerca può essere attivata.
  - l’originie di un trigger di ricerca.
  - se vengono trovati risultati rilevanti.
- **searchInitiated**: determina se la ricerca può essere attivata e l'origine del trigger di ricerca.
- **searchMeetingParticipants**: cercare i partecipanti da aggiungere nel modulo di programmazione. Per distinguere il numero di appuntamenti creati rispetto al numero di riunioni create.
- **searchResultsClicked** determina:
  - se possono essere trovati risultati rilevanti.
  - se i risultati della ricerca provenivano dalla scheda Tutti rispetto a un singolo dominio.
- **searchTab** determina:
  - informazioni sul dominio del risultato della ricerca: per persone, chat, messaggi e file.
  - se i risultati della ricerca provenivano dalla scheda Tutti rispetto a un singolo dominio.
- **searchTabClicked** determina:
  - informazioni sul dominio del risultato della ricerca: per persone, chat, messaggi e file.
  - se vengono trovati risultati rilevanti.
- **seeAllMeetingParticipants**: seleziona **Vedi tutti** dalla pagina dei dettagli della riunione o visualizza tutti i partecipanti. Registra i dati degli utenti attraverso la canalizzazione del calendario, dove i dettagli della riunione del calendario svolgono un ruolo importante, questo consente di convalidare le selezioni per chiamate in ingresso, riunioni di Teams, conferma di partecipazione, ecc.
- **seeMeetingDescription**: aprire la pagina Dettagli riunione o selezionare **Vedi altro** nella descrizione della riunione dalla pagina dei dettagli della riunione. I dati vengono registrati attraverso la canalizzazione del calendario, dove i dettagli della riunione del calendario svolgono un ruolo importante, questo consente di convalidare le selezioni per chiamate in entrata, riunioni di Teams, conferma di partecipazione, ecc.
- **seeRsvpMeetingOptions**: selezionare **Notifica organizzatore** dalla finestra popup di conferma di partecipazione o selezionare le opzioni di **conferma di partecipazione** dalla pagina dei dettagli della riunione.
- **selectActivityType**: acquisisce i movimenti selezionati nell'elemento di alimentazione.
- **selectCalendarDate**: selezionare una data specifica nel controllo selezione data calendario.
- **selectDevice**: selezionare un dispositivo specifico nell'app Visualizza.
- **selectGeneralSetting**: passare alle impostazioni generali.
- **selection**: contatto del dispositivo selezionato o contatto dell'azienda selezionato.
- **selectMeetingChicklet**: riunione.
- **selectMeetingRsvpOption**: selezionare il pulsante **conferma di partecipazione** per scegliere un'opzione.
- **selectMeetingRsvpOptions**: selezionare il pulsante **conferma di partecipazione** per scegliere un'opzione.
- **selectPersonalList**: conferma che l'utente ha eseguito l'esplorazione di un elenco attività personale toccando il pulsante.
- **selectPlannerList**: conferma che l'utente ha eseguito l'esplorazione di un elenco attività condivisa toccando il pulsante.
- **selectSettingOption**: passare alla scheda **Impostazioni** dal menu di scelta rapida.
- **selectTheme**: abilita tema scuro.
- **selectUser**: conferma che un assegnatario è stato selezionato con successo a un'attività.
- **selfLongPress**: pressione lunga su stessi.
- **Send_earlycancelledCQF**: un utente invia commenti e suggerimenti su CQF, modulo di chiamate annullate.
- **send_map_pin_clicked**: un utente invia un percorso statico.
- **Send_ratemycallCQF**: un utente invia il proprio feedback su CQF, modulo Valuta la mia chiamata.
- **Send_ratemyliveeventCQF**: un utente invia il proprio feedback su CQF, modulo Valuta il mio evento live.
- **sendForward**: un utente conferma di inviare un messaggio di inoltro dalla selezione di inoltro.
- **sendImage**: inviare immagine.
- **sendLocation**: inviare posizione.
- **sendMsg**: selezionare **Invia** in risposta.
- **sendRequestBulkClicked**: questa operazione viene registrata una sola volta per ogni richiesta di invio in blocco.
- **sendRequestClicked** - **Richiesta di turno inviata** selezionato.
- **sendVoiceMessage** - il pulsante **Registra** viene rilasciato.
- **Setting/Dismiss**: impostazione dei contatti del dispositivo.
- **settingsNavReadReceiptNotice**: l'utente è passato alle impostazioni dall'avviso di funzionalità.
- **settingsOpened**: questa operazione viene attivata quando il fuso orario del dispositivo dell'utente non corrisponde al fuso orario del team e quindi l'utente passa a impostazioni.
- **shareFile**: viene attivata quando viene selezionato **Condividi file**. Inoltre, consente di verificare se:
  - l'utente è stato in grado di avviare l'operazione di condivisione dei file.
  - l'utente può condividere il file correttamente.
- **shareHistory**: condividi selezione della cronologia selezionato.
- **shareInto**: un utente condivide un elemento da un'altra app in Teams.
- **sharePlanToChat**: Un elenco condiviso viene condiviso manualmente dall'app Attività alla chat di gruppo come quadratino, controlla il quadratino inviato tramite il servizio di messaggistica di backend.
- **sharePPTFromChannels** - **Teams and Channels** è selezionato.
- **sharePPTFromOneDrive** - **OneDrive** è selezionato.
- **shareRecording**: condividere una registrazione.
- **shareScreen**: avviare o arrestare una condivisione dello schermo.
- **shareShift**: le informazioni fornite al momento della condivisione di un turno.
- **shareShiftsClicked**: i dettagli di un turno aperto.
- **shareTray** - **Condividi…** è selezionato nel foglio delle azioni.
- **shiftAssigneeClicked**: la visualizzazione del Calendario turni mostra i dettagli dei turni.
- **shiftDetails**: consente di visualizzare i dettagli di un turno.
- **shiftDetailsCalendar**: l'utente passa ai dettagli del turno.
- **shiftDetailsMyShifts**: toccare **Calendario** dalla scheda **Programmazioni**.
- **shiftDetailsTodaysCoworkers**: nella schermata di registrazione dell’orario in entrata, il pulsate **Inizia** o **Termina pausa** viene selezionato.
- **shortCircuitContactCount**: Il numero di contatti cortocircuito corrispondenti a quelli ricevuti da un recupero dei contatti.
- **showBanner**: numero di volte in cui viene visualizzato il banner **Wi-Fi connesso, Internet non disponibile**.
- **showCard**: toccare i pulsanti sulla scheda. Le schede sono costrutti chiave della piattaforma e misurare il loro utilizzo e modello è necessario per comprendere l'uso della piattaforma, tenendo così d'occhio potenziali problemi dal lato client.
- **shownReadReceiptNotice**: L'utente ha mostrato l'avviso di funzionalità con le opzioni di impostazione.
- **signIn** - **Accedi** viene selezionato nella home page, o viene premuto il pulsante **Accedi**.
- **signUp** - **Crea un account gratuito** o **Iscriviti gratis** è selezionato.
- **simultaneousCallForward** viene attivato quando:
  - viene impostato l’inoltro delle chiamate simultanee.
  - l'inoltro di chiamata simultaneo è abilitato (Ricevo io le chiamate è abilitato e anche lo squillo è impostato).
- **skipVerificationForLink**: un utente THW sceglie di ignorare la verifica.
- **smartReply**: viene selezionato l'interruttore di risposta intelligente.
- **SMSSendMessage**: l'utente invia un messaggio SMS.
- **sortChanged**: si attiva quando l'utente modifica l'ordinamento durante la visualizzazione di un elenco di attività.
- **startEditing** -  pulsante **Modifica** selezionato.
- **startPresentPhoto**: avviare presentazione foto.
- **startPresentVideo**: avviare presentazione video.
- **startPSTNCall** viene attivato a causa di:
  - risultato PSTN nella ricerca globale (persone).
  - chiamate PSTN effettuate da dispositivo contactCard.
  - chiamate PSTN effettuate da callList.
  - Numero DialPSTN con il tastierino numerico.
- **startRecording**: avviare la registrazione.
- **startVoicemailCall** - **Modifica messaggio di saluto della segreteria** selezionato.
- **static_place_selected**: un utente trascina la mappa per selezionare un luogo statico.
- **statusCheckBoxClicked**: si attiva quando l'elemento dell'attività è completato o meno.
- **statusMsgCancel**: un utente annulla la modifica al messaggio di stato.
- **statusMsgExpiry**: un utente imposta la data di scadenza.
- **statusMsgSet**: un utente imposta un nuovo messaggio di stato.
- **statusPageViaContactCard**: un utente accede all'esperienza di composizione dello stato tramite una scheda contatto.
- **statusPageViaHamburger**: un utente accede all'esperienza di composizione dello stato tramite il pulsante Hamburger.
- **stop_location_sharing_logout**: un utente si disconnette dall'app.
- **stopMeetingButton**: il numero di volte in cui un utente esce dalla sala di attesa senza essere ammesso alla riunione.
- **stopPresentPhoto**: interrompere presentazione foto.
- **stopPresentVideo**: interrompere presentazione video.
- **stopRecording**: interrompere registrazione.
- **structuredMeetingsBannerDismiss**: un utente chiude il banner che lo informa sul proprio ruolo nella riunione.
- **stuckOnConnectingDialInSelected** - **Componi** viene selezionato dal cassetto.
- **stuckOnConnectingRetrySelected** - **Riprova** viene selezionato dal cassetto.
- **stuckOnConnectingShownDismissed**: un utente ha ignorato il cassetto.
- **suggested_place_selected**: un utente condivide un percorso statico selezionando una posizione consigliata.
- **switchTeamAction**: un utente cambia team nel marcatempo. Questo dovrebbe attivarsi dopo che l'utente ha selezionato il team a cui desidera passare.
- **switchTeamsDialogTriggered**: un utente visualizza la scheda **Turni**.
- **tabActionCopyLink**: in che modo gli utenti scoprono e utilizzano il collegamento di copia della scheda sui dispositivi mobili.
- **tabActionMoreOptions**: comprendere l'utilizzo dei puntini di sospensione (**...**) dall'interno di una scheda.
- **tabActionOpenInAction**: uso di Apri nel browser. È necessario per capire se gli utenti preferiscono aprire una scheda all'esterno di Teams.
- **tabActionOpenInBrowserFromTab**: informazioni sull'utilizzo di Apri nel browser dall'interno di una scheda per altre opzioni: individuazione e uso.
- **tabActionOpenInTeams**: uso di Apri. È fondamentale per capire se la scheda può essere impostata per impostazione predefinita per essere aperta in Teams.
- **tabActionRemove**: capire in che modo è possibile individuare l'opzione di eliminazione e l'uso della funzionalità.
- **tabActionRemove**: capire quanto è rilevabile la ridenominazione e l'uso della funzionalità.
- **tabActionSetting, Android - aggiornamento**: come individuare e usare la configurazione della scheda nei dispositivi mobili.
- **table**: selezionare una tabella.
- **tabListMoreOptions**: informazioni sull'utilizzo delle altre opzioni per una scheda.
- **tabOpen** :le note che sono andate a buon fine nell'apertura delle schede o se ci sono problemi nel modo in cui le schede si aprono.
- **tabViewed**: viene registrato solo se la richiesta inviata è uno scambio, per le voci nella selezione **Turno Team**.
- **takePhoto**: scattare una foto.
- **takePhotoPicker** - **Scatta foto** selezionato all'interno del riquadro di selezione immagini.
- **tapChicletExpand**: in che modo gli utenti possono visualizzare in anteprima le schede nei dispositivi mobili.
- **tapDatePickerHandle**: espandere il controllo selezione data calendario.
- **tapSettings**: il numero di utenti che riconfigurano le app nei dispositivi mobili.
- **tasksAppLaunchAdaptiveCard**: l'app Attività viene aperta da un adaptivecard in una chat di gruppo, controllare l'avvio dell'app tramite l'URL del servizio IC3.
- **tasksAppLaunchComposeExtension**: l'app attività viene aperta dall'estensione comporre in una chat di gruppo, controllare l'avvio dell'app tramite il servizio MT.
- **tasksAppLaunchDashboard**: l'app attività è aperta dal riquadro dashboard o piano specifico, controllare l'avvio dell'app tramite il servizio MT.
- **tasksAppLaunchDashboard**: l'app attività è aperta dal riquadro dashboard del pulsante **Vedi tutti**, controllare l'avvio dell'app tramite il servizio MT.
- **tasksAppLaunchDefault**: l'app attività viene aperta nel cassetto inferiore, controllare l'avvio dell'app tramite il servizio MT.
- **tabCalendarClicked**: un utente ha scelto un team dalla selezione team.
- **teamChannelChanged**: attivato quando un utente seleziona e passa a un piano dall'elenco dei piani. Inviato solo ad AppInsights, non ad Aria.
- **teamCreate**: un utente seleziona l'opzione per creare un nuovo team.
- **teamEdit**: un utente modifica alcuni aspetti di un team di cui è proprietario o che gestisce.
- **teamNav**: visualizzare opzioni menu per un team.
- **teamsDeviceCallResumed**: un utente con una periferica Bluetooth collegata (dock per telefoni cellulari) riattiva una chiamata in attesa.
- **teamSelectedClicked**: quando un utente seleziona **Team selezionato** da una scheda attività.
- **teamShiftPickerClicked**: quando un utente aggiunge una nuova voce per una pausa. L'evento viene registrato dopo che l'utente ha salvato le modifiche.
- **tenantSwitch**: nel cambio tenant. Metriche sulla riuscita delle funzionalità per l'MTMA (diversi tenant e account), che consente di identificare e correggere i problemi in modo proattivo e di offrire un'esperienza di passaggio uniforme.
- **tenant UnsupportedError**: errore di tenant non supportato (quando un utente visualizza l'errore). Le metriche sulla riuscita delle funzionalità per MTMA (diversi tenant e account), forniscono la telemetria sugli errori di passaggio di account o tenant, in modo che è possibile identificare e correggere i problemi in modo proattivo e offrire un'esperienza di passaggio uniforme.
- **timeClockClicked**: un utente seleziona il pulsante **Marcatempo** nella scheda turni personali.
- **timeOffReasonClicked**: determina se viene citato un motivo per il periodo di ferie.
- **timesheetAddClicked**: quando un utente aggiunge una nota alla modica della pausa. L'evento viene registrato dopo che l'utente ha salvato le modifiche.
 **timesheetBreakAdded**: aggiunta di una nuova voce all’orologio. L'evento viene registrato dopo che le modifiche sono state salvate.
- **timesheetBreakEdited**: quando un utente conferma la scheda attività. L'evento viene registrato quando l'utente preme conferma nel modale.
- **timesheetBreakNoteAdded**: quando un utente elimina la scheda attività. L'evento viene registrato quando l'utente conferma l'eliminazione nel modale.
- **timesheetClockAdded**: quando un utente seleziona Modifica per una scheda attività.
- **timesheetClockEdited**: quando un utente seleziona Salva su una scheda attività modificata.
- **timesheetConfirmed**: quando un utente aggiunge una nota alle modifiche della scheda attività. L'evento viene registrato dopo che l'utente ha salvato le modifiche.
- **timesheetDeleted**: se un utente ha o non ha impostato un promemoria del turno e il numero di minuti prima di un turno che un utente desidera essere avvisato.
- **timesheetEditClicked**: telemetria configurazione utente.
- **timesheetEditSaved**: un utente tocca una scheda attività del profilo di un utente per aprirla.
- **timesheetNoteAdded**: per visualizzare una richiesta di permesso approvata.
- **titleChanged**: si attiva quando il titolo di un elemento dell'attività cambia, si attiva a ogni cambio di carattere.
- **toast**: messaggio toast all’interno dell’app è selezionato.
- **toggleChannelsInChat**: attivare o disattivare la funzionalità. Metriche sulle funzionalità per le chat unificate e l'esperienza di canale.
- **toggleClicked**: è selezionato un interruttore.
- **transferNow** viene attivata quando:
  - un utente seleziona **Trasferisci** > **Trasferisci ora**.
  - la destinazione di trasferimento è impostata su Persona.
  - la destinazione di trasferimento è impostata su Numero di telefono.
- **translateFailed**: traduzione non riuscita (escluso offline). Metriche sulle funzionalità di successo per la traduzione dei messaggi.
- **unansweredCallForward**: viene impostato l’inoltro di chiamata senza risposta. Abilita anche l'inoltro delle chiamate senza risposta (Ricevo io le chiamate è abilitato e Se senza risposta è abilitato).
- **unblockCaller** sblocca:
  - contatti o numeri dal foglio di lavoro.
  - contatto o numero da una scheda contatto.
  - numeri dalle impostazioni.
- **unblockChat**: sbloccare una chat bot.
- **unpinChannel**: rimuovere un canale.
- **unpinSelf**: rimuovere se stessi dal foglio di lavoro.
- **unpinUser**: rimuovere un utente dal foglio di lavoro.
- **unsafeLink**: un collegamento era considerato pericoloso.
- **updatePersonalTask**: conferma che è stata aggiornata correttamente un’attività personale.
- **updatePlaybackSpeedVoicemail**: il valore della velocità di riproduzione della segreteria telefonica è stato modificato.
- **updateTask**: conferma che l'azione di aggiornamento delle attività non è riuscita.
- **updateTaskState**: conferma che lo stato dell'attività è stato aggiornato. Azione.
- **upgrade**: selezionare il pulsante **Aggiorna** nel menu **Altro**.
- **uploadFile**: un utente seleziona **Carica da dispositivo**.
- **uploadSelectedFile** si attiva nelle seguenti circostanze:
  - caricamento file nel canale con successo.
  - caricamento file nella chat con successo.
  - caricamento file nella finestra Rispondi.
  - caricamento file nel chat di gruppo con successo.
  - uso dello scenario di base.
  - scenario iniziale di caricamento nel canale.
  - scenario iniziale di caricamento nella chat.
  - scenario iniziale della fine del caricamento nel canale.
  - caricare un file nella scheda **File** con successo.
  - se viene attivata una richiesta durante il caricamento del file.
  - se il file selezionato viene caricato correttamente.
- **uploadSelectFile**: selezionare un file corretto. Selezionare il pulsante **Carica file**.
- **urgentMessageSelect**: consente di selezionare un messaggio urgente dal menu di priorità di scelta rapida.
- **urgentMessageSend**: invia un messaggio urgente.
- **url**: URL.
- **urlPreview**: anteprima URL.
- **urlPreviewAdd**: aggiungere URL preview.
- **urlPreviewOpen**: aprire anteprima URL.
- **urlPreviewRemove**: anteprima URL rimossa.
- **userConfiguration**: per visualizzare una richiesta di permesso in sospeso.
- **userJoinedViaShareLink**: un utente ha partecipato a una riunione da un collegamento.
- **userLongPress**: pressione lunga su un partecipante.
- **userProfileOpened**: un utente seleziona un'icona di **Utente** per aprire un profilo utente.
- userTimesheetOpened **: un utente seleziona una scheda attività nel profilo di un utente per aprire la scheda attività di quella persona.
- **useWifiForAudioDialog**: un utente seleziona **OK** quando il sistema lo richiede, quando un amministratore ha bloccato le chiamate audio e video da cellulare.
- **useWifiForVideoDialog** viene attivato quando:
  - viene selezionato **OK** quando il sistema lo richiede, quando un amministratore ha bloccato le chiamate video da cellulare.
  - Si sta provando a abilitare il video in una riunione, quando un amministratore l'ha bloccato da cellulare.
  - viene selezionato **OK** quando il sistema lo richiede, quando un amministratore ha bloccato le chiamate il video delle riunioni da cellulare.
- **videoUserDoubleTap**: effettuare un doppio tocco sul video di un partecipante.
- **viewChannelMembers**: visualizzare un elenco dei membri del canale.
- **viewContactCard** ContactCard selezionato da:
  - un elemento di callHistory.
  - un elemento della segreteria telefonica.
  - un elenco chiamate.
- **viewed**: un utente ha visualizzato una pagina.
- **viewFullAllDayMeetingList**: visualizzazione Agenda da dispositivo mobile.
- **viewLobbyFromBanner**: il numero di volte in cui un utente seleziona **Visualizza sala di attesa** da un banner di notifica.
- **viewMeetingDetails**: selezionare il menu **...** nella pagina Dettagli riunione. Riguardante l'uso del menu **Altro** sui calendari per dispositivo mobile.
- **viewMeetingOccurrence**: aprire i dettagli della riunione di un'istanza di una riunione ricorrente. Telemetria per registrare i dati degli utenti attraverso la canalizzazione del calendario, in cui i dettagli della riunione del calendario svolgono un ruolo importante, che permette di convalidare le chiamate in ingresso selezionate, le riunioni di Teams, le conferme di partecipazione e così via.
- **viewMeetingSeries** per registrare il rendering riuscito di una serie di riunioni nelle seguenti circostanze:
  - quando si passa da un'istanza alla pagina dei dettagli della riunione della serie.
  - selezionando **Visualizza serie** dalla pagina dei dettagli della riunione.
- **viewOrgChart**: telemetria di utilizzo di base per l'organigramma.
- **viewRequests**: viene premuto il pulsante **Visualizza richieste**.
- **voiceDataCollectionOptOut**: un utente disattiva la registrazione dal cellulare facendo clic sul banner.
- **voicemail - Nessun AS Assegnato**: un relatore tocca un elemento della segreteria telefonica.
- **whiteboardUsed**: un utente annota su una lavagna (qualsiasi azione nel WebView).
- **wiki - Nessun AS assegnato**: telemetria uso Wiki.

### <a name="scenario"></a>Scenario

> [!NOTE]
> Per informazioni sulle proprietà degli eventiPanelAction, vedere [Proprietà inviate con eventi scenario](#properties-sent-with-scenario-events).

- **create_default_plan_and_nav_to_view**: conferma la corretta creazione di un elenco di attività condivise predefinito e il tempo impiegato da un utente per raggiungere la visualizzazione dopo l'azione.
- **create_personal_plan_and_nav_to_view**: conferma la corretta creazione di un elenco di attività personali e il tempo impiegato da un utente per raggiungere la visualizzazione dopo l'azione.
- **create_personal_task**: conferma la creazione di un elemento di attività personale.
- **create_planner_plan_and_nav_to_view**: conferma la corretta creazione di un elenco di attività condivise e il tempo impiegato da un utente per raggiungere la visualizzazione dopo l'azione.
- **create_planner_task**: conferma la creazione di un elemento di attività personale.
- **delete_personal_plan**: conferma la riuscita dell'eliminazione di un elenco attività personale.
- **delete_personal_task**: conferma la riuscita dell'eliminazione di un elemento di attività personale.
- **delete_planner_plan**: conferma la riuscita dell'eliminazione di un elenco attività condivise.
- **delete_planner_task**: conferma la riuscita dell'eliminazione di un elemento di attività condivise.
- **get_sender_sub_scenario**: ottenere il sottoscenario del mittente secondario nell'attività.
- **load_chat_plans_list**: conferma il recupero dei piani di pianificazione della chat.
- **load_home_page**: conferma il recupero riuscito di elenchi di attività personali e condivisi per la visualizzazione principale.
- **load_personal_task_list**: conferma il recupero riuscito delle attività di un elenco attività personale per la visualizzazione elenco attività.
- **load_shared_task_list**: conferma il recupero riuscito delle attività di un elenco attività condivise per la visualizzazione elenco attività.
- **load_smart_task_list**: conferma il recupero riuscito delle attività di un elenco attività smart per la visualizzazione elenco attività.
- **rename_personal_plan**: conferma la riuscita ridenominazione di un elenco attività personale.
- **rename_planner_plan**: conferma la riuscita ridenominazione di un elenco attività condivise.
- **smart_reply_enabled**: conferma che la risposta intelligente è abilitata per l'utente corrente.
- **smart_reply_received**: conferma la ricezione di un suggerimento per una risposta intelligente.
- **smart_reply_banned**: conferma che non è possibile visualizzare una risposta intelligente per l'utente corrente.
- **update_planner_task_and_nav_to_view**: conferma il corretto aggiornamento di un elemento di attività condivisa e il tempo impiegato da un utente per arrivare alla visualizzazione dopo l'azione.
- **update_personal_task_and_nav_to_view**: conferma il corretto aggiornamento di un elemento dell'attività personale e il tempo impiegato da un utente per arrivare alla vista dopo **updatePlannerTask**. Conferma che un utente ha aggiornato correttamente un'attività in un elenco di attività condivise. 

## <a name="property-lists"></a>Elenchi delle proprietà

### <a name="properties-sent-with-all-events"></a>Proprietà inviate con tutti gli eventi

| Nome della proprietà                    | Descrizione                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | Ora di generazione dell'evento                                                |
| EventInfo_Name                   | Nome evento - Usato per distinguere tra tipi di evento               |
| EventInfo_BaseType/name          | Tipo evento - Usato per distinguere tra tipi di evento in un evento   |
| EventInfo_Source                 | Origine della generazione dell’evento                                       |
| AppInfo_Language                 | Lingua dell'app                                                         |
| AppInfo_ETag                     | ID di sperimentazione assegnato a un utente                                     |
| DeviceInfo_OsBuild               | Versione del sistema operativo                                              |
| UserInfo_Mri                     | Digitare un ID utente                                                       |
| Session_RunId                    | Digitare una sessione ID                                                 |
| DeviceInfo_DetailModel           | Modello del dispositivo                                                  |
| UserInfo_TimeZone                | Fuso orario dell'utente                                                |
| DeviceInfo_OsName                | Nome del sistema operativo del dispositivo                                                       |
| DeviceInfo_NetworkProvider       | Provider di rete di dispositivi                                              |
| DeviceInfo_Model                 | Modello dispositivo                                                         |
| DeviceInfo_NetworkType           | Tipo di rete del dispositivo                                                  |
| UserInfo_Language                | Lingua utente - simile a quella dell'app                              |
| client_ring/UserInfo_Ring        | Anello utente che consente di rilasciare le funzionalità agli Early Adopter           |
| UserInfo_Id                      | ID utente                                                              |
| UserInfo_TenantId                | ID tenant                                                            |
| EventInfo_SdkVersion             | Versione SDK usata per generare l'evento                               |
| DeviceInfo_Id                    | ID dispositivo fornito dal sistema operativo del dispositivo                                      |
| eventpriority                    | Priorità di un evento                                                 |
| DeviceInfo_Make                  | Produttore del dispositivo                                                  |
| AppInfo_Version                  | Versione dell'app                                                   |
| DeviceInfo_OsVersion             | Versione del sistema operativo del dispositivo                                                    |
| Session_Id/SessionId             | ID sessione della richiesta                                            |
| Session_Environment              | Ambiente della sessione                                                  |
| isNetworkIssue                   | Acquisisce informazioni se si è verificato un problema di rete durante l'elaborazione della richiesta |
| UserRole                         | Ruolo utente in un tenant                                                |
| Tenant_Model                     | Verifica se l'account è un account Freemium o Enterprise          |
| licenseType/UserInfo_LicenseType | Tipo di licenza assegnato all'utente                                    |
| UserLocale                       | Impostazioni locali in cui è stato eseguito l'accesso all'app                                |
| Intune_sdkVersion                | Versione di Intune SDK                                            |
| Intune_sdkBundleVersion          | Versione dettagliata di Intune SDK                                   |
| AppInfo_Environment              | Ambiente in cui si accede all'app                         |

### <a name="properties-sent-with-panelaction-events"></a>Proprietà inviate con gli eventi panelaction

| Nome della proprietà         | Descrizione                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | URI della risorsa a cui si accede tramite l'azione dell'utente                  |
| Panel_Uri             | URI del pannello inviato all'utente                             |
| Action_Gesture        | Tipo di gesto eseguito dall'utente nell'app                       |
| Action_ScenarioType   | Raggruppamento delle funzionalità correlate a metriche aziendali       |
| Panel_Type            | Tipo di pannello a cui l'utente ha eseguito l'accesso                                    |
| Action_Outcome        | Esito dell'azione eseguita dall'utente                            |
| Team_Id               | ID del team in cui l'utente ha eseguito l'azione           |
| Module_Type           | Tipo di modulo su cui è stata allocata l'azione dell'utente                        |
| Module_Name           | Nome del modulo su cui è stata allocata l'azione dell'utente                        |
| Module_Summary        | Riepilogo del modulo che ha ospitato l'azione dell'utente                      |
| Thread_Id             | ID del thread a cui l'utente ha eseguito l'accesso                         |
| Panel_PreviousUri     | URI del riquadro precedente                                          |
| Panel_Region          | Area in cui il pannello era collocato nell'app                       |
| Panel_LaunchMethod    | Metodo attraverso cui è stato avviato il pannello                        |
| Panel_PreviousType    | Tipo del riquadro precedente                                         |
| Thread_Type           | Tipo di thread a cui l'utente ha eseguito l'accesso                                    |
| Module_State          | Stato del modulo a cui l'utente ha eseguito l'accesso                               |
| Action_Scenario       | Funzionalità di un gruppo di funzionalità correlate alle metriche aziendali |
| Panel_LaunchSource    | Informazioni sull'origine del pannello che è stato lanciato                  |
| Tab_Type              | Tipo di scheda a cui l'utente ha eseguito l'accesso                                   |
| Team_Type             | Tipo di team a cui l'utente ha eseguito l'accesso                                      |

### <a name="properties-sent-with-panelview-events"></a>Proprietà inviate con eventi panelview

| Panel_Uri          | URI del pannello inviato all'utente                   |
|--------------------|----------------------------------------------------------|
| Panel_Type         | Tipo di pannello a cui l'utente ha eseguito l'accesso                          |
| Team_Id            | ID del team in cui l'utente ha eseguito l'azione |
| Thread_Id          | ID del thread a cui l'utente ha eseguito l'accesso               |
| Panel_PreviousUri  | URI del riquadro precedente                                |
| Panel_Region       | Area in cui il pannello era collocato nell'app             |
| Panel_LaunchMethod | Metodo attraverso cui è stato avviato il pannello              |
| Panel_PreviousType | Tipo del riquadro precedente                               |
| Thread_Type        | Tipo di thread a cui l'utente ha eseguito l'accesso                          |
| Panel_LaunchSource | Informazioni sull'origine del pannello che è stato lanciato        |
| Tab_Type           | Tipo di scheda a cui l'utente ha eseguito l'accesso                         |
| Team_Type          | Tipo di team a cui l'utente ha eseguito l'accesso                            |

### <a name="properties-sent-with-scenario-events"></a>Proprietà inviate con eventi scenario

| Nome della proprietà        | Descrizione |
|----------------------|-------------|
| Scenario_Status      | Stato di uno scenario - Abbandonare/OK/errore |
| Scenario_Step        | Se uno scenario contiene più passaggi con punti di errore diversi, questa proprietà acquisisce i dettagli sul passaggio |
| Scenario_StatusCode  | La proprietà registra il codice di stato dello scenario in base al successo o al fallimento dello scenario |

### <a name="properties-sent-with-trace-events"></a>Proprietà inviate con gli eventi di traccia

| Nome della proprietà | Descrizione                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | Contiene la stringa di errore e i dettagli sui motivi per i quali potrebbe essersi verificato un errore |
