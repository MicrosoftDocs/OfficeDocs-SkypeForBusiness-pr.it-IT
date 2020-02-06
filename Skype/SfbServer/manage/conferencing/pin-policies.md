---
title: Gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
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
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Riepilogo: informazioni su come gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 567d57edc4db5bae87653d8d3e11e44054efc0cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818477"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.
  
Gli utenti di Skype for Business Server che hanno credenziali Active Directory Domain Services (AD DS) nell'organizzazione possono partecipare a conferenze telefoniche con accesso esterno come utenti autenticati usando un PIN (Personal Identification Number). I criteri PIN definiscono le regole per il funzionamento dei pin di conferenza telefonica con accesso esterno.
  
 Se si vogliono usare gli stessi criteri PIN per l'intera organizzazione, è possibile usare il criterio PIN globale e modificarlo in base alle esigenze. Il criterio PIN globale definisce le regole per i pin di conferenza telefonica con accesso esterno a livello di foresta. È possibile modificare il criterio PIN globale, ma non è possibile eliminarlo.
  
Se si vuole applicare un criterio specifico a un sito o a un determinato gruppo di utenti, è possibile creare un nuovo criterio PIN.
  
I criteri PIN si applicano agli utenti dall'ambito più limitato all'ambito più ampio. Se si assegna un criterio PIN a livello di utente a un utente, queste impostazioni hanno la precedenza. Se non si assegna un criterio utente, il criterio PIN a livello di sito si applica, se esistente. Se non si applicano criteri per l'utente o il sito, il criterio PIN globale fornisce le impostazioni predefinite.
  
## <a name="view-information-about-pin-policies"></a>Visualizzare le informazioni sui criteri PIN

Puoi visualizzare le informazioni sui criteri PIN usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Visualizzare le informazioni sui criteri PIN tramite il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole visualizzare, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Visualizzare le informazioni sui criteri PIN usando Skype for Business Server Management Shell

Per visualizzare le informazioni sui criteri PIN, usare il cmdlet **Get-CsPinPolicy** . Ad esempio, il comando seguente restituisce informazioni su un singolo criterio PIN con il sito identità: Redmond:
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Per altre informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modificare il criterio PIN globale

Puoi modificare il criterio PIN globale usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificare il criterio PIN di conferenza telefonica con accesso esterno globale usando il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic sul criterio **globale** , fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica criterio PIN**, in **lunghezza minima PIN**, digitare o selezionare la lunghezza minima del PIN che si vuole consentire. La lunghezza minima predefinita è di cinque cifre.
    
6. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** . Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
7. Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
8. Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** . Se non si seleziona questa opzione, i pin non scadono mai. Per impostazione predefinita, i pin non scadono mai.
    
9. Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.
    
10. In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
11. Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** . Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre. Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.
    
    > [!IMPORTANT]
    > Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni. 
  
12. Fare clic su **Commit**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificare il criterio PIN di conferenza telefonica con accesso esterno globale usando Skype for Business Server Management Shell

Per modificare il criterio PIN per i servizi di conferenza telefonica con accesso esterno globale, usare il cmdlet **Set-CsPinPolicy** .
  
Con il comando seguente viene modificato il valore di MinPasswordLength per tutti i criteri PIN configurati per l'uso nell'organizzazione. A questo scopo, il comando chiama prima il cmdlet **Get-CsPinPolicy** senza parametri per recuperare una raccolta di tutti i criteri PIN esistenti. La raccolta viene quindi inviata tramite pipe al cmdlet **Set-CsPinPolicy** , che modifica il valore della proprietà MinPasswordLength per ogni criterio della raccolta:
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Per altre informazioni, ad esempio una descrizione completa della sintassi e un elenco di parametri, vedere [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Creare un criterio PIN per un utente o un sito

È possibile creare un criterio PIN per un utente o un sito usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Creare un criterio PIN per un utente o un sito utilizzando il pannello di controllo di Skype for Business Server

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
   - Per creare un criterio a livello di utente, fare clic su **criteri utente**. In **nome**digitare un nome che descriva il criterio in **nuovo criterio PIN**.
    
   - Per creare un criterio a livello di sito, fare clic su **criteri sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio. Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.
    
5. Nel campo **Descrizione** Digitare una descrizione del criterio PIN.
    
6. Nel campo **lunghezza minima PIN** Digitare o selezionare la lunghezza minima del PIN che si vuole consentire. La lunghezza minima predefinita è di cinque cifre.
    
7. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** . Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
8. Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
9. Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** . Se non si seleziona questa opzione, i pin non scadono mai. Per impostazione predefinita, i pin non scadono mai.
    
10. Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.
    
11. In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
12. Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** . Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre. Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.
    
    > [!IMPORTANT]
    > Per motivi di sicurezza, Microsoft consiglia di non consentire modelli comuni. 
  
13. Fare clic su **Commit**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Creare un criterio PIN per un utente o un sito utilizzando Skype for Business Server Management Shell

Per creare un criterio PIN per un utente o un sito, usare il cmdlet **New-CsPinPolicy** .
  
Il comando seguente crea un nuovo criterio PIN con il sito Identity: Redmond. Questo comando include solo un parametro facoltativo, MinPasswordLength, usato per impostare la proprietà MinPasswordLength su 7. Tutte le proprietà dei criteri rimanenti verranno configurate usando i valori predefiniti.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Per altre informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modificare un criterio PIN per un utente o un sito

È possibile modificare i criteri di un utente o di un PIN del sito usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificare i criteri di un utente o di un PIN del sito usando il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica criterio PIN**modificare le impostazioni dei criteri (ad eccezione del nome del criterio, che non può essere modificato).
    
6. Fare clic su **Commit**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificare i criteri di un utente o di un PIN del sito utilizzando Skype for Business Server Management Shell

Per modificare il criterio PIN per i servizi di conferenza telefonica con accesso esterno, usare il cmdlet **Set-CsPinPolicy** .
  
Il comando seguente modifica il criterio PIN assegnato al sito Redmond. In questo caso, il comando modifica il valore della proprietà MinPasswordLength su 10; Ciò significa che i nuovi PIN dovranno contenere almeno 10 cifre:
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Per altre informazioni, ad esempio una descrizione completa della sintassi e un elenco di parametri, vedere [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Eliminare un criterio PIN per un utente o un sito

Puoi eliminare un criterio PIN per un utente o un sito usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Eliminare un criterio PIN per un utente o un sito utilizzando il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole modificare, fare clic su **modifica**e quindi su **Elimina**.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Eliminare un criterio PIN per un utente o un sito utilizzando Skype for Business Server Management Shell

Per eliminare un criterio PIN per un utente o un sito, usare il cmdlet **Remove-CsPinPolicy** .
  
Il comando seguente rimuove tutti i criteri PIN configurati nell'ambito del sito. A questo scopo, usa il cmdlet **Get-CsPinPolicy** insieme al parametro Filter per restituire una raccolta di tutti i criteri con un'identità che inizia con i caratteri "sito:". La raccolta viene quindi inviata tramite pipe al cmdlet **Remove-CsPinPolicy** , che elimina ogni criterio della raccolta:
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Per altre informazioni, ad esempio una descrizione completa della sintassi e un elenco di parametri, vedere [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
  

