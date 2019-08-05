---
title: Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Riepilogo: impostare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: d52c52e65fbfe706f243f420d6397319e4d00a32
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194958"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server
 
**Riepilogo:** Impostare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.
  
Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Skype for Business Server con credenziali di Active Directory Domain Services (AD DS) richiede un PIN (Personal Identification Number). Se un utente dimentica il PIN per i servizi di conferenza telefonica con accesso esterno o non ha impostato il PIN usando Skype for Business Server, è possibile impostare il PIN dell'utente dal pannello di controllo di Skype for Business Server. È possibile generare automaticamente il PIN o crearne uno manualmente.
  
> [!NOTE]
> Le caratteristiche specifiche del PIN, ad esempio la lunghezza minima, possono essere configurate come criteri. Oltre al criterio globale, è possibile configurare un criterio PIN per singoli siti o utenti. 
  
### <a name="to-set-a-users-pin"></a>Per impostare il PIN di un utente

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
    
    > [!NOTE]
    > Se il PIN è bloccato, è necessario sbloccare il PIN prima di poterlo impostare. Per sbloccare il PIN, fare clic sull'utente, fare clic su **azione**e quindi su **Sblocca PIN**. 
  
6. Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Imposta PIN**.
    
7. Nella finestra di dialogo **Imposta PIN** eseguire una delle operazioni seguenti:
    
   - Per consentire a Skype for Business Server di generare il PIN dell'utente, selezionare **genera automaticamente un PIN valido** (impostazione predefinita).
    
   - Per creare un PIN personalizzato, fare clic su **immettere manualmente un PIN specifico**, fare clic sulla casella di testo e quindi digitare un pin che soddisfi i requisiti del PIN specificati nelle impostazioni dei criteri PIN.
    
8. Fare clic su **OK**.
    
9. In **Imposta PIN**eseguire una delle operazioni seguenti: 
    
   - Selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiare il PIN e comunicarlo all'utente usando il metodo preferito dell'organizzazione.
    
   - Fare clic su **Apri l'applicazione di posta elettronica per inviare il nuovo PIN all'utente** per inviare il PIN tramite posta elettronica. Se Microsoft Office Outlook è il client di posta elettronica, il PIN viene copiato automaticamente in un nuovo messaggio di posta elettronica. Se si usa un altro client di posta elettronica, selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiarlo nel messaggio di posta elettronica.
    
10. Fare clic su **Chiudi**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Assegnazione di un PIN utente tramite i cmdlet di Windows PowerShell

Puoi assegnare i numeri di PIN anche usando il cmdlet Set-CsClientPin. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Per assegnare automaticamente un numero PIN a un utente

Con il comando seguente viene assegnato un numero PIN all'utente Ken. Dato che il parametro PIN non è incluso, Skype for Business Server genera e assegna automaticamente il numero di PIN.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Per assegnare un numero PIN specifico a un utente

Questo comando usa il parametro PIN per assegnare il PIN numero 121989 all'utente Ken.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .
  

