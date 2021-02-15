---
title: Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Riepilogo: informazioni su come recuperare, aggiornare e creare le impostazioni di configurazione per il servizio di registrazione centralizzata in Skype for Business Server 2015.'
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835156"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business Server

**Riepilogo:** Informazioni su come recuperare, aggiornare e creare le impostazioni di configurazione per il servizio di registrazione centralizzata in Skype for Business Server 2015.

Il servizio di registrazione centralizzata è controllato e configurato da impostazioni e parametri creati e utilizzati da CLSController (Centralized Logging Service Controller) per inviare comandi all'agente del servizio di registrazione centralizzato (CLSAgent) del singolo computer. L'agente elabora i comandi inviati e, nel caso di un comando Start, utilizza la configurazione degli scenari, dei provider, della durata della traccia e dei flag per iniziare a raccogliere i registri di traccia in base alle informazioni di configurazione fornite.

> [!IMPORTANT]
>  Non tutti Windows PowerShell cmdlet elencati per il servizio di registrazione centralizzata sono destinati all'uso con le distribuzioni locali di Skype for Business Server 2015. Anche se sembrano funzionare, i cmdlet seguenti non sono progettati per funzionare con le distribuzioni locali di Skype for Business Server 2015:

-  **Cmdlet CsClsRegion:** [Get-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) [Set-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps) [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion.](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)
-  **Cmdlet CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlet CsClsSecurityGroup:** [Get-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [Set-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps) [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup.](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)

Le impostazioni definite in questi cmdlet non impediranno o causeranno comportamenti negativi, ma sono progettate per l'uso con Microsoft 365 o Office 365 e non producono i risultati previsti nelle distribuzioni locali. Questo non significa che non si possono utilizzare nelle distribuzioni locali, ma il loro utilizzo è descritto in un argomento più avanzato che non è incluso in questa documentazione.

Il servizio di registrazione centralizzata può essere eseguito in un ambito che include un singolo computer o un pool di computer, in un ambito sito , ovvero in un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione, oppure in un ambito globale, ovvero in tutti i computer e i pool della distribuzione.

Per configurare l'ambito del servizio di registrazione centralizzata utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator in base al controllo di accesso basato sui ruoli (RBAC) oppure un ruolo RBAC personalizzato contenente uno di questi due gruppi. Per ottenere un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati dall'utente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Ad esempio:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Esistono differenze fondamentali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController. Windows PowerShell offre un metodo efficace per configurare e definire gli scenari e riutilizzarli in modo significativo per gli scenari di risoluzione dei problemi. Mentre CLSController non offre un modo rapido ed efficiente per eseguire comandi e ottenere risultati, il set di comandi di CLSController è limitato dal numero finito di comandi disponibili dalla riga di comando. A differenza dei cmdlet Windows PowerShell, CLSController non può definire nuovi scenari, gestire l'ambito a livello di sito o globale e molte altre limitazioni di un set di comandi finito che non può essere configurato dinamicamente. Anche se CLSController fornisce un mezzo per l'esecuzione rapida, Windows PowerShell offre un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre a quanto possibile con CLSController.

Durante l'esecuzione di un comando [Search-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps) [Stop-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps) [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) è possibile definire un singolo ambito computer utilizzando il parametro -Computers. Il parametro -Computers accetta un elenco delimitato da virgole di nomi di dominio completi (FQDN) per il computer di destinazione.

> [!TIP]
> È inoltre possibile definire -Pools e un elenco delimitato da virgole di pool in cui si desidera eseguire i comandi di registrazione.

Gli ambiti sito e Globale sono definiti nei cmdlet **New-**, **Set-** e **Remove-** Centralized Logging Service. Negli esempi seguenti viene illustrato come impostare un ambito a livello di sito o globale.

> [!IMPORTANT]
> I comandi illustrati possono contenere i parametri e concetti trattati in altre sezioni. I comandi di esempio hanno lo scopo di illustrare l'utilizzo del parametro **-Identity** per definire l'ambito e gli altri parametri sono inclusi per completezza e per specificare l'ambito. Per dettagli sui cmdlet **Set-CsClsConfiguration**, vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) nella documentazione sulle operazioni.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Per recuperare la configurazione corrente del servizio di registrazione centralizzata

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Utilizzare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o aggiornare una configurazione esistente. Quando si esegue **Get-CsClsConfiguration,** vengono visualizzate informazioni simili alla schermata seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono definite configurazioni di sito:

![Output di esempio da Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Per recuperare la configurazione corrente del servizio di registrazione centralizzata dall'archivio locale del computer

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Quando si utilizza il primo esempio in cui **Get-CsClsConfiguration** non specifica alcun parametro, il comando fa riferimento all'archivio di gestione centrale per i dati. Se si specifica il parametro -LocalStore, il comando fa riferimento al computer LocalStore anziché all'archivio di gestione centrale.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Per recuperare un elenco di scenari attualmente definiti

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Ad esempio, per recuperare gli scenari definiti nell'ambito globale:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Il cmdlet **Get-CsClsConfiguration** visualizza sempre gli scenari che fanno parte della configurazione di un determinato ambito. Nella maggior parte dei casi, non sono visualizzati tutti gli scenari e sono presenti troncamenti. Il comando usato in questo caso elenca tutti gli scenari e informazioni parziali sui provider, le impostazioni e i flag in uso.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Esempio:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

Il comando indica al CLSAgent in ogni computer e pool della distribuzione di impostare le dimensioni del valore di rollover per il file di traccia su 40 megabyte. Il comando si applica a tutti i computer e i pool in tutti i siti e imposta il valore di rollover del log di traccia configurato su 40 megabyte.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito del sito per il servizio di registrazione centralizzato tramite Windows PowerShell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Esempio:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Come si nota nell'esempio, il percorso predefinito dei file di log è %TEMP%\Tracing. Tuttavia, poiché il file viene in effetti scritto da CLSAgent il quale viene eseguito con l'account Servizio di rete, la variabile %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

Il comando indica al CLSAgent in ogni computer e pool del sito Redmond di impostare le dimensioni del valore di rollover per il file di traccia su 40 megabyte. I computer e i pool in altri siti non verranno modificati dal comando e continueranno a usare il valore di rollover del log di traccia definito per impostazione predefinita (20 megabyte) o durante l'avvio della sessione di registrazione.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Per creare una nuova configurazione del servizio di registrazione centralizzato

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration offre accesso a numerose impostazioni di configurazione facoltative. Per informazioni dettagliate sulle opzioni di configurazione, vedere [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) e [Understanding Centralized Logging Service Configuration Settings.](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)

Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per tali file, occorre digitare quanto segue:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

È consigliabile pianificare con attenzione la creazione di nuove configurazioni e la modalità di definizione delle nuove proprietà per il servizio di registrazione centralizzato. È anche opportuno prestare attenzione alle modifiche che vi si apportano accertandosi di comprenderne l'impatto sulla capacità di registrare correttamente gli scenari dei problemi. È consigliabile apportare alla configurazione modifiche in grado di migliorare la gestione dei log con dimensioni e periodi di rollover che consentano di risolvere i problemi quando si verificano.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Per rimuovere una configurazione esistente del servizio di registrazione centralizzata

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Ad esempio, per rimuovere una configurazione del servizio di registrazione centralizzata creata per aumentare il tempo di rollover dei file di registro, aumentare le dimensioni del file di registro di rollover e impostare il percorso della cache dei file di registro su una condivisione di rete come segue:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Si tratta della nuova configurazione creata nella procedura "Per creare una nuova configurazione del servizio di registrazione centralizzata".

Se si sceglie di rimuovere una configurazione a livello di sito, il sito userà le impostazioni globali.
## <a name="see-also"></a>Vedere anche

[Configurare i provider per il servizio di registrazione centralizzato in Skype for Business Server 2015](configure-providers.md)

[Configurare gli scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015](configure-scenarios.md)

[Servizio di registrazione centralizzato in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
