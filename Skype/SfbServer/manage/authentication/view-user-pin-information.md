---
title: Visualizzare le informazioni sul PIN dell'utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: "Riepilogo: visualizzare le informazioni sul PIN dell'utente Skype for Business Server."
ms.openlocfilehash: 9135a502879f3d6d28c2aab9fbdbf81e9d399e29
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765504"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Visualizzare le informazioni sul PIN dell'utente in Skype for Business Server
 
**Riepilogo:** Visualizzare le informazioni sul PIN dell'utente Skype for Business Server.
  
Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Skype for Business Server con credenziali di Servizi di dominio Active Directory richiede un PIN. Puoi visualizzare le informazioni sul PIN di un utente Skype for Business Server Pannello di controllo.
  
> [!NOTE]
> È possibile visualizzare informazioni sullo stato del PIN, ad esempio per scoprire se il PIN è stato impostato o quando è stato modificato l'ultima volta, ma non è possibile vedere il PIN corrente controllandone lo stato. Se un utente ha perso il PIN, è possibile reimpostarlo seguendo le procedure descritte in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Per visualizzare il PIN di un utente nel Skype for Business Server Pannello di controllo

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Utilizzare uno dei metodi seguenti per individuare un utente:
    
   - Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.
    
   - Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.
    
5. (Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:
    
   a. Fare clic su **Aggiungi filtro**.
    
   b. Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.
    
   c. Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).
    
   d. A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.
    
    > [!TIP]
    > Per aggiungere ulteriori clausole di ricerca alla query, fare clic su **Aggiungi filtro**. 
  
   e. Fare clic su **Trova**.
    
    > [!NOTE]
    > Se il PIN è bloccato, è necessario sbloccarlo per poterlo impostare. Per sbloccare il PIN, fare clic sull'utente, su **Azione** e quindi su **Sblocca PIN**. 
  
6. Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Visualizza stato PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul PIN dell'utente tramite Windows PowerShell cmdlet

È possibile visualizzare le informazioni sul PIN dell'utente utilizzando il cmdlet Get-CsClientPinInfo utente. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota di PowerShell per [Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-user-pin-information"></a>Per visualizzazione informazioni sul PIN di un utente

Per visualizzare le informazioni sul PIN di un utente, digitare un comando simile al seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Verranno restituite informazioni simili alle seguenti:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsConferenceDisclaimer.](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)
  
## <a name="see-also"></a>Vedere anche

[Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloccare o sbloccare un PIN utente in Skype for Business Server](lock-or-unlock-a-user-pin.md)