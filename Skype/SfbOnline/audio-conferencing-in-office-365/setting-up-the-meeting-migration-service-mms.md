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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Migrazione servizio MMS delle riunioni è Skype per servizio di Business che viene eseguito in background e vengono aggiornati automaticamente Skype per le riunioni aziendali e Teams Microsoft per gli utenti. MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunioni per aggiornare i Skype per le riunioni aziendali e Teams Microsoft.
ms.openlocfilehash: 4a1cdc03945e6399b4c77dd12b800fd25b2401cc
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561707"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configurazione del servizio MMS (Meeting Migration Service)

Migrazione servizio MMS delle riunioni è Skype per servizio di Business che viene eseguito in background e vengono aggiornati automaticamente Skype per le riunioni aziendali e Teams Microsoft per gli utenti. MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunioni per aggiornare i Skype per le riunioni aziendali e Teams Microsoft.  Questo strumento non esegue la migrazione delle riunioni di Skype for Business in quelle di Microsoft Teams.  
  
 **Requisiti**
  
MMS richiede che le caselle postali degli organizzatori delle riunioni siano su Exchange Online.
  
 **Scenari primari**
  
MMS aggiorna le riunioni Skype per un utente nei due seguenti scenari primari:
  
- Quando l'utente viene eseguita la migrazione da locale Skype per Business Server a Skype Business online.
    
- Quando un amministratore apporta una modifica per le impostazioni dell'utente audioconferenze con accesso esterno che richiedono l'aggiornamento delle informazioni di audioconferenza nelle riunioni dell'utente.
    
  **Scenari comuni in cui non è possibile utilizzare il servizio MMS**
  
Ecco alcuni scenari comuni che potrebbero essere applicabili all'utente. Questi sono tutti scenari supportati per la migrazione. Tuttavia, il servizio MMS non verrà eseguito in questi scenari e sarà invece necessario utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Le cassette postali degli utenti sono in Exchange Server locale
    
- Utilizzo di un provider di servizi di conferenza audio di terze parti
    
- Migrazione degli utenti da Skype Business online per il Server locale Skype
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Aggiornare le riunioni quando un utente locale viene migrato a Skype for Business online

Questo è lo scenario più comune in cui il servizio MMS può contribuire a creare una transizione agevole per gli utenti. Quando un utente viene eseguita la migrazione da un Skype locale per il Server di Business per Skype Business online, MMS in grado di rilevare il nuovo utente e in grado di rilevare calendario dell'utente Skype per le riunioni aziendali e Teams Microsoft. Le riunioni future verranno aggiornati con le nuove informazioni per tale utente.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Se si utilizza attualmente 2015 Server Skype per le conferenze audio

Si consiglia di seguire le migliori pratiche riportate di seguito per la migliore esperienza con MMS in questo scenario:
  
- Dato che MMS richiede che la posta dell'utente sia su Exchange Online, se si esegue la migrazione anche da Exchange Server locale, spostare prima la posta dell'utente su Exchange Online.
    
- Assegnare la licenza di **Audioconferenza** all'utente prima di eseguire il `Move-CSUser` cmdlet per eseguire la migrazione dell'utente. Ciò avviene perché MMS aggiorna anche le riunioni quando si modificano le impostazioni di conferenza per un utente. Se non si assegna prima la licenza, il servizio MMS aggiornerà di nuovo tutte le riunioni quando si assegna la licenza.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Se si sta utilizzando un provider di servizi di audioconferenza telefonica audio (ACP) di terze parti

Con un'AUDIOCONFERENZA di terze parti o meno MMS esegue dipende dalle impostazioni di audioconferenze con accesso esterno dell'organizzazione. È possibile scegliere di sostituire automaticamente i numeri di accesso dai servizi di Audioconferenza quando un utente si assegna una licenza di **Conferenze Audio** . D';altra parte, potrebbe essere necessario evitare che ciò accada e mantenere i numeri di accesso esterno dal proprio ACP. Per visualizzare l'impostazione dell'organizzazione, eseguire il seguente comando di Windows PowerShell e controllare il valore del parametro `AutomaticallyReplaceAcpProvider`. Se serve aiuto con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Se il valore di questo parametro è $true, MMS verrà eseguito quando un utente viene assegnata una licenza di **Conferenze Audio** e aggiornare le riunioni. I numeri di accesso dai servizi di Audioconferenza vengono conservati fino a quando non viene assegnata alla licenza di **Conferenze Audio** .
    
- Se il valore di questo parametro è $false, MMS non aggiornare le riunioni anche se un utente viene assegnata una licenza di **Conferenze Audio** . I numeri di accesso dai servizi di Audioconferenza vengono conservati fino a quando l'utente manualmente il provisioning per l'audioconferenza in Skype per Business admin center o utilizzando Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni quando modificano le impostazioni di conferenza audio di un utente

MMS per aggiornare un Skype esistente per le riunioni aziendali e Teams Microsoft nei casi seguenti:
  
- Quando si assegnare o rimuovere licenze **Audioconferenze** .
    
- Quando si attiva o disattiva audioconferenze con accesso esterno.
    
- Quando si modifica o Reimposta l'ID conferenza per un utente configurato per utilizzare le riunioni pubbliche.
    
- Quando l'utente si passa a un ponte per conferenze audio nuovo.
    
- Quando un numero di telefono è assegnato a un ponte per conferenze audio. Questo è uno scenario complesso che richiede passaggi aggiuntivi. Per ulteriori informazioni, vedere [modificare il numero a tariffa o numeri gratuito a pagamento il bridge di conferenze Audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> Il servizio MMS aggiorna le riunioni solo quando si utilizza il bridge Microsoft. Se si utilizza un provider di servizi di conferenza audio di terze parti, gli utenti saranno necessario aggiornare le riunioni manualmente. In questo caso, è possibile utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Non tutte le modifiche alle impostazioni di conferenza audio di un utente attivano MMS. In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:
  
- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)
    
- Quando si cambia l'URL della riunione dell'organizzazione utilizzando il comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>Cosa succede quando il servizio MMS aggiorna le riunioni?

Quando il servizio MMS rileva che le riunioni di un utente devono essere aggiornate, procede come segue:
  
1. Identificare tutti Skype per le riunioni aziendali e Teams Microsoft, l'utente è pianificata in futuro
    
   - Qualsiasi Skype per le riunioni aziendali o Teams Microsoft che si sono verificati prima del quale viene eseguito MMS vengono ignorati
    
   - Vengono aggiornate solo le riunioni in cui l'utente è l'organizzatore
    
2. Sostituisce il blocco di informazioni sulla riunione online nei dettagli della riunione
    
3. Invia aggiornamenti a tutti i destinatari della riunione a nome dell'organizzatore della riunione
    
   **Quanto tempo occorre per l';esecuzione del servizio MMS?**
  
Il periodo di tempo necessario a MMS eseguire la migrazione di riunioni varia in base al numero di utenti interessato e il numero totale di Skype per le riunioni aziendali o Microsoft Teams che ogni utente dispone sul proprio calendario. Come minimo, occorreranno 10 minuti per l';esecuzione. Alcune grandi migrazioni possono richiedere fino a 12 ore, ma la maggior parte delle migrazioni dovrebbe essere completata entro 1 ora.
  
 **Limitazioni e potenziali problemi**
  
- Viene eseguita la migrazione solo il Skype per Business o Microsoft Teams riunioni pianificate facendo clic sul pulsante **Aggiungi Skype riunione** in Outlook sul Web oppure utilizzando il componente aggiuntivo riunione Skype per Outlook. In altre parole, se un utente copia e incolla le informazioni sulla riunione online Skype da una riunione a una nuova riunione, quella nuova riunione non sarà aggiornata.
    
- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.
    
     ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- I contenuti della riunione creati o allegati alla riunione (lavagne, sondaggi e così via) non saranno mantenuti dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
    
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note di riunione effettive memorizzate in OneNote saranno ancora presenti, solo il collegamento alle note condivise viene sovrascritto.
    
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
    
- Alcuni caratteri UNICODE nel corpo dell';invito possono essere aggiornati in modo non corretto e modificati in uno dei seguenti caratteri speciali: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>Cosa vedranno gli utenti quando il servizio MMS aggiorna le loro riunioni?

Proprio come lo Strumento di migrazione riunioni, MMS invia aggiornamenti sulle riunioni per conto degli utenti. Pertanto, l'unica cosa che gli utenti vedranno sarà un altro giro notifiche di accettazione per le loro riunioni. Potrebbe essere fuorviante per gli utenti, si consiglia di informare gli utenti in precedenza non solo quando si eseguirne la migrazione da locale a Skype Business online, ma anche quando si apportano modifiche di audioconferenza che venga attivato MMS.
  
## <a name="managing-mms"></a>Gestione del servizio MMS

È necessario utilizzare Windows PowerShell per gestire MMS e controllare lo stato di migrazione in corso. Le informazioni in questa sezione danno per scontato che l';utente abbia familiarità con l';uso di PowerShell per gestire l';organizzazione di Skype for Business. Se si conosce PowerShell, vedere la sezione [Utilizzo di PowerShell per gestire i Skype per organizzazione aziendale](setting-up-the-meeting-migration-service-mms.md#WPSInfo) alla fine di questo articolo.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Come si controlla lo stato della migrazione delle riunioni?

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

MMS è attivato per impostazione predefinita per tutte le organizzazioni, ma può essere disattivato, se necessario. Ad esempio, se si desidera eseguire manualmente la migrazione di tutte le riunioni o se si utilizza un provider di servizi di conferenza audio di terze parti, potrebbe non essere MMS in esecuzione. È inoltre possibile scegliere di disattivare temporaneamente MMS. Ad esempio durante notevoli modifiche alle impostazioni di conferenza per l'organizzazione e non si desidera MMS eseguito finché non siano state completate tutte le modifiche.
  
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

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Abilitazione e disabilitazione MMS solo le modifiche di audioconferenze con accesso esterno
<a name="Troubleshooting"> </a>

È inoltre possibile disattivare MMS solo le modifiche di audioconferenza. Ancora verrà eseguita quando un utente viene eseguita la migrazione da Skype aziendali locali per Skype Business online. Per verificare lo stato corrente di MMS per gli aggiornamenti di audioconferenza, eseguire il seguente comando e verificare il valore per il `AutomaticallyMigrateUserMeetings` parametro. Se questo parametro è impostato su$ true, MMS è impostato per gli aggiornamenti di riunioni utente quando si modificano le impostazioni di conferenza.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Per disabilitare MMS per le conferenze audio, eseguire il comando seguente:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Per abilitare MMS per le conferenze audio, eseguire il comando seguente:
  
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
  
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
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
>   ```
>   Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>   $credential = Get-Credential
>   $session = New-CsOnlineSession -Credential $credential
>   Import-PSSession $session
>   ```
> Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [impostare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
