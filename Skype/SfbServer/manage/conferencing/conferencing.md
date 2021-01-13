---
title: Gestire le conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Riepilogo: informazioni su come gestire le conferenze in Skype for Business Server.'
ms.openlocfilehash: b1df4a339d7764c86ba76804dc67d1e1f11fc397
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810216"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Gestire le conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire le conferenze in Skype for Business Server.
  
In questo argomento viene descritto come gestire le conferenze. Per ulteriori informazioni su come pianificare e distribuire le conferenze, vedere [Plan for Conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
In Skype for Business Server, è possibile gestire i dettagli delle conferenze specificando le impostazioni di configurazione e dei criteri come indicato di seguito. Si noti che i termini conferenza e riunione vengono talvolta utilizzati in senso intercambiabile. Tuttavia, in generale, è possibile considerare una riunione come un'istanza specifica di servizi di conferenza.
  
- **Le impostazioni dei criteri di conferenza** comprendono una vasta gamma di opzioni di pianificazione e partecipazione, che variano dal fatto che una riunione possa includere audio e video IP per il numero massimo di utenti che possono partecipare. È possibile utilizzare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.
    
    Tenere presente che i criteri di conferenza vengono applicati all'utente o al sito e non possono essere applicati a una riunione specifica. Pertanto, l'invito alla riunione per la conferenza può essere creato alcune settimane prima, ma il criterio di conferenza restrittivo deve essere applicato all'account Skype for business dell'organizzatore della riunione subito prima dell'inizio della conferenza. 
    
    Se si utilizza un account dedicato per il ruolo organizzatore della riunione, i criteri di conferenza possono rimanere assegnati a quell'account. Se l'organizzatore della riunione utilizza un account Skype for business generale, è necessario rimuovere il criterio dopo la fine della conferenza.
    
- **Le impostazioni di configurazione delle riunioni** determinano il tipo di riunioni che gli utenti possono creare, oltre a controllare come (o anche se) gli utenti anonimi e le conferenze telefoniche con accesso esterno possano partecipare a queste riunioni. Si noti che queste impostazioni influiscono solo sulle riunioni pianificate. Le configurazioni delle riunioni vengono applicate per ogni pool, per sito o a livello globale.
    
- Le **impostazioni di configurazione** per le conferenze determinano elementi quali la dimensione massima consentita per il contenuto e gli stampati della riunione; quantità massima di larghezza di banda per il servizio di conferenza di condivisione applicazioni; limiti di spazio di archiviazione e periodi di scadenza; gli URL per i download interni ed esterni del client supportato; puntatori a URL interni ed esterni in cui gli utenti possono ottenere assistenza e risorse per le conferenze; e le porte utilizzate per la condivisione di applicazioni, per l'audio client, per i trasferimenti di file e per il traffico multimediale.
    
    Queste impostazioni consentono di gestire i server effettivi. Queste impostazioni possono essere impostate solo tramite Skype for Business Server Management Shell. 
    
- **Le impostazioni di accesso** esterno consentono di definire le informazioni relative al modo in cui gli utenti si connettono da un telefono. È possibile specificare alcune delle informazioni di accesso esterno, ad esempio il numero di accesso, dalla scheda conferenza del pannello di controllo e alcune informazioni per le chiamate in ingresso, ad esempio dial plan, criteri vocali, route e utilizzo PSTN, dalla scheda routing vocale del pannello di controllo.
    
- **Le impostazioni dei criteri PIN** consentono di denominare e definire il PIN utilizzato dai partecipanti per l'accesso esterno.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gestire le conferenze tramite il pannello di controllo di Skype for Business Server o utilizzando Skype for Business Server Management Shell

È possibile gestire la maggior parte dei criteri di conferenza e delle impostazioni di configurazione utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. Alcune impostazioni di configurazione sono disponibili solo utilizzando Skype for Business Server Management Shell.
  
- Per gestire le impostazioni del criterio di conferenza:
    
  - Nel pannello di controllo, selezionare **conferenza | Criteri di conferenza**.
    
  - In PowerShell, cercare i cmdlet **-CsConferencingPolicy** .
    
- Per gestire le impostazioni di configurazione delle riunioni:
    
  - Nel pannello di controllo, selezionare **conferenza | Configurazione delle riunioni**.
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsMeetingConfiguration** .
    
- Per gestire le impostazioni del numero di accesso esterno:
    
  - Nel pannello di controllo, selezionare **conferenza | Numero di accesso** esterno.
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsDialInConferencing** .
    
- Per gestire le informazioni di accesso esterno, ad esempio dial plan, criteri vocali, route e utilizzo PSTN: 
    
  - Nel pannello di controllo, selezionare **conferenza | Routing vocale**.
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsDialPlan** e **-CsVoice** .
    
- Per gestire le impostazioni del criterio PIN:
    
  - Nel pannello di controllo, selezionare **conferenza | Criterio PIN**.
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsPinPolicy** .
    
- Per gestire le impostazioni di configurazione delle conferenze, è necessario utilizzare Skype for Business Server Management Shell. Cercare i cmdlet **-CsConferencingConfiguration** .
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlet per Skype for Business Server Management Shell

Per gestire i servizi di conferenza, è possibile utilizzare i seguenti cmdlet di Skype for Business Server Management Shell: 
  
**Impostazioni per i criteri di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri conferenza configurati per l'utilizzo nell'organizzazione. I criteri conferenza determinano le funzionalità e le caratteristiche che è possibile utilizzare in una conferenza, ad esempio se includere o meno nella conferenza le funzionalità audio e video IP o il numero massimo di persone che possono partecipare.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Assegna un criterio di conferenza nell'ambito per utente.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea un nuovo criterio relativo alle conferenze da utilizzare all'interno dell'organizzazione.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Rimuove il criterio conferenza specificato.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Consente di modificare un criterio di conferenza.  <br/> |
   
**Impostazioni di configurazione delle riunioni**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione. Le impostazioni di configurazione delle riunioni consentono di definire il tipo di riunioni che gli utenti possono creare e di controllare in che modo (o anche se) gli utenti anonimi e i servizi di conferenza telefonica con accesso esterno possano partecipare a queste riunioni.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle riunioni nell'ambito del sito o del servizio. Si noti che queste impostazioni influiscono solo sulle riunioni pianificate. non influiscono sulle riunioni ad hoc create facendo clic sull'opzione Meet Now in Skype for business.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una raccolta esistente di impostazioni di configurazione delle riunioni.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione.  <br/> |
   
**Impostazioni di configurazione delle conferenze**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione della conferenza per la propria organizzazione. Tali impostazioni determinano aspetti quali la dimensione massima consentita per il contenuto e gli stampati delle conferenze, il periodo di tolleranza (ovvero per quanto tempo il contenuto resterà archiviato prima di essere eliminato) e gli URL per i download interni ed esterni del client supportato.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle conferenze.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Rimuove la raccolta specificata di impostazioni di configurazione di conferenza.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una raccolta esistente di impostazioni di configurazione delle conferenze.  <br/> |
   
**Impostazioni di configurazione delle chiamate in accesso esterno**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Restituisce informazioni sulle directory conferenze configurate per l'utilizzo nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera le informazioni relative al modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Restituisce informazioni su tutti i numeri di accesso per le conferenze telefoniche in ingresso configurati per l'utilizzo nell'organizzazione.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Restituisce le impostazioni della segnalazione DTMF (Dual Tone Multi-Frequency) per le conferenze telefoniche con accesso esterno. La tecnologia DTMF consente agli utenti che accedono dall'esterno a una conferenza di controllarne le impostazioni, ad esempio disattivare o riattivare il proprio audio oppure bloccare e sbloccare la conferenza, mediante la tastiera del telefono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Restituisce un elenco di lingue, incluse le lingue regionali e minoritarie, supportate per l'utilizzo con le conferenze telefoniche con accesso esterno di Skype for Business Server. Queste lingue vengono utilizzate per trasmettere messaggi e istruzioni audio agli utenti che partecipano a una conferenza tramite telefono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Restituisce informazioni sui dial plan utilizzati nell'organizzazione.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Assegna un dial plan a uno o più utenti o gruppi.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa le directory conferenze da Microsoft Office Communications Server 2007 R2 a Skype for Business Server. In questo modo è possibile garantire l'interoperabilità tra Skype for Business Server e Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Sposta una directory conferenze esistente da un pool all'altro. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea una nuova directory conferenze da utilizzare nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un nuovo numero di accesso per le conferenze telefoniche con accesso esterno.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione per le conferenze telefoniche con accesso esterno. Queste impostazioni determinano il modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno. In particolare, vengono restituite informazioni sul fatto che i partecipanti devono o meno registrare il proprio nome quando partecipano a una conferenza e come (o se) il sistema annuncia che un utente ha aderito o ha lasciato la chiamata.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni della segnalazione DTMF (Dual Tone Multi-Frequency) per le conferenze telefoniche con accesso esterno.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un nuovo dial plan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Rimuove una directory conferenze esistente. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Rimuove un numero di accesso esistente per le conferenze telefoniche con accesso esterno.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Rimuove una o più raccolte di impostazioni di configurazione delle conferenze telefoniche con accesso esterno. Queste impostazioni determinano il modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Rimuove una raccolta esistente di impostazioni di segnalazione DTMF (Dual Tone Multi-Frequency) utilizzate per le conferenze telefoniche con accesso esterno.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica i valori delle proprietà di un numero di accesso a conferenze telefoniche con accesso esterno esistente. Le conferenze telefoniche con accesso esterno consentono agli utenti di utilizzare un normale telefono, un cellulare o un altro dispositivo sulla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio di una conferenza.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Consente di modificare le impostazioni che determinano il modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica le impostazioni della segnalazione DTMF (Dual Tone Multi-Frequency) per le conferenze telefoniche con accesso esterno.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un dial plan esistente.  <br/> |
   
**Impostazioni di criteri PIN**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri PIN client configurati per l'utilizzo nell'organizzazione. L'autenticazione del PIN consente agli utenti di accedere a Skype for Business Server specificando un PIN anziché un nome utente e una password.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Assegna un criterio PIN client a un utente o a un gruppo di utenti.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea un nuovo criterio PIN (Personal Identification Number) client.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Rimuove il criterio PIN specificato.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uno o più criteri PIN client esistenti.  <br/> |
   
**Altre impostazioni per i servizi di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Disattiva una sala riunioni di Skype for Business Server. Una sala riunioni è un dispositivo per conferenze progettato per gestire videoconferenze e scenari di collaborazione in piccole sale conferenze. Quando si disabilita un oggetto sala riunioni, vengono rimossi tutti gli attributi di Active Directory specifici di Skype for Business Server assegnati all'account utente che rappresenta la sala riunioni. L'account utente Active Directory tuttavia non viene eliminato.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Consente di abilitare una sala riunioni di Skype for Business Server. Per abilitare una sala riunioni, è necessario innanzitutto creare un account utente di Active Directory che rappresenterà tale sistema. Benché gli oggetti sala riunioni siano basati su account utente, tali oggetti non verranno visualizzati quando si esegue il cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Restituisce informazioni sulla dichiarazione di non responsabilità per le conferenze in uso nell'organizzazione. Tale dichiarazione è un messaggio visualizzato agli utenti che accedono a una conferenza utilizzando un collegamento ipertestuale (ad esempio, incollando un collegamento alla conferenza in un browser come Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Restituisce informazioni su tutte le sale riunioni di Skype for Business Server configurate per l'utilizzo nell'organizzazione.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Sposta un oggetto della sala riunioni di Skype for Business Server da un pool di registrazione a un altro.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Cancella il testo dell'intestazione e del corpo della dichiarazione di non responsabilità relativa alle conferenze utilizzata nell'organizzazione. Tale dichiarazione è un messaggio visualizzato agli utenti che accedono a una conferenza utilizzando un collegamento ipertestuale (ad esempio, incollando un collegamento alla conferenza in un browser come Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica i valori delle proprietà di una sala riunioni di Skype for Business Server esistente.  <br/> |
   
**Impostazioni di test**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Verifica che due utenti possano partecipare a una conferenza di condivisione applicazioni.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Verifica se un utente è in grado di connettersi al proprio provider di servizi di audioconferenza. Un provider di servizi di audioconferenza è una società di terze parti che fornisce servizi di conferenza alle organizzazioni. Tra le altre cose, i provider di servizi di audioconferenza consentono agli utenti che si trovano fuori sede, e non sono connessi alla rete aziendale o Internet, di partecipare alla parte audio di una conferenza o di una riunione.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Verifica se due utenti possono partecipare a una conferenza audio/video (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Verifica se una coppia di utenti può partecipare a una conferenza Web di Skype for Business Server che include attività come la condivisione o la visualizzazione di diapositive, lavagne o sondaggi di PowerPoint. Il cmdlet verifica inoltre che il servizio Web Conferencing di Skype for Business Server possa individuare il server Office Web Apps e che un client possa caricare un file di PowerPoint per la trasmissione da parte del server Office Web Apps.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Verifica se un utente può partecipare a una sessione di conferenza telefonica con accesso esterno.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Verifica un numero di telefono rispetto a un dial plan (precedentemente noto come profilo località) e restituisce la regola di normalizzazione che verrà applicata al numero, nonché il numero convertito dopo l'applicazione della regola di normalizzazione.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Verifica la capacità di tre utenti di partecipare a una conferenza del servizio per dispositivi mobili di Skype for Business Server. Il servizio per dispositivi mobili consente agli utenti di telefoni cellulari, come iPhones e telefoni Windows, di eseguire operazioni quali messaggi istantanei e informazioni sulla presenza di Exchange; archiviare e recuperare i messaggi vocali internamente anziché con il provider di servizi wireless; e approfitta delle funzionalità di Skype for Business Server come la chiamata tramite il lavoro e la conferenza telefonica con accesso esterno.  <br/> **Nota:** I client che utilizzano MCX non sono supportati in Skype for Business Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Verifica la capacità di una coppia di utenti di pianificare, partecipare e quindi condurre una conferenza online utilizzando Unified Communications Web API (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Restituisce informazioni diagnostiche per le funzionalità di conferenza dati incluse in Skype for Business Server.  <br/> |
   

