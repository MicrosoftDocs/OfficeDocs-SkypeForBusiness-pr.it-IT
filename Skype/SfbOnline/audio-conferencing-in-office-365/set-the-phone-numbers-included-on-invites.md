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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Ottenere i passaggi per creare un numero di telefono predefinito affinché i chiamanti possano partecipare ad una riunione di Skype for Business online. '
ms.openlocfilehash: 7136a8108a5ecd9e55d2def1e4cedd1076b270ff
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729055"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Impostare in Skype for Business online i numeri di telefono inclusi negli inviti

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Per informazioni sui numeri di telefono inclusi negli inviti di Microsoft Teams, vedere[Impostare i numeri di telefono inclusi negli inviti di Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

L'audioconferenza in Microsoft 365 o Office 365 consente agli utenti dell'organizzazione di creare riunioni Skype for Business e quindi consentire agli utenti di accedere a tali riunioni usando un telefono. In Microsoft 365 e Office 365, è possibile usare un bridge di audioconferenza Microsoft o un bridge di audioconferenza di terze parti ospitato da un provider di servizi di audioconferenza (ACP) approvato.
  
> [!NOTE]
> Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza. Se si sta cercando di verificare se sono disponibili numeri di telefono per l'accesso esterno nella propria area geografica o paese/area geografica, usare l'interfaccia di amministrazione di **Skype for Business**  >  **Numeri**  >  **vocali Telefono**,  fare clic su Aggiungi e quindi su Nuovi numeri di **servizio**. Utilizza gli elenchi **Paese/area geografica**, **Stato/regione** e **Città** per filtrare la ricerca. > Inoltre, se stai cercando numeri di servizio gratuiti, seleziona **Numero verde** dall'elenco **Stato/regione**.
  
Un ponte per conferenze offre un insieme di numeri di telefono di accesso esterno per l'organizzazione. Tutti questi numeri possono essere utilizzati per accedere alle riunioni create dall'organizzatore, ma è possibile selezionare quelli che verranno inclusi negli inviti alle riunioni.
  
> [!NOTE]
> Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Impostare il numero di telefono di accesso esterno predefinito per l'organizzatore della riunione

1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Scegli **Utenti**.
    
    ![Mostra la selezione di utenti nell'Skype for Business di amministrazione.](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Scegli gli utenti che desideri modificare:
    
   - Per selezionare un singolo utente, seleziona il nome dell'utente.
    
   - Per selezionare tutti gli utenti della pagina, seleziona la casella accanto al **Nome visualizzato** nella parte superiore dell'elenco.
    
   - Per selezionare più utenti, seleziona la casella accanto al nome di ogni utente.
    
5. Nel riquadro destro, scegli **Modifica**.
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Scegli **servizi di audioconferenza**.
    
7. Nella pagina **Proprietà** nell'elenco **Nome provider** scegli il provider per l'utente. A seconda del provider, completa le caselle seguenti.
    
   - **Microsoft è il provider**: usa gli elenchi **Numero a pagamento predefinito** e **Numero verde predefinito** per selezionare i numeri predefiniti per l'utente.
    
     > [!NOTE]
     > Almeno un numero verde deve essere assegnato al ponte per conferenze prima che possa essere impostato come numero verde predefinito per un utente. Per ottenere un numero verde, vedere Ottenere i numeri di telefono del servizio [per Skype for Business](/microsoftteams/getting-service-phone-numbers). 
  
   - **Il provider è una terza parte**: utilizza i campi **Numero a pagamento** e **Numero verde** per immettere i numeri per l'utente.


## <a name="reset-audio-conferencing-phone-numbers"></a>Reimpostare i numeri di telefono per Audioconferenza

1. **Nell'Skype for Business di amministrazione scegliere** **Audioconferenza.**
    
2. Nella parte superiore della pagina, scegli **Utenti**.
    
3. Scegli gli utenti che desideri ripristinare e quindi nel riquadro azioni, fai clic su **Cancella**.
    
Per impostazione predefinita, quando si modificano le impostazioni di conferenza dell'utente, un messaggio di posta elettronica viene inviato all'utente. Per modificare questa impostazione, vedere [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di audioconferenza.](enable-or-disable-sending-emails-when-their-settings-change.md)
  
> [!IMPORTANT]
> Quando vengono modificate le impostazioni di audioconferenza di un utente, è necessario aggiornare le riunioni di Skype for Business ricorrenti e future ed inviarle ai partecipanti. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Usa il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) per modificare il numero a pagamento o verde predefinito di utenti specifici.
    
    Per modificare il numero verde predefinito di un utente, esegui:
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Usa il cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** per cambiare il numero a pagamento o verde predefinito di utenti in base al loro numero predefinito originale o alla loro località.
    
    > [!NOTE]
    > Per trovare bridgeID, usare il cmdlet **Get-CsOnlineDialInConferencingBridge.**
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Per impostare il numero verde predefinito per tutti gli utenti senza uno su +18005551234, eseguire:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Per modificare il numero verde predefinito di tutti gli utenti che hanno +18005551234 come numero verde predefinito in +18005551239, eseguire:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Per impostare il numero verde predefinito di tutti gli utenti che si trovano negli Stati Uniti su +18005551234, eseguire:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Per altre informazioni sulle Windows PowerShell?
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
