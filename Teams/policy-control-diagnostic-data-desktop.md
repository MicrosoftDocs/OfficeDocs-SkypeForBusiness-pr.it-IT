---
title: Dati di diagnostica necessari per il client desktop di Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Elenco delle proprietà e degli eventi desktop per i controlli dei criteri di Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbac20caa3f1eff0ead7ef0bf7f11d55b7718903
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136053"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Dati di diagnostica necessari per la versione desktop di Microsoft Teams

Questo articolo contiene un elenco degli eventi desktop di Microsoft Teams e delle proprietà raccolte da ciascun evento.

## <a name="events"></a>Eventi

> [!NOTE]
> Ci sono proprietà comuni per tutti gli eventi sottostanti: per rivederle, consultare [Proprietà inviate per tutti gli eventi](#properties-sent-with-all-events).

### <a name="logging"></a>Registrazione

> [!NOTE]
> Per informazioni sulle proprietà di registrazione degli eventi, vedere [Proprietà inviate con eventi di registrazione](#properties-sent-with-logging-events).

- **adal-anonymous-mac.ts:this.logger.logError** - Registra che si è verificato un errore SSO generico durante l'accesso anonimo in un dispositivo Mac.
- **adalAnonymousUtil.ts:loggingService.getInstance** - Registra una istruzione di errore segnalando che l'app non è riuscita ad avviare l'autenticazione anonima dell'utente.
- **adal-anonymous-windows.ts:this.logger.logError** - Registra che si è verificato un errore SSO generico durante l'accesso anonimo in un dispositivo Windows.
- **adalBase.ts:this.loggingService.logError** - Registra informazioni necessarie per determinare che il profilo utente è null o vuoto.
- **adal-impl-mac.ts:this.loggingService.logError** - Registra l'occorrenza di un problema durante l'analisi della telemetria ricevuta durante l'autenticazione o un errore SSO generico durante l'accesso a un dispositivo Mac.
- **adal-rigel-windows.ts:this.logger.logError** - Registrazione generica che indica che un errore generico SSO si è verificato durante l'accesso al dispositivo della sala riunioni.
- **adal-sso-windows.ts:this.loggingService.logError** - Registra che un errore generico SSO si è verificato durante l'accesso a un dispositivo Windows, e informazioni su errori di avvio del servizio di chat o di autenticazione.
- **appOnlineService.ts:loggingService.getInstance** - Registra che si è verificato un errore causato da impostazioni che non possono essere analizzate durante l'avvio, oppure un errore durante il caricamento di impostazioni di preautorizzate di autenticazione.
- **appStart.ts:loggingService.logError** - Registra che un errore che ha impedito all'applicazione di avviarsi, oppure un errore causato dallo spazio su disco, da un certificato non valido o dall'impossibilità di trovare il certificato corretto, e che l'app è stata riavviata. 
- **browserWindowHttp.ts:this.loggingService.logError** - Registra informazioni per indicare che non è stato possibile aggiornare l'applicazione a causa di problemi con il file system.
- **contextInstallService.ts:loggingService.getInstance** - Registra che si è verificato un errore:
  - durante il tentativo di analizzare o leggere un file o risolvere un URL critico per la funzionalità di installazione contestuale.
  - quando il processo di accorciamento dell'URL tenta di avviare la funzionalità di installazione contestuale.
- **crashManager.ts:loggingService.logError** - Registra informazioni per determinare la causa di un errore in caso di arresto anomalo dell'applicazione.
- **localStorageService.ts:loggingService.getInstance** - Registra che si è verificato un errore quando i dati di avvio essenziali non vengono caricati correttamente per eseguire l'applicazione.
- **logProviders\pageDumpProvider.ts:loggingService.getInstance** - Registra informazioni sull'errore quando l'applicazione si arresta in modo anomalo.
- **multiWindowManager.ts:this.logError** - Registra che si è verificato un errore quando i dati di avvio essenziali non vengono caricati correttamente per eseguire l'applicazione.
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError** - Questo evento registra che un errore si è verificato durante il tentativo di avviare una notifica relativa a un errore.
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance** - Registra che un errore si è verificato durante il tentativo di connettersi a una riunione usando il componente aggiuntivo per riunioni di Outlook.
- **recoveryManager.ts:loggingService.getInstance** - Registra che un errore si è verificato durante la disinstallazione degli aggiornamenti.
- **renderer\startPage\startPage.ts:this.logger.logError** - Registra che si è verificato un errore nella pagina di avvio dell'applicazione.
- **settingsService.ts:loggingService.getInstance** - Registra che si è verificato un errore con le impostazioni dell'applicazione.
- **updateInfo.ts:loggingService.getInstance** - Registra che si è verificato un errore di trasmissione degli aggiornamenti.
- **updatenotification.js:this._loggingService.logError** - Registra che si sono verificati problemi con lo spazio su disco.
- **utility.ts:loggingService.logError** - Registra un errore di accesso ai file (un file nell'applicazione).
- **utility.ts:loggingService.getInstance** - Registra errori legati allo spazio disponibile, alla visualizzazione, agli URL, ai cookie, ai protocolli o alla chiave RegKey sul computer in cui l'applicazione deve essere caricata. 
- **windowmanager.js:this._loggingService.logError** - Registra che si sono verificati problemi con cookie, errori “schermo bianco”, problemi di comunicazione tra desktop e shell, problemi con URL, errori di caricamento dei messaggi delle pagine, errori di rendering dei processi e problemi di connettività di rete.
- **windowmanager.js:loggingService.getInstance** - Registra informazioni per indicare quando la finestra di ripristino non può essere mostrata.

### <a name="outlook-addin"></a>Componente aggiuntivo di Outlook

> [!NOTE]
> Per informazioni sulle proprietà degli eventi del componente aggiuntivo di Outlook, vedere [Proprietà inviate con eventi del componente aggiuntivo di Outlook](#properties-sent-with-outlook-addin-events).

- **joinmeetingoperation** - Registra informazioni necessarie per far partecipare un utente a una riunione.
- **meetingaddinapplifecycle** - Registra informazioni sullo stato dell'app, come Avviata o Chiusa.
- **meetingaddinloadtime** - Registra il tempo necessario per caricare le informazioni sulla riunione da Outlook.
- **openmeetingoperation** - Registra informazioni necessarie per aprire una riunione pianificata.
- **savemeetingoperation** - Registra informazioni necessarie per salvare la riunione senza pianificarla.

### <a name="scenario"></a>Scenario

> [!NOTE]
> Per informazioni sulle proprietà degli eventi scenario, vedere [Proprietà inviate da eventi scenario](#properties-sent-with-scenario-events).

- **desktop_app_load** - Registra informazioni necessarie per stabilire se l'applicazione desktop è avviata, se il servizio non può essere inizializzato, e se può essere inizializzato.
- **desktop_app_not_ready** - Registra informazioni necessarie per determinare se l'applicazione desktop non è pronta a funzionare.
- **desktop_install** - Registra informazioni necessarie per stabilire se l'applicazione desktop è stata installata correttamente, oppure l'installazione non è riuscita.
- **desktop_previous_lifecycle_invalid** - Registra informazioni necessarie per stabilire se l'applicazione desktop si è riavviata dopo essersi arrestata in modo anomalo durante l'esecuzione precedente.

### <a name="tracking"></a>Rilevamento eventi

> [!NOTE]
> Per informazioni sulle proprietà di rilevamento degli eventi, vedere [Proprietà inviate con il rilevamento degli eventi](#properties-sent-with-tracking-events).

- **deeplink_scenario_missing** - Teams è stato avviato da un collegamento deeplink, ma la telemetria/diagnostica non è presente.
- **desktop_app_initialized** - Registra informazioni necessarie per stabilire se l'applicazione si è avviata corretttamento quando è stata inizializzata.
- **desktop_app_quit_exception** - L'applicazione si è arrestata in modo anomalo durante la chiusura.
- **desktop_blankScreenDetected** - Registra informazioni necessarie per determinare gli errori quando l'applicazione desktop mostra una schermata nera.
- **desktop_blankScreenDetectedAfterRepaint** - È stato rilevato che la pagina era vuota durante il tentativo di rendering.
- **desktop_blankScreenRecoveredAfterRepaint** - Ripristino dopo un problema di rendering precedente che impediva la riproduzione della pagina. 
- **desktop_configuration_failed_to_save** - Raccoglie informazioni necessarie per rilevare i problemi di configurazione quando il salvataggio delle impostazioni desktop non è riuscito.
- **desktop_navigation_error_recovery** - Raccoglie informazioni necessarie per rilevare errori di navigazione sul desktop quando una pagina non si apre dopo cinque tentativi.
- **desktop_previous_gpu_crashed** - Registra informazioni necessarie per determinare errori dell'unità di elaborazione grafica quando il desktop si arresta in modo anomalo.
- **desktop_previous_plugin_host_crashed** - Raccoglie informazioni necessarie per determinare problemi relativi agli stack multimediali associati ad arresti anomali dell'applicazione desktop.
- **desktop_recovery_cleared_user_data** - Registra che l'applicazione si è arrestata in modo anomalo più volte, ed è stato necessario svuotare la cache locale per il ripristino.
- **desktop_settings_blank_on_load** - Questo errore indica che le impostazioni dell'applicazione non sono presenti.
- **desktop_settings_failed_to_load** - Raccoglie informazioni necessarie per individuare il motivo per cui le impostazioni desktop non possono essere caricate.
- **desktop_silent_restart** - L'aggiornamento del client è eseguito gradualmente e il client viene aggiornato senza disturbare l'utente.
- **desktop_terminated** - Registra informazioni necessarie per determinare se la comunicazione tra un processo e l'altro si è interrotta quando l'utente ha chiuso l'applicazione desktop.
- **desktop_uncaught_exception** Invocazione di funzione su un oggetto non definito. Provoca arresto anomalo/riavvio applicazione.
- **desktop_write_storage_failed** - Registra informazioni necessarie per determinare gli errori del disco quando l'applicazione desktop non riesce a scrivere sull'unità di archiviazione.
- **registration_failed** - Registra informazioni necessarie per risolvere i problemi di registrazione dei componenti aggiuntivi.
- **registration_success** - Registra informazioni necessarie per determinare se le registrazioni dei componenti aggiuntivi sono andate a buon fine.
- **security_unsupported_ipc_channel** - Il messaggio interprocesso non consentito era in ingresso.
- **sfb_running_not_connected** - Registra che è stato rilevato che l'app Skype for Business non è in esecuzione.
- **sfb_not_running** - Registra che l'operazione “In attesa di risposa” della chiamata a Skype for Business è scaduta.
- **sfb_never_replied** - Registra che non sono state ricevute risposte dalla API durante la comunicazione con Skype for Business.
- **server_error_hit** - Registra un errore degli oggetti pipe IPC durante la comunicazione con Skype for Business.
- **unexpected_sfb_ipc_disconnection** - Registra informazioni necessarie per determinare problemi di connessione al servizio.
- **unregister_failed** - Registra informazioni necessarie per determinare errori di annullamento della registrazione del componente aggiuntivo per le riunioni di Outlook.

## <a name="userbi-panelaction"></a>UserBI panelaction

> [!NOTE]
> Per informazioni sulle proprietà degli eventi UserBI panelaction, vedere [Proprietà inviate con gli eventi UserBI panelaction](#properties-sent-with-userbi-panelaction-events).

- **inlinereply** - Registra informazioni quando un utente risponde a una notifica.
- **toastclick** - Registra un clic dell'utente per passare al messaggio della notifica popup per monitorare il contratto SLA del servizio e caricare la risposta appropriata per la notifica popup.
- **toastdismiss** - Registra informazioni necessarie per determinare errori e ritardi quando l'utente annulla il rendering di una notifica popup.

- **toast_skip** - Registra informazioni necessarie per evitare di trasmettere in ritardo una notifica popup.
- **toasttimeout** - Registra informazioni necessarie per determinare errori e ritardi quando il rendering di una notifica popup è scaduto.

### <a name="userbi-panelview"></a>UserBI PanelView

> [!NOTE]
> Per informazioni sulle proprietà degli eventi UserBI panelview, vedere [Proprietà inviate con gli eventi UserBI panelwiew](#properties-sent-with-userbi-panelview-events).

- **toastshow** - Registra informazioni necessarie per determinare se un avviso popup è stato riprodotto.

## <a name="property-lists"></a>Elenchi delle proprietà

### <a name="properties-sent-with-all-events"></a>Proprietà inviate con tutti gli eventi

| Nome della proprietà                              | Descrizione                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | Ora di generazione dell'evento                                              |
| EventInfo_Name                             | Nome evento - Usato per distinguere tra tipi di evento             |
| EventInfo_BaseType/name                    | Tipo evento - Usato per distinguere tra tipi di evento in un evento |
| EventInfo_Sequence                         | Sequenza dell'evento                                              |
| userAgent                                  | Stringa agente browser                                               |
| userpdclevel                               | Impostazione di controllo della privacy dell'utente                           |
| eventpdclevel                              | Livello di categorizzazione del controllo della privacy dell'evento             |
| AppInfo_Language                           | Lingua dell'app                                                       |
| clientType/AppInfo_ClientType              | Tipo di client in cui l'app è in esecuzione                               |
| environment/AppInfo_Environment            | Ambiente di progettazione usato per la richiesta dell'utente               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | Versione dell'app                               |
| buildtime                                  | timestamp che indica che l'app è stata creata in sistemi ingegneristici            |
| osversion/DeviceInfo_OsVersion             | Versione del sistema operativo                                                         |
| AppInfo_ProcessArchitecture                | Architettura di sistema (32/64 bit)                                  |
| preferredLocales                           | impostazione internazionale preferita dell'utente                                      |
| locale/AppInfo_Locale                      | Impostazione internazionale dell'app                                                         |
| os/DeviceInfo_OsName                       | Nome del sistema operativo                                                            |
| UserInfo_Language                          | Lingua utente corrente                                             |
| UserInfo_Id                                | ID utente                                                            |
| UserInfo_TenantId/TenantId                 | ID tenant                                                          |
| ring/UserInfo_Ring                         | Concetto che aiuta a distribuire le applicazione in modo graduale          |
| area geografica                                     | Regione del data center usato per la richiesta dell'utente                       |
| UserInfo_ConfigIds/UserInfo_Etag           | ID che consente di identificare gli utenti in diversi esperimenti/rollout     |
| DeviceInfo_BrowserName                     | Nome del browser                                                       |
| DeviceInfo_BrowserVersion                  | Versione del browser                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | ID che consente di identificare il dispositivo                                  |
| totalMemory                                | Memoria hardware del dispositivo                                      |
| cores                                      | Memorie centrali hardware del dispositivo                                       |
| cpuspeed                                   | Velocità della CPU hardware del dispositivo                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | Architettura CPU del dispositivo                                     |
| UserRole                                   | Aiuta a identificare il ruolo dell'utente in un tenant                               |
| DeviceInfo_WindowsMode                     | Consente di identificare la modalità di sicurezza di Windows                               |
| desktopSession/Session_Id                  | Consente di identificare una sessione                                           |
| dbOpen                                     | Acquisisce lo stato del database locale                               |
| UserInfo_Upn                               | Hash unidirezionale dell'identificatore utente                                  |

### <a name="properties-sent-with-logging-events"></a>Proprietà inviate con gli eventi registrati

| Nome della proprietà         | Descrizione                                                        |
|-----------------------|--------------------------------------------------------------------|
| messaggio               | Acquisisce un messaggio dettagliato sul log                          |

### <a name="properties-sent-with-scenario-events"></a>Proprietà inviate con eventi scenario

| Nome della proprietà                     | Descrizione                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | Stato di uno scenario                                                               |
| Scenario_Step                     | Passaggio di uno scenario                                                                 |
| sequence                          | Numero di sequenza dello scenario                                                    |
| delta                             | Il tempo necessario per completare diversi passaggi di uno scenario                               |
| elapsed                           | Tempo trascorso dall'avvio dello scenario                                                    |
| scenario                          | Identificazione univoca di uno scenario                                                       |
| Scenario_Name                     | Nome dello scenario                                                               |
| errorInfo                         | Informazioni sull'errore che potrebbe essersi verificato durante uno scenario                       |
| session                           | ID univoco sessione                                                                  |
| freeMemory                        | Acquisisce la memoria libera disponibile                                                     |
| processMemory                     | Acquisisce la memoria del processo                                                            |
| scenarioDelta                     | Acquisisce il tempo trascorso tra 2 passaggi di uno scenario                                   |
| Session_DesktopId                 | ID univoco sessione                                                                  |
| machineLocked                     | Rileva se il computer era bloccato o no                                          |
| windowIsVisible                   | Rileva se la finestra dell'app era visibile per l'utente                                      |
| appStates/webAppStates            | registra un elenco di stati dell'app. Questo è utile per l'analisi dell'arresto anomalo, perché è possibile vedere quale era lo stato dell'app |
| crashDesktopSession               | Acquisisce l'ID della sessione arrestata in modo anomalo                                                 |
| appRuntime                        | Acquisisce il tempo di esecuzione dell'app                                                        |
| diagnosticEvents                  | Ultimi 50 eventi di diagnostica dell'app web prima dell'arresto anomalo dell'app                                 |
| attività                        | Nomi degli ultimi 50 scenari utente che si sono verificati prima dell'arresto anomalo                            |
| crashSession                      | Acquisisce l'ID della sessione arrestata in modo anomalo                                                 |
| crashId                           | Acquisisce l'ID della sessione arrestata in modo anomalo                                                 |
| isPreviousLifecycleValid          | Acquisisce se l'app è stata avviata e chiusa correttamente             |
| isSettingValid                    | Acquisisce se le impostazioni di preautenticazione sono valide                                                 |
| rollbackReason                    | Motivo per cui è stato eseguito il rollback dell'app                                            |
| deeplinkType                      | Tipo di deeplink                                                               |
| watchdogCrash                     | Acquisisce se l'arresto anomalo dell'app è stato causasto da un blocco                                                    |
| protocolli                         | Protocollo usato per eseguire l'app.                                                    |
| electronBuild                     | Versione build dell'app Electron                                                      |
| distribution                      |  Acquisisce se Teams è stato installato tramite file EXE, MSI, DMG, O PKG, ecc.                    |
| updateTimeOfDay                   | Orario in cui l'app è stata aggiornata                                                           |
| launchPath                        | Acquisisce se Team è stato installato in %LOCALAPPDATA%, %PROGRAMFILES%, o in altre posizioni   |
| loggedIn                          | Se l'utente ha eseguito l'accesso                                                          |
| envType/complianceEnvironmentType | Cloud commerciale o privato (p. es. DoD, GCC-High, ecc.)                              |
| cpuusage                          | Utilizzo CPU                                                                          |
| installationSource                | Tipo di installazione                                                      |
| adalVersion                       | Versione della libreria di autenticazione                                                        |
| asyncStart                        | Uso dell'avvio sincrono o asincrono da parte dell'app                                 |
| attempts                          | Numero di tentativi di verifica online eseguiti dall'utente prima di visualizzare una schermata di blocco |

### <a name="properties-sent-with-tracking-events"></a>Proprietà inviate con gli eventi di verifica

| Nome della proprietà                      | Descrizione                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | Acquisisce il nome dell'evento di verifica                                              |
| numVisibleNotifications            | Numero di notifiche dell'applicazione visibili                                      |
| giphyEnabled                       | Se il servizio Giphy era abilitato                                                |
| errore                              | Acquisisce dettagli di errore correlati all'evento di verifica                             |
| method                             | Metodo procollo GET o POST                                                      |
| channel                            | Acquisisce il canale di comunicazione tra processi all'interno dell'app                      |
| windowTitle                        | Tipo di finestra di visualizzazione associato all'evento                                     |
| messaggio                            | Il tipo di messaggio di errore                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | Acquisisce l'ID univoco per le finalità di debug della sessione |
| responseCode                       | Acquisisce il codice di risposta per la chiamata di servizio                                      |
| errorUrl                           | L'URL che non è stato caricato                                                      |
| errorCode                          | Acquisisce il codice di errore                                                              |
| ssoEventData                       | Stato di autenticazione e stato                                                  |
| correlationId                      | ID per correlare eventi sul lato servizio per finalità di debug                      |
| errorDescription                   | Acquisisce la descrizione di errorCode                                            |
| source                             | Il metodo di ottenimento dell'app Teams e il tipo di pacchetto da cui Teams è stato installato       |
| windowIsDestroyed                  | Stato true/false della finestra dell'applicazione durante l'evento                             |
| windowIsFocused                    | Stato true/false della finestra dell'applicazione durante l'evento                             |
| windowIsVisible                    | Acquisisce se l'applicazione era visibile durante l'evento si è verificato                                  |
| windowIsMinimized                  | Stato true/false della finestra dell'applicazione durante l'evento                             |
| windowIsMaximized                  | Stato true/false della finestra dell'applicazione durante l'evento                             |
| windowIsFullscreen                 | Stato true/false della finestra dell'applicazione durante l'evento                             |
| distSrc                            | Acquisisce l'origine di distribuzione dell'accesso dell'utente all'app                    |
| retries                            | Conteggio dei nuovi tentativi durante la connessione a un endpoint                            |
| uses_slimcore                      | Vero o falso se la chiamata via web usa slimcore                                      |
| persistCookieExpiresIn             | Tempo di validità rimanente del cookie dell'applicazione web                             |
| tenantName                         | Nome del tenant per l'utente dell'applicazione                                       |
| appStartReason                     | Modalità di avvio della sessione dell'applicazione, p. es. avvio dell'utente, dopo un aggiornamento, ecc. |
| machineLocked                      | Acquisisce se il computer era bloccato o no durante l'evento                        |
| dati                               | Acquisisce i dati tecnici per l'indagine dello scenario                               |
| appRuntime                         | Acquisisce il tempo di esecuzione dell'app                                                      |
| attività                         | Nomi degli ultimi 50 scenari utente che si sono verificati prima dell'arresto anomalo                          |
| timeSinceActivity                  | Tempo trascorso dall'ultima attività dell'utente                                                    |
| appStates                          | Registra un elenco degli stati dell'applicazione desktop, che è utile per le analisi degli anomali perché mostra lo stato in cui si trovava l'applicazione desktop |
| timeSinceAppState                  | Tempo trascorso dalla modifica dello stato dell'app                                                 |
| webAppStates                       | Registra un elenco degli stati del client web, che è utile per le analisi degli anomali perché mostra lo stato in cui si trovava il client web |
| timeSinceWebAppState               | Tempo trascorso dalla modifica dello stato dell'app web                                             |
| diagnosticEvents                   | Ultimi 50 eventi di diagnostica dell'app web prima dell'arresto anomalo dell'app                               |
| timeSinceLastDiagnosticEvent       | Tempo trascorso dall'ultimo evento di diagnostica inviato                                            |
| timeSinceSecondLastDiagnosticEvent | Tempo trascorso dal penultimo evento di diagnostica inviato                                     |
| appInitialized                     | Se l'applicazione si è avviata                                               |
| targetVersion                      | La versione dell'applicazione sarà aggiornata a                                    |
| port                               | Numero porta messaggio internet                                                     |
| originalUrl                        | Posizione originale della pagina riprodotta                                         |
| deeplinkId                         | Identificatore univoco globale per il tipo di destinazione del collegamento di Teams                                           |
| appSessionEnd                      | Se un errore si è verificato alla fine della sessione dell'applicazione                             |
| eventData                          | Acquisisce lo stato del computer e la configurazione dell'app per facilitare il debug in caso di problemi        |
| deeplinkType                       | Tipo di deeplink (chat, riunione, canale)                                    |
| previousUpdateUrl                  | Posizione da cui l'applicazione ha recuperato l'aggiornamento                        |
| previousUpdateVersion              | Ultimo versione a cui l'applicazione è stata aggiornata                                          |
| previousUpdateTime                 | Ultimo aggiornamento dei file binari dell'applicazione                                      |
| protocollo                           | Tipo di gestore del collegamento, come file o immagine                                     |
| file                              | Tipo di file associato all'evento, come cache dell'applicazione o cache della GPU    |
| Perf_WorkingSetSizeKB              | Dimensioni della cache di memoria                                                             |
| isTimeboxingWebAppInitialize       | Se l'app è stata inizializzata prima della scadenza del contatore della casella del tempo                          |
| isExp                              | Se la versione dell'app in uso fa parte di un esperimento                          |
| deviceType                         | Acquisisce il tipo di dispositivo                                                      |
| sanitizedErr                       | Acquisisce la versione purificata delle informazioni sull'errore                              |
| rigelVersion                       | Acquisisce la versione del dispositivo Rigel                                                 |
| DeviceInfo_OsSku                   | Acquisisce le informazioni SKU del sistema operativo                                                      |
| isLoggedOut                        | Acquisisce se l'utente è disconnesso                                               |
| complianceEnvironmentType          | Cloud commerciale o privato (p. es. DoD, GCC-High, ecc.)                           |
| restartTimes                       | Ora esatta dei riavvii precedenti                                                 |
| Skype_ResultCode                   | Acquisisce il risultato della comunicazione interoperativa tra Skype e Teams                 |
| cpumodel                           | Acquisisce il modello di CPU                                                            |
| isSlimCoreRunningOutproc           | Se il componente Slimcore sta eseguendo un processo                         |
| isSlimCoreStartedAsync             | Tipo di lancio dello stack audio video (A/V) interno                               |
| networkState                       | Acquisisce lo stato della rete                                                    |
| desktopBuildAge                    | Età della build dell'applicazione al momento dell'evento                                   |
| vdiMode                            | Acquisisce se l'app viene eseguita in modalità VDI                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>Proprietà inviate con eventi UserBI panelview

| Proprietà           | Descrizione                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | URI del pannello inviato all'utente                   |
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

### <a name="properties-sent-with-userbi-panelaction-events"></a>Proprietà inviate con gli eventi UserBI panelaction

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
| Module_Summary        | Riepilogo del modulo che ha gestito l'azione dell'utente                       |
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

### <a name="properties-sent-with-outlook-addin-events"></a>Proprietà inviate con eventi dei componenti aggiuntivi di Outlook

| Nome della proprietà                   | Descrizione                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | Il componente aggiuntivo confronta l'account con l'account di Teams per verificare se la creazione è consentita; l'evento viene inviato se il confronto non riesce |
| AccountComparisonSuccessful     | Il componente aggiuntivo confronta l'account con l'account di Teams per verificare se la creazione è consentita; l'evento viene inviato se il confronto va a buon fine |
| AdalVersion                     | Versione della libreria di autenticazione usata                               |
| AddinBitness                    | Versione del componente aggiuntivo                                                         |
| AddinLanguage                   | Lingue delle stringe del componente aggiuntivo usate                                     |
| AggregatorSetupCompletedTime    | Tempo di configurazione per lo strumento di caricamento del componente aggiuntivo                                              |
| AppDomainCreatedTime            | Ora in cui lo strumento di caricamento del componente aggiuntivo inizializza il dominio dell'app                            |
| AppointmentDisplayTime          | Ora in cui è stato visualizzato l'elemento dell'appuntamento durante la creazione di una riunione |
| AuthenticationCompletedTime     | Ora in cui è stata fornita l'autenticazione per una determinata richiesta            |
| ConnectionMode                  | Indica la modalità di connessione dell'account di Exchange primario dell'utente     |
| ConnectionStartedTime           | Ora in cui Outlook chiama OnConnection                                     |
| ErrorDetails                    | Acquisisce i dettagli dell'errore                                            |
| ErrorName                       | Acquisisce il nome dell'errore                                               |
| ExchangeVersion                 | Acquisisce la versione di Exchange                                             |
| IsSmtpFormatError               | Indirizzo SMTP del gruppo                                                    |
| IsTeamsRunning                  | Acquisisce se è in esecuzione un processo di Teams                             |
| IsTeamsUserLoggedOut            | Acquisisce se l'utente è disconnesso da Teams                              |
| LanguageSetupCompletedTime      | Ora in cui è stata completata la configurazione della lingua                               |
| ManagedConnectTime              | Ora in cui il componente aggiuntivo gestito ha ricevuto il callback di connessione               |
| ManagedOnStartupTime            | Ora di avvio della procedura gestita di esecuzione                                    |
| MTFetchCompleted                | Ora di completamento della richiesta per le opzioni delle riunione MT                        |
| NetFrameworkVersion             | Versione di .NET framework in uso                                                      |
| NetworkAvailable                | Disponibilità della rete                                                     |
| OperationStartTime              |  Ora di inizio di operazioni diverse                                  |
| OsBitness                       | Numero di bit del sistema operativo                                                            |
| OutlookLanguage                 | Acquisisce la lingua dell'app Outlook                                     |
| OutlookVersion                  | Acquisisce la versione dell'app Outlook                                          |
| OwnerResolutionTime             | Tempo necessario per risolvere il proprietario della riunione                                        |
| ParseResponseCompletedTime      | Tempi di analisi della risposta completata                                  |
| RecipientResolutionError        | Dettagli di errore per la risoluzione di un destinatario                                 |
| RecipientsResolutionTime        | Tempo totale di risoluzione di tutti i destinatari                                     |
| RehydrateCompletedTime          | Ora in cui le proprietà sono lette da Outlook                               |
| SaveToOutlookCompletedTime      | Ora in cui le proprietà sono salvate in Outlook                                |
| ServiceRequestStartTime         | Ora di inizio della richiesta di servizio                                        |
| ServiceResponseReceiveTime      | Tempo di risposta del servizio                                        |
| SettingsInitializeCompletedTime | Ora di inizializzazione delle impostazioni                                           |
| SetupLoggingCompletedTime       | Tempo di configurazione dell'autenticazione                                             |
| ShutdownBeginTime               | Ora di inizio della chiusura del componente aggiuntivo                                       |
| ShutdownCompletedTime           | Ora di completamento dell'operazione di chiusura                                             |
| StartupBeginTime                | Ora di inizio dell'avvio del componente aggiuntivo                                        |
| StartupCompletedTime            | Ora di completamento dell'operazione di avvio                                              |
| TeamsDeployment                 | Distribuzione del client di Teams (Dev, Prod)                                   |
| TeamsRing                       | Anello dell'utente corrente autenticato nel client di Teams                            |
| TeamsVersion                    | Acquisisce la versione dell'app Teams                                            |
| TelemetrySetupCompletedTime     | Ora di completamento della configurazione della telemetria                                   |
| UpnMismatch                     | Rilevamento delle mancate corrispondenze tra Outlook e Teams                  |
| UserDomain                      | Dominio dell'utente                                                       |
| ViewUpdatedTime                 | Ora di aggiornamento della visualizzazione                                           |
