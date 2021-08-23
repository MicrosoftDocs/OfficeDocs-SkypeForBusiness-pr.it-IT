---
title: Diagnosticare i problemi di connessione in Skype for Business Online Connector
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Risolvere i problemi relativi alla creazione di una sessione remota di PowerShell per connettersi a Skype for Business Online, inclusi gli errori di import-module, shell simultanei, Live ID e autorizzazioni.
ms.openlocfilehash: 81b612b8b3e2ab82f0986110b2aa612fafe6402f
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407015"
---
# <a name="diagnose-connection-problems-in-the-skype-for-business-online-connector"></a>Diagnosticare i problemi di connessione in Skype for Business Online Connector

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Questo argomento offre informazioni che ti aiuteranno a diagnosticare e risolvere i problemi che si possono verificare quando provi a creare una sessione remota di Microsoft PowerShell che si connette a Skype for Business online. Consulta le sezioni seguenti:
  
- [Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Errore di Import-Module causato da una versione errata di Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Connessione al server Live ID non riuscita](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Caricamento del modulo Live ID non riuscito](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Accesso non riuscito per l'utente](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L'utente non dispone delle autorizzazioni per la gestione del tenant](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [Il numero massimo di shell simultanee per questo utente in Skype for Business Online è stato superato](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Il criterio di esecuzione di PowerShell consente di determinare quali file di configurazione possono essere caricati nella console di PowerShell e quali script possono essere eseguiti da un utente da questa console. Come minimo, non è possibile importare il modulo Skype for Business Online Connector a meno che i criteri di esecuzione non siano stati impostati su RemoteSigned. In caso contrario, quando si prova a importare il modulo viene visualizzato il messaggio di errore seguente:
  
- **Errore:** Import-Module: File C: File di programma File comuni <em>Microsoft Lync Server \\ \\ \\ 2013 Moduli \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 non può essere caricato perché l'esecuzione di script è disabilitata in questo sistema. Per altre informazioni, vedere about_Execution_Policies all'indirizzo https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Soluzione:** per risolvere il problema, avviare PowerShell come amministratore e quindi eseguire il comando seguente:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Per informazioni dettagliate sul criterio di esecuzione, consulta l'argomento all'indirizzo [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Errore di Import-Module causato da una versione errata di Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Il Modulo del connettore di Skype for Business Online può essere eseguito solo in Windows PowerShell 3.0. Se si prova a importare il modulo in una versione precedente di PowerShell, il processo di importazione non riuscirà con un messaggio di errore simile al seguente:
  
  - **Errore:** *Import-Module: la versione di PowerShell caricata è '2.0'. Il modulo 'D: Programmi File comuni \\ \\ Microsoft Lync Server \\ 2013 Moduli LyncOnlineConnectorLyncOnlineConnector.psd1' richiede una versione minima di \\ \\ \\ PowerShell '3.0' per l'esecuzione. Verificare l'installazione di PowerShell e riprovare.*

- **Soluzione:** l'unico modo per risolvere il problema è installare Windows PowerShell 3.0, disponibile nell'Area download Microsoft all'indirizzo [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="failed-to-connect-to-live-id-server"></a>Connessione al server Live ID non riuscita
<a name="BKMKFailedConnect"> </a>

Sono in genere tre i motivi della non riuscita di un tentativo di connessione, con l'errore riportato di seguito:

  - **Errore:** *Get-CsWebTicket: impossibile connettere i server Live Id. Verificare che il proxy sia abilitato o che il computer abbia una connessione di rete ai server Live Id.*

- **Soluzione:** spesso questo errore indica che l Microsoft Online Services assistente per l'accesso non è in esecuzione. Puoi verificare lo stato di questo servizio eseguendo il comando seguente dal prompt di PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Se il servizio non è in esecuzione, avvia il servizio usando questo comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Se il servizio è in esecuzione, potrebbero essersi verificati problemi di connessione di rete tra il computer e il server di autenticazione di Microsoft Live ID. Per verificare, apri Internet Explorer e accedi a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Prova ad accedere per Microsoft 365 o Office 365 da lì. Se non è possibile, probabilmente si verificano problemi di connessione di rete.
  
    Meno comunemente, è possibile che l'URI di connessione per il server di autenticazione Microsoft Live ID sia stato configurato sul valore errato. Se è già stato stabilito che l'Assistente Sign-In è in esecuzione e che non si verificano problemi di rete, il problema potrebbe essere dovuto a questa configurazione. In questo caso, contattare il supporto tecnico Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Caricamento del modulo Live ID non riuscito
<a name="BKMKFailedLoad"> </a>

Uno dei prerequisiti per l'uso di PowerShell per la gestione di Skype for Business online è l'installazione di Assistente per l'accesso ai Microsoft Online Services. Se l'Assistente per l'accesso non è installato, quando si prova a stabilire una sessione remota con Skype for Business Online viene visualizzato il messaggio di errore seguente:

- **Errore:** *Get-CsWebTicket: impossibile caricare il modulo Live Id. Verificare che sia installata la versione corretta dell'assistente per l'accesso a Live Id.*

- **Soluzione:** l Microsoft Online Services assistente per l'accesso è disponibile nell'Area download Microsoft [all'indirizzo Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Accesso non riuscito per l'utente
<a name="BKMKLogonFailed"> </a>

Quando tenti di effettuare una connessione remota a Skype for Business online, devi fornire il nome utente e la password di un account utente di Skype for Business online valido. In caso contrario, l'accesso avrà esito negativo insieme a un messaggio di errore simile al seguente:

- **Errore:** *Get-CsWebTicket: accesso non riuscito per l'utente 'kenmyer@litwareinc.com'. Creare un nuovo oggetto PSCredential, assicurando di aver* usato il nome utente e la password corretti.

- **Soluzione:** se si pensa di usare un account utente valido e si ha la password corretta, provare di nuovo ad accedere. In caso di esito negativo, usa le stesse credenziali e prova ad accedere all'indirizzo [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se non è possibile accedere, contattare il supporto tecnico Microsoft. 

  
## <a name="the-user-doesnt-have-permission-to-manage-this-tenant"></a>L'utente non ha l'autorizzazione per gestire questo tenant
<a name="BKMKUserPermission"> </a>

Non è possibile stabilire una connessione remota di PowerShell aSkype for Business Online a meno che non si sia membri del gruppo Amministratori tenant. In caso contrario, il tentativo di connessione non riuscirà e verrà visualizzato il messaggio di errore seguente:

- **Errore:** New-PSSession : [admin.vdomain.com] L'elaborazione dei dati dal server remoto admin.vdomain.com non è riuscita con il messaggio di errore seguente: L'utente 'user@foo.com' non ha l'autorizzazione per gestire il *tenant. Le autorizzazioni possono essere concesse assegnando l'utente al ruolo RBAC appropriato. Per altre informazioni, vedere Risoluzione [dei problemi in remoto.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **Soluzione:** se si pensa di essere o si suppone di essere un membro del gruppo Amministratori tenant, contattare il supporto tecnico Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online
<a name="BKMKAbilityConnect"> </a>

Per poter usare PowerShell per la gestone di Skype for Business online, è necessario che la proprietà di EnableRemotePowerShellAccess del criterio del tenant di PowerShell in uso sia impostata su  `True`. In caso contrario, la connessione non riuscirà e verrà visualizzato il messaggio di errore seguente:

- **Errore:** New-PSSession : [admin.vdomain.com] L'elaborazione dei dati dal server remoto admin.vdomain.com non è riuscita con il messaggio di errore seguente: La possibilità di connettersi a questo tenant usando una sessione remota di PowerShell è stata *disabilitata. Contattare la Guida di Lync per controllare i criteri powershell tenant di questo tenant. Per altre informazioni, vedere Risoluzione [dei problemi in remoto.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **Soluzione:** se viene visualizzato questo messaggio di errore, è necessario contattare il supporto tecnico Microsoft e ottenere l'accesso remoto a PowerShell abilitato.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business Online
<a name="BKMKMaxNumberShellsUser"> </a>

Ogni amministratore può eseguire fino a tre connessioni remote simultanee a Skype for Business online. Se sono attive tre connessioni remote a PowerShell, qualsiasi tentativo di effettuare una quarta connessione simultanea non riuscirà, generando il messaggio di errore seguente:

- **Errore:** New-PSSession : [admin.vdomain.com] Connessione al server remoto admin.vdomain.com non riuscita con il messaggio di errore seguente: Il servizio WS-Management non è in grado di elaborare *la richiesta. È stato superato il numero massimo di shell simultanee per questo utente. Chiudere le shell esistenti o aumentare la quota per questo utente. Per altre informazioni, vedere Risoluzione [dei problemi in remoto.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **Soluzione:** l'unico modo per risolvere il problema è chiudere una o più delle connessioni precedenti. Al termine di una sessione Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa azione consente di evitare questo problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Anche se ogni amministratore può avere fino a tre connessioni simultanee a un tenant di Skype for Business Online, nessun singolo tenant può avere più di 20 connessioni simultanee. Ad esempio, sei amministratori potrebbero avere tre sessioni aperte. Se un settimo amministratore prova ad aprire più di due connessioni ,con un totale di 21 connessioni simultanee, il tentativo non riesce, con il messaggio di errore seguente:
  
- **Errore:** New-PSSession : [admin.vdomain.com] Connessione al server remoto admin.vdomain.com non riuscita con il messaggio di errore seguente: Il servizio WS-Management non è in grado di elaborare *la richiesta. È stato superato il numero massimo di shell simultanee per questo tenant. Chiudere le shell esistenti o aumentare la quota per questo tenant. Per altre informazioni, vedere la sezione [risoluzione dei problemi remota](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **Soluzione:** l'unico modo per risolvere il problema è chiudere una o più delle connessioni precedenti. Al termine di una sessione Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. In questo modo è possibile evitare questo problema.  
 
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione online di Skype for Business usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
