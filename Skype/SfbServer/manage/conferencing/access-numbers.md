---
title: 'Gestire i numeri dei servizi di conferenza telefonica con accesso esterno in Skype for Business Server '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Riepilogo: informazioni su come gestire i numeri dei servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 48fae5535607c59931be1c7f5201c3c45a150417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818668"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Gestire i numeri dei servizi di conferenza telefonica con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i numeri di accesso per i servizi di conferenza telefonica con chiamata in Skype for Business Server.
  
Quando si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono effettuare la chiamata dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze. I numeri di accesso per le connessioni in ingresso vengono visualizzati negli inviti alle riunioni e nella pagina Web delle impostazioni di conferenza telefonica con accesso esterno. 
  
Questo argomento descrive come visualizzare, modificare o eliminare i numeri di accesso ai servizi di conferenza telefonica in ingresso esistenti. Per altre informazioni su come creare numeri di accesso per le connessioni telefoniche iniziali, vedere [configurare le conferenze telefoniche con ingresso esterno in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Visualizzare i numeri di accesso per i servizi di conferenza telefonica

Puoi visualizzare i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso usando Skype for Business Server Control Panel o usando Skype for Business Server Management Shell.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Visualizzare i numeri di accesso per le connessioni telefoniche tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.
    
4. Nella pagina **numero di accesso** esterno, fare clic sul numero di accesso che si vuole visualizzare.
    
5. In **modifica**selezionare la casella di controllo **Mostra dettagli** .
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Visualizzare i numeri di accesso per le connessioni telefoniche tramite Skype for Business Server Management Shell

Per visualizzare le informazioni sui numeri di accesso esterno, usare il cmdlet **Get-CsDialInConferencingAccessNumber** .
  
Il comando seguente restituisce una raccolta di tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso configurati per l'uso nell'organizzazione: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

Di seguito è riportato un esempio del tipo di informazioni restituite:
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

Per altre informazioni, vedere [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modificare i numeri di accesso per i servizi di conferenza telefonica

Puoi modificare i numeri di accesso esterno usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modificare i numeri di accesso esterno tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.
    
4. Nella pagina **numero di accesso** esterno, fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
    > [!NOTE]
    > L'uso del campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso per la chiamata in ingresso potrebbe non restituire i risultati previsti. Ordinare invece l'elenco in base alla colonna di interesse per identificare il numero di accesso esterno che si vuole visualizzare o modificare. 
  
5. In **numero di visualizzazione**Digitare il numero di telefono che gli utenti del telefono PSTN (Public Switched Telephone Network) Dial per partecipare a una conferenza. 
    
    Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.
    
6. In **nome visualizzato**Digitare una descrizione per il numero di accesso esterno. Questo è il nome associato al numero di accesso esterno nei risultati della ricerca di Skype for business.
    
    Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso. 
    
7. In **URI di linea**Digitare il numero e. 164 del numero di accesso esterno in formato Tel URI, incluso il simbolo + prima del numero ed escludendo gli spazi. Ad esempio, Tel: + 14255550200.
    
    > [!NOTE]
    > Lo stesso URI di linea non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica in ingresso. 
  
8. In **URI SIP**eseguire le operazioni seguenti:
    
   Nella casella di testo digitare un URI SIP univoco per questo numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso. Questo URI SIP viene visualizzato in varie posizioni, inclusi, ma non solo, i messaggi di notifica delle chiamate e le versioni precedenti dei client Lync.
    
    > [!NOTE]
    > Lo stesso URI SIP non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso. L'URI SIP non può essere modificato dopo la creazione del numero di accesso. L'unico modo per modificare l'URI SIP consiste nell'eliminare e ricreare il numero di accesso. 
  
   Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione operatore di conferenza che supporta questo numero di accesso esterno.
    
9. In **pool**fare clic sul pool in cui è in esecuzione l'istanza di operatore conferenza che supporta questo numero di accesso esterno.
    
    > [!NOTE]
    > Se è necessario modificare il pool dopo la creazione del numero di accesso, è necessario usare il cmdlet **Move-CsApplicationEndpoint** oppure eliminare e ricreare il numero di accesso.
  
10. In **lingua principale**fare clic sulla lingua in cui vengono riprodotti le richieste per questo numero di accesso esterno. 
    
    La lingua principale è la lingua che l'operatore di conferenza USA per rispondere alla chiamata. Le lingue supportate vengono visualizzate accanto a ogni numero di telefono di Access nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.
    
11. Opzionale In **lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti per il numero di accesso esterno e quindi fare clic su **OK**. 
    
    È possibile scegliere fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando effettuano la chiamata a una conferenza.
    
12. Per aggiungere un'area geografica per il numero di accesso esterno, fare clic su **Aggiungi**in **aree geografiche associate**, fare clic su una o più aree geografiche associate ai dial plan per questo numero di accesso esterno e quindi fare clic su **OK**.
    
13. Per eliminare un'area dal numero di accesso esterno, in **aree geografiche associate**fare clic sull'area che si vuole eliminare e quindi fare clic su **Rimuovi**.
    
14. Fare clic su **Commit**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modificare i numeri di accesso esterno con Skype for Business Server Management Shell

Per modificare i numeri di accesso esterno, usare il cmdlet **Set-CsDialInConferencingAccessNumber** .
  
Il comando seguente modifica la proprietà DisplayName per il numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso con Identity sip:RedmondDialIn@litwareinc.com. In questo esempio, il nome visualizzato è impostato su "numero di accesso telefonico di Redmond":
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

Nell'esempio successivo il numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso con identità sip:RedmondDialIn@litwareinc.com viene modificato per includere due aree geografiche: Redmond e Seattle. A questo scopo, viene chiamato il parametro regions, seguito dalle due aree geografiche (due valori stringa separati da virgole). Tieni presente che questo comando avrà esito negativo, a meno che le aree Redmond e Seattle non siano già state definite in dial plan.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Per altre informazioni, vedere [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Eliminare un numero di accesso ai servizi di conferenza telefonica con chiamata in ingresso

Puoi eliminare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso utilizzando Skype for Business Server Control Panel o usando Skype for Business Server Management Shell.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Eliminare un numero di conferenza telefonica con accesso esterno tramite il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno**.
    
4. Nella pagina fare clic sul numero di accesso esterno che si vuole eliminare nell'elenco, fare clic su **modifica**e quindi su **Elimina**.
    
5. Fare clic su **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Eliminare un numero di conferenza telefonica con accesso esterno con Skype for Business Server Management Shell

Per eliminare un numero di conferenza telefonica con accesso esterno, usare il comando **Remove-CsDialInConferencingAccessNumber**.
  
Il comando seguente elimina il numero di accesso per i servizi di conferenza telefonica con chiamata in sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

Il comando successivo Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso associati all'area nord-ovest:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

Il comando successivo Elimina tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso in cui l'italiano è la lingua principale:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Per altre informazioni, vedere [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
  

