---
title: Modificare i numeri di telefono nel bridge per audioconferenza
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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sui passaggi necessari per assegnare un nuovo numero di telefono di servizio al bridge di conferenza per espandere la copertura per gli utenti.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918752"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiare i numeri di telefono del bridge per i servizi di audioconferenza

Quando acquisti licenze **per i servizi di audioconferenza,** Microsoft ospita il bridge di audioconferenza per l'organizzazione. Il bridge per i servizi di audioconferenza fornisce numeri di telefono per l'accesso esterno da diverse località, in modo che organizzatori e partecipanti possano usarli per partecipare alle riunioni Skype for Business o Microsoft Teams con un telefono.
  
Oltre ai numeri di telefono già assegnati al bridge di conferenza, puoi ottenere numeri di servizio aggiuntivi [(numeri](/microsoftteams/getting-service-phone-numbers) a pedaggio e numeri verde utilizzati per le audioconferenze) da altre località e quindi assegnarli al bridge di conferenza per poter espandere la copertura per gli utenti.
  
> [!NOTE]
> Per poter assegnare/annullare l'assegnazione di un numero di telefono per un bridge di conferenza, il numero di telefono deve essere un *numero* di ' servizio'. Per vedere il tipo di numero, passare a Numeri di telefono vocali nell'interfaccia di amministrazione di Microsoft Teams e cercare nella  >   colonna **Tipo di** numero. I Crediti comunicazioni Microsoft 365 o Office 365 devono essere prima impostati per consentire agli utenti di accedere al bridge con un numero verde.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Passaggio 1 - Assegnare il nuovo numero di telefono al bridge per audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro passa a **Numeri**  >  **di telefono vocali.**

2. Selezionare il numero di telefono nell'elenco e fare clic su **Modifica.**

3. Nella pagina **Modifica,** in **Assegnata a,** espandere l'elenco a discesa e selezionare **Applica bridge**  >  **conferenza.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Passaggio 2 - Modificare il numero di telefono predefinito del bridge di conferenza (facoltativo)

Il numero di telefono predefinito del bridge di conferenza definisce l'ID chiamante che verrà utilizzato quando una chiamata in uscita viene effettuato da un partecipante o dall'organizzatore all'interno di una riunione.

Solo un numero di servizio a numero verde può essere impostato come numero predefinito per il bridge di conferenza; i numeri di servizio gratuiti non possono essere impostati come numero **predefinito del bridge di conferenza.** Se assegni un numero di servizio a numero verde e desideri impostarlo come nuovo numero predefinito per il bridge di audioconferenza, effettua queste operazioni:

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro, passare **a Bridge**  >  **conferenza riunioni.**

2. Evidenziare il numero di servizio a numero verde da configurare come predefinito.

3. Selezionare **Imposta come predefinito.**
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Passaggio 3 - Modificare i numeri di telefono predefiniti inclusi negli inviti alle riunioni degli utenti (facoltativo)

I numeri di telefono predefiniti di un utente sono quelli inclusi nella convocazione di riunione quando pianificano una riunione. Per ulteriori informazioni, tra cui l'assegnazione dei numeri di telefono predefiniti per i nuovi utenti, consulta Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in Skype for Business [online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro passare a **Utenti e** fare clic sul nome visualizzato dell'utente desiderato nell'elenco.

2. Accanto a **Audioconferenza,** fai clic su **Modifica.**

3. In **Numero a verde o** **Numero** verde seleziona il numero nell'elenco a discesa e fai clic su **Applica.**

Dopo l'applicazione delle modifiche, i nuovi numeri di telefono predefiniti verranno inclusi nelle convocazioni di riunione degli organizzatori la volta successiva che pianificano una nuova riunione.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Passaggio 4 - Aggiornare gli inviti alle riunioni esistenti degli utenti che usano il servizio Meeting Migration Service (facoltativo)

Per i due passaggi successivi, è necessario iniziare a Windows PowerShell.
  
Se sono stati aggiornati i numeri di telefono predefiniti inclusi negli inviti alle riunioni per alcuni o tutti gli utenti, è possibile aggiornare gli inviti alle riunioni già inviati agli utenti dell'organizzazione prima che i loro numeri di telefono predefiniti siano stati modificati mediante il servizio Meeting Migration Service. Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Eseguire il servizio MMS (Meeting Migration Service) per gli utenti che hanno modificato i numeri di telefono predefiniti nel Passaggio 2. Per farlo, eseguire il comando seguente:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- È inoltre possibile visualizzare lo stato della migrazione della riunione. Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza


Quando si annulla l'assegnazione di un numero di telefono da un ponte di conferenza, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono. Dato che il numero di telefono cambia, è importante aggiornare tutti gli utenti che potrebbero avere un numero di telefono come numero predefinito (se presente) e aggiornare gli inviti alle riunioni esistenti prima che l'assegnazione del numero di telefono al bridge di audioconferenza non venga assegnata.

Se il numero di telefono viene rimosso senza aggiornare gli utenti e le loro riunioni, gli inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona per partecipare alle riunioni.

Per i tre passi successivi, è necessario avviare Windows PowerShell. Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Passo 1 - Aggiornare gli utenti che hanno il numero di telefono da annullare l'assegnazione come uno dei loro numeri predefiniti

Sostituire il numero a pedaggio o numero verde predefinito per tutti gli utenti che hanno come numero predefinito il numero da annullare e avviare il processo di ripianificazione delle loro riunioni. Per farlo, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Puoi anche modificare il numero a numero verde o a numero verde predefinito di utenti nell'interfaccia di amministrazione di Microsoft Teams. Tuttavia, questa azione non riprogrammerà automaticamente le riunioni. 
 
 Per ulteriori informazioni, consulta Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in Skype for Business [online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell

Tutte le riunioni verranno ripianificate una volta che non ci saranno operazioni in *sospeso* o *in* corso.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Passo 3 - Annullare l'assegnazione del vecchio numero di telefono dal bridge di audioconferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono**.

2. Se il numero di telefono è un numero verde, seleziona il numero di telefono nell'elenco e fai clic su **Rilascia.** Se il numero di telefono è a numero verde, contatta il [supporto Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) per ottenere l'annullamento dell'assegnazione del numero.

3. Se il numero di telefono è un numero verde, fai clic su **Sì** nella finestra di conferma.

   > [!IMPORTANT]
   > Dopo l'annullamento dell'assegnazione di un numero di telefono da un bridge per audioconferenza, il numero di telefono non sarà più disponibile per gli utenti per partecipare a riunioni nuove o esistenti.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Per verificare se Windows PowerShell è pronto

 Questi passaggi verificano che sia in esecuzione Windows PowerShell versione 3.0 o successiva.

1. Digita **Menu di avvio** > **Windows PowerShell**.

2. Digita _Get-Host_ nella finestra di **Windows PowerShell** per verificare la versione.

3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0.
Quando richiesto, riavviare il computer.

4. È inoltre necessario installare il modulo Windows PowerShell per Skype for Business online che consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online. Questo modulo è supportato solo nei computer a 64 bit e può essere scaricato dall'Area download Microsoft [nel modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
Se richiesto, riavviare il computer.

Per altre informazioni, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx)un'unica Windows PowerShell singola.

### <a name="to-start-windows-powershell"></a>Per avviare Windows PowerShell

 **Avviare una sessione di Windows PowerShell**

1. Fare clic sul pulsante **Start** > **Windows PowerShell**.

2. Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
>
> Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell oppure connettersi a [Skype for Business online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)tramite Windows PowerShell.

### <a name="save-time-and-automate"></a>Risparmiare tempo e automatizzare

Per risparmiare tempo automatizzando questo processo, puoi utilizzare i cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**

- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.

  - Per modificare il numero verde predefinito di un utente, esegui:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.

    > [!NOTE]
    > Per trovare il BridgeID, usa **Il Get-CsOnlineDialInConferencingBridge.**

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
    > La posizione usata sopra deve corrispondere alle informazioni di contatto degli utenti impostate nell'interfaccia di amministrazione di Microsoft 365.

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Il pulsante Annulla assegnazione non è disponibile**

Si vuole annullare l'assegnazione di un numero, ma il pulsante non è disponibile e, se si passa il mouse su di esso, si viene reindirizzati a contattare il supporto con il messaggio seguente "Non è possibile annullare l'assegnazione di numeri predefiniti o condivisi dal _bridge. Per annullare l'assegnazione dei numeri a verde dedicati, contatta il supporto._".

Per ottenere altre informazioni sui bridge, eseguire powershell seguente:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Il risultato, oltre ad altre informazioni come Identity, Name e Region, deve contenere anche DefaultServiceNumber.

**Ad** esempio, per annullare l'assegnazione, defaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informazioni su Windows PowerShell

Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no. Windows PowerShell consente di gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano, soprattutto quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)
