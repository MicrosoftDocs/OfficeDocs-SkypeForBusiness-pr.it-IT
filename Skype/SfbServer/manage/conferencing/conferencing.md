---
title: Gestire i servizi di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Riepilogo: informazioni su come gestire i servizi di conferenza in Skype for Business Server.'
ms.openlocfilehash: 55fd2ff645e6e95199b2558ef494eea019b155bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188960"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Gestire i servizi di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i servizi di conferenza in Skype for Business Server.
  
Questo argomento descrive come gestire i servizi di conferenza. Per altre informazioni su come pianificare e distribuire i servizi di conferenza, vedere [pianificare le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
In Skype for Business Server è possibile gestire i dettagli delle conferenze specificando le impostazioni di configurazione e criteri nel modo seguente. Tieni presente che i termini di conferenza e riunione vengono talvolta usati in modalità intercambiabile. In generale, però, si può pensare a una riunione come a una specifica istanza di conferenza.
  
- **Le impostazioni dei criteri di conferenza** includono una vasta gamma di opzioni di pianificazione e partecipazione, che vanno dal fatto che una riunione possa includere l'audio e il video IP al numero massimo di persone che possono partecipare. È possibile usare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.
    
    Tieni presente che i criteri di conferenza vengono applicati all'utente o al sito e non possono essere applicati a una riunione specifica. Di conseguenza, l'invito alla riunione per la conferenza può essere creato in anticipo alcune settimane, ma i criteri di conferenza restrittivi devono essere applicati all'account Skype for business dell'organizzatore della riunione appena prima dell'inizio della conferenza. 
    
    Se per il ruolo dell'organizzatore delle riunioni viene usato un account dedicato, i criteri di conferenza possono rimanere assegnati a tale account. Se l'organizzatore della riunione usa un account generale Skype for business, il criterio deve essere rimosso al termine della conferenza.
    
- **Le impostazioni di configurazione della riunione** dettano il tipo di riunioni che gli utenti possono creare, oltre a controllare come (o anche se) utenti anonimi e servizi di conferenza telefonica con accesso esterno possono partecipare a queste riunioni. Tieni presente che queste impostazioni influenzano solo le riunioni pianificate. Le configurazioni delle riunioni vengono applicate per ogni pool, per sito o globalmente.
    
- Le **impostazioni di configurazione della conferenza** determinano elementi come la dimensione massima consentita per il contenuto della riunione e gli stampati; quantità massima di larghezza di banda per il servizio di conferenza di condivisione applicazioni limiti di spazio di archiviazione e periodi di scadenza; URL per i download interni ed esterni del client supportato; puntatori a URL interni ed esterni in cui gli utenti possono ottenere assistenza e risorse per i servizi di conferenza; e le porte usate per la condivisione delle applicazioni, l'audio client, i trasferimenti di file e il traffico multimediale.
    
    Queste impostazioni consentono di gestire i server effettivi. Queste impostazioni possono essere impostate solo usando Skype for Business Server Management Shell. 
    
- **Le impostazioni di accesso** esterno consentono di definire le informazioni sul modo in cui gli utenti accedono da un telefono. È possibile specificare alcune delle informazioni di accesso in ingresso, ad esempio numero di accesso, nella scheda conferenze del pannello di controllo e in alcune informazioni per la chiamata in ingresso, ad esempio dial plan, criteri vocali, route e uso PSTN, nella scheda routing vocale del pannello di controllo.
    
- **Le impostazioni dei criteri PIN** consentono di assegnare un nome e definire il pin che i partecipanti usano per l'accesso esterno.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gestire i servizi di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell

Puoi gestire la maggior parte dei criteri di conferenza e delle impostazioni di configurazione usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell. Alcune impostazioni di configurazione sono disponibili solo con Skype for Business Server Management Shell.
  
- Per gestire le impostazioni dei criteri di conferenza:
    
  - Nel pannello di controllo selezionare **conferenza | Criteri di conferenza**.
    
  - In PowerShell cercare i cmdlet **-CsConferencingPolicy** .
    
- Per gestire le impostazioni di configurazione delle riunioni:
    
  - Nel pannello di controllo selezionare **conferenza | Configurazione della riunione**.
    
  - In Skype for Business Server Management Shell cercare i cmdlet **-CsMeetingConfiguration** .
    
- Per gestire le impostazioni per i numeri di accesso per la chiamata in ingresso:
    
  - Nel pannello di controllo selezionare **conferenza | Numero di accesso**esterno.
    
  - In Skype for Business Server Management Shell cercare i cmdlet **-CsDialInConferencing** .
    
- Per gestire le informazioni di accesso esterno, ad esempio dial plan, criteri vocali, route e uso PSTN: 
    
  - Nel pannello di controllo selezionare **conferenza | Routing vocale**.
    
  - In Skype for Business Server Management Shell cercare i cmdlet **-CsDialPlan** e **-CsVoice** .
    
- Per gestire le impostazioni dei criteri PIN:
    
  - Nel pannello di controllo selezionare **conferenza | Criteri PIN**.
    
  - In Skype for Business Server Management Shell cercare i cmdlet **-CsPinPolicy** .
    
- Per gestire le impostazioni di configurazione dei servizi di conferenza, è necessario usare Skype for Business Server Management Shell. Cercare cmdlet **-CsConferencingConfiguration** .
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlet di Skype for Business Server Management Shell

Puoi usare i seguenti cmdlet di Skype for Business Server Management Shell per gestire i servizi di conferenza: 
  
**Impostazioni dei criteri di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri di conferenza configurati per l'uso nell'organizzazione. I criteri di conferenza determinano le caratteristiche e le funzionalità che possono essere usate in una conferenza; Questo include tutti gli elementi che includono o meno la conferenza può includere l'audio e il video IP al numero massimo di persone che possono partecipare a una riunione.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Assegna un criterio per i servizi di conferenza nell'ambito per utente.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea un nuovo criterio di conferenza per l'uso nell'organizzazione.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Rimuove i criteri di conferenza specificati.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica un criterio di conferenza esistente.  <br/> |
   
**Impostazioni di configurazione delle riunioni**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione della riunione attualmente in uso nell'organizzazione. Le impostazioni di configurazione della riunione consentono di stabilire il tipo di riunioni che gli utenti possono creare e di controllare in che modo (o anche se) gli utenti anonimi e i servizi di conferenza telefonica con accesso esterno possono partecipare a queste riunioni.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione della riunione nell'ambito del sito o del servizio. Tieni presente che queste impostazioni influenzano solo le riunioni programmate; non influiscono sulle riunioni ad hoc create facendo clic sull'opzione incontra ora in Skype for business.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una raccolta esistente di impostazioni di configurazione della riunione.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni di configurazione della riunione attualmente in uso nell'organizzazione.  <br/> |
   
**Impostazioni di configurazione per i servizi di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione della conferenza per l'organizzazione. Le impostazioni conferenza determinano elementi come la dimensione massima consentita per il contenuto e gli stampati per conferenze, il periodo di tolleranza del contenuto, ovvero la quantità di tempo che verrà archiviata prima di essere eliminata, e gli URL per i download interni ed esterni della client supportato.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione conferenza.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Rimuove la raccolta specificata delle impostazioni di configurazione della conferenza.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una raccolta esistente di impostazioni di configurazione per i servizi di conferenza.  <br/> |
   
**Impostazioni di configurazione con accesso esterno**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Restituisce informazioni sulle directory conferenza configurate per l'uso nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informazioni sul modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Restituisce informazioni su tutti i numeri di accesso per le conferenze telefoniche con chiamata in ingresso configurati per l'uso nell'organizzazione.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Restituisce le impostazioni di segnalazione DTMF (Dual Tone Multifrequency) usate per i servizi di conferenza telefonica con accesso esterno. DTMF consente agli utenti che effettuano la chiamata a una conferenza di controllare le impostazioni della conferenza, ad esempio per disattivare e riattivare l'audioconferenza o bloccare o sbloccare la conferenza, usando la tastiera del telefono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Restituisce un elenco di lingue, incluse le lingue regionali/minoritarie, supportate per l'uso con le conferenze telefoniche con accesso esterno di Skype for Business Server. Queste lingue vengono usate per inoltrare i messaggi audio e le istruzioni agli utenti che partecipano a una conferenza usando un telefono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Restituisce informazioni sui dial plan usati nell'organizzazione.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Assegna un dial plan a uno o più utenti o gruppi.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa le directory conferenza da Microsoft Office Communications Server 2007 R2 a Skype for Business Server. Ciò consente di garantire l'interoperabilità tra Skype for Business Server e Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Sposta una directory conferenze esistente da un pool all'altro. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea una nuova directory conferenze da utilizzare nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un nuovo numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione per i servizi di conferenza telefonica con accesso esterno. Queste impostazioni determinano in che modo Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno. In particolare vengono restituite informazioni relative alla necessità o meno dei partecipanti di registrare il proprio nome quando partecipano a una conferenza e come (o se) il sistema annuncia che qualcuno ha aderito o lasciato la chiamata.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di segnalazione DTMF (Dual Tone Multifrequency) usate per i servizi di conferenza telefonica con accesso esterno.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un nuovo dial plan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Rimuove una directory conferenze esistente. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Consente di rimuovere un numero di accesso esterno per i servizi di conferenza telefonica esistente.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Consente di rimuovere una o più raccolte di impostazioni di configurazione dei servizi di conferenza telefonica con accesso esterno. Queste impostazioni determinano in che modo Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Rimuove una raccolta esistente di impostazioni di segnalazione DTMF (Dual-Tone Multi-Frequency) usate per i servizi di conferenza telefonica con accesso esterno.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica i valori delle proprietà di un numero di accesso esterno per i servizi di conferenza telefonica esistente. I servizi di conferenza telefonica con accesso esterno offrono agli utenti un modo per usare un telefono "normale", un cellulare o un altro dispositivo nella rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio di una conferenza.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni che determinano il modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica le impostazioni di segnalazione DTMF (Dual Tone Multifrequency) usate per i servizi di conferenza telefonica con accesso esterno.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un dial plan esistente.  <br/> |
   
**Impostazioni dei criteri PIN**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri PIN (client Personal Identification Number) configurati per l'uso nell'organizzazione. L'autenticazione tramite PIN consente agli utenti di accedere a Skype for Business Server fornendo un PIN anziché un nome utente e una password.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Assegna un criterio PIN (client Personal Identification Number) a un utente o un gruppo di utenti.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea un nuovo criterio PIN (client Personal Identification Number).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Rimuove il criterio PIN (Personal Identification Number) specificato.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uno o più criteri PIN (client Personal Identification Number) esistenti.  <br/> |
   
**Altre impostazioni di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Disabilita una sala riunioni di Skype for Business Server. Una sala riunioni è un dispositivo per conferenze progettato per gestire videoconferenze e scenari di collaborazione in piccole sale conferenze. Quando si disattiva un oggetto della sala riunioni, si rimuovono tutti gli attributi di Active Directory specifici di Skype for Business Server assegnati all'account utente che rappresenta la sala riunioni. Tuttavia, l'account utente di Active Directory non viene eliminato.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Abilita una sala riunioni di Skype for Business Server. Per abilitare una sala riunioni, è necessario prima di tutto creare un account utente di Active Directory che rappresenterà il sistema. Tieni presente che, anche se gli oggetti della sala riunioni sono basati sugli account utente, questi oggetti non verranno visualizzati quando Esegui il cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Restituisce informazioni sulla dichiarazione di non responsabilità della conferenza usata nell'organizzazione. La dichiarazione di non responsabilità per la conferenza è un messaggio che viene visualizzato agli utenti che partecipano alla conferenza usando un collegamento ipertestuale, ad esempio gli utenti che incollano un collegamento alla conferenza in un browser, ad esempio Windows Internet Explorer.  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Restituisce informazioni su tutte le sale riunioni di Skype for Business Server configurate per l'uso nell'organizzazione.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Sposta un oggetto della sala riunioni di Skype for Business Server da un pool di registrazione a un altro.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Cancella il testo dall'intestazione e dal corpo della dichiarazione di non responsabilità della conferenza utilizzata nell'organizzazione. La dichiarazione di non responsabilità per la conferenza è un messaggio che viene visualizzato agli utenti che partecipano alla conferenza usando un collegamento ipertestuale, ad esempio gli utenti che incollano un collegamento alla conferenza in un browser, ad esempio Windows Internet Explorer.  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica i valori delle proprietà di una sala riunioni di Skype for Business Server esistente.  <br/> |
   
**Impostazioni di test**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Verifica la capacità di una coppia di utenti di partecipare a una conferenza di condivisione applicazioni.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Test per verificare se un utente può connettersi al proprio provider di servizi di audioconferenza. Un provider di servizi di audioconferenza è una società di terze parti che fornisce le organizzazioni con servizio di conferenza. Tra le altre cose, i provider di servizi di audioconferenza consentono agli utenti ubicati fuori sede e non connessi alla rete aziendale o Internet di partecipare alla parte audio di una conferenza o di una riunione.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Verifica la capacità di una coppia di utenti di partecipare a una conferenza audio/video (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Verifica se una coppia di utenti può partecipare a una conferenza Web di Skype for Business Server che include attività come la condivisione o la visualizzazione di diapositive di PowerPoint, lavagne o sondaggi. Il cmdlet verifica inoltre che il servizio Web Conferencing di Skype for Business Server possa individuare Office Web Apps Server e che un client possa caricare un file di PowerPoint per la trasmissione tramite Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Consente di verificare se un utente può partecipare a una sessione di conferenza telefonica con accesso esterno.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Verifica un numero di telefono in un dial plan (in precedenza noto come profilo della posizione) e restituisce la regola di normalizzazione che verrà applicata al numero e al numero tradotto dopo l'applicazione della regola di normalizzazione.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Verifica la capacità di tre utenti di partecipare a una conferenza di servizi mobili di Skype for Business Server. Il servizio di mobilità consente agli utenti di telefoni cellulari come iPhone e telefoni Windows di eseguire operazioni come messaggi istantanei di Exchange e informazioni sulla presenza; archiviare e recuperare i messaggi vocali internamente anziché con il provider wireless; e approfitta delle funzionalità di Skype for Business Server, come la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno.  <br/> **Nota:** I client che usano MCX non sono supportati in Skype for Business Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Verifica la possibilità di una coppia di utenti di pianificare, partecipare e quindi condurre una conferenza online con l'API Web Unified Communications (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Restituisce le informazioni di diagnostica per le funzionalità di conferenza dati incluse in Skype for Business Server.  <br/> |
   

