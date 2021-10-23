---
title: Modificare i numeri di telefono nel bridge di audioconferenza
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sui passaggi necessari per assegnare un nuovo numero di telefono del servizio al bridge di conferenza per espandere la copertura per gli utenti.
ms.openlocfilehash: f39a963759e768f4fab70d2a06e6d90b480699e0
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536717"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiare i numeri di telefono del bridge per i servizi di audioconferenza

Quando si acquistano licenze **di audioconferenza,** Microsoft ospita il bridge di audioconferenza per l'organizzazione. Il bridge di audioconferenza fornisce numeri di telefono per l'accesso esterno da posizioni diverse, in modo che gli organizzatori e i partecipanti possano usarli per partecipare alle riunioni Skype for Business o Microsoft Teams con un telefono.
  
Oltre ai numeri di telefono già assegnati al bridge di conferenza, è possibile ottenere altri numeri di servizio [(numeri](./getting-service-phone-numbers.md) a pedaggio e a numero verde usati per le audioconferenze) da altre posizioni e quindi assegnarli al bridge di conferenza in modo da poter espandere la copertura per gli utenti.
  
> [!NOTE]
> Per poter assegnare/annullare l'assegnazione di un numero di telefono per un bridge di conferenza, il numero di telefono deve essere un *numero* di servizio. Per visualizzare il tipo di numero, passare a Numeri Telefono voce nell'interfaccia di amministrazione di Microsoft Teams e cercare nella  >   **colonna Tipo** numero. Microsoft 365 o Office 365 i Crediti comunicazioni devono essere impostati per primi per consentire agli utenti di accedere al bridge su un numero verde.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Istruzioni per assegnare un numero telefonico di servizio al tuo bridge di conferenza

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Passaggio 1 - Assegnare il nuovo numero di telefono al bridge di audioconferenza

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro passare **a** Numeri  >  **Telefono vocali.**

2. Selezionare il numero di telefono nell'elenco e fare clic su **Modifica**.

3. Nella pagina **Modifica,** in **Assegnato a,** espandere l'elenco a discesa e quindi selezionare **Bridge di**  >  **conferenza Applica.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Passaggio 2 - Modificare il numero di telefono predefinito del bridge di conferenza (facoltativo)

Il numero di telefono predefinito del bridge di conferenza definisce l'ID chiamante che verrà usato quando un partecipante o l'organizzatore esegue una chiamata in uscita all'interno di una riunione.

È possibile impostare come numero predefinito per il bridge di conferenza solo un numero a pedaggio del servizio. **I numeri verde del servizio non possono essere impostati come numero predefinito del bridge di conferenza.** Se si sta assegnando un numero a pedaggio del servizio e si vuole impostarlo come nuovo numero predefinito per il bridge di audioconferenza, eseguire questa procedura:

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro passare a **Ponti**  >  **conferenza riunioni**.

2. Evidenziare il numero a pedaggio del servizio che si vuole configurare come predefinito.

3. Selezionare **Imposta come predefinito.**
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Passaggio 3 - Modificare i numeri di telefono predefiniti inclusi negli inviti alla riunione degli utenti (facoltativo)

I numeri di telefono predefiniti di un utente sono quelli inclusi nelle convocazioni di riunione quando pianificano una riunione. Per altre informazioni, inclusa la modalità di assegnazione dei numeri di telefono predefiniti per i nuovi utenti, vedere Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in [Skype for Business Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro passare a **Utenti** e fare clic sul nome visualizzato dell'utente desiderato nell'elenco.

2. Accanto a **Audioconferenza** fare clic su **Modifica.**

3. In **Numero verde o** **Numero** verde selezionare il numero nell'elenco a discesa e fare clic su **Applica.**

Dopo l'applicazione delle modifiche, i nuovi numeri di telefono predefiniti verranno inclusi nelle convocazioni di riunione degli organizzatori alla successiva pianificazione di una nuova riunione.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Passaggio 4 - Aggiornare gli inviti a riunioni esistenti degli utenti usando il servizio di migrazione delle riunioni (facoltativo)

Per i due passaggi successivi, è necessario iniziare a Windows PowerShell.
  
Se sono stati aggiornati i numeri di telefono predefiniti inclusi negli inviti alla riunione per alcuni o tutti gli utenti, è possibile aggiornare facoltativamente gli inviti alle riunioni già inviati agli utenti dell'organizzazione prima che i numeri di telefono predefiniti siano stati modificati con il servizio di migrazione delle riunioni. Per ulteriori informazioni, consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Eseguire il servizio di migrazione delle riunioni (MMS) per gli utenti che hanno modificato i numeri di telefono predefiniti nel passaggio 2. Per farlo, eseguire il comando seguente:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- È inoltre possibile visualizzare lo stato della migrazione della riunione. Tutte le riunioni sono ripianificate una volta che non ci sono più operazioni con lo stato  *In attesa*  o *In corso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Istruzioni per annullare l'assegnazione di un numero telefonico di servizio da un bridge di conferenza


Quando si annulla l'assegnazione di un numero di telefono da un ponte di conferenza, gli utenti non saranno più in grado di partecipare alle riunioni con quel numero di telefono. Poiché il numero di telefono cambia, è importante aggiornare tutti gli utenti che potrebbero avere un numero di telefono come numero predefinito (se presente) e aggiornare gli inviti alle riunioni esistenti prima che il numero di telefono non sia assegnato dal bridge di audioconferenza.

Se il numero di telefono viene rimosso senza aggiornare gli utenti e le riunioni, gli inviti alle riunioni esistenti potrebbero contenere un numero di telefono che non funziona per partecipare alle riunioni.

Per i tre passi successivi, è necessario avviare Windows PowerShell. Per informazioni su come eseguire questa operazione, fai clic su [Vuoi sapere come gestire con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Passaggio 1 - Aggiornare gli utenti che hanno il numero di telefono da annullare l'assegnazione come uno dei numeri predefiniti

Sostituire il numero verde o a pedaggio predefinito per tutti gli utenti che hanno il numero da annullare l'assegnazione come numero predefinito e avviare il processo di riprogrammazione delle riunioni. Per farlo, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >È anche possibile modificare il numero di utenti a pedaggio o a numero verde predefinito nell'interfaccia Microsoft Teams di amministrazione. Tuttavia, questa azione non riprogrammerà automaticamente le riunioni. 
 
 Per altre informazioni, vedere Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o Impostare i numeri di telefono inclusi negli inviti in [Skype for Business Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > A seconda delle dimensioni della tua organizzazione, questa operazione potrebbe richiedere un certo tempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Passo 2 - Visualizzare lo stato della migrazione delle riunioni con Windows PowerShell

Tutte le riunioni verranno riprogrammate quando non sono presenti operazioni *in* stato In sospeso *o In* corso.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Per ulteriori informazioni sul servizio MMS (Meeting Migration Service), consulta [Configurazione del servizio MMS (Meeting Migration Service)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Passaggio 3 - Annullare l'assegnazione del vecchio numero di telefono dal bridge di audioconferenza

Usare il cmdlet Unregister-CsOnlineDialInConferencingServiceNumber per annullare la registrazione di un numero verde o a pedaggio da un bridge per conferenze

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```
Nota: per trovare l'ID del bridge di conferenza, eseguire powershell seguente: Get-CsOnlineDialInConferencingBridge.


   > [!IMPORTANT]
   > Dopo che un numero di telefono non è stato assegnato da un bridge di audioconferenza, il numero di telefono non sarà più disponibile per gli utenti per partecipare a riunioni nuove o esistenti.

### <a name="save-time-and-automate"></a>Risparmiare tempo e automatizzare

Per risparmiare tempo automatizzando questo processo, è possibile usare i cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**

- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) per modificare il numero a pagamento o verde predefinito di utenti specifici.

  - Per modificare il numero verde predefinito di un utente, esegui:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.

    > [!NOTE]
    > Per trovare bridgeID, usare **Get-CsOnlineDialInConferencingBridge**.

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
    > La posizione usata in precedenza deve corrispondere alle informazioni di contatto degli utenti impostate nel interfaccia di amministrazione di Microsoft 365.

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Il pulsante Annulla assegnazione non è disponibile**

Si vuole annullare l'assegnazione di un numero ma il pulsante non è disponibile e, se si passa il puntatore del mouse su di esso, si viene reindirizzati a contattare il supporto con il messaggio seguente: "I numeri predefiniti o condivisi non possono essere non assegnati dal _bridge. Per annullare l'assegnazione di numeri a pedaggio dedicati, contattare il supporto._".

Per ottenere altre informazioni sui bridge, eseguire powershell seguente:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Il risultato, oltre ad altre informazioni come Identity, Name e Region, deve contenere anche DefaultServiceNumber.

**Esempio,** per annullare l'assegnazione, il valore DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informazioni su Windows PowerShell

Con Windows PowerShell puoi gestire gli utenti e cosa gli è consentito fare oppure no. Windows PowerShell consente di gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, soprattutto quando è necessario eseguire più attività. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

  - [Uso di Windows PowerShell per gestire Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Argomenti correlati
[Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md)
