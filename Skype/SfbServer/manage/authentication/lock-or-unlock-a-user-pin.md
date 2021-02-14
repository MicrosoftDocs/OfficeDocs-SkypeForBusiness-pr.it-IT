---
title: Bloccare o sbloccare un PIN utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Riepilogo: bloccare o sbloccare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828366"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Bloccare o sbloccare un PIN utente in Skype for Business Server
 
**Riepilogo:** Bloccare o sbloccare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.
  
È possibile bloccare o sbloccare il PIN di un utente dalla **sezione Utenti** del Pannello di controllo di Skype for Business Server.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Per bloccare il PIN di un utente nel Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.  
    
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
    
   f. Fare clic sull'utente, su **Azione** e quindi su **Blocca PIN**.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Per sbloccare il PIN di un utente nel Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.  
    
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
    
   f. Fare clic sull'utente, su **Azione** e quindi su **Sblocca PIN**.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Blocco e sblocco dei PIN degli utenti tramite Windows PowerShell cmdlet

È possibile bloccare e sbloccare i PIN degli utenti utilizzando Windows PowerShell e i cmdlet Lock-CsClientPin e Unlock-CsClientPin utenti. È possibile eseguire questi cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-lock-a-user-pin"></a>Per bloccare il PIN di un utente

- Per bloccare il PIN di un utente, utilizzare il cmdlet Lock-CsClientPin seguente. Ad esempio:
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Per sbloccare il PIN di un utente

- Per sbloccare il PIN di un utente, utilizzare il cmdlet Unlock-CsClientPin seguente. Ad esempio:
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) [e Unlock-CsClientPin.](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)
