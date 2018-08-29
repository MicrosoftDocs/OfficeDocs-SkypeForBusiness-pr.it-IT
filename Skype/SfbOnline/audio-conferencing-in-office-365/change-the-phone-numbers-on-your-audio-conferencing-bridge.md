---
title: Cambiare i numeri di telefono del ponte per audioconferenze
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
description: Quando si acquistano le licenze di Audioconferenza, Microsoft ospita il ponte per audioconferenze per la propria organizzazione. Il ponte per audioconferenze assegna numeri di telefono per accesso esterno da diverse località per consentire ad organizzatori di riunioni e partecipanti di usarli per partecipare alle riunioni usando un telefono.
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255712"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiare i numeri di telefono del ponte per audioconferenze

Quando si acquistano le licenze di **Audioconferenza**, Microsoft ospita il *ponte per audioconferenze* per la propria organizzazione. Il ponte per audioconferenze assegna numeri di telefono per accesso esterno da diverse località per consentire ad organizzatori di riunioni e partecipanti di usarli per partecipare alle riunioni usando un telefono.

Oltre ai numeri di telefono già assegnati al ponte per conferenze audio, è possibile [ottenere i numeri di servizio aggiuntivi](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (numeri a pagamento e numeri verdi utilizzati per le audioconferenze) da altri percorsi e di assegnarli al ponte per audioconferenza in modo da poter estendere la copertura per gli utenti.

> [!NOTE]
> Per potere assegnare/annullare l'assegnazione di un numero di telefono per un ponte per audioconferenze, il numero di telefono deve essere un numero di "*servizio*". È possibile visualizzare il tipo di numero navigando su **Voce** > **Numeri di telefono** e guardando nella colonna **Tipo di numero**. Bisogna prima impostare il Credito per la comunicazione di Office 365 per consentire agli utenti di accedere al ponte per audioconferenze su un numero verde.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Istruzioni per assegnare un numero telefonico di servizio al tuo ponte per audioconferenze

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Passo 1 - Assegnare il nuovo numero di telefono al ponte per audioconferenze

1. Accedi a Office 365 con l'account aziendale.

2. Vai all' **interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Voce** > **Numeri di telefono**.

3. Seleziona il numero di telefono dall'elenco, e nel riquadro Azioni, fai clic su **Assegna**.

4. Sulla pagina **Assegna**, fai clic su **Salva**.

    Solo un numero di servizio a pagamento può essere impostato come numero predefinito per il ponte per audioconferenze; **i numeri di servizio gratuiti non possono essere impostati come numero predefinito del ponte per audioconferenze**. Se assegni un numero di servizio a pagamento e desideri impostarlo come nuovo numero predefinito per il ponte per audioconferenze, seleziona **Utilizza questo numero come predefinito**.

    > [!NOTE]
    > Una volta assegnato un nuovo numero di telefono, anche se il numero è diventato il nuovo numero predefinito, il numero predefinito per gli utenti esistenti non cambierà. Per impostare il numero a pagamento o verde predefinito che viene aggiunto agli inviti alla riunione di un organizzatore, consulta [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Passo 2 - Cambiare i numeri di telefono predefiniti inclusi negli inviti alle riunioni degli utenti (facoltativo)

I numeri di telefono predefiniti per gli utenti sono quelli inclusi nell'invito alla riunione quando essi pianificano una riunione. Per ulteriori informazioni, consulta[Impostare i numeri di telefono numeri inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).

1. Accedi a Office 365 con l'account aziendale o scolastico.

2. Vai all'**interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Audioconferenza** > **Utenti** e seleziona gli utenti nell'elenco.

3. Nel riquadro Azione, fai clic su **Modifica**.

4. Alla voce**Numero a pagamento predefinito** o **Numero verde predefinito**, seleziona il numero nella lista e fai clic su **Salva**.

Una volta salvate le modifiche, i nuovi numeri di telefono predefiniti saranno inclusi negli inviti alle riunioni degli organizzatori la prossima volta che pianificheranno una nuova riunione.

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Passo 3 - Aggiornare gli inviti alle riunioni esistenti degli utenti che utilizzano il servizio MMS (Meeting Migration Service) (facoltativo)

Per i due passaggi successivi, è necessario avviare Windows PowerShell.

Utilizzando il servizio MMS (Meeting Migration Service), puoi aggiornare gli inviti alle riunioni che sono stati già inviati agli utenti della tua organizzazione prima che i loro numeri di telefono predefiniti venissero cambiati. Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).

- Esegui il servizio MMS (Meeting Migration Service) per gli utenti i cui numeri di telefono predefiniti sono stati cambiati nel Passo 2. Per farlo, esegui il comando seguente:

```
    Start-CsExMeetingMigration user@contoso.com
```

- È inoltre possibile visualizzare lo stato della migrazione della riunione. Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*.

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un ponte per conferenze audio


Quando si annulla l'assegnazione di un numero di telefono da un ponte per audioconferenze, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono. Dato che il numero di telefono è stato cambiato, è importante aggiornare tutti gli utenti che potrebbero avere quel numero di telefono come numero predefinito (se presente) e aggiornare i loro inviti alle riunioni esistenti prima che l'assegnazione del numero di telefono al ponte per audioconferenze venga annullata.

Se il numero di telefono viene rimosso senza aggiornare gli utenti e le loro riunioni, i loro inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona più per partecipare.

Per i primi tre passi, è necessario avviare Windows PowerShell. Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Passo 1 - Aggiornare gli utenti che hanno il numero di telefono da cui rimuovere l'assegnazione tra i loro numeri predefiniti

Sostituire numero a tariffa o numero verde predefinito per tutti gli utenti che hanno come numero predefinito il numero di cui annullare l'assegnazione e avviare il processo di ripianificazione delle loro riunioni. Per farlo, eseguire il comando seguente:

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 >È inoltre possibile modificare il numero a pagamento o il numero verde predefinito degli utenti nell'interfaccia di amministrazione di Skype for Business. Tuttavia, questa azione non riprogrammerà automaticamente le riunioni.

 Per ulteriori informazioni, consulta [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).

  > [!NOTE]
  > A seconda della grandezza della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell

Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato *In attesa* o *In corso*.

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](setting-up-the-meeting-migration-service-mms.md).

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Passo 3 - Annullare l'assegnazione del vecchio numero di telefono dal ponte per audioconferenze

1. Accedi a Office 365 con l'account aziendale o scolastico.

2. Vai all' **interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Voce** > **Numeri di telefono**.

3. Seleziona il numero di telefono dall'elenco, e nel riquadro Azioni fai clic su **Annulla assegnazione**.

4. Nella finestra di conferma, fai clic su **Sì**.

  > [!IMPORTANT]
  > Una volta annullata l'assegnazione di un numero di telefono da un ponte per audioconferenze, il numero di telefono non sarà più utilizzabile dagli utenti per partecipare a riunioni nuove o esistenti.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Come verificare se Windows PowerShell è pronto

 Questi passi verificano che sia in esecuzione Windows PowerShell 3.0 o versioni successive.

1. Digita **Menu di avvio** > **Windows PowerShell**.

2. Digita _Get-Host_ nella finestra di **Windows PowerShell** per verificare la versione.

3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.

4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
Se richiesto, riavviare il computer.

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

Per altre informazioni sull'avvio di Windows PowerShell, consulta [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Risparmiare tempo e automatizzare

Per risparmiare tempo automatizzare il processo, è possibile utilizzare [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber**.

- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.

  - Per modificare il numero verde predefinito di un utente, esegui:

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.

    > [!NOTE]
    > Per trovare il BridgeID, usa il **Get-CsOnlineDialInConferencingBridge**.

  - Per impostare il numero verde predefinito per tutti gli utenti senza uno a 8005551234, esegui:

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
    > La posizione che viene utilizzata sopra deve corrispondere alle informazioni sul contatto dell'utente/degli utenti impostate nell'interfaccia di amministrazione di Office 365.

## <a name="about-windows-powershell"></a>Informazioni su Windows PowerShell

Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, consulta questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Perché devi utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:

  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Modificare le impostazioni per un ponte per audioconferenze](change-the-settings-for-an-audio-conferencing-bridge.md)
