---
title: Gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server
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
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Riepilogo: informazioni su come gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827956"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i criteri PIN per le conferenze telefoniche con accesso esterno in Skype for Business Server.
  
Gli utenti di Skype for Business Server che dispongono di credenziali Active Directory Domain Services (AD DS) nell'organizzazione possono partecipare a conferenze telefoniche con accesso esterno come utenti autenticati utilizzando un PIN (Personal Identification Number). Il criterio PIN definisce le regole per il funzionamento dei PIN per le conferenze telefoniche con accesso esterno.
  
 Se si desidera utilizzare lo stesso criterio PIN per l'intera organizzazione, è possibile utilizzare il criterio PIN globale e modificarlo in base alle esigenze. Il criterio PIN globale definisce le regole per i PIN delle conferenze telefoniche con accesso esterno a livello della foresta. È possibile modificare il criterio PIN globale, ma non è possibile eliminarlo.
  
È possibile creare un nuovo criterio PIN se si desidera un criterio specifico da applicare a un sito o a un determinato gruppo di utenti.
  
I criteri PIN si applicano agli utenti partendo dall'ambito più limitato fino all'ambito più esteso. Se si assegna a un utente un criterio PIN a livello utente, tali impostazioni avranno la priorità. Se invece non si assegna un criterio utente, si applicherà il criterio PIN a livello di sito, se esistente. Se non si applica alcun criterio utente o sito, le impostazioni predefinite verranno fornite dal criterio PIN globale.
  
## <a name="view-information-about-pin-policies"></a>Visualizzare le informazioni sui criteri PIN

È possibile visualizzare le informazioni sui criteri PIN utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Visualizzare le informazioni sui criteri PIN tramite il pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic sul criterio PIN che si desidera visualizzare, fare clic su **modifica** e quindi su **Mostra dettagli**.
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Visualizzare le informazioni sui criteri PIN tramite Skype for Business Server Management Shell

Per visualizzare le informazioni sui criteri PIN, utilizzare il cmdlet **Get-CsPinPolicy** . Ad esempio, il comando seguente restituisce informazioni su un singolo criterio PIN con identità site: Redmond:
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Per ulteriori informazioni, inclusa una descrizione completa della sintassi e l'elenco dei parametri, vedere [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modificare il criterio PIN globale

È possibile modificare il criterio PIN globale utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificare il criterio PIN per le conferenze telefoniche con accesso esterno tramite il pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.
    
4. Nella pagina **Criteri PIN** fare clic sul criterio **Globale**, su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica criteri PIN**, in **Lunghezza minima PIN**, digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.
    
6. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
7. Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
8. Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.
    
9. Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.
    
10. In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
11. Per consentire schemi comuni di cifre nei PIN, ad esempio numeri progressivi o gruppi ripetuti di numeri, selezionare la casella di controllo **Consenti formati comuni**. Se non si seleziona questa opzione, saranno consentiti solo schemi complessi di cifre, come da impostazione predefinita.
    
    > [!IMPORTANT]
    > Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni. 
  
12. Fare clic su **Commit**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificare il criterio PIN per le conferenze telefoniche con accesso esterno tramite Skype for Business Server Management Shell

Per modificare il criterio PIN per le conferenze telefoniche con accesso esterno, utilizzare il cmdlet **Set-CsPinPolicy** .
  
Il comando seguente consente di modificare il valore di MinPasswordLength per tutti i criteri PIN configurati per l'utilizzo nell'organizzazione. A tale scopo, nel comando viene innanzitutto chiamato il cmdlet **Get-CsPinPolicy** senza alcun parametro per recuperare una raccolta di tutti i criteri per il PIN esistenti. La raccolta viene quindi inviata tramite pipe al cmdlet **Set-CsPinPolicy** , che consente di modificare il valore della proprietà MinPasswordLength per ogni criterio nell'insieme:
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Per ulteriori informazioni, tra cui una descrizione completa della sintassi e l'elenco dei parametri, vedere [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Creare un criterio PIN di un utente o di un sito

È possibile creare un criterio PIN per l'utente o il sito utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Creare un criterio PIN per l'utente o il sito utilizzando il pannello di controllo di Skype for Business Server

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.
    
4. Nella pagina **Criteri PIN** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
   - Per creare criteri a livello di utente fare clic su **Criteri utente**. In **Nuovi criteri PIN** digitare un nome descrittivo dei criteri in **Nome**.
    
   - Per creare criteri a livello di sito, fare clic su **Criteri sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera creare i criteri, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.
    
5. Nel campo **Descrizione** digitare una descrizione per i criteri per il PIN.
    
6. Nel campo **Lunghezza minima PIN** digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.
    
7. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
8. Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
9. Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.
    
10. Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.
    
11. In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
12. Per consentire schemi comuni di cifre nei PIN, ad esempio numeri progressivi o gruppi ripetuti di numeri, selezionare la casella di controllo **Consenti formati comuni**. Se non si seleziona questa opzione, saranno consentiti solo schemi complessi di cifre, come da impostazione predefinita.
    
    > [!IMPORTANT]
    > Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni. 
  
13. Fare clic su **Commit**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Creare un criterio PIN di un utente o di un sito tramite Skype for Business Server Management Shell

Per creare un criterio PIN di un utente o di un sito, utilizzare il cmdlet **New-CsPinPolicy** .
  
Il comando seguente crea un nuovo criterio PIN con identità site: Redmond. Questo comando include un solo parametro facoltativo, MinPasswordLength, che viene utilizzato per impostare la proprietà MinPasswordLength su 7. Tutte le proprietà dei criteri rimanenti verranno configurate utilizzando i valori predefiniti.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Per ulteriori informazioni, inclusa una descrizione completa della sintassi e l'elenco dei parametri, vedere [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modificare un criterio PIN di un utente o di un sito

È possibile modificare un criterio PIN di un utente o sito utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificare un criterio PIN di un utente o di un sito tramite il pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.
    
4. Nella pagina **Criteri PIN** fare clic sui criteri per il PIN che si desidera modificare, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica criteri PIN** modificare le impostazioni dei criteri nel modo desiderato, con l'eccezione del nome che non è modificabile.
    
6. Fare clic su **Commit**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificare un criterio PIN di un utente o di un sito tramite Skype for Business Server Management Shell

Per modificare il criterio PIN per le conferenze telefoniche con accesso esterno, utilizzare il cmdlet **Set-CsPinPolicy** .
  
Il comando seguente consente di modificare il criterio PIN assegnato al sito Redmond. In questo caso, il comando cambia il valore della proprietà MinPasswordLength su 10; Questo significa che i nuovi PIN dovranno contenere almeno 10 cifre:
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Per ulteriori informazioni, tra cui una descrizione completa della sintassi e l'elenco dei parametri, vedere [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Eliminare un criterio PIN di un utente o di un sito

È possibile eliminare un criterio PIN di un utente o di un sito utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Eliminare un criterio PIN di un utente o di un sito tramite il pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic sul criterio PIN che si desidera modificare, fare clic su **modifica** e quindi su **Elimina**.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Eliminare un criterio PIN di un utente o di un sito tramite Skype for Business Server Management Shell

Per eliminare un criterio PIN di un utente o di un sito, utilizzare il cmdlet **Remove-CsPinPolicy** .
  
Il seguente comando rimuove tutti i criteri PIN che sono stati configurati nell'ambito del sito. A tale scopo, utilizzare il cmdlet **Get-CsPinPolicy** , insieme al parametro Filter, per restituire una raccolta di tutti i criteri che dispongono di un'identità che inizia con i caratteri "site:". La raccolta viene quindi inviata tramite pipe al cmdlet **Remove-CsPinPolicy** , che elimina ogni criterio nell'insieme:
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Per ulteriori informazioni, tra cui una descrizione completa della sintassi e l'elenco dei parametri, vedere [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
  

