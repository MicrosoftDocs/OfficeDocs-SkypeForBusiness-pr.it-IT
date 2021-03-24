---
title: 'Gestire i numeri di accesso alle conferenze telefoniche con accesso esterno in Skype for Business Server '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Riepilogo: informazioni su come gestire i numeri di accesso alle conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099152"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Gestire i numeri di accesso alle conferenze telefoniche con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i numeri di accesso alle conferenze telefoniche con accesso esterno in Skype for Business Server.
  
Quando si distribuiscono conferenze telefoniche con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono comporre dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze. Questi numeri di accesso esterno vengono visualizzati negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno. 
  
In questo argomento viene descritto come visualizzare, modificare o eliminare i numeri di accesso alle conferenze telefoniche con accesso esterno esistenti. Per ulteriori informazioni su come creare numeri di accesso esterno iniziali, vedere Configurare le conferenze telefoniche con accesso [esterno in Skype for Business Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Visualizzare i numeri di accesso alle conferenze telefoniche con accesso esterno

È possibile visualizzare i numeri di accesso alle conferenze telefoniche con accesso esterno utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Visualizzare i numeri di accesso esterno tramite il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.
    
4. Nella pagina **Numero di accesso esterno** fare clic sul numero di accesso che si desidera visualizzare.
    
5. In **Modifica** selezionare la **casella di controllo** Mostra dettagli.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Visualizzare i numeri di accesso esterno tramite Skype for Business Server Management Shell

Per visualizzare informazioni sui numeri di accesso esterno, utilizzare il cmdlet **Get-CsDialInConferencingAccessNumber.**
  
Il comando seguente restituisce una raccolta di tutti i numeri di accesso alle conferenze telefoniche con accesso esterno configurati per l'utilizzo nell'organizzazione: 
  
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

Per ulteriori informazioni, vedere [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modificare i numeri di accesso alle conferenze telefoniche con accesso esterno

È possibile modificare i numeri di accesso esterno utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modificare i numeri di accesso esterno utilizzando il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.
    
4. Nella pagina **Numero di accesso esterno** fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su Modifica e quindi su Mostra **dettagli.** 
    
    > [!NOTE]
    > Se si utilizza il campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso esterno, i risultati ottenuti potrebbero non essere quelli previsti. Ordinare invece l'elenco in base alla colonna a cui si è interessati per identificare il numero di accesso esterno da visualizzare o modificare. 
  
5. In **Numero visualizzato** digitare il numero di telefono che gli utenti della rete PSTN (Public Switched Telephone Network) devono comporre per partecipare a una conferenza. 
    
    Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.
    
6. In **Nome visualizzato** digitare una descrizione per il numero di accesso esterno. Questo è il nome associato al numero di accesso remoto nei risultati di ricerca di Skype for Business.
    
    Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso. 
    
7. In **URI linea** digitare il numero E.164 del numero di accesso esterno nel formato URI TEL, preceduto dal simbolo + e senza utilizzare spazi. Ad esempio, tel:+14255550200.
    
    > [!NOTE]
    > Non è possibile riutilizzare lo stesso URI linea per un altro numero di accesso per conferenze con accesso esterno. 
  
8. In **URI SIP** eseguire le operazioni seguenti:
    
   Nella casella di testo digitare un URI SIP univoco per il numero di accesso per conferenze con accesso esterno. Questo URI SIP viene visualizzato in diverse posizioni, tra cui, ma non solo, i messaggi di notifica delle chiamate e le versioni precedenti dei client Lync.
    
    > [!NOTE]
    > Non è possibile riutilizzare lo stesso URI SIP per un altro numero di accesso per conferenze con accesso esterno. L'URI SIP non può essere modificato dopo che il numero di accesso è stato creato. L'unico modo per modificare l'URI SIP è quello di eliminare e ricreare il numero di accesso. 
  
   Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione Operatore conferenza che supporta questo numero di accesso esterno.
    
9. In **Pool** fare clic sul pool che esegue l'istanza di Operatore Conferenza che supporta il numero di accesso esterno.
    
    > [!NOTE]
    > Se è necessario modificare il pool dopo avere creato il numero di accesso, utilizzare il cmdlet **Move-CsApplicationEndpoint** oppure eliminare e ricreare il numero di accesso.
  
10. In **Lingua principale** fare clic sulla lingua in cui verranno riprodotte le richieste per il numero di accesso esterno. 
    
    La lingua principale è la lingua utilizzata da Operatore Conferenza per rispondere alla chiamata. Le lingue supportate vengono visualizzate insieme a ogni numero di telefono di accesso nella pagina Web Impostazioni conferenza telefonica con accesso esterno.
    
11. (Facoltativo) In **Lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti al numero di accesso esterno e quindi fare clic su **OK**. 
    
    È possibile selezionare fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando chiamano per partecipare a una conferenza.
    
12. Per aggiungere un'area per il numero di accesso remoto, in Aree associate **fare** clic su **Aggiungi,** fare clic su una o più aree associate ai dial plan per il numero di accesso remoto e quindi fare clic su **OK.**
    
13. Per eliminare un'area dal numero di accesso esterno, in **Aree associate** fare clic sull'area desiderata e quindi su **Rimuovi**.
    
14. Fare clic su **Commit**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modificare i numeri di accesso esterno tramite Skype for Business Server Management Shell

Per modificare i numeri di accesso esterno, utilizzare il cmdlet **Set-CsDialInConferencingAccessNumber.**
  
Il comando seguente modifica la proprietà DisplayName per il numero di accesso alle conferenze telefoniche con accesso esterno con il parametro Identity sip:RedmondDialIn@litwareinc.com. In questo esempio il nome visualizzato è impostato su "Redmond Dial-In Access Number":
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

Nell'esempio successivo, il numero di accesso alle conferenze telefoniche con accesso esterno con sip:RedmondDialIn@litwareinc.com identity viene modificato in modo da includere due aree geografiche: Redmond e Seattle. Per ottenere questo risultato, viene utilizzato il parametro Region, seguito dalle due aree (due stringhe separate da virgole). Si noti che questo comando avrà esito negativo se le due aree Redmond e Seattle non sono già state definite nei dial plan.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Per ulteriori informazioni, [vedere Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Eliminare un numero di accesso alle conferenze telefoniche con accesso esterno

È possibile eliminare un numero di accesso alle conferenze telefoniche con accesso esterno utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Eliminare un numero di accesso alle conferenze telefoniche con accesso esterno tramite il Pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.
    
4. Nella pagina fare clic sul numero di accesso esterno che si desidera eliminare nell'elenco, fare clic su **Modifica** e quindi su **Elimina**.
    
5. Fare clic su **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Eliminare un numero di accesso per le conferenze telefoniche con accesso esterno tramite Skype for Business Server Management Shell

Per eliminare un numero di accesso alle conferenze telefoniche con accesso esterno, utilizzare **Remove-CsDialInConferencingAccessNumber.**
  
Il comando seguente elimina il numero di accesso alle conferenze telefoniche con accesso esterno con identità sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

Il comando successivo elimina tutti i numeri di accesso alle conferenze telefoniche con accesso esterno associati all'area nord-occidentale:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

Il comando successivo elimina tutti i numeri di accesso alle conferenze telefoniche con accesso esterno in cui l'italiano è la lingua principale:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Per ulteriori informazioni, [vedere Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
