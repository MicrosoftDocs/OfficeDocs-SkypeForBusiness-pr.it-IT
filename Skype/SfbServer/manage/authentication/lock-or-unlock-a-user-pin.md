---
title: Bloccare o sbloccare un PIN utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: e9a5e59497a4cb771d0b20cef55b09b26817216d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818788"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Bloccare o sbloccare un PIN utente in Skype for Business Server
 
**Riepilogo:** Bloccare o sbloccare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.
  
È possibile bloccare o sbloccare il PIN di un utente dalla sezione **utenti** del pannello di controllo di Skype for Business Server.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Per bloccare il PIN di un utente nel pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Usare uno dei metodi seguenti per individuare un utente:
    
    - Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.
    
    - Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.
    
5. Opzionale Specificare altri criteri di ricerca per restringere i risultati:
    
   un. Fare clic su **Aggiungi filtro**.
    
   b. Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.
    
   c. Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.
    
   3D. A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.
    
    > [!TIP]
    > Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**. 
  
   e. Fare clic su **trova**.
    
   f. Fare clic sull'utente, fare clic su **azione**e quindi su **blocca pin**.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Per sbloccare il PIN di un utente nel pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Usare uno dei metodi seguenti per individuare un utente:
    
   - Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.
    
   - Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.
    
5. Opzionale Specificare altri criteri di ricerca per restringere i risultati:
    
   un. Fare clic su **Aggiungi filtro**.
    
   b. Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.
    
   c. Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.
    
   3D. A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.
    
    > [!TIP]
    > Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**. 
  
   e. Fare clic su **trova**.
    
   f. Fare clic sull'utente, scegliere **azione**e quindi fare clic su **Sblocca PIN**.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Blocco e sblocco di PIN utente tramite i cmdlet di Windows PowerShell

È possibile bloccare e sbloccare i pin degli utenti usando Windows PowerShell e i cmdlet Lock-CsClientPin e Unlock-CsClientPin. Puoi eseguire questi cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-lock-a-user-pin"></a>Per bloccare un PIN utente

- Per bloccare il PIN di un utente, usare il cmdlet Lock-CsClientPin. Ad esempio:
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Per sbloccare un PIN utente

- Per sbloccare il PIN di un utente, usare il cmdlet Unlock-CsClientPin. Ad esempio:
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Per altre informazioni, vedere l'argomento della Guida per i cmdlet [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .
