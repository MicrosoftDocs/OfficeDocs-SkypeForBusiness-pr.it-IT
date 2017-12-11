---
title: "Configurazione del servizio MMS (Meeting Migration Service)"
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
description: "Servizio di migrazione (MMS) della riunione è un Skype per servizi aziendali che viene eseguita in background e aggiorna automaticamente Skype per Business e Teams Microsoft riunioni per gli utenti. MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunione per aggiornare i Skype per le riunioni aziendali e Teams Microsoft."
---

# Configurazione del servizio MMS (Meeting Migration Service)

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/031f09c0-9d2a-487a-b6db-b5d4bed6d16a). 
  
Servizio di migrazione (MMS) della riunione è un Skype per servizi aziendali che viene eseguita in background e aggiorna automaticamente Skype per Business e Teams Microsoft riunioni per gli utenti. MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunione per aggiornare i Skype per le riunioni aziendali e Teams Microsoft.
  
 **Requisiti**
  
MMS richiede che le caselle postali degli organizzatori delle riunioni siano su Exchange Online.
  
 **Scenari primari**
  
MMS aggiorna le riunioni Skype per un utente nei due seguenti scenari primari: 
  
- Quando l'utente viene eseguita la migrazione da locale Skype for Business Server a Skype for Business Online.
    
- Quando un amministratore apporta una modifica alle impostazioni di conferenze audio dell'utente che richiedono l'aggiornamento delle informazioni di conferenze audio nelle riunioni dell'utente.
    
 **Scenari comuni in cui non è possibile utilizzare il servizio MMS**
  
Ecco sono alcuni scenari comuni che possono applicarsi alla situazione dell';utente. Questi sono tutti scenari supportati per la migrazione. Tuttavia, il servizio MMS non verrà eseguito in questi scenari e sarà invece necessario utilizzare lo strumento [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Le cassette postali degli utenti sono in Exchange Server locale
    
- Utilizzo di un provider di conferenze audio di terze parti
    
- Migrazione degli utenti da Skype for Business Online al Server di Skype locale
    
## Aggiornare le riunioni quando un utente locale viene migrato a Skype for Business online

Questo è lo scenario più comune in cui MMS consente di creare una transizione più fluida per gli utenti. Quando un utente viene eseguita la migrazione da un locale Skype for Business Server a Skype for Business Online, MMS in grado di rilevare il nuovo utente e in grado di rilevare calendario dell'utente Skype per le riunioni aziendali e Teams Microsoft. Tutte le riunioni future verranno aggiornate con le nuove informazioni per l'utente.
  
### Se si usa attualmente 2015 Server Skype per le conferenze audio

Si consiglia di seguire le migliori pratiche riportate di seguito per la migliore esperienza con MMS in questo scenario:
  
- Dato che MMS richiede che la posta dell'utente sia su Exchange Online, se si esegue la migrazione anche da Exchange Server locale, spostare prima la posta dell'utente su Exchange Online.
    
- Assegnare la licenza di **Conferenze Audio** all'utente prima di eseguire il cmdlet `Move-CSUser` migrazione dell'utente. In questo modo MMS inoltre aggiorna le riunioni quando vengono modificate audioconferenza impostazioni per un utente. Se si non assegna la licenza prima di tutto, MMS aggiornerà tutte le riunioni nuovamente quando si assegna la licenza.
    
### Se si sta utilizzando un provider di servizi di audioconferenza telefonica audio (ACP) di terze parti

Con un servizi di Audioconferenza di terze parti o meno MMS esegue dipende dalle impostazioni di conferenze audio dell'organizzazione. È possibile scegliere sostituire automaticamente i numeri di telefono dai servizi di Audioconferenza quando si assegna una licenza di **Conferenze Audio** a un utente. Mano, potrebbe essere necessario per evitare che e mantenere i numeri di telefono dai servizi di Audioconferenza. Per visualizzare l'impostazione dell'organizzazione, eseguire il seguente comando di Windows PowerShell e controllare il valore del parametro `AutomaticallyReplaceAcpProvider`. Se occorre assistenza con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) alla fine di questo articolo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Se il valore di questo parametro è $true, MMS verrà eseguito quando un utente viene assegnata una licenza di **Conferenze Audio** e aggiornare le riunioni. I numeri di telefono dai servizi di Audioconferenza vengono mantenuti fino a quando non è assegnata la licenza di **Conferenze Audio**.
    
- Se il valore di questo parametro è $false, MMS non è possibile aggiornare le riunioni anche se un utente viene assegnata una licenza di **Conferenze Audio**. I numeri di telefono dai servizi di Audioconferenza vengono mantenuti fino a quando l'utente manualmente è stato eseguito il provisioning di conferenze audio in Skype for Business admin center o usando Windows PowerShell.
    
## Aggiornamento delle riunioni quando modificate le impostazioni di conferenze audio di un utente

MMS aggiorneranno un Skype esistente per le riunioni aziendali e Teams Microsoft nei seguenti casi:
  
- Quando si assegnare o rimuovere la licenza **Conferenze Audio**.
    
- Quando si attiva o disattiva audioconferenza.
    
- Quando si modifica o Reimposta l'ID conferenza per un utente configurato per l'utilizzo di riunioni pubbliche.
    
- Quando l'utente si sposta a un bridge di conferenze audio nuovo.
    
- Quando un numero di telefono è assegnato a un bridge di conferenza audio. Si tratta di uno scenario complesso che richiede ulteriori passaggi. Per ulteriori informazioni, vedere [Modificare il numero verde o numeri a pagamento gratuito il bridge di conferenze Audio](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS Aggiorna riunioni solo quando si usa il bridge Microsoft. Se si utilizza un provider di conferenze audio di terze parti, gli utenti saranno necessario aggiornare le riunioni manualmente. In questo caso, è possibile utilizzare [Strumento di migrazione riunione](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Non tutte le modifiche alle impostazioni di conferenze audio di un utente impostare un trigger MMS. In particolare, MMS aggiornamento delle riunioni non comporta la due modifiche seguenti:
  
- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il loro nome utente SIP o il dominio SIP)
    
- Quando si cambia l';URL della riunione dell';organizzazione utilizzando il comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## Cosa succede quando il servizio MMS aggiorna le riunioni?

Quando il servizio MMS rileva che le riunioni di un utente devono essere aggiornate, procede come segue:
  
1. Identificare tutti Skype per le riunioni aziendali e Teams Microsoft l'utente è programmato in futuro
    
  - Vengono ignorate le Skype per Business o Teams Microsoft riunioni che si sono verificati prima dell'esecuzione di MMS
    
  - Vengono aggiornate solo le riunioni in cui l'utente è l'organizzatore
    
2. Sostituisce il blocco di informazioni sulla riunione online nei dettagli della riunione
    
3. Invia aggiornamenti a tutti i destinatari della riunione a nome dell'organizzatore della riunione
    
 **Quanto tempo occorre per l';esecuzione del servizio MMS?**
  
La quantità di tempo per MMS eseguire la migrazione delle riunioni varia a seconda di quanti utenti sono interessati e il numero totale di Skype per Business o Teams Microsoft riunioni che ogni utente è presente nel calendario. Minimo, sarà necessaria 10 minuti per l'esecuzione. Mentre alcune migrazioni di grandi dimensioni possono richiedere fino a 12 ore, la maggior parte delle migrazioni devono completare entro 1 ora.
  
 **Limitazioni e potenziali problemi**
  
- Viene eseguita solo di Skype per Business o Teams Microsoft riunioni programmata facendo clic sul pulsante **Aggiungi Skype riunione** in Outlook sul Web con il componente aggiuntivo riunione di Skype per Outlook. In altre parole, se un utente copia e Incolla le informazioni sulla riunione online di Skype da una riunione in una nuova riunione, la nuova riunione non verranno aggiornati.
    
- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato. 
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- I contenuti della riunione creati o allegati alla riunione (lavagne, sondaggi e così via) non saranno mantenuti dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
    
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note di riunione effettive memorizzate in OneNote saranno ancora presenti, solo il collegamento alle note condivise viene sovrascritto.
    
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate. 
    
- Alcuni caratteri UNICODE nel corpo dell';invito possono essere aggiornati in modo non corretto e modificati in uno dei seguenti caratteri speciali: ï, ¿, ½, �.
    
### Cosa vedranno gli utenti quando il servizio MMS aggiorna le loro riunioni?

Esattamente come lo strumento di migrazione di riunione, MMS invia gli aggiornamenti di riunione per conto di utenti. L'unica che gli utenti vedranno è un altro arrotondamento di soddisfare le notifiche di accettazione delle riunioni. Potrebbe essere confusione per gli utenti, è consigliabile informare gli utenti in anticipo non solo quando si eseguirne la migrazione da locale a Skype for Business Online, ma anche il quando si apportano modifiche di conferenze audio attiverà MMS.
  
## Gestione del servizio MMS

È necessario utilizzare Windows PowerShell per gestire il servizio MMS e controllare lo stato delle migrazioni in corso. Le informazioni in questa sezione danno per scontato che l';utente abbia familiarità con l';uso di PowerShell per gestire l';organizzazione di Skype for Business. Se non si ha dimestichezza con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) al termine di questo articolo.
  
### Come si controlla lo stato della migrazione delle riunioni?

Per controllare lo stato della migrazione delle riunioni è necessario usare il cmdlet  `Get-CsMeetingMigrationStatus`. Di seguito sono riportati alcuni esempi.
  
Per ottenere un riepilogo di tutte le migrazioni MMS, eseguire il seguente comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Questo darà una rappresentazione tabulare di tutti gli stati di migrazione come questa:
  
State UserCount----- ---------Pending 21InProgress 6Failed 2Succeeded 131
> [!IMPORTANT]
> Se si notano migrazioni non riuscite (stato Failed), intervenire per risolvere questi problemi il più presto possibile. Le persone non saranno in grado di utilizzare l';accesso esterno per le riunioni organizzate da quegli utenti fino a quando i problemi non saranno risolti. Vedere la sezione [Cosa devo fare se si verifica un errore?](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#Troubleshooting) per maggiori informazioni.
  
Per avere tutti i dettagli di tutte le migrazioni entro un periodo di tempo specifico, è possibile utilizzare i parametri  `StartTime` e `EndTime`. Ad esempio, il seguente comando restituirà tutti i dettagli su tutte le migrazioni che si sono verificati dal 1° ottobre 2016 al 8 ottobre 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Si consiglia inoltre di controllare lo stato della migrazione per un utente specifico, ed è possibile utilizzare il parametro  `UserId` per questo. Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### Cosa devo fare se si verifica un errore?
<a name="Troubleshooting"> </a>

Quando si esegue il cmdlet  `Get-CsMeetingMigrationStatus` per ottenere una riepilogo e si nota che ci sono migrazioni in stato Operazione non riuscita le operazioni da eseguire sono le seguenti:
  
1. Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l';elenco degli utenti interessati e l';errore specifico che è stato segnalato:
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. Per ciascuno di questi utenti, eseguire lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047) per migrare manualmente le relative riunioni.
    
3. Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:
    
  - Fare creare agli utenti nuove riunioni Skype.
    
  - [Contattare l';assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).
    
### Attivazione e disattivazione del servizio MMS
<a name="Troubleshooting"> </a>

MMS è attivata per impostazione predefinita per tutte le organizzazioni, ma può essere disattivata in base alle esigenze. Ad esempio, se si desidera eseguire manualmente la migrazione di tutte le riunioni o se si usa un provider di conferenze audio di terze parti, potrebbe essere necessario non MMS in esecuzione. È anche possibile disattivare temporaneamente MMS. Ad esempio, si possono eseguire le operazioni modifiche significative alle impostazioni di conferenze audio per l'organizzazione e non si vuole MMS per l'esecuzione fino al completamento di tutte le modifiche.
  
Per verificare se il servizio MMS è attivato nella propria organizzazione, eseguire il seguente comando e controllare il valore del parametro  `MeetingMigrationEnabled`. Se questo parametro è impostato su $true, il servizio MMS è abilitato.
  
```
Get-CsTenantMigrationConfiguration
```

Per disabilitare il servizio MMS, eseguire il comando seguente:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Per abilitare il servizio MMS, eseguire il comando seguente:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### Attivazione e disattivazione MMS solo per le modifiche di conferenze audio
<a name="Troubleshooting"> </a>

È anche possibile disabilitare MMS solo per le modifiche di conferenze audio. Verrà comunque eseguita quando un utente viene eseguita la migrazione da Skype for Business locale a Skype for Business Online. Per verificare lo stato corrente di MMS aggiornamenti audioconferenza, eseguire il comando seguente e selezionare il valore per il parametro  `AutomaticallyMigrateUserMeetings` . Se questo parametro è impostato su$true, MMS è impostato per aggiornare le riunioni utente quando vengono modificate le impostazioni di conferenze audio.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Per disattivare MMS per conferenze audio, eseguire il comando seguente:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Per attivare MMS per conferenze audio, eseguire il comando seguente:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### Come si esegue manualmente la migrazione delle riunioni per un utente?
<a name="Troubleshooting"> </a>

Oltre a migrazioni riunione automatica oppure eseguire la migrazione di riunione manualmente per un utente eseguendo il cmdlet **Start-CsExMeetingMigration**. Questo cmdlet aggiunge l'utente nella coda di migrazione della riunione. Servizio di migrazione della riunione leggerà la richiesta dell'utente e le riunioni di eseguire la migrazione. È possibile verificare lo stato della riunione la migrazione da cmdlet **Get-CsMeetingMigrationStatus**.
  
Ecco un esempio che avvia la migrazione riunioni per l'utente ashaw@contoso.com:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## Uso di PowerShell per gestire l'organizzazione di Skype for Business
<a name="WPSInfo"> </a>

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
  
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
 **Avviare una sessione di Windows PowerShell**
  
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

