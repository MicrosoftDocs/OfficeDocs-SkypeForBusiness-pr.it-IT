---
title: "Diagnosi dei problemi di connessione con il connettore di Skype for Business Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# Diagnosi dei problemi di connessione con il connettore di Skype for Business Online

Questo argomento offre informazioni che ti aiuteranno a diagnosticare e risolvere i problemi che si possono verificare quando provi a creare una sessione remota di Microsoft PowerShell che si connette a Skype for Business online. Consulta le sezioni seguenti:
  
- [Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_PowerShellExecutionPolicy)
    
- [Errore di Import-Module causato da una versione errata di Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_IncorrectVersion)
    
- [Connessione al server Live ID non riuscita](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedConnect)
    
- [Caricamento del modulo Live ID non riuscito](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedLoad)
    
- [Accesso non riuscito per l'utente](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_LogonFailed)
    
- [L'utente non dispone delle autorizzazioni per la gestione del tenant](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_UserPermission)
    
- [La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_AbilityConnect)
    
- [È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business Online ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell
<a name="BKMK_PowerShellExecutionPolicy"> </a>

Il criterio di esecuzione di PowerShell consente di determinare quali file di configurazione possono essere caricati nella console di PowerShell e quali script possono essere eseguiti da un utente da questa console. Come minimo, il Modulo del connettore di Skype for Business Online non può essere importato a meno che il criterio di esecuzione non sia stato impostato su RemoteSigned. In caso contrario, quando si prova a importare il modulo verrà visualizzato il seguente messaggio di errore:
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

Per risolvere il problema, avvia PowerShell come amministratore ed esegui il comando seguente:
  
```
Set-ExecutionPolicy RemoteSigned
```

Per informazioni dettagliate sul criterio di esecuzione, consulta l'argomento all'indirizzo [about_Execution_Policies](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## Errore di Import-Module causato da una versione errata di Windows PowerShell
<a name="BKMK_IncorrectVersion"> </a>

Il Modulo del connettore di Skype for Business Online può essere eseguito solo in Windows PowerShell 3.0. Se provi a importare il modulo in una versione precedente di PowerShell, il processo di importazione non riesce e viene visualizzato un messaggio di errore analogo al seguente:
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

L'unica soluzione a questo problema è l'installazione di Windows PowerShell 3.0, disponibile nell'Area download Microsoft all'indirizzo [http://www.microsoft.com/en-us/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939).
  
## Connessione al server Live ID non riuscita
<a name="BKMK_FailedConnect"> </a>

Sono in genere tre i motivi della non riuscita di un tentativo di connessione, con l'errore riportato di seguito:
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

Spesso questo errore significa che Assistente per l'accesso ai Microsoft Online Services non è in esecuzione. Puoi verificare lo stato di questo servizio eseguendo il comando seguente dal prompt di PowerShell:
  
```
Get-Service "msoidsvc"
```

Se il servizio non è in esecuzione, avvialo usando il comando seguente:
  
```
Start-Service "msoidsvc"
```

Se il servizio è in esecuzione, potrebbero essersi verificati problemi di connessione di rete tra il computer e il server di autenticazione di Microsoft Live ID. Per verificare, apri Internet Explorer e accedi a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Prova ad accedere a Office 365 da questa pagina. Se l'accesso non riesce, è probabile che ci siano problemi con la connessione di rete.
  
Meno frequentemente, è possibile che l'URI di connessione per il server di autenticazione di Microsoft Live ID sia stato impostato con un valore errato. Se si è già verificato che l'Assistente per l'accesso è in esecuzione e non sono stati riscontrati problemi di rete, questa potrebbe essere la causa del problema. In tal caso, contatta il supporto tecnico di Office 365.
  
## Caricamento del modulo Live ID non riuscito
<a name="BKMK_FailedLoad"> </a>

Uno dei prerequisiti per l'uso di PowerShell per la gestione di Skype for Business online è l'installazione di Assistente per l'accesso ai Microsoft Online Services. Se l'Assistente per l'accesso non è installato e si cerca di stabilire una connessione remota con Skype for Business online, viene visualizzato il messaggio di errore seguente:
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

L'Assistente per l'accesso ai Microsoft Online Services è disponibile nell'Area download Microsoft nell'articolo [Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177).
  
## Accesso non riuscito per l'utente
<a name="BKMK_LogonFailed"> </a>

Quando tenti di effettuare una connessione remota a Skype for Business online, devi fornire il nome utente e la password di un account utente di Skype for Business online valido. In caso contrario, l'accesso non riuscirà e verrà restituito un messaggio di errore simile al seguente:
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

Se ritieni che l'account utente usato sia valido e la password corretta, prova di nuovo a eseguire l'accesso. In caso di esito negativo, usa le stesse credenziali e prova ad accedere all'indirizzo [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se non riesci comunque a eseguire l'accesso, contatta il supporto tecnico di Office 365.
  
## L'utente non dispone delle autorizzazioni per la gestione del tenant
<a name="BKMK_UserPermission"> </a>

Non puoi stabilire una connessione remota di PowerShell a Skype for Business online a meno che tu non faccia parte del gruppo di amministratori del tenant. Se non sei un membro di questo gruppo, il tentativo di connessione non riuscirà e verrà visualizzato il messaggio di errore seguente:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

Se ritieni di essere o di dover essere un membro del gruppo degli amministratori del tenant, contatta il supporto tecnico di Office 365.
  
## La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online
<a name="BKMK_AbilityConnect"> </a>

Per poter usare PowerShell per la gestone di Skype for Business online, è necessario che la proprietà di EnableRemotePowerShellAccess del criterio del tenant di PowerShell in uso sia impostata su  `True`. In caso contrario, la connessione non riesce e viene visualizzato il messaggio di errore seguente:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

Se viene visualizzato questo messaggio di errore, contatta il supporto tecnico di Office 365 per richiedere l'abilitazione dell'accesso remoto a PowerShell.
  
## È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business Online
<a name="BKMK_MaxNumberShellsUser"> </a>

Ogni amministratore può eseguire fino a tre connessioni remote simultanee a Skype for Business online. Se sono attive tre connessioni remote a PowerShell, qualsiasi tentativo di effettuare una quarta connessione simultanea non riuscirà, generando il messaggio di errore seguente:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

L'unico modo per risolvere il problema consiste nel chiudere almeno una delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.
  
## È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online
<a name="BKMK_MaxNumberShellsTenant"> </a>

Sebbene ogni amministratore possa stabilire fino a tre connessioni simultanee a un tenant di Skype for Business online, un tenant non può avere più di nove connessioni simultanee. Supponiamo ad esempio che tre amministratori abbiano tre sessioni aperte ciascuno. Se un quarto amministratore cerca di stabilire una connessione, portando a 10 le connessioni simultanee, il tentativo non riuscirà e verrà generato il messaggio di errore seguente:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

L'unico modo per risolvere il problema consiste nel chiudere almeno una delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.
  

