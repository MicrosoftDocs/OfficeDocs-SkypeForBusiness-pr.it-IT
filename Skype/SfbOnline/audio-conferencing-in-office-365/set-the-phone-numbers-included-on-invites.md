---
title: Impostare il telefono numeri incluso nel invita
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'È possibile ottenere i passaggi per creare un numero di telefono predefinito per i chiamanti partecipare a una Skype per riunione in linea aziendale. '
ms.openlocfilehash: 5ddc20d1b9166315581a6f894c5d630d9e247881
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568282"
---
# <a name="set-the-phone-numbers-included-on-invites"></a>Impostare il telefono numeri incluso nel invita

Audioconferenze con accesso esterno in Office 365 consente agli utenti dell'organizzazione creare Skype per le riunioni aziendali e Teams Microsoft e quindi consentire agli utenti di accedere a tali riunioni mediante un telefono. In Office 365, è necessario l'opzione di utilizzare un ponte per conferenze audio Microsoft o un ponte per conferenze audio di terze parti ospitato da un provider approvato audioconferenza (ACP).
  
> [!NOTE]
> Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza. Se si desidera utilizzare per verificare se sono disponibili i numeri di telefono di accesso esterno nell'area o paese/area geografica, utilizzare **Skype per Business admin center** > **vocale** > **I numeri di telefono**, fare clic su **Aggiungi** , quindi **nuovi numeri di servizio **. Utilizzare gli elenchi **Paese/area geografica**, **paese** e **città** per filtrare la ricerca. >, inoltre, se sta cercando numeri a pagamento servizio gratuito, **numero verde** selezionare dal **paese** elenco.
  
Un ponte per conferenze offre un set di numeri di telefono di accesso esterno per l'organizzazione. Tutti gli elementi da utilizzare per partecipare alle riunioni creati dall'organizzatore della riunione, ma è possibile selezionare quelli che verranno inclusi nel proprio gli inviti di riunione.
  
> [!NOTE]
> Può esistere un massimo di un numero a pagamento e un numero verde nel invito alla riunione per organizzare una riunione, ma è disponibile anche un collegamento presente nella parte inferiore di ogni invito alla riunione che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che può essere utilizzato per accedere a una riunione. 
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Impostare il numero di telefono di accesso esterno predefinito per l'organizzatore della riunione

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

    ![Visualizza la selezione utenti in Microsoft Teams e Skype per Business Admin Center](../images/teamsselectusers.png)

2. Nella parte superiore della pagina, fare clic su **Modifica**.

    ![Fare clic su Modifica nel team di Microsoft e Skype per Business Admin Center](../images/teamsedituser.png)

3. Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**. 
    
    ![Fare clic su Modifica accanto a conferenze Audio](../images/teamseditaudioconf.png)

4. Utilizzare i campi **numero a pagamento** o **numero verde** per immettere i numeri per l'utente.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Scegliere **Admin Center** > **Skype per le aziende**.
    
3. Scegliere **utenti**.
    
    ![Visualizza la selezione utenti in Skype per interfaccia di amministrazione di Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Scegliere gli utenti che si desidera modificare:
    
  - Per selezionare un singolo utente, selezionare il nome dell'utente.
    
  - Per selezionare tutti gli utenti della pagina, selezionare la casella accanto al **nome visualizzato** nella parte superiore dell'elenco.
    
  - Per selezionare più utenti, selezionare la casella accanto al nome di ogni utente.
    
5. Riquadro destro fare clic su **Modifica**.
    
    ![Scegliere l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Scegliere **servizi di conferenza Audio**.
    
7. Nella pagina **proprietà** nell'elenco **nome Provider di** scegliere il provider per l'utente. A seconda del provider, completare le caselle seguenti.
    
  - **Microsoft è il provider**: **numero verde predefinito** elenchi per selezionare i numeri predefiniti per l'utente e utilizzare il **numero a pagamento predefinito** .
    
    > [!NOTE]
    > Almeno un numero verde deve essere assegnato ai bridge conferenza prima può essere impostata come il numero verde predefinito di un utente. Per ottenere un numero verde, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team di Microsoft](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
  - **Terze parti sono il provider**: utilizzare i campi **numero a pagamento** e **numero verde** per immettere i numeri per l'utente.


## <a name="change-the-audio-conferencing-phone-number-for-users"></a>Modificare il numero di telefono per conferenze audio per gli utenti

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**. 
    
4. Utilizzare i campi **numero a pagamento** o **numero verde** per immettere i numeri per l'utente.

## <a name="reset-audio-conferencing-phone-numbers"></a>Reimpostare i numeri di telefono di accesso esterno alle audioconferenze

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1. **Skype per interfaccia di amministrazione di Business**, scegliere **audioconferenze**.
    
2. Nella parte superiore della pagina, scegliere **utenti**.
    
3. Scegliere gli utenti che si desidera ripristinare e quindi nel riquadro azioni fare clic su **Cancella**.
    
Per impostazione predefinita, quando si modificano le impostazioni di conferenza dell'utente, un messaggio di posta elettronica viene inviato all'utente. Per modificare questa impostazione, vedere [abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Quando si modificano le impostazioni di conferenza audio di un utente, Skype ricorrenti e future per le riunioni aziendali e Microsoft Teams deve essere aggiornato e inviati ai partecipanti. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) per modificare il numero a pagamento o verde predefinito di utenti specifici.
    
    Per modificare il numero verde predefinito di un utente, esegui:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.
    
    > [!NOTE]
    > Per trovare il BridgeID, utilizzare il cmdlet **Get-CsOnlineDialInConferencingBridge** .
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Per impostare il numero verde predefinito per tutti gli utenti senza 1 in modo da +18005551234, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti che hanno +18005551234 come il numero verde predefinito per +18005551239, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Per impostare il numero verde predefinito di tutti gli utenti presente negli Stati Uniti a +18005551234, eseguire:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>Fonti di ulteriori informazioni su Windows PowerShell
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
