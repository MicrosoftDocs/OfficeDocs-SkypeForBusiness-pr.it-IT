---
title: "Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
description: "Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. "
---

# Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Audioconferenza in Office 365 consente agli utenti dell'organizzazione creare un Skype per le riunioni aziendali e Teams Microsoft e quindi consentire agli utenti di connettersi a essa mediante il telefono. In Office 365, è possibile dell'utilizzo di un bridge di conferenza audio Microsoft o utilizzare un bridge di audioconferenza di terze parti che è ospitato da un provider di conferenze audio approvata (servizi di Audioconferenza).
  
Un bridge per i servizi di conferenza ti offre una serie di numeri di telefono per la tua organizzazione. Tutti possono essere utilizzati per partecipare alle riunioni create da un organizzatore di riunioni, ma puoi selezionare quelli da includere negli inviti alla riunione.
  
> [!NOTE]
> È possibile che un massimo di un numero a pagamento e un numero verde nella convocazione di riunione per l'organizzatore della riunione, ma è anche un collegamento nella parte inferiore di ogni convocazione di riunione che si apre l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere usate per partecipare a una riunione. 
  
## Impostazione del numero di telefono predefinito per un organizzatore di riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Scegliere **Interfacce di amministrazione** > **Skype for Business**. 
    
3. Scegliere **Utenti**. 
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Scegliere quale utente modificare: 
    
  - Per selezionare un solo utente, scegliere il nome corrispondente.
    
  - Per selezionare tutti gli utenti nella pagina, selezionare la casella di controllo accanto a **Nome visualizzato** in alto nell'elenco.
    
  - Per selezionare più utenti, tenere premuto CTRL e scegliere gli utenti desiderati.
    
5. Nel riquadro destro scegliere **Modifica**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Nell'elenco a discesa **Provider** verso il basso, scegliere il provider per l'utente. A seconda del provider, completare le caselle seguenti.
    
  - **Microsoft è il provider di servizi**: utilizzare il **numero a pagamento predefinito** e **numero verde predefinito** elenchi per selezionare i numeri predefiniti per l'utente.
    
    > [!NOTE]
    > Devi assegnare almeno un numero verde al bridge per i servizi di conferenza per poterlo impostare come numero verde predefinito per un utente. Per ottenere un numero verde, consulta [Recupero di numeri di telefono di servizio Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). 
  
  - **Se il provider è di terze parti**: utilizzare i campi **Numero a tariffa** e **Numero verde** per immettere i numeri per l'utente.
    
## Reimpostare i numeri di telefono di conferenze audio

1. In **Interfaccia di amministrazione di Skype for Business**, scegliere **conferenze Audio**.
    
2. Nella parte superiore della pagina, scegliere **utenti accesso esterno**.
    
3. Scegliere gli utenti desiderati, poi scegliere **Cancella**. 
    
    ![Choose Clear to reset phone numbers.](../images/28664b62-0d6f-42e1-960b-fdb1c6c14020.png)
  
Per impostazione predefinita, quando si modificano le impostazioni di servizi di conferenza dell'utente, messaggi di posta elettronica inviati agli utenti. Per modificare questa impostazione, vedere [Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
  
> [!IMPORTANT]
> Quando si modificano le impostazioni di conferenze audio di un utente, è necessario aggiornato ricorrente e futuri Skype per le riunioni aziendali e Teams Microsoft e inviare ai partecipanti. 
  
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) .
    
- Utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero verde predefinito o il numero verde per utenti specifici.
    
    Per modificare il numero verde predefinito di un utente, esegui:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.
    
    > [!NOTE]
    > Per trovare il BridgeID, usa il **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  
  ```

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Per impostare il numero verde predefinito per tutti gli utenti senza uno a +18005551234, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti che hanno +18005551234 come il numero verde predefinito per +18005551239, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Per impostare il numero verde predefinito di tutti gli utenti che si trova negli Stati Uniti a +18005551234, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti che hanno +18005551234 come il numero verde predefinito per +18005551239 e modificare la pianificazione di tutte le riunioni con nuovo numero verde, eseguire:
    
  -     > [!NOTE]
    > La località che viene utilizzata sopra deve corrispondere alle informazioni sul contatto dell'utente/degli utenti impostate nell'interfaccia di amministrazione di Office 365. 
  
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

