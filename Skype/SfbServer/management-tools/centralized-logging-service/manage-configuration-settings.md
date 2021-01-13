---
title: Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business Server 2015
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
description: 'Riepilogo: informazioni su come recuperare, aggiornare e creare impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835156"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business Server 2015

**Riepilogo:** Informazioni su come recuperare, aggiornare e creare impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.

Il servizio di registrazione centralizzato è controllato e configurato dalle impostazioni e dai parametri creati e utilizzati dal controller del servizio di registrazione centralizzato (CLSController) per inviare comandi all'agente di servizio di registrazione centralizzato del singolo computer (CLSAgent). L'agente elabora i comandi inviati e, nel caso di un comando di avvio, utilizza la configurazione di scenari, provider, durata traccia e flag per iniziare a raccogliere i log di traccia in base alle informazioni di configurazione fornite.

> [!IMPORTANT]
>  Non tutti i cmdlet di Windows PowerShell elencati per il servizio di registrazione centralizzato sono progettati per essere utilizzati con le distribuzioni locali di Skype for Business Server 2015. Sebbene possano sembrare utili, i cmdlet seguenti non sono stati creati per funzionare con le distribuzioni locali di Skype for Business Server 2015:

-  **Cmdlet di CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlet CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlet di CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Le impostazioni definite in questi cmdlet non impediscono o causano un comportamento avverso, ma sono progettate per l'utilizzo con Microsoft 365 o Office 365 e non restituiscono i risultati previsti nelle distribuzioni locali. Questo non significa che non si possono utilizzare nelle distribuzioni locali, ma il loro utilizzo è descritto in un argomento più avanzato che non è incluso in questa documentazione.

Il servizio di registrazione centralizzato può essere eseguito in un ambito che include un singolo computer o un pool di computer, nell'ambito di un sito, ovvero in un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione, oppure in un ambito globale (ovvero tutti i computer e i pool della distribuzione).

Per configurare l'ambito del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno dei due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Ad esempio:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Sono presenti differenze fondamentali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController. Windows PowerShell fornisce un metodo RTF per la configurazione e la definizione degli scenari e per riutilizzare tali scenari in modo significativo per gli scenari di risoluzione dei problemi. Mentre CLSController non offre un modo rapido ed efficiente per eseguire comandi e ottenere risultati, il set di comandi di CLSController è limitato dal numero finito di comandi disponibili dalla riga di comando. A differenza dei cmdlet di Windows PowerShell, CLSController non è in grado di definire nuovi scenari, gestire gli ambiti a livello di sito o globale e molte altre limitazioni di un set di comandi finiti che non può essere configurato dinamicamente. Mentre CLSController fornisce un mezzo per l'esecuzione rapida, Windows PowerShell fornisce un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre ciò che è possibile con CLSController.

È possibile definire un singolo ambito del computer durante l'esecuzione di un comando [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) tramite il parametro-Computers. Il parametro-Computers accetta un elenco separato da virgole di nomi di dominio completi (FQDN) per il computer di destinazione.

> [!TIP]
> È inoltre possibile definire i pool e un elenco separato da virgole dei pool a cui si desidera eseguire i comandi di registrazione.

I siti e gli ambiti globali sono definiti nei cmdlet **New-**, **set-** e **Remove-** centralizzated Logging Service. Negli esempi seguenti viene illustrato come impostare un ambito a livello di sito o globale.

> [!IMPORTANT]
> I comandi illustrati possono contenere i parametri e concetti trattati in altre sezioni. I comandi di esempio hanno lo scopo di dimostrare l'utilizzo del parametro **-Identity** per definire l'ambito e gli altri parametri sono inclusi per la completezza e per specificare l'ambito. Per dettagli sui cmdlet **Set-CsClsConfiguration**, vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) nella documentazione sulle operazioni.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Utilizzare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o per aggiornare una configurazione esistente. Quando si esegue **Get-CsClsConfiguration**, vengono visualizzate informazioni analoghe alla schermata seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono state definite configurazioni di sito:

![Output di esempio da Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente dall'archivio locale del computer

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Quando si utilizza il primo esempio in cui **Get-CsClsConfiguration** non specifica alcun parametro, il comando fa riferimento all'archivio di gestione centrale per i dati. Se si specifica il parametro-LocalStore, il comando fa riferimento al computer LocalStore anziché all'archivio di gestione centrale.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Per recuperare un elenco di scenari attualmente definiti

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Ad esempio, per recuperare gli scenari definiti nell'ambito globale:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Il cmdlet **Get-CsClsConfiguration** Visualizza sempre gli scenari che fanno parte della configurazione di un determinato ambito. Nella maggior parte dei casi, non sono visualizzati tutti gli scenari e sono presenti troncamenti. Il comando usato in questo caso elenca tutti gli scenari e informazioni parziali sui provider, le impostazioni e i flag in uso.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

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

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Per creare una nuova configurazione del servizio di registrazione centralizzata

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration offre accesso a numerose impostazioni di configurazione facoltative. Per informazioni dettagliate sulle opzioni di configurazione, vedere [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) e [informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per tali file, occorre digitare quanto segue:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

È consigliabile pianificare attentamente la creazione di nuove configurazioni e la modalità di definizione di nuove proprietà per il servizio di registrazione centralizzato. È anche opportuno prestare attenzione alle modifiche che vi si apportano accertandosi di comprenderne l'impatto sulla capacità di registrare correttamente gli scenari dei problemi. È consigliabile apportare alla configurazione modifiche in grado di migliorare la gestione dei log con dimensioni e periodi di rollover che consentano di risolvere i problemi quando si verificano.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Per rimuovere una configurazione del servizio di registrazione centralizzata esistente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt dei comandi:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Ad esempio, per rimuovere una configurazione del servizio di registrazione centralizzata creata per aumentare il tempo di rollover dei file di registro, aumentare le dimensioni del file di registro di rollover e impostare il percorso della cache dei file di registro su una condivisione di rete, come indicato di seguito:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Questa è la nuova configurazione creata nella procedura "per creare una nuova configurazione del servizio di registrazione centralizzata".

Se si sceglie di rimuovere una configurazione a livello di sito, il sito userà le impostazioni globali.
## <a name="see-also"></a>Vedere anche

[Configurare i provider per il servizio di registrazione centralizzato in Skype for Business Server 2015](configure-providers.md)

[Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015](configure-scenarios.md)

[Servizio di registrazione centralizzato in Skype for business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
