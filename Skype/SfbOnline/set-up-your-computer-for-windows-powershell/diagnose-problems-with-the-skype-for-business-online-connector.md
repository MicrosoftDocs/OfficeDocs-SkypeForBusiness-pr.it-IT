---
title: Diagnosi dei problemi di connessione con il connettore di Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: 276385a1de2fe79ca03afaeeac3bb6c28945c7f7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898101"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosi dei problemi di connessione con il connettore di Skype for Business Online

[] Questo argomento offre informazioni che ti aiuteranno a diagnosticare e risolvere i problemi che si possono verificare quando provi a creare una sessione remota di Microsoft PowerShell che si connette a Skype for Business online. Consulta le sezioni seguenti:
  
- [Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Errore di Import-Module causato da una versione errata di Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Connessione al server Live ID non riuscita](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Caricamento del modulo Live ID non riuscito](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Accesso non riuscito per l'utente](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L'utente non dispone delle autorizzazioni per la gestione del tenant](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business Online ](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online ](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Il criterio di esecuzione di PowerShell consente di determinare quali file di configurazione possono essere caricati nella console di PowerShell e quali script possono essere eseguiti da un utente da questa console. Come minimo, il Modulo del connettore di Skype for Business Online non può essere importato a meno che il criterio di esecuzione non sia stato impostato su RemoteSigned. In caso contrario, quando si prova a importare il modulo verrà visualizzato il seguente messaggio di errore:
  
- **Errore**: <em>Import-Module: c: File\\i file di programma\\Common Files\\Microsoft Lync Server 2013\\moduli\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 non possono essere caricati perché è in esecuzione script è disattivato nel sistema. Per ulteriori informazioni, vedere about_Execution_Policies in https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Soluzione** Per risolvere questo problema, avviare PowerShell come amministratore e quindi eseguire il comando seguente:
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Per informazioni dettagliate sul criterio di esecuzione, consulta l'argomento all'indirizzo [about_Execution_Policies](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Errore di Import-Module causato da una versione errata di Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Il Modulo del connettore di Skype for Business Online può essere eseguito solo in Windows PowerShell 3.0. Se provi a importare il modulo in una versione precedente di PowerShell, il processo di importazione non riesce e viene visualizzato un messaggio di errore analogo al seguente:
  
  - **Errore**: *Import-Module: la versione di PowerShell caricato è '2.0'. Il modulo ' D:\\i file di programma\\Common Files\\Microsoft Lync Server 2013\\moduli\\LyncOnlineConnector\\LyncOnlineConnector.psd1' richiede una versione minima di PowerShell di '3.0' per l'esecuzione. Verificare l'installazione di PowerShell e riprovare.*

- **Soluzione**: è l'unico modo per risolvere il problema per l'installazione di Windows PowerShell 3.0 è disponibile da Microsoft Download Center al [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>Connessione al server Live ID non riuscita
<a name="BKMKFailedConnect"> </a>

Sono in genere tre i motivi della non riuscita di un tentativo di connessione, con l'errore riportato di seguito:

  - **Errore**: *Get-CsWebTicket: non riuscito per connettere i server live id. Verificare che il proxy è attivato o computer con connessione di rete ai server live id server.*

- **Soluzione**: spesso questo errore indica che l'Assistente di accesso a Microsoft Online Services non è in esecuzione. Puoi verificare lo stato di questo servizio eseguendo il comando seguente dal prompt di PowerShell: 
    ```
    Get-Service "msoidsvc"
    ```
    Se il servizio non è in esecuzione, avvialo usando il comando seguente:
    ```
    Start-Service "msoidsvc"
    ```

    Se il servizio è in esecuzione, potrebbero essersi verificati problemi di connessione di rete tra il computer e il server di autenticazione di Microsoft Live ID. Per verificare, apri Internet Explorer e accedi a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Prova ad accedere a Office 365 da questa pagina. Se l'accesso non riesce, è probabile che ci siano problemi con la connessione di rete.
  
    Meno frequentemente, è possibile che l'URI di connessione per il server di autenticazione di Microsoft Live ID sia stato impostato con un valore errato. Se si è già verificato che l'Assistente per l'accesso è in esecuzione e non sono stati riscontrati problemi di rete, questa potrebbe essere la causa del problema. In tal caso, contatta il supporto tecnico di Office 365.
  
## <a name="failed-to-load-live-id-module"></a>Caricamento del modulo Live ID non riuscito
<a name="BKMKFailedLoad"> </a>

Uno dei prerequisiti per l'uso di PowerShell per la gestione di Skype for Business online è l'installazione di Assistente per l'accesso ai Microsoft Online Services. Se l'Assistente per l'accesso non è installato e si cerca di stabilire una connessione remota con Skype for Business online, viene visualizzato il messaggio di errore seguente:

- **Errore**: *Get-CsWebTicket: possono caricare Live Id modulo. Verificare che vengono installate versioni di Live Id Assistente per l'accesso corretto.*

- **Soluzione**: Assistente per l'accesso Microsoft Online Services è disponibile in Microsoft Download Center [all'Assistente Microsoft Online Services accesso per RTW i professionisti IT](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Accesso non riuscito per l'utente
<a name="BKMKLogonFailed"> </a>

Quando tenti di effettuare una connessione remota a Skype for Business online, devi fornire il nome utente e la password di un account utente di Skype for Business online valido. In caso contrario, l'accesso non riuscirà e verrà restituito un messaggio di errore simile al seguente:

- **Errore**: *Get-CsWebTicket: accesso non riuscito per l'utente 'kenmyer@litwareinc.com'. Creare un nuovo oggetto PSCredential, assicurandosi che è stato utilizzato il nome utente corretto e la password.*

- **Soluzione**: se si ritiene che si utilizza un account utente valido e che è necessario la password corretta, provare ad accedere nuovamente. In caso di esito negativo, usa le stesse credenziali e prova ad accedere all'indirizzo [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se non riesci comunque a eseguire l'accesso, contatta il supporto tecnico di Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L'utente non dispone delle autorizzazioni per la gestione del tenant
<a name="BKMKUserPermission"> </a>

Non puoi stabilire una connessione remota di PowerShell a Skype for Business online a meno che tu non faccia parte del gruppo di amministratori del tenant. Se non sei un membro di questo gruppo, il tentativo di connessione non riuscirà e verrà visualizzato il messaggio di errore seguente:

- **Errore**: *New-PSSession: [admin.vdomain.com] elaborazione dei dati dal server remoto admin.vdomain.com non riuscito con il messaggio di errore: l'utente 'user@foo.com' non dispone dell'autorizzazione per gestire il tenant. È possibile concedere autorizzazioni assegnando l'utente al ruolo RBAC appropriato. Per ulteriori informazioni, vedere la [Risoluzione dei problemi di Remote](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Soluzione**: se si ritiene che sono o dovrebbero essere, un membro del gruppo amministratori Tenant, è necessario contattare il supporto di Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online
<a name="BKMKAbilityConnect"> </a>

Per poter usare PowerShell per la gestone di Skype for Business online, è necessario che la proprietà di EnableRemotePowerShellAccess del criterio del tenant di PowerShell in uso sia impostata su  `True`. In caso contrario, la connessione non riesce e viene visualizzato il messaggio di errore seguente:

- **Errore**: *New-PSSession: [admin.vdomain.com] elaborazione dei dati dal server remoto admin.vdomain.com non riuscito con il messaggio di errore: la possibilità di connettersi a questo tenant mediante una sessione remote PowerShell è stata disattivata. Contattare Guida di Lync per verificare i criteri di Powershell Tenant di questo tenant. Per ulteriori informazioni, vedere la [Risoluzione dei problemi di Remote](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Soluzione**: se viene visualizzato questo messaggio di errore, è necessario contattare il supporto di Office 365 e ottenere abilitato l'accesso PowerShell remoto.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business Online
<a name="BKMKMaxNumberShellsUser"> </a>

Ogni amministratore può eseguire fino a tre connessioni remote simultanee a Skype for Business online. Se sono attive tre connessioni remote a PowerShell, qualsiasi tentativo di effettuare una quarta connessione simultanea non riuscirà, generando il messaggio di errore seguente:

- **Errore**: *New-PSSession: [admin.vdomain.com] la connessione al server remoto admin.vdomain.com non riuscito con il messaggio di errore: servizio The WS-Management non è in grado di elaborare la richiesta. Il numero massimo di shell simultanee per l'utente è stato superato. Chiudere le shell o aumentare la quota per l'utente. Per ulteriori informazioni, vedere [remoto Troubleshooting] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Soluzione**: è l'unico modo per risolvere il problema per chiudere una o più delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Anche se ogni amministratore può avere al massimo tre connessioni simultanee a Skype per tenant Business Online, non tenant singolo può avere più di 20 connessioni simultanee. Ad esempio, gli amministratori di sei possono avere tre sessioni aperte. Se un amministratore della quarto tenta di effettuare connessioni più di 2 (causando un totale di connessioni simultanee 21), questo tentativo avrà esito negativo, il messaggio di errore seguente:
  
- **Errore**: *New-PSSession: [admin.vdomain.com] la connessione al server remoto admin.vdomain.com non riuscito con il messaggio di errore: servizio The WS-Management non è in grado di elaborare la richiesta. È stato superato il numero massimo di shell simultanee per il tenant. Chiudere le shell o aumentare la quota per il tenant. Per ulteriori informazioni, vedere [remoto Troubleshooting] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Soluzione**: è l'unico modo per risolvere il problema per chiudere una o più delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.  
 
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
