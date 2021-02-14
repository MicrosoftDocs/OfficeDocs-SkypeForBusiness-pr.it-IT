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
  
In questo argomento viene descritto come gestire le conferenze. Per ulteriori informazioni su come pianificare e distribuire le conferenze, vedere Pianificare le conferenze [in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Distribuire le conferenze in Skype for Business [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
In Skype for Business Server puoi gestire i dettagli delle conferenze specificando le impostazioni di configurazione e dei criteri come indicato di seguito. Si noti che i termini conferenza e riunione vengono talvolta utilizzati in modo intercambiabile. In generale, tuttavia, è possibile pensare a una riunione come a un'istanza specifica delle conferenze.
  
- **Le impostazioni dei** criteri di conferenza includono un'ampia gamma di opzioni di pianificazione e partecipazione, dalla possibilità o meno a una riunione di includere audio e video IP al numero massimo di persone che possono partecipare. È possibile utilizzare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.
    
    Si noti che i criteri di conferenza vengono applicati all'utente o al sito e non possono essere applicati a una riunione specifica. Pertanto, l'invito alla riunione può essere creato con alcune settimane di anticipo, ma i criteri restrittivi per le conferenze devono essere applicati all'account Skype for Business dell'organizzatore della riunione subito prima dell'inizio della conferenza. 
    
    Se per il ruolo Organizzatore riunione viene utilizzato un account dedicato, il criterio di conferenza può rimanere assegnato a tale account. Se l'organizzatore della riunione usa un account Skype for Business generale, il criterio deve essere rimosso al termine della conferenza.
    
- **Le** impostazioni di configurazione delle riunioni determinano il tipo di riunioni che gli utenti possono creare, oltre a controllare come (o anche se) gli utenti anonimi e gli utenti di conferenze telefoniche con accesso esterno possono partecipare a queste riunioni. Si noti che queste impostazioni influiscono solo sulle riunioni pianificate. Le configurazioni delle riunioni vengono applicate per pool, per sito o a livello globale.
    
- **Le impostazioni di configurazione** delle conferenze determinano aspetti quali la dimensione massima consentita per il contenuto e gli stampati delle riunioni; quantità massima di larghezza di banda per il servizio Conferenza di condivisione applicazioni; limiti di archiviazione e periodi di scadenza; gli URL per i download interni ed esterni del client supportato; puntatori a URL interni ed esterni in cui gli utenti possono ottenere la Guida e le risorse per le conferenze; e le porte utilizzate per la condivisione di applicazioni, l'audio del client, i trasferimenti di file e il traffico multimediale.
    
    Queste impostazioni consentono di gestire i server effettivi. Queste impostazioni possono essere impostate solo tramite Skype for Business Server Management Shell. 
    
- **Le impostazioni di accesso remoto** consentono di definire le informazioni su se e come gli utenti eccedono da un telefono. Alcune delle informazioni di accesso esterno, ad esempio il numero di accesso, vengono specificate dalla scheda Servizi di conferenza del Pannello di controllo e alcune informazioni sull'accesso esterno, ad esempio dial plan, criteri vocali, route e utilizzo PSTN, dalla scheda Routing vocale del Pannello di controllo.
    
- **Le impostazioni dei criteri** PIN consentono di assegnare un nome e definire il PIN utilizzato dai partecipanti per l'accesso esterno.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gestire le conferenze utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell

È possibile gestire la maggior parte dei criteri di conferenza e delle impostazioni di configurazione utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. Alcune impostazioni di configurazione sono disponibili solo tramite Skype for Business Server Management Shell.
  
- Per gestire le impostazioni dei criteri di conferenza:
    
  - Nel Pannello di controllo selezionare Servizio di **| Criteri conferenza**.
    
  - In PowerShell, cercare i cmdlet **-CsConferencingPolicy.**
    
- Per gestire le impostazioni di configurazione delle riunioni:
    
  - Nel Pannello di controllo selezionare Servizio di **| Configurazione riunione**.
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsMeetingConfiguration.**
    
- Per gestire le impostazioni dei numeri di accesso remoto:
    
  - Nel Pannello di controllo selezionare Servizio di **| Numero di accesso remoto**.
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsDialInConferencing.**
    
- Per gestire le informazioni di accesso remoto, ad esempio dial plan, criteri vocali, route e utilizzo PSTN: 
    
  - Nel Pannello di controllo selezionare Servizio di **| Routing vocale.**
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsDialPlan** e **-CsVoice.**
    
- Per gestire le impostazioni dei criteri pin:
    
  - Nel Pannello di controllo selezionare Servizio di **| Criteri PIN**.
    
  - In Skype for Business Server Management Shell, cercare i cmdlet **-CsPinPolicy.**
    
- Per gestire le impostazioni di configurazione delle conferenze, è necessario utilizzare Skype for Business Server Management Shell. Cercare i **cmdlet -CsConferencingConfiguration.**
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlet di Skype for Business Server Management Shell

È possibile utilizzare i seguenti cmdlet di Skype for Business Server Management Shell per gestire le conferenze: 
  
**Impostazioni dei criteri di conferenza**

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
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione. Le impostazioni di configurazione delle riunioni consentono di determinare il tipo di riunioni che gli utenti possono creare e di controllare come (o anche se) gli utenti anonimi e gli utenti di conferenze telefoniche con accesso esterno possono partecipare a tali riunioni.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle riunioni nell'ambito del sito o del servizio. Si noti che queste impostazioni influiscono solo sulle riunioni pianificate; non influiscono sulle riunioni ad hoc create facendo clic sull'opzione Riunione ora in Skype for Business.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una raccolta esistente di impostazioni di configurazione delle riunioni.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione.  <br/> |
   
**Impostazioni di configurazione delle conferenze**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione delle conferenze per l'organizzazione. Tali impostazioni determinano aspetti quali la dimensione massima consentita per il contenuto e gli stampati delle conferenze, il periodo di tolleranza (ovvero per quanto tempo il contenuto resterà archiviato prima di essere eliminato) e gli URL per i download interni ed esterni del client supportato.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle conferenze.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Rimuove la raccolta specificata di impostazioni di configurazione di conferenza.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una raccolta esistente di impostazioni di configurazione delle conferenze.  <br/> |
   
**Impostazioni di configurazione per l'accesso remoto**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Restituisce informazioni sulle directory conferenze configurate per l'utilizzo nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informazioni sulla risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Restituisce informazioni su tutti i numeri di accesso alle conferenze telefoniche con accesso esterno configurati per l'utilizzo nell'organizzazione.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Restituisce le impostazioni della segnalazione DTMF (Dual Tone Multi-Frequency) per le conferenze telefoniche con accesso esterno. La tecnologia DTMF consente agli utenti che accedono dall'esterno a una conferenza di controllarne le impostazioni, ad esempio disattivare o riattivare il proprio audio oppure bloccare e sbloccare la conferenza, mediante la tastiera del telefono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Restituisce un elenco di lingue, incluse le lingue regionali/di minoranza, supportate per l'uso con le conferenze telefoniche con accesso remoto di Skype for Business Server. Queste lingue vengono utilizzate per trasmettere messaggi e istruzioni audio agli utenti che partecipano a una conferenza tramite telefono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Restituisce informazioni sui dial plan utilizzati nell'organizzazione.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Assegna un dial plan a uno o più utenti o gruppi.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa le directory conferenze da Microsoft Office Communications Server 2007 R2 a Skype for Business Server. Ciò consente di garantire l'interoperabilità tra Skype for Business Server e Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Sposta una directory conferenze esistente da un pool all'altro. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea una nuova directory conferenze da utilizzare nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un nuovo numero di accesso per le conferenze telefoniche con accesso esterno.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle conferenze telefoniche con accesso esterno. Queste impostazioni determinano la risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto. In particolare, vengono restituite informazioni sulla necessità o meno ai partecipanti di registrare il proprio nome durante la partecipazione a una conferenza e su come (o se) il sistema annuncia che qualcuno si è unito o ha lasciato la chiamata.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni della segnalazione DTMF (Dual Tone Multi-Frequency) per le conferenze telefoniche con accesso esterno.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un nuovo dial plan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Rimuove una directory conferenze esistente. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Rimuove un numero di accesso esistente per le conferenze telefoniche con accesso esterno.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Rimuove una o più raccolte di impostazioni di configurazione delle conferenze telefoniche con accesso esterno. Queste impostazioni determinano la risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Rimuove una raccolta esistente di impostazioni di segnalazione DTMF (Dual Tone Multi-Frequency) utilizzate per le conferenze telefoniche con accesso esterno.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica i valori delle proprietà di un numero di accesso a conferenze telefoniche con accesso esterno esistente. Le conferenze telefoniche con accesso esterno consentono agli utenti di utilizzare un normale telefono, un cellulare o un altro dispositivo sulla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio di una conferenza.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni che determinano la risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica le impostazioni della segnalazione DTMF (Dual Tone Multi-Frequency) per le conferenze telefoniche con accesso esterno.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un dial plan esistente.  <br/> |
   
**Impostazioni dei criteri PIN**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri PIN client configurati per l'utilizzo nell'organizzazione. L'autenticazione PIN consente agli utenti di accedere a Skype for Business Server fornendo un PIN anziché un nome utente e una password.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Assegna un criterio PIN client a un utente o a un gruppo di utenti.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea un nuovo criterio PIN client.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Rimuove il criterio PIN specificato.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uno o più criteri PIN client esistenti.  <br/> |
   
**Altre impostazioni di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Disabilita una sala riunioni di Skype for Business Server. Una sala riunioni è un dispositivo per conferenze progettato per gestire videoconferenze e scenari di collaborazione in piccole sale conferenze. Quando si disabilita un oggetto sala riunioni, si rimuovono tutti gli attributi di Active Directory specifici di Skype for Business Server assegnati all'account utente che rappresenta la sala riunioni. L'account utente Active Directory tuttavia non viene eliminato.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Abilita una sala riunioni di Skype for Business Server. Per abilitare una sala riunioni, è necessario innanzitutto creare un account utente di Active Directory che rappresenterà tale sistema. Benché gli oggetti sala riunioni siano basati su account utente, tali oggetti non verranno visualizzati quando si esegue il cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Restituisce informazioni sulla dichiarazione di non responsabilità per le conferenze in uso nell'organizzazione. Tale dichiarazione è un messaggio visualizzato agli utenti che accedono a una conferenza utilizzando un collegamento ipertestuale (ad esempio, incollando un collegamento alla conferenza in un browser come Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Restituisce informazioni su tutte le sale riunioni di Skype for Business Server configurate per l'utilizzo nell'organizzazione.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Sposta un oggetto sala riunioni di Skype for Business Server da un pool di registrazione a un altro.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Cancella il testo dell'intestazione e del corpo della dichiarazione di non responsabilità relativa alle conferenze utilizzata nell'organizzazione. Tale dichiarazione è un messaggio visualizzato agli utenti che accedono a una conferenza utilizzando un collegamento ipertestuale (ad esempio, incollando un collegamento alla conferenza in un browser come Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica i valori delle proprietà di una sala riunioni di Skype for Business Server esistente.  <br/> |
   
**Impostazioni di test**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Verifica che due utenti possano partecipare a una conferenza di condivisione applicazioni.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Verifica se un utente può connettersi al provider di servizi di audioconferenza. Un provider di servizi di audioconferenza è una società di terze parti che fornisce servizi di conferenza alle organizzazioni. Tra l'altro, i provider di servizi di audioconferenza consentono agli utenti che si trovano fuori sede e non connessi alla rete aziendale o a Internet di partecipare alla parte audio di una conferenza o di una riunione.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Verifica se due utenti possono partecipare a una conferenza audio/video (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Verifica se una coppia di utenti può partecipare a una conferenza Web di Skype for Business Server che include attività quali la condivisione o la visualizzazione di diapositive di PowerPoint, lavagne o sondaggi. Il cmdlet verifica inoltre che il servizio Web Conferencing di Skype for Business Server sia in grado di individuare il server Office Web Apps e che un client possa caricare un file di PowerPoint per la trasmissione dal server Office Web Apps.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Verifica se un utente può partecipare a una sessione di conferenza telefonica con accesso esterno.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Verifica un numero di telefono rispetto a un dial plan (precedentemente noto come profilo località) e restituisce la regola di normalizzazione che verrà applicata al numero, nonché il numero convertito dopo l'applicazione della regola di normalizzazione.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Verifica la capacità di tre utenti di partecipare a una conferenza del servizio per dispositivi mobili di Skype for Business Server. Il servizio per dispositivi mobili consente agli utenti di telefoni cellulari come iPhone e Windows Phone di eseguire operazioni quali lo scambio di messaggi istantanei e informazioni sulla presenza; archiviare e recuperare la segreteria telefonica internamente anziché con il provider wireless; e sfruttare le funzionalità di Skype for Business Server, ad esempio Chiamata da lavoro e conferenze telefoniche con accesso esterno.  <br/> **Nota:** I client che usano MCX non sono supportati in Skype for Business Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Verifica la capacità di una coppia di utenti di pianificare, partecipare e quindi condurre una conferenza online utilizzando Unified Communications Web API (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Restituisce informazioni di diagnostica per le funzionalità di conferenza dati incluse in Skype for Business Server.  <br/> |
   

