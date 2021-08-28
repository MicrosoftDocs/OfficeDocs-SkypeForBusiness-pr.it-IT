---
title: Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Riepilogo: impostare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: d3871fe99de89bdd1430e2b870f5ddd36be188ed
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614216"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server
 
**Riepilogo:** Impostare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.
  
Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Skype for Business Server con credenziali di Servizi di dominio Active Directory richiede un PIN ( Personal Identification Number). Se un utente dimentica il PIN di conferenza telefonica con accesso esterno o non lo ha impostato tramite Skype for Business Server, è possibile impostare il PIN dell'utente Skype for Business Server Pannello di controllo. È possibile generare automaticamente il PIN o crearne uno manualmente.
  
> [!NOTE]
> Le caratteristiche specifiche del PIN, ad esempio la lunghezza minima, possono essere configurate come criterio. Oltre al criterio globale, è possibile configurare un criterio PIN per singoli siti o utenti. 
  
### <a name="to-set-a-users-pin"></a>Per impostare il PIN di un utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
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
  
6. Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Imposta PIN**.
    
7. Nella finestra di dialogo **Imposta PIN** eseguire una delle operazioni seguenti:
    
   - Per consentire Skype for Business Server il PIN dell'utente, selezionare Genera automaticamente **un PIN valido** (impostazione predefinita).
    
   - Per creare un PIN personalizzato, fare clic su **Immetti manualmente un PIN specifico**, fare clic sulla casella di testo e quindi digitare un PIN che soddisfi i requisiti PIN specificati nelle impostazioni del criterio PIN.
    
8. Fare clic su **OK**.
    
9. In **Imposta PIN** eseguire una delle operazioni seguenti: 
    
   - Selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiare il PIN e comunicarlo all'utente utilizzando il metodo preferito dell'organizzazione.
    
   - Fare clic su **Apri applicazione di posta elettronica per inviare il nuovo PIN all'utente** per inviare il PIN per posta elettronica. Se si utilizza Microsoft Office Outlook come client di posta elettronica, il PIN verrà copiato automaticamente in un nuovo messaggio di posta elettronica. Se invece si utilizza un altro client di posta elettronica, selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiarlo nel messaggio di posta elettronica.
    
10. Fare clic su **Chiudi**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Assegnazione di un PIN utente tramite Windows PowerShell cmdlet

È possibile assegnare i numeri pin anche utilizzando il cmdlet Set-CsClientPin. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Per assegnare automaticamente un numero PIN a un utente

Il comando seguente assegna un numero PIN all'utente Ken Myer. Poiché il parametro Pin non è incluso, Skype for Business Server genererà e assegna automaticamente il numero PIN.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Per assegnare un numero PIN specifico a un utente

Questo comando usa il parametro Pin per assegnare il numero PIN 121989 all'utente Ken Myer.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientPin.](/powershell/module/skype/set-csclientpin?view=skype-ps)
