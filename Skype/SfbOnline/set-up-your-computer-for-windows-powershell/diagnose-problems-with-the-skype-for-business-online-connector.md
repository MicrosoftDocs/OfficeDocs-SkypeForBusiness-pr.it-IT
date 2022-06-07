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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913394"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosi dei problemi di connessione con il connettore di Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Questo argomento offre informazioni che ti aiuteranno a diagnosticare e risolvere i problemi che si possono verificare quando provi a creare una sessione remota di Microsoft PowerShell che si connette a Skype for Business online. Consulta le sezioni seguenti:
  
- [Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Errore di Import-Module causato da una versione errata di Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [L'autenticazione moderna non riesce quando l'autenticazione di base di WinRM è stata disabilitata](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Connessione al server Live ID non riuscita](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [Accesso non riuscito per l'utente](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L'utente non dispone delle autorizzazioni per la gestione del tenant](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Il criterio di esecuzione di PowerShell consente di determinare quali file di configurazione possono essere caricati nella console di PowerShell e quali script possono essere eseguiti da un utente da questa console. Come minimo, il Modulo del connettore di Skype for Business Online non può essere importato a meno che il criterio di esecuzione non sia stato impostato su RemoteSigned. In caso contrario, quando si prova a importare il modulo verrà visualizzato il seguente messaggio di errore:
  
- **Errore**: <em>Import-Module: File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot beloaded because running scripts is disabled on this system. Per ulteriori informazioni, vedere about_Execution_Policies all'indirizzo https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Risoluzione** Per risolvere il problema, avviare PowerShell come amministratore e quindi eseguire il comando seguente:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Per informazioni dettagliate sul criterio di esecuzione, consulta l'argomento all'indirizzo [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Errore di Import-Module causato da una versione errata di Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Il Modulo del connettore di Skype for Business Online può essere eseguito solo in Windows PowerShell 3.0. Se si prova a importare il modulo in una versione precedente di PowerShell, il processo di importazione avrà esito negativo con un messaggio di errore simile a questo messaggio:
  
  - **Errore**: *Import-Module: La versione di PowerShell caricata è '2.0'. Il modulo 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' richiede una versione minima di PowerShell di '3.0' per l'esecuzione. Verificare l'installazione di PowerShell e riprovare.*

- **Risoluzione**: l'unico modo per risolvere il problema consiste nell'installare Windows PowerShell 3.0, disponibile nell'Area download Microsoft all'indirizzo [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>L'autenticazione moderna non riesce quando l'autenticazione di base di WinRM è stata disabilitata
<a name="BKMKWinRMBasicAuth"> </a>

La versione più recente del modulo Skype for Business Online Connector utilizza l'autenticazione moderna, ma il client Gestione remota Windows sottostante (WinRM) deve essere configurato per consentire l'autenticazione di base.  L'autenticazione moderna usa token di portatore, che in genere vengono passati nell'intestazione *Autorizzazione: Bearer* . Windows PowerShell, su cui è stato creato Skype for Business PowerShell, non consente la manipolazione di questa intestazione.  Skype for Business PowerShell usa invece l'intestazione *Autorizzazione: Di base* per passare il token di portatore.

Per istruzioni su come abilitare WinRM per l'autenticazione di base, vedere [Scaricare e installare Windows PowerShell](./download-and-install-windows-powershell-5-1.md) .

## <a name="failed-to-connect-to-live-id-server"></a>Connessione al server Live ID non riuscita
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> L'autenticazione Live ID è stata deprecata per Skype For Business Online Connector. Usare il modulo PowerShell di Teams per gestire il tenant online. Quando si gestiscono ambienti ibridi, eseguire l'aggiornamento all'aggiornamento cumulativo più recente o usare l'autenticazione oAuth.

Sono in genere tre i motivi della non riuscita di un tentativo di connessione, con l'errore riportato di seguito:

  - **Errore**: *Get-CsWebTicket: impossibile connettere i server degli ID in tempo reale. Verificare che il proxy sia abilitato o che il computer disponga di una connessione di rete ai server degli ID in tempo reale.*

- **Risoluzione**: spesso questo errore indica che Assistente per l'accesso ai Microsoft Online Services non è in esecuzione. Puoi verificare lo stato di questo servizio eseguendo il comando seguente dal prompt di PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Se il servizio non è in esecuzione, avvialo usando il comando seguente:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Se il servizio è in esecuzione, potrebbero essersi verificati problemi di connessione di rete tra il computer e il server di autenticazione di Microsoft Live ID. Per verificare, apri Internet Explorer e accedi a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Provare ad accedere a Microsoft 365 o Office 365 da questa pagina. Se l'accesso non riesce, è probabile che ci siano problemi con la connessione di rete.
  
    Meno frequentemente, è possibile che l'URI di connessione per il server di autenticazione di Microsoft Live ID sia stato impostato con un valore errato. Se si è già verificato che l'Assistente per l'accesso è in esecuzione e non sono stati riscontrati problemi di rete, questa potrebbe essere la causa del problema. In questo caso, contatta il supporto tecnico Microsoft.
  
## <a name="logon-failed-for-the-user"></a>Accesso non riuscito per l'utente
<a name="BKMKLogonFailed"> </a>

Quando tenti di effettuare una connessione remota a Skype for Business online, devi fornire il nome utente e la password di un account utente di Skype for Business online valido. In caso contrario, l'accesso non riuscirà insieme a un messaggio di errore simile al seguente:

- **Errore**: *Get-CsWebTicket: accesso non riuscito per l'utente 'kenmyer@litwareinc.com'. Creare un nuovo oggetto PSCredential, assicurandosi di aver usato il nome utente e la password corretti.*

- **Risoluzione**: se pensi di usare un account utente valido e di avere la password corretta, prova di nuovo ad accedere. In caso di esito negativo, usare le stesse credenziali e provare ad accedere a [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se non riesci ad accedere, contatta il supporto tecnico Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L'utente non dispone delle autorizzazioni per la gestione del tenant
<a name="BKMKUserPermission"> </a>

Non puoi stabilire una connessione remota di PowerShell a Skype for Business online a meno che tu non faccia parte del gruppo di amministratori del tenant. Se non sei un membro di questo gruppo, il tentativo di connessione non riuscirà e verrà visualizzato il messaggio di errore seguente:

- **Errore**: *New-PSSession : [admin.vdomain.com] Elaborazione dei dati dal server remoto admin.vdomain.com non riuscita con il seguente messaggio di errore: L'utente 'user@foo.com' non dispone dell'autorizzazione per gestire il tenant. Le autorizzazioni possono essere concesse assegnando all'utente il ruolo di controllo degli accessi in base al ruolo appropriato. Per ulteriori informazioni, vedi Risoluzione [remota dei problemi](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Risoluzione**: se si ritiene di essere un membro del gruppo Amministratori tenant, è necessario contattare il supporto tecnico Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online
<a name="BKMKAbilityConnect"> </a>

Per poter usare PowerShell per la gestone di Skype for Business online, è necessario che la proprietà di EnableRemotePowerShellAccess del criterio del tenant di PowerShell in uso sia impostata su  `True`. In caso contrario, la connessione non riesce e viene visualizzato il messaggio di errore seguente:

- **Errore**: *New-PSSession : [admin.vdomain.com] Elaborazione dei dati dal server remoto admin.vdomain.com non riuscita con il seguente messaggio di errore: La possibilità di connettersi a questo tenant usando una sessione remota di PowerShell è stata disabilitata. Contattare la Guida di Lync per controllare i criteri di PowerShell tenant di questo tenant. Per ulteriori informazioni, vedi Risoluzione [remota dei problemi](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Risoluzione**: se viene visualizzato questo messaggio di errore, dovrai contattare il supporto tecnico Microsoft e attivare l'accesso remoto a PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business Online
<a name="BKMKMaxNumberShellsUser"> </a>

Ogni amministratore può eseguire fino a tre connessioni remote simultanee a Skype for Business online. Se sono attive tre connessioni remote a PowerShell, qualsiasi tentativo di effettuare una quarta connessione simultanea non riuscirà, generando il messaggio di errore seguente: 

- **Errore**: *New-PSSession : [admin.vdomain.com] Connessione al server remoto admin.vdomain.com non riuscita con il seguente messaggio di errore: Il servizio WS-Management non può elaborare la richiesta. È stato superato il numero massimo di shell simultanee per questo utente. Chiudere le shell esistenti o aumentare la quota per questo utente. Per ulteriori informazioni, vedi Risoluzione [remota dei problemi](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Risoluzione**: l'unico modo per risolvere il problema consiste nel chiudere una o più delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Anche se ogni amministratore può avere fino a tre connessioni simultanee a un tenant di Skype for Business Online, nessun tenant può avere più di 20 connessioni simultanee. Ad esempio, sei amministratori potrebbero avere tre sessioni aperte. Se un quarto amministratore prova a effettuare più di due connessioni, con un totale di 21 connessioni simultanee, il tentativo non riesce e viene visualizzato il messaggio di errore seguente:
  
- **Errore**: *New-PSSession : [admin.vdomain.com] La connessione al server remoto admin.vdomain.com non riuscita con il seguente messaggio di errore: Il servizio WS-Management non può elaborare la richiesta. È stato superato il numero massimo di shell simultanee per questo tenant. Chiudi le shell esistenti o aumenta la quota per questo tenant. Per ulteriori informazioni, vedi Risoluzione [remota dei problemi](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Risoluzione**: l'unico modo per risolvere il problema consiste nel chiudere una o più delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.  
 
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione di Skype for Business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
