---
title: Impostare in Skype for Business online i numeri di telefono inclusi negli inviti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Ottenere i passaggi per creare un numero di telefono predefinito affinché i chiamanti possano partecipare ad una riunione di Skype for Business online. '
ms.openlocfilehash: 53a733bf7874c507416c4cc54820cbebb4fbc844
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "34329541"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Impostare in Skype for Business online i numeri di telefono inclusi negli inviti

> [!Note]
> Per informazioni sui numeri di telefono inclusi negli inviti di Microsoft Teams, vedere[Impostare i numeri di telefono inclusi negli inviti di Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone. In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.
  
A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.
  
> [!NOTE]
> Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Impostare il numero di telefono di accesso esterno predefinito per l'organizzatore della riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Scegli **Utenti**.
    
    ![Visualizza la selezione utenti nell'interfaccia di amministrazione di Skype for Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Scegli gli utenti che desideri modificare:
    
   - Per selezionare un singolo utente, seleziona il nome dell'utente.
    
   - Per selezionare tutti gli utenti della pagina, seleziona la casella accanto al **Nome visualizzato** nella parte superiore dell'elenco.
    
   - Per selezionare più utenti, seleziona la casella accanto al nome di ogni utente.
    
5. Nel riquadro destro, scegli **Modifica**.
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Scegli **servizi di audioconferenza**.
    
7. On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.
    
   - **Microsoft è il provider**: usa gli elenchi **Numero a pagamento predefinito** e **Numero verde predefinito** per selezionare i numeri predefiniti per l'utente.
    
     > [!NOTE]
     > At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers). 
  
   - **Il provider è una terza parte**: utilizza i campi **Numero a pagamento** e **Numero verde** per immettere i numeri per l'utente.


## <a name="reset-audio-conferencing-phone-numbers"></a>Reimpostare i numeri di telefono per Audioconferenza

1. Nell'interfaccia di **amministrazione di Skype for business**scegli **audioconferenza**.
    
2. Nella parte superiore della pagina, scegli **Utenti**.
    
3. Scegli gli utenti che desideri ripristinare e quindi nel riquadro azioni, fai clic su **Cancella**.
    
By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Quando vengono modificate le impostazioni di audioconferenza di un utente, è necessario aggiornare le riunioni di Skype for Business ricorrenti e future ed inviarle ai partecipanti. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.
    
    Per modificare il numero verde predefinito di un utente, esegui:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.
    
    > [!NOTE]
    > Per trovare il BridgeID, usa il cmdlet **Get-CsOnlineDialInConferencingBridge** .
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Per impostare il numero verde predefinito per tutti gli utenti senza uno a + 18005551234, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti che hanno + 18005551234 come numero verde predefinito a + 18005551239, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Per impostare il numero verde predefinito di tutti gli utenti che si trovano negli Stati Uniti in + 18005551234, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Ulteriori informazioni su Windows PowerShell
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
