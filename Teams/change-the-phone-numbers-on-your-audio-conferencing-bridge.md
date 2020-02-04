---
title: Cambiare i numeri di telefono del bridge per i servizi di audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: When you buy Audio Conferencing licenses, Microsoft is hosting your audio conferencing bridge for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.
ms.openlocfilehash: 7476f7831ce830c8719940ae555dcd461e19ab2c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684109"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiare i numeri di telefono del bridge per i servizi di audioconferenza

Quando si acquistano le licenze per i servizi **di audioconferenza,** Microsoft ospita il Bridge per audioconferenza per l'organizzazione. Il Bridge per i servizi di audioconferenza offre numeri di telefono con accesso esterno provenienti da posizioni diverse in modo che gli organizzatori e i partecipanti possano usarli per partecipare alle riunioni di Skype for business o Microsoft teams con un telefono.
  
Oltre ai numeri di telefono già assegnati al Bridge per i servizi di conferenza, è possibile [ottenere numeri di servizio aggiuntivi](/microsoftteams/getting-service-phone-numbers) (numeri verdi e numerati usati per le conferenze audio) da altre posizioni e quindi assegnarli al Bridge di conferenza in modo da poter espandere la copertura per gli utenti.
  
> [!NOTE]
> Per poter assegnare o annullare l'assegnazione di un numero di telefono per un Bridge per i servizi di conferenza, il numero di telefono deve essere un numero di*servizio*. Per visualizzare il tipo di numero, è possibile spostarsi in numeri di **** > **telefono** vocale nel portale legacy e cercare nella colonna tipo di **numero** . I crediti per le comunicazioni di Office 365 devono essere configurati prima di tutto per consentire agli utenti di effettuare una chiamata in plancia su un numero verde.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Passaggio 1-assegnare il nuovo numero di telefono al Bridge di audioconferenza

1. Accedi a Office 365 con l'account aziendale.

2. Accedere a**Teams** > di interfaccia**di amministrazione di** > interfaccia di amministrazione di **Microsoft 365** > &**numeri di telefono****vocali** > del**portale** > legacy Skype.

3. Selezionare il numero di telefono nell'elenco, quindi fare clic su **assegna**nel riquadro azioni.

4. Sulla pagina **Assegna**, fai clic su **Salva**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Passaggio 2: cambiare il numero di telefono predefinito del Bridge di conferenza (facoltativo)

Il numero di telefono predefinito del Bridge conferenza definisce l'ID chiamante che verrà usato quando una chiamata in uscita viene inserita da un partecipante o dall'organizzatore all'interno di una riunione.

Solo un numero a pagamento del servizio può essere impostato come numero predefinito per il Bridge per i servizi di conferenza; **i numeri verdi del servizio non possono essere impostati come numero predefinito del Bridge per i servizi di conferenza**. Se si sta assegnando un numero di servizio a pagamento e si vuole impostarlo come nuovo numero predefinito per il Bridge di audioconferenza, eseguire questa procedura:

1. Accedi a Office 365 con l'account aziendale.

2. Vai all'interfaccia**di amministrazione di** > interfaccia di amministrazione di **Microsoft 365** > &**ponti conferenza****riunioni** > **Skype** > .

3. Evidenziare il numero a pagamento del servizio che si vuole configurare come predefinito.

4. Selezionare **Imposta come predefinito**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Passaggio 3-modificare i numeri di telefono predefiniti inclusi negli inviti alla riunione degli utenti (facoltativo)

I numeri di telefono predefiniti di un utente sono quelli inclusi negli inviti alla riunione quando pianificano una riunione. Per altre informazioni, incluso il modo in cui vengono assegnati i numeri di telefono di defaul per i nuovi utenti, vedere [impostare i numeri di telefono inclusi negli inviti in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md) o [impostare i numeri di telefono inclusi negli inviti in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Accedere ai team di**Amministrazione** > dell'interfaccia di amministrazione di **Microsoft 365** > &**agli utenti**di servizi di**audioconferenza** > di**Skype** > **legacy Portal** > e selezionare gli utenti nell'elenco.

3. Nel riquadro Azione, fai clic su **Modifica**.

4. In numero a **pagamento predefinito** o **numero verde predefinito**Selezionare il numero nell'elenco e fare clic su **Salva**.

Dopo aver salvato le modifiche, i nuovi numeri di telefono predefiniti verranno inclusi nella riunione invita gli organizzatori la volta successiva che pianificano una nuova riunione.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Passaggio 4-aggiornare gli inviti alle riunioni esistenti degli utenti che usano il servizio di migrazione delle riunioni (facoltativo)

Per i due passaggi successivi sarà necessario avviare Windows PowerShell.
  
Se sono stati aggiornati i numeri di telefono predefiniti inlcuded nella riunione invita per alcuni o tutti gli utenti, è possibile facoltativamente aggiornare gli inviti alle riunioni già inviati agli utenti dell'organizzazione prima che i numeri di telefono predefiniti vengano modificati usando il Servizio di migrazione delle riunioni. Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Eseguire il servizio di migrazione delle riunioni (MMS) per gli utenti che avevano i numeri di telefono predefiniti modificati nel passaggio 2. Per farlo, eseguire il comando seguente:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- È inoltre possibile visualizzare lo stato della migrazione della riunione. Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza


Quando si annulla l'assegnazione di un numero di telefono da un ponte di conferenza, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono. Poiché il numero di telefono cambia, è importante aggiornare tutti gli utenti che potrebbero avere un numero di telefono come numero predefinito (se disponibile) e aggiornare gli inviti alle riunioni esistenti prima che il numero di telefono venga assegnato dal Bridge di audioconferenza.

Se il numero di telefono viene rimosso senza aggiornare gli utenti e le relative riunioni, gli inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona per partecipare alle riunioni.

Per i tre passi successivi, è necessario avviare Windows PowerShell. Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Passaggio 1-aggiornare gli utenti che hanno il numero di telefono per non essere assegnati come uno dei numeri predefiniti

Sostituire il numero verde o a pagamento predefinito per tutti gli utenti che hanno il numero da non assegnare come numero predefinito e avviare il processo di ripianificazione delle riunioni. Per farlo, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >È anche possibile modificare il numero verde o il pedaggio predefinito degli utenti nell'interfaccia di amministrazione di Skype for business. Tuttavia, questa azione non riprogrammerà automaticamente le riunioni. 
 
 Per altre informazioni, vedere [impostare i numeri di telefono inclusi negli inviti in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md) o [impostare i numeri di telefono inclusi negli inviti in Skype for business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell

Tutte le riunioni verranno ripianificate quando non ci sono operazioni in stato in *sospeso* o *in corso* .

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Passaggio 3-annullare l'assegnazione del vecchio numero di telefono dal Bridge di audioconferenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Accedere ai team di interfaccia**di amministrazione di** > interfaccia di amministrazione di **Microsoft 365** > **&** > i**numeri di telefono****vocali** > del**portale** > legacy Skype.

3. Se il numero di telefono è un numero verde, selezionare il numero di telefono nell'elenco e quindi fare clic su **Annulla assegnazione**nel riquadro azioni. Se il numero di telefono è un numero a pagamento, contattare il [supporto Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) per ottenere il numero di telefono non assegnato.

4. Se il numero di telefono è un numero a pagamento, fare clic su **Sì** nella finestra di conferma.

   > [!IMPORTANT]
   > Dopo che un numero di telefono non è stato assegnato da un Bridge per i servizi di audioconferenza, il numero di telefono non sarà più disponibile per consentire agli utenti di partecipare a riunioni nuove o esistenti.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Per verificare se Windows PowerShell è pronto

 Questa procedura consente di verificare che sia in esecuzione Windows PowerShell versione 3,0 o successiva.

1. Digita **Menu di avvio** > **Windows PowerShell**.

2. Digita _Get-Host_ nella finestra di **Windows PowerShell** per verificare la versione.

3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.
Quando richiesto, riavviare il computer.

4. È inoltre necessario installare il modulo Windows PowerShell per Skype for business online che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online. Questo modulo è supportato solo in computer a 64 bit e può essere scaricato dall'area download Microsoft nel [modulo di Windows PowerShell per Skype for business online](https://go.microsoft.com/fwlink/?LinkId=294688).
Se richiesto, riavviare il computer.

Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Per avviare Windows PowerShell

 **Avviare una sessione di Windows PowerShell**

1. Fare clic sul pulsante **Start** > **Windows PowerShell**.

2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o connettersi [a Skype for business online tramite Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Risparmiare tempo e automatizzare

Per risparmiare tempo automatizzando questo processo, è possibile usare i cmdlet [set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **set-CsOnlineDialInConferencingUserDefaultNumber** .

- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.

  - Per modificare il numero verde predefinito di un utente, esegui:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.

    > [!NOTE]
    > Per trovare il BridgeID, usa il **Get-CsOnlineDialInConferencingBridge**.

  - Per modificare il numero verde predefinito di tutti gli utenti a cui ne manca uno in 8005551234, esegui:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti che hanno 8005551234 come numero verde predefinito in 8005551239 e ripianificare automaticamente le loro riunioni, esegui:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti con sede negli USA in 8005551234 e ripianificare automaticamente le loro riunioni, esegui:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > La posizione usata sopra deve corrispondere alle informazioni di contatto degli utenti impostati nell'interfaccia di amministrazione di Microsoft 365.

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Pulsante Annulla assegnazione in grigio**

Si vuole annullare l'assegnazione di un numero ma il pulsante è in grigio e se durante l'aspirapolvere viene reindirizzato al supporto per il contatto con il messaggio seguente _"i numeri predefiniti o condivisi possono ´ non essere assegnati dal Bridge. Per annullare l'assegnazione di numeri a pedaggio dedicati, contattare il supporto tecnico._".

Per ottenere altre informazioni sui Bridge, eseguire la seguente PowerShell:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Il risultato, oltre ad altre informazioni come l'identità, il nome e l'area geografica, dovrebbe contenere anche il DefaultServiceNumber.

Ad **esempio**, per annullare l'assegnazione, DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informazioni su Windows PowerShell

Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no. Windows PowerShell consente di gestire Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, in particolare quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:

  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usare Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)
