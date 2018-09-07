---
title: Configurazione del servizio MMS (Meeting Migration Service)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) è un servizio di Skype for Business eseguito in background che aggiorna automaticamente le riunioni di Skype for Business e Microsoft Teams per gli utenti. MMS è progettato per eliminare la necessità di avviare lo Strumento di migrazione riunioni per aggiornare le riunioni di Skype for Business e Microsoft Teams.
ms.openlocfilehash: 562cc616af59ee2fb87b5a2a023c9efe6c3093c3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854316"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configurazione del servizio MMS (Meeting Migration Service)

Meeting Migration Service (MMS) è un servizio di Skype for Business eseguito in background che aggiorna automaticamente le riunioni di Skype for Business e Microsoft Teams per gli utenti. MMS è progettato per eliminare la necessità di avviare lo Strumento di migrazione riunioni per aggiornare le riunioni di Skype for Business e Microsoft Teams.  Questo strumento non esegue la migrazione delle riunioni di Skype for Business in quelle di Microsoft Teams.  
  
 **Requisiti**
  
MMS richiede che le caselle postali degli organizzatori delle riunioni siano su Exchange Online.
  
 **Scenari primari**
  
MMS aggiorna le riunioni Skype per un utente nei due seguenti scenari primari:
  
- Quando l'utente viene migrato da Skype for Business Server a Skype for Business online.
    
- Quando un amministratore apporta una modifica alle impostazioni di audioconferenza dell'utente che richiederebbe l'aggiornamento delle informazioni di audioconferenza nelle riunioni di questo utente.
    
 **Scenari comuni in cui non è possibile utilizzare il servizio MMS**
  
Ecco alcuni scenari comuni che potrebbero essere applicabili all'utente. Questi sono tutti scenari supportati per la migrazione. Tuttavia, il servizio MMS non verrà eseguito in questi scenari e sarà invece necessario utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Le cassette postali degli utenti sono in Exchange Server locale
    
- Utilizzo di un provider di servizi di audioconferenza di terze parti
    
- Migrazione di utenti da Skype for Business online a Skype for Business Server locale
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Aggiornare le riunioni quando un utente locale viene migrato a Skype for Business online

Questo è lo scenario più comune in cui il servizio MMS può contribuire a creare una transizione agevole per i tuoi utenti. Quando l'utente viene migrato da Skype for Business Server a Skype for Business online, il servizio MMS rileva il nuovo utente e analizza il calendario di quell'utente alla ricerca di riunioni di Skype for Business e Microsoft Teams. Tutte le future riunioni saranno aggiornate con le nuove informazioni per l'utente.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Se stai attualmente utilizzando Skype Server 2015 per le audioconferenze

Si consiglia di seguire le migliori pratiche riportate di seguito per la migliore esperienza con MMS in questo scenario:
  
- Dato che MMS richiede che la posta dell'utente sia su Exchange Online, se si esegue la migrazione anche da Exchange Server locale, spostare prima la posta dell'utente su Exchange Online.
    
- Assegna la licenza di **Audioconferenza** all'utente prima di eseguire il `Move-CSUser` cmdlet per migrare l'utente. Questo perché MMS aggiorna anche le riunioni quando vengono modificate le impostazioni di audioconferenza per un utente. Se non assegni prima la licenza, il servizio MMS aggiornerà di nuovo tutte le riunioni quando assegni la licenza.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Se stai utilizzando un provider di servizi di audioconferenza telefonica audio (ACP) di terze parti

Con un ACP di terze parti, il fatto che venga eseguito o meno il servizio MMS dipende dalle impostazioni di audioconferenza dell'organizzazione. È possibile scegliere di sostituire automaticamente i numeri di accesso esterno dal proprio ACP quando assegni a un utente una licenza di **Audioconferenza**. D'altra parte, potrebbe essere necessario evitare che ciò accada e mantenere i numeri di accesso esterno dal proprio ACP. Per consultare l'impostazione della propria organizzazione, esegui il seguente comando di Windows PowerShell e controlla il valore del parametro `AutomaticallyReplaceAcpProvider`. Se serve aiuto con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Se il valore di questo parametro è $true, il servizio MMS verrà eseguito quando un utente riceve una licenza di **Audioconferenza** e aggiorna le proprie riunioni. I numeri di accesso esterno dal proprio ACP vengono mantenuti finché non viene assegnata la licenza di **Audioconferenza**.
    
- Se il valore di questo parametro è $false, il servizio MMS non aggiornerà le riunioni anche se un utente riceve una licenza di **Audioconferenza**. I numeri di accesso esterno dal proprio ACP vengono mantenuti finché l'utente non viene configurato manualmente per l'audioconferenza nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni quando si modificano le impostazioni di audioconferenza di un utente

MMS aggiornerà le riunioni esistenti di Skype for Business e Microsoft Teams nei seguenti casi:
  
- Quando si assegna o si rimuove la licenza di **Audioconferenza**.
    
- Quando si attiva o si disattiva l'audioconferenza.
    
- Quando si modifica o si reimposta l'ID conferenza per un utente configurato per l'uso di riunioni pubbliche.
    
- Quando si trasferisce l'utente a un nuovo bridge di audioconferenza.
    
- Quando un numero di telefono non è impostato in un ponte per audioconferenza. Questo è uno scenario complesso che richiede passaggi aggiuntivi. Per maggiori informazioni, consulta [Modifica i numeri a tariffa o i numeri gratuiti del ponte per Audioconferenza](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> Il servizio MMS aggiorna le riunioni solo quando utilizzi il ponte Microsoft. Se utilizzi un provider di servizi di audioconferenza di terze parti, gli utenti dovranno aggiornare le riunioni manualmente. In questo caso, è possibile utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Non tutte le modifiche alle impostazioni di audioconferenza di un utente attivano il servizio MMS. In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:
  
- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)
    
- Quando si cambia l'URL della riunione dell'organizzazione utilizzando il comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>Cosa succede quando il servizio MMS aggiorna le riunioni?

Quando il servizio MMS rileva che le riunioni di un utente devono essere aggiornate, procedi come segue:
  
1. Identifica tutte le riunioni di Skype for Business e Microsoft Teams che l'utente ha in programma in futuro
    
  - Eventuali riunioni di Skype for Business o Microsoft Teams che sono avvenute prima dell'esecuzione del servizio MMS vengono tralasciate
    
  - Vengono aggiornate solo le riunioni in cui l'utente è l'organizzatore
    
2. Sostituisce il blocco di informazioni sulla riunione online nei dettagli della riunione
    
3. Invia aggiornamenti a tutti i destinatari della riunione a nome dell'organizzatore della riunione
    
 **Quanto tempo occorre per l'esecuzione del servizio MMS?**
  
La quantità di tempo necessaria al servizio MMS per la migrazione delle riunioni varia a seconda di quanti utenti sono interessati e del numero totale di riunioni di Skype for Business o Microsoft Teams che ogni utente ha sul proprio calendario. Come minimo, occorreranno 10 minuti per l'esecuzione. Alcune grandi migrazioni possono richiedere fino a 12 ore, ma la maggior parte delle migrazioni dovrebbe essere completata entro 1 ora.
  
 **Limitazioni e potenziali problemi**
  
- Facendo clic sul pulsante **Aggiungi riunione Skype** in Outlook sul web o utilizzando il componente aggiuntivo Riunione Skype per Outlook vengono migrate solo le riunioni di Skype for Business o Microsoft Teams pianificate. In altre parole, se un utente copia e incolla le informazioni sulla riunione online Skype da una riunione a una nuova riunione, quella nuova riunione non sarà aggiornata.
    
- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.
    
     ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- I contenuti della riunione creati o allegati alla riunione (lavagne, sondaggi e così via) non saranno mantenuti dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
    
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note di riunione effettive memorizzate in OneNote saranno ancora presenti, solo il collegamento alle note condivise viene sovrascritto.
    
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
    
- Alcuni caratteri UNICODE nel corpo dell';invito possono essere aggiornati in modo non corretto e modificati in uno dei seguenti caratteri speciali: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>Cosa vedranno gli utenti quando il servizio MMS aggiorna le loro riunioni?

Proprio come lo Strumento di migrazione riunioni, MMS invia aggiornamenti sulle riunioni per conto degli utenti. Pertanto, l'unica cosa che gli utenti vedranno sarà un'altra tornata di notifiche di accettazione per le loro riunioni. Questo potrebbe essere fonte di confusione per gli utenti, perciò si consiglia di informarli in anticipo non solo per la migrazione da Skype for Business locale a Skype for Business online, ma anche quando si effettua una modifica all'audioconferenza che attiverà il servizio MMS.
  
## <a name="managing-mms"></a>Gestione del servizio MMS

È necessario utilizzare Windows PowerShell per gestire il servizio MMS e controllare lo stato delle migrazioni in corso. Le informazioni in questa sezione danno per scontato che l'utente abbia familiarità con l'uso di PowerShell per gestire l'organizzazione di Skype for Business. Se non hai dimestichezza con PowerShell, consulta la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Come posso controllare lo stato della migrazione delle riunioni?

Per controllare lo stato della migrazione delle riunioni è necessario usare il cmdlet  `Get-CsMeetingMigrationStatus`. Di seguito sono riportati alcuni esempi.
  
Per ottenere un riepilogo di tutte le migrazioni MMS, eseguire il seguente comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Questo darà una rappresentazione tabulare di tutti gli stati di migrazione come questa:
  
Stato UserCount---------------<br/> 21 in sospeso<br/>6 in corso<br/> 2 non riuscito <br/> 131 completato
> [!IMPORTANT]
> Se si notano migrazioni non riuscite (stato Failed), intervenire per risolvere questi problemi il più presto possibile. Le persone non saranno in grado di utilizzare l'accesso esterno per le riunioni organizzate da quegli utenti fino a quando i problemi non saranno risolti. Vedere la sezione [Cosa devo fare se si verifica un errore?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) per maggiori informazioni.
  
Per avere tutti i dettagli di tutte le migrazioni entro un periodo di tempo specifico, è possibile utilizzare i parametri  `StartTime` e `EndTime`. Ad esempio, il seguente comando restituirà tutti i dettagli su tutte le migrazioni che si sono verificate dal 1° ottobre 2016 all'8 ottobre 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Si consiglia inoltre di controllare lo stato della migrazione per un utente specifico, ed è possibile utilizzare il parametro  `UserId` per questo. Ad esempio, il seguente comando restituirà lo stato dell'utente ashaw@contoso.com:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>Cosa devo fare se si verifica un errore?
<a name="Troubleshooting"> </a>

Quando si esegue il cmdlet  `Get-CsMeetingMigrationStatus` per ottenere una visualizzazione Riepilogo e si nota che ci sono migrazioni in stato "non riuscito" le operazioni da eseguire sono le seguenti:
  
1. Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l'elenco degli utenti interessati e l'errore specifico che è stato segnalato:
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. Per ciascuno di questi utenti, eseguire lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047) per migrare manualmente le relative riunioni.
    
3. Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:
    
  - Far creare agli utenti nuove riunioni Skype.
    
  - [Contattare l'assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).
    
### <a name="enabling-and-disabling-mms"></a>Attivazione e disattivazione del servizio MMS
<a name="Troubleshooting"> </a>

MMS è attivato per impostazione predefinita per tutte le organizzazioni, ma può essere disattivato, se necessario. Ad esempio, se si desidera migrare manualmente tutte le riunioni o se si utilizza un provider di servizi di audioconferenza di terze parti, potrebbe non essere necessario eseguire il servizio MMS. È inoltre possibile scegliere di disattivare temporaneamente MMS. Ad esempio, stai facendo delle modifiche sostanziali alle impostazioni di audioconferenza per l'organizzazione e non vuoi che MMS venga eseguito fino a quando sono state completate tutte.
  
Per verificare se il servizio MMS è attivato nella propria organizzazione, eseguire il seguente comando e controllare il valore del parametro  `MeetingMigrationEnabled`. Se questo parametro è impostato su $true, il servizio MMS è abilitato.
  
```
Get-CsTenantMigrationConfiguration
```

Per disabilitare il servizio MMS, eseguire il comando seguente:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Per abilitare il servizio MMS, esegui il comando seguente:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Abilitazione e disabilitazione del servizio MMS solo per le modifiche relative all'audioconferenza
<a name="Troubleshooting"> </a>

È anche possibile disattivare il servizio MMS solo le modifiche relative all'audioconferenza. Il servizio verrà comunque eseguito quando l'utente viene migrato da Skype for Business locale a Skype for Business online. Per verificare lo stato attuale del servizio MMS per gli aggiornamenti relativi all'audioconferenza, eseguire il seguente comando e controllare il valore del parametro `AutomaticallyMigrateUserMeetings`. Se questo parametro è impostato su $true, il servizio MMS è impostato per aggiornare le riunioni degli utenti quando vengono modificate le impostazioni di audioconferenza.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Per disabilitare il servizio MMS per l'audioconferenza, eseguire il comando seguente:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Per abilitare il servizio MMS per l'audioconferenza, esegui il comando seguente:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Come si esegue manualmente la migrazione delle riunioni per un utente?
<a name="Troubleshooting"> </a>

Oltre alle migrazioni automatiche delle riunioni, è possibile anche eseguire la migrazione riunioni manualmente per un utente eseguendo il cmdlet **Start-CsExMeetingMigration**. Questo cmdlet consente di aggiungere l'utente nella coda di migrazione delle riunioni. Meeting Migration Service leggerà la richiesta dell';utente e migrerà le sue riunioni. È possibile controllare lo stato della migrazione riunioni con il cmdlet **Get-CsMeetingMigrationStatus**.
  
Ecco un esempio che avvia la migrazione riunioni per l'utente ashaw@contoso.com:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>Uso di PowerShell per gestire l'organizzazione di Skype for Business
<a name="WPSInfo"> </a>

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
  
1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Avviare una sessione di Windows PowerShell**
  
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
