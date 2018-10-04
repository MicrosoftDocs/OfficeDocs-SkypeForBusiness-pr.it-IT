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
description: Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 045896fe8b612e01a22360e0c12f15ebe2719c76
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374641"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configurazione del servizio MMS (Meeting Migration Service)

Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.  This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.  
  
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

This is the most common scenario where MMS can help create a smoother transition for your users. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Se si utilizza attualmente 2015 Server Skype per le conferenze audio

Si consiglia di seguire le migliori pratiche riportate di seguito per la migliore esperienza con MMS in questo scenario:
  
- Dato che MMS richiede che la posta dell'utente sia su Exchange Online, se si esegue la migrazione anche da Exchange Server locale, spostare prima la posta dell'utente su Exchange Online.
    
- Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Se si sta utilizzando un provider di servizi di audioconferenza telefonica audio (ACP) di terze parti

With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.
    
- If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni quando modificano le impostazioni di conferenza audio di un utente

MMS per aggiornare un Skype esistente per le riunioni aziendali e Teams Microsoft nei casi seguenti:
  
- Quando si assegnare o rimuovere licenze **Audioconferenze** .
    
- Quando si attiva o disattiva audioconferenze con accesso esterno.
    
- Quando si modifica o Reimposta l'ID conferenza per un utente configurato per utilizzare le riunioni pubbliche.
    
- Quando l'utente si passa a un ponte per conferenze audio nuovo.
    
- When a phone number is unassigned from a audio conferencing bridge. This is a complex scenario which requires additional steps. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> MMS only updates meetings when you're using the Microsoft bridge. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:
  
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
  
The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. At a minimum, it will take 10 minutes to run. While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.
  
 **Limitazioni e potenziali problemi**
  
- Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.
    
- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.
    
     ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- I contenuti della riunione creati o allegati alla riunione (lavagne, sondaggi e così via) non saranno mantenuti dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
    
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note di riunione effettive memorizzate in OneNote saranno ancora presenti, solo il collegamento alle note condivise viene sovrascritto.
    
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
    
- Alcuni caratteri UNICODE nel corpo dell';invito possono essere aggiornati in modo non corretto e modificati in uno dei seguenti caratteri speciali: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>Cosa vedranno gli utenti quando il servizio MMS aggiorna le loro riunioni?

Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.
  
## <a name="managing-mms"></a>Gestione del servizio MMS

You need to use Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new to PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.

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

MMS is enabled by default for all organizations, but it can be disabled as needed. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. You may also choose to temporarily disable MMS. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.
  
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

You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.
  
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

In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.
  
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
>   ```
>   Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>   $credential = Get-Credential
>   $session = New-CsOnlineSession -Credential $credential
>   Import-PSSession $session
>   ```
> Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
