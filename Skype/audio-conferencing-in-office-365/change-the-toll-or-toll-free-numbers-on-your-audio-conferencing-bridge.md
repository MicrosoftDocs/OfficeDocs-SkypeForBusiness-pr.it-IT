---
title: "Modificare il numero verde o numeri a pagamento gratuito il bridge di conferenze Audio"
ms.author: tonysmit
author: tonysmit
ms.date: 11/29/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingRemovePhoneNumberFromBridge
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
description: "Quando si acquistano licenze Audioconferenza, Microsoft ospita i bridge di conferenza audio per l'organizzazione. Bridge audioconferenza fornisce i numeri di telefono di accesso esterno da diverse posizioni in modo che i partecipanti e organizzatori della riunione usarli per partecipare a Skype for Business o Teams Microsoft riunioni tramite telefono."
---

# Modificare il numero verde o numeri a pagamento gratuito il bridge di conferenze Audio

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/6403f6d1-c05a-44ab-a6e0-558000e246f4). 
  
Quando si acquistano licenze **Audioconferenza**, Microsoft ospita i  *bridge di conferenza audio*  per l'organizzazione. Bridge audioconferenza fornisce i numeri di telefono di accesso esterno da diverse posizioni in modo che i partecipanti e organizzatori della riunione usarli per partecipare a Skype for Business o Teams Microsoft riunioni tramite telefono.
  
Oltre ai numeri di telefono già assegnati al bridge di conferenza, è possibile [Recupero di numeri di telefono di servizio Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) (a pagamento e numeri verdi utilizzati per le conferenze audio) da altri percorsi e quindi assegnare loro per i servizi di conferenza bridge in modo da poter Espandere la copertura per gli utenti.
  
> [!NOTE]
> Per assegnare o annullare l'assegnazione di un numero di telefono per un bridge di conferenza, il numero di telefono deve essere un numero " *servizio*  ". È possibile visualizzare il tipo di numero è posizionandosi **vocali** > **numeri di telefono** e la ricerca nella colonna **Tipo di numero**. > Office 365 comunicazioni crediti necessario impostare prima per consentire agli utenti di comporre in bridge su un numero verde. Vedere [Modificare il numero verde o numeri a pagamento gratuito il bridge di conferenze Audio](6403f6d1-c05a-44ab-a6e0-558000e246f4.md). 
  
## Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza

### Passaggio 1 - assegnare il nuovo numero di telefono per il bridge di conferenza audio

1. Accedi a Office 365 con l'account aziendale.
    
2. Passare all'interfaccia **di amministrazione di Office 365** > **amministratore Centra** > **Skype for Business** > **vocali** > **numeri di telefono**.
    
3. Selezionare il numero di telefono dall'elenco nel riquadro azioni, quindi fare clic su **Assegna**.
    
4. Sulla pagina **Assegna**, fai clic su **Salva**.
    
    Solo un numero a pagamento servizio può essere impostato come il numero predefinito per il bridge di conferenza; **numeri verdi servizio non è possibile impostare come il numero predefinito del bridge di conferenza**. Se si sta assegnando un numero a pagamento servizio e si desidera impostare come nuovo numero predefinito per il bridge di conferenza audio, selezionare **Usa questo numero come predefinito**.
    
    > [!NOTE]
    > Dopo che è stato assegnato un nuovo numero di telefono, anche se il numero è diventato il nuovo numero predefinito, non è possibile modificare il numero predefinito per gli attuali utenti. Per impostare il numero a pagamento predefinito o un numero verde che viene aggiunto alla riunione dell'organizzatore invita, vedere [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md). 
  
### Passo 2 - Cambiare i numeri di telefono predefiniti inclusi nelle inviti alle riunioni degli utenti (facoltativo)

I numeri di telefono predefinito per utente sono quelli inclusi nel loro riunione invita quando si pianifica una riunione. Per ulteriori informazioni, vedere [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
1. Accedere a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passare all'interfaccia **di amministrazione di Office 365** > **amministratore Centra** > **Skype for Business** > **conferenze Audio** > **utenti** e selezionare gli utenti nell'elenco.
    
3. Nel riquadro Azione, fai clic su **Modifica**.
    
4. In **numero a pagamento predefinito** o **numero verde predefinito**, selezionare il numero nell'elenco e fare clic su **Salva**.
    
Dopo che sono state salvate le modifiche, il telefono predefinito nuovi numeri saranno incluso nella riunione invita degli organizzatori della volta successiva che si pianifica una nuova riunione.
  
### Passo 3 - Aggiornare gli inviti alle riunioni esistenti degli utenti che utilizzano il servizio MMS (Meeting Migration Service) (facoltativo)

Per i due passaggi successivi, sarà necessario avviare Windows PowerShell. Per informazioni su come eseguire questa operazione, fare clic [Vuoi sapere come gestire queste operazioni con Windows PowerShell?](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell).
  
Usa il servizio di migrazione di riunione, è possibile aggiornare facoltativamente inviti alle riunioni già inviati agli utenti dell'organizzazione prima che i numeri di telefono predefinito sono stati modificati. Per ulteriori informazioni, vedere [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).
  
- Eseguire il servizio di migrazione riunione (MMS) per gli utenti che dispongono i numeri di telefono predefinito modificati nel passaggio 2. A tale scopo, eseguire il comando seguente:
    
```
	Start-CsExMeetingMigration user@contoso.com

```

- È inoltre possibile visualizzare lo stato della migrazione della riunione. Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .
    
```
	Get-CsMeetingMigrationStatus -SummaryOnly
```

## Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza
<a name="bk_StartPowerShell"> </a>

Quando si annullare l'assegnazione di un numero di telefono a un bridge di conferenza, gli utenti non potranno partecipare a riunioni con più il numero di telefono. Poiché sta modificando il numero di telefono, è importante per aggiornare tutti gli utenti che potrebbero avere un numero di telefono come il numero predefinito (se presente) e per aggiornare gli esistenti prima che il numero di telefono viene assegnato dal bridge di conferenze audio della riunione gli inviti.
  
Se il numero di telefono viene rimosso senza aggiornare gli utenti e le loro riunioni, i loro inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona più per partecipare.
  
Per i primi tre passaggi, sarà necessario avviare Windows PowerShell. Per informazioni su come eseguire questa operazione, fare clic [Vuoi sapere come gestire queste operazioni con Windows PowerShell?](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell).
  
### Passo 1 - Aggiornare gli che hanno il numero di telefono di cui rimuovere l'assegnazione tra i loro numeri predefiniti

Sostituire numero a tariffa o numero verde predefinito per tutti gli utenti che hanno come numero predefinito il numero di cui annullare l'assegnazione e avviare il processo di ripianificazione delle loro riunioni. Per farlo, eseguire il comando seguente:
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

> [!NOTE]
> A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo. 
  
 **è inoltre possibile modificare il numero verde predefinito o il numero verde utenti di Skype per Business admin center. Tuttavia, questo non è possibile automaticamente modificare la pianificazione alle riunioni**. Per ulteriori informazioni, vedere[Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
### Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell

Una volta non sono presenti operazioni nello stato  *in sospeso*  o *In corso*  , verranno riprogrammate tutte le riunioni.
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).
  
### Passaggio 3 - annullare l'assegnazione di vecchio numero di telefono dal bridge di conferenze audio

1. Accedere a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passare all'interfaccia **di amministrazione di Office 365** > **amministratore Centra** > **Skype for Business** > **vocali** > **numeri di telefono**.
    
3. Selezionare il numero di telefono dall'elenco nel riquadro azioni, quindi fare clic su **Annulla assegnazione**.
    
4. Nella finestra di conferma fare clic su **Sì**.
    
> [!IMPORTANT]
> Dopo avere inserito un numero di telefono assegnato da un bridge di conferenze audio, il numero di telefono non saranno disponibile per gli utenti partecipare alle riunioni di nuove o esistente. 
  
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?
<a name="bk_PowerShell"> </a>

### Per verificare se Windows PowerShell è pronto

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
  
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
### Per avviare Windows PowerShell

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
  
### Automatizzare o risparmiare tempo

Per risparmiare tempo o automatizzare questa procedura, è possibile utilizzare i cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** o[Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) .
  
- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.
    
  - Per modificare il numero verde predefinito di un utente, esegui:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.
    
    > [!NOTE]
    > Nota:per trovare il BridgeID, usa il **Get-CsOnlineDialInConferencingBridge**.
  
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
  
### Per saperne di più

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
  

