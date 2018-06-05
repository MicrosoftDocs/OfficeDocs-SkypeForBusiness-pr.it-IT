---
title: Modificare i numeri di telefono del ponte per conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: Quando si acquistano le licenze di accesso esterno alle audioconferenze, Microsoft ospita la ponte per conferenze audio per la propria organizzazione. Consente di ponte per conferenze audio numeri di telefono di accesso esterno da posizioni diverse in modo i partecipanti e gli organizzatori delle riunioni possono utilizzarli per partecipare a Skype per le riunioni aziendali o Microsoft Teams mediante un telefono.
ms.openlocfilehash: 0eceff97470bf6c0df6b0818734955ebf71d0f76
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568364"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Modificare i numeri di telefono del ponte per conferenze Audio

Quando si acquistano le licenze di **Accesso esterno alle audioconferenze** , Microsoft ospita la *ponte per conferenze audio* per la propria organizzazione. Consente di ponte per conferenze audio numeri di telefono di accesso esterno da posizioni diverse in modo i partecipanti e gli organizzatori delle riunioni possono utilizzarli per partecipare a Skype per le riunioni aziendali o Microsoft Teams mediante un telefono.
  
Oltre ai numeri di telefono già assegnati al ponte per conferenze, è possibile [ottenere i numeri di servizio aggiuntive](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (numero a pagamento e numeri verdi utilizzati per le conferenze audio) da altri percorsi e di assegnare loro le conferenze che in modo da poter Espandere la copertura per gli utenti.
  
> [!NOTE]
> Per poter assegnare/annullare l'assegnazione di un numero di telefono per un ponte per conferenze, il numero di telefono deve essere un numero "*servizio*". È possibile visualizzare il tipo di numero è, passare a **Voice** > **numeri di telefono** e informazioni nella colonna **Tipo di numero** . Titoli di coda di Office 365 Communications deve impostare prima per consentire agli utenti di accedere alla bridge su un numero verde. 
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Passaggio 1 - assegnare il nuovo numero di telefono per il ponte per conferenze audio

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

1. Accedi a Office 365 con l'account aziendale.
    
2. Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **vocale** > **i numeri di telefono**.
    
3. Selezionare il numero di telefono dall'elenco, quindi nel riquadro azioni, fare clic su **Assegna**.
    
4. Sulla pagina **Assegna**, fai clic su **Salva**.
    
    Solo un numero a pagamento servizio può essere impostato come il numero predefinito per i bridge conferenza; **numeri verdi servizio non è possibile impostare come il numero predefinito del ponte per conferenze**. Se si assegna un numero a pagamento del servizio e si desidera impostare come il nuovo numero predefinito per il ponte per conferenze audio, selezionare **Usa questo numero, come il valore predefinito**.
    
    > [!NOTE]
    > Una volta assegnato un nuovo numero di telefono, anche se il numero è diventato il nuovo numero predefinito, il numero predefinito per gli utenti esistenti non cambierà. Per impostare il numero a tariffa predefinito o un numero verde viene aggiunto alla riunione dell'organizzatore invita, vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md). 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Passo 2 - Cambiare i numeri di telefono predefiniti inclusi nelle inviti alle riunioni degli utenti (facoltativo)

I numeri di telefono predefiniti per gli utenti sono quelli inclusi nell'invito alla riunione quando pianificano una riunione. Per ulteriori informazioni, vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **audioconferenze** > **utenti** e selezionare gli utenti nell'elenco.
    
3. Nel riquadro Azione, fai clic su **Modifica**.
    
4. In **numero a pagamento predefinito** o **predefinito numero verde**, selezionare il numero nell'elenco e fare clic su **Salva**.
    
Dopo che le modifiche sono state salvate, il nuovo telefono predefinito numeri verranno incluse nella riunione invita di Organizer la volta successiva che si pianifica una nuova riunione.
  
### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Passo 3 - Aggiornare gli inviti alle riunioni esistenti degli utenti che utilizzano il servizio MMS (Meeting Migration Service) (facoltativo)

Per i due passaggi successivi, è necessario avviare Windows PowerShell.
  
Utilizzo del servizio di migrazione di riunioni, è possibile aggiornare facoltativamente gli inviti di riunione già inviate agli utenti dell'organizzazione prima che sono stati modificati i numeri di telefono predefinito. Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).
  
- Eseguire il servizio di migrazione riunione (MMS) per gli utenti che hanno ai numeri di telefono predefinito modificati nel passaggio 2. Per farlo, eseguire il comando seguente:
    
```
    Start-CsExMeetingMigration user@contoso.com
```

- È inoltre possibile visualizzare lo stato della migrazione della riunione. Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .
    
```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza


Quando si annulla l'assegnazione di un numero di telefono da un ponte di conferenza, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono. Dal momento che cambia il numero di telefono, è importante per aggiornare tutti gli utenti che potrebbero includere un numero di telefono come il numero predefinito (se esistenti) e per aggiornare gli inviti della riunione prima che il numero di telefono non assegnato da ponte per conferenze audio esistenti. 
  
Se il numero di telefono viene rimosso senza aggiornare gli utenti e le loro riunioni, i loro inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona più per partecipare.
  
Per i tre passi successivi, è necessario avviare Windows PowerShell. Per informazioni su come eseguire questa operazione, fare clic su [desiderano informazioni su come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)
  
### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Passo 1 - Aggiornare gli che hanno il numero di telefono di cui rimuovere l'assegnazione tra i loro numeri predefiniti

Sostituire numero a tariffa o numero verde predefinito per tutti gli utenti che hanno come numero predefinito il numero di cui annullare l'assegnazione e avviare il processo di ripianificazione delle loro riunioni. Per farlo, eseguire il comando seguente:
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >È inoltre possibile modificare il numero a tariffa predefinita o numero verde degli utenti in Skype per interfaccia di amministrazione di Business. Tuttavia, questo non verrà riprogrammare automaticamente alle riunioni. 
 
 Per ulteriori informazioni, vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).

  > [!NOTE]
  > A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo. 
  
### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell

Tutte le riunioni ripianificate dopo nessuna operazione nello stato *in sospeso* o *In corso* .
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Passaggio 3: annullare l'assegnazione il vecchio numero di telefono di ponte per conferenze audio

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **vocale** > **i numeri di telefono**.
    
3. Selezionare il numero di telefono dall'elenco, quindi nel riquadro azioni fare clic su **Annulla assegnazione**.
    
4. Nella finestra di conferma fare clic su **Sì**.
    
  > [!IMPORTANT]
  > Dopo un numero di telefono non assegnato da un ponte per conferenze audio, il numero di telefono non saranno disponibile agli utenti di partecipare alle riunioni nuove o esistente. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Per verificare se Windows PowerShell è pronto

 La procedura seguente verificare che sia in esecuzione Windows PowerShell versione 3.0 o versione successiva.
  
1. Digitare **il Menu di avvio** > **Windows PowerShell**.
    
2. Digitare _Get-Host_ nella finestra di **Windows PowerShell** per verificare la versione.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. È inoltre necessario installare il modulo di Windows PowerShell per Skype Business online che consente di creare una sessione remota di Windows PowerShell che si connette a Skype Business online. In questo modulo è supportato solo nei computer a 64 bit e può essere scaricato da Microsoft Download Center al [Modulo di Windows PowerShell per Skype Business online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
### <a name="to-start-windows-powershell"></a>Per avviare Windows PowerShell

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

Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
### <a name="save-time-and-automate"></a>Risparmiare tempo e l'automazione

Per risparmiare tempo automatizzare il processo, è possibile utilizzare [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) o il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** .
  
- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.
    
  - Per modificare il numero verde predefinito di un utente, esegui:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.
    
    > [!NOTE]
    > Per trovare il BridgeID, utilizzare **Get-CsOnlineDialInConferencingBridge**.
  
  - Per modificare il numero verde predefinito di tutti gli utenti a cui ne manca uno in 8005551234, esegui:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti che hanno 8005551234 come numero verde predefinito in 8005551239 e ripianificare automaticamente le loro riunioni, esegui:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti con sede negli USA in 8005551234 e ripianificare automaticamente le loro riunioni, esegui:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > La località che viene utilizzata sopra deve corrispondere alle informazioni sul contatto dell'utente/degli utenti impostate nell'interfaccia di amministrazione di Office 365. 
  
## <a name="about-windows-powershell"></a>Su Windows PowerShell

Con Windows PowerShell per gestire utenti e quali vengono o non è consentiti eseguire. Windows PowerShell consentono di gestire Office 365 e Skype per Business Online utilizzando un singolo punto di amministrazione che consente di semplificare le attività quotidiane, soprattutto se si dispone di più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)
