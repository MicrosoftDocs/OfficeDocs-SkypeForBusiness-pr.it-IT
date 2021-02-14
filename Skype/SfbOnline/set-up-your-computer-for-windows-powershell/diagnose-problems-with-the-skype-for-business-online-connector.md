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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: 019ef023b325227be046aae1e855573449453864
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204877"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosi dei problemi di connessione con il connettore di Skype for Business Online

[] Questo argomento offre informazioni che ti aiuteranno a diagnosticare e risolvere i problemi che si possono verificare quando provi a creare una sessione remota di Microsoft PowerShell che si connette a Skype for Business online. Consulta le sezioni seguenti:
  
- [Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Errore di Import-Module causato da una versione errata di Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [L'autenticazione moderna non riesce quando l'autenticazione di base di WinRM è stata disabilitata](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Connessione al server Live ID non riuscita](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Caricamento del modulo Live ID non riuscito](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Accesso non riuscito per l'utente](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L'utente non dispone delle autorizzazioni per la gestione del tenant](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> Per impostazione predefinita, le sessioni di PowerShell hanno un timeout dopo 60 minuti. Per riconnettersi, è necessario chiudere la sessione e avviare una nuova sessione di PowerShell. Una nuova versione di Skype for Business online, modulo [Windows PowerShell (2046.123 - Pubblicato il 2/10/2019),](https://www.microsoft.com/download/details.aspx?id=39366)è stata avviata di recente, che include un nuovo cmdlet chiamato **Enable-CsOnlineSessionForReconnection** che attenua il problema di timeout di 60 minuti.
> La sessione di PowerShell si riconnette ed esegue l'autenticazione, consentendone il nuovo uso senza dover avviare una nuova istanza per riconnetterla.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Errore di Import-Module causato dal criterio di esecuzione di Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Il criterio di esecuzione di PowerShell consente di determinare quali file di configurazione possono essere caricati nella console di PowerShell e quali script possono essere eseguiti da un utente da questa console. Come minimo, il Modulo del connettore di Skype for Business Online non può essere importato a meno che il criterio di esecuzione non sia stato impostato su RemoteSigned. In caso contrario, quando si prova a importare il modulo verrà visualizzato il seguente messaggio di errore:
  
- **Errore:** Modulo importazione: File C: File di programma File comuni Microsoft <em> \\ Lync Server \\ \\ 2013 Moduli \\ di \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 non possono essere caricati perché l'esecuzione di script è disabilitata nel sistema. Per altre informazioni, vedere about_Execution_Policies all'indirizzo https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Risoluzione** Per risolvere il problema, avviare PowerShell come amministratore, quindi eseguire il comando seguente:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Per informazioni dettagliate sul criterio di esecuzione, consulta l'argomento all'indirizzo [about_Execution_Policies](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Errore di Import-Module causato da una versione errata di Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Il Modulo del connettore di Skype for Business Online può essere eseguito solo in Windows PowerShell 3.0. Se provi a importare il modulo in una versione precedente di PowerShell, il processo di importazione non riesce e viene visualizzato un messaggio di errore analogo al seguente:
  
  - **Errore:** *Import-Module: La versione di PowerShell caricata è '2.0'. Il modulo 'D: Programmi File comuni \\ \\ Microsoft Lync Server \\ 2013 Modules LyncOnlineConnectorLyncOnlineConnector.psd1' richiede una versione minima di \\ \\ \\ PowerShell "3.0" per l'esecuzione. Verificare l'installazione di PowerShell e riprovare.*

- **Soluzione:** l'unico modo per risolvere il problema è installare Windows PowerShell 3.0, disponibile nell'Area download Microsoft all'indirizzo [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>L'autenticazione moderna non riesce quando l'autenticazione di base di WinRM è stata disabilitata
<a name="BKMKWinRMBasicAuth"> </a>

L'ultima versione del modulo Skype for Business Online Connector usa l'autenticazione moderna, ma il client Windows Remote Management (WinRM) sottostante deve essere configurato per consentire l'autenticazione di base.  L'autenticazione moderna usa token di orso, che in genere vengono passati nell'intestazione *Autorizzazione: Orso.* Windows PowerShell, su cui è stato creato Skype for Business PowerShell, non consente la modifica di questa intestazione.  Al contrario, PowerShell di Skype for Business usa *l'intestazione Autorizzazione: Base* per superare il token di orso.

Vedere [scaricare e installare Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) per istruzioni su come abilitare WinRM per l'autenticazione di base.

## <a name="failed-to-connect-to-live-id-server"></a>Connessione al server Live ID non riuscita
<a name="BKMKFailedConnect"> </a>

Sono in genere tre i motivi della non riuscita di un tentativo di connessione, con l'errore riportato di seguito:

  - **Errore:** *Get-CsWebTicket: Impossibile connettere i server Live ID. Verificare che il proxy sia abilitato o che il computer abbia una connessione di rete ai server Live ID.*

- **Soluzione:** spesso questo errore indica che l Microsoft Online Services assistente per l'accesso non è in esecuzione. Puoi verificare lo stato di questo servizio eseguendo il comando seguente dal prompt di PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Se il servizio non è in esecuzione, avvialo usando il comando seguente:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Se il servizio è in esecuzione, potrebbero essersi verificati problemi di connessione di rete tra il computer e il server di autenticazione di Microsoft Live ID. Per verificare, apri Internet Explorer e accedi a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Provare ad accedere a Microsoft 365 o Office 365 da questa pagina. Se l'accesso non riesce, è probabile che ci siano problemi con la connessione di rete.
  
    Meno frequentemente, è possibile che l'URI di connessione per il server di autenticazione di Microsoft Live ID sia stato impostato con un valore errato. Se si è già verificato che l'Assistente per l'accesso è in esecuzione e non sono stati riscontrati problemi di rete, questa potrebbe essere la causa del problema. In questo caso, contattare il supporto tecnico Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Caricamento del modulo Live ID non riuscito
<a name="BKMKFailedLoad"> </a>

Uno dei prerequisiti per l'uso di PowerShell per la gestione di Skype for Business online è l'installazione di Assistente per l'accesso ai Microsoft Online Services. Se l'Assistente per l'accesso non è installato e si cerca di stabilire una connessione remota con Skype for Business online, viene visualizzato il messaggio di errore seguente:

- **Errore:** *Get-CsWebTicket: Impossibile caricare il modulo Live Id. Verificare che sia installata la versione corretta di Assistente per l'accesso con Live Id.*

- **Soluzione:** l Microsoft Online Services assistente per l'accesso è disponibile nell'Area download Microsoft presso Microsoft Online Services Sign-In Assistant per professionisti [IT - RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Accesso non riuscito per l'utente
<a name="BKMKLogonFailed"> </a>

Quando tenti di effettuare una connessione remota a Skype for Business online, devi fornire il nome utente e la password di un account utente di Skype for Business online valido. In caso contrario, l'accesso non riuscirà e verrà restituito un messaggio di errore simile al seguente:

- **Errore:** *Get-CsWebTicket: accesso non riuscito per l'utente 'kenmyer@litwareinc.com'. Crea un nuovo oggetto PSCredential, verifica di* aver usato il nome utente e la password corretti.

- **Soluzione:** se si pensa di usare un account utente valido e si dispone della password corretta, provare di nuovo ad accedere. In caso di esito negativo, usa le stesse credenziali e prova ad accedere all'indirizzo [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se non è possibile accedere, contattare il supporto tecnico Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L'utente non dispone delle autorizzazioni per la gestione del tenant
<a name="BKMKUserPermission"> </a>

Non puoi stabilire una connessione remota di PowerShell a Skype for Business online a meno che tu non faccia parte del gruppo di amministratori del tenant. Se non sei un membro di questo gruppo, il tentativo di connessione non riuscirà e verrà visualizzato il messaggio di errore seguente:

- **Errore:** New-PSSession: [admin.vdomain.com] L'elaborazione dei dati dal server remoto admin.vdomain.com non è riuscita con il messaggio di errore seguente: L'utente 'user@foo.com' non ha l'autorizzazione per gestire il *tenant. Le autorizzazioni possono essere concesse assegnando all'utente il ruolo RBAC appropriato. Per altre informazioni, vedere risoluzione [dei problemi remota.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Soluzione:** se si pensa di essere, o si dovrebbe essere, un membro del gruppo Amministratori tenant, è necessario contattare il supporto tecnico Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La possibilità di connetterti al tenant è stata disabilitata in Skype for Business Online
<a name="BKMKAbilityConnect"> </a>

Per poter usare PowerShell per la gestone di Skype for Business online, è necessario che la proprietà di EnableRemotePowerShellAccess del criterio del tenant di PowerShell in uso sia impostata su  `True`. In caso contrario, la connessione non riesce e viene visualizzato il messaggio di errore seguente:

- **Errore:** New-PSSession: [admin.vdomain.com] L'elaborazione dei dati dal server remoto admin.vdomain.com non è riuscita con il messaggio di errore seguente: La connessione al tenant tramite una sessione remota di PowerShell è stata *disabilitata. Contattare la Guida di Lync per verificare i criteri di PowerShell per il tenant. Per altre informazioni, vedere risoluzione [dei problemi remota.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Soluzione:** se viene visualizzato questo messaggio di errore, è necessario contattare il supporto Microsoft e ottenere l'accesso remoto a PowerShell abilitato.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo utente in Skype for Business Online
<a name="BKMKMaxNumberShellsUser"> </a>

Ogni amministratore può eseguire fino a tre connessioni remote simultanee a Skype for Business online. Se sono attive tre connessioni remote a PowerShell, qualsiasi tentativo di effettuare una quarta connessione simultanea non riuscirà, generando il messaggio di errore seguente:

- **Errore:** New-PSSession: [admin.vdomain.com] Connessione al server remoto admin.vdomain.com non riuscita con il messaggio di errore seguente: Il servizio WS-Management non può *elaborare la richiesta. È stato superato il numero massimo di shell simultanee per questo utente. Chiudere le shell esistenti o aumentare la quota per l'utente. Per altre informazioni, vedere la https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 sezione [Risoluzione dei problemi remota](*

- **Soluzione:** l'unico modo per risolvere il problema è chiudere una o più delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>È stato superato il numero massimo di shell simultanee per questo tenant in Skype for Business Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Anche se ogni amministratore può avere fino a tre connessioni simultanee a un tenant di Skype for Business Online, nessun tenant può avere più di 20 connessioni simultanee. Ad esempio, sei amministratori potrebbero avere tre sessioni aperte ognuna. Se un quarto amministratore cerca di effettuare più di 2 connessioni, con un totale di 21 connessioni simultanee, il tentativo non riuscirà e verrà visualizzato il messaggio di errore seguente:
  
- **Errore:** New-PSSession: [admin.vdomain.com] Connessione al server remoto admin.vdomain.com non riuscita con il messaggio di errore seguente: Il servizio WS-Management non può *elaborare la richiesta. È stato superato il numero massimo di shell simultanee per questo tenant. Chiudere le shell esistenti o aumentare la quota per il tenant. Per altre informazioni, vedere la https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 sezione [Risoluzione dei problemi remota](*

- **Soluzione:** l'unico modo per risolvere il problema è chiudere una o più delle connessioni precedenti. Dopo aver concluso una sessione di Skype for Business online, è consigliabile usare il cmdlet **Remove-PSSession** per terminare la sessione. Questa soluzione aiuta a prevenire il problema.  
 
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione di Skype for Business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
