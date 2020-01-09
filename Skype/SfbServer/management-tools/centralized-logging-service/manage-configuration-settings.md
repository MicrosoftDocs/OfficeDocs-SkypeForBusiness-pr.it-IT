---
title: Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Riepilogo: informazioni su come recuperare, aggiornare e creare impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 20f62a5568bef6f11eab35e13fa4e4f7adf8102e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991461"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business 2015

**Riepilogo:** Informazioni su come recuperare, aggiornare e creare impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.

Il servizio di registrazione centralizzato viene controllato e configurato tramite le impostazioni e i parametri creati e usati dal controller del servizio di registrazione centralizzato (CLSController) per inviare comandi all'agente del servizio di registrazione centralizzato del singolo computer ( CLSAgent). L'agente elabora i comandi inviati e (nel caso di un comando Start) usa la configurazione degli scenari, i provider, la durata della traccia e i contrassegni per iniziare a raccogliere i log di traccia in base alle informazioni di configurazione fornite.

> [!IMPORTANT]
>  Non tutti i cmdlet di Windows PowerShell elencati per il servizio di registrazione centralizzata sono progettati per l'uso con le distribuzioni locali di Skype for Business Server 2015. Anche se potrebbero sembrare utili, i cmdlet seguenti non sono progettati per funzionare con le distribuzioni locali di Skype for Business Server 2015:

-  **Cmdlet CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlet CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlet CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Le impostazioni definite in questi cmdlet non impediscono o causano alcun comportamento indesiderato, ma sono progettate per l'uso con Microsoft Office 365 e non restituiscono i risultati previsti nelle distribuzioni locali. Questo non significa che non sia possibile usare questi cmdlet in distribuzioni locali, ma il loro uso è un argomento più avanzato che non è incluso in questa documentazione.

Il servizio di registrazione centralizzato può essere eseguito in un ambito che include un singolo computer o un pool di computer, in un ambito del sito (ovvero un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione) o in un ambito globale (ovvero , tutti i computer e i pool della distribuzione.

Per configurare l'ambito del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Ad esempio:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Esistono differenze sostanziali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController. Windows PowerShell offre un metodo RTF per configurare e definire scenari e per riutilizzare questi scenari in modo significativo per gli scenari di risoluzione dei problemi. Mentre CLSController offre un modo rapido ed efficiente per emettere comandi e ottenere risultati, il set di comandi per CLSController è limitato dai comandi finiti disponibili dalla riga di comando. Diversamente dai cmdlet di Windows PowerShell, CLSController non è in grado di definire nuovi scenari, gestire l'ambito a livello di sito o globale e molte altre limitazioni di un set di comandi finito che non può essere configurato in modo dinamico. Mentre CLSController offre un mezzo per l'esecuzione veloce, Windows PowerShell offre un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre ciò che è possibile con CLSController.

Un singolo ambito computer può essere definito durante l'esecuzione di un comando [Cerca-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) usando il parametro-Computers. Il parametro-Computers accetta un elenco delimitato da virgole di nomi di dominio completi (FQDN) per il computer di destinazione.

> [!TIP]
> È anche possibile definire i pool e un elenco di pool separati da virgole per cui si vogliono eseguire i comandi di registrazione.

Il sito e gli ambiti globali sono definiti nei cmdlet **nuovo-**, **set-** e **Rimuovi-** servizio di registrazione centralizzato. Gli esempi seguenti illustrano come impostare un sito e un ambito globale.

> [!IMPORTANT]
> I comandi visualizzati possono contenere parametri e concetti trattati in altre sezioni. I comandi di esempio hanno lo scopo di dimostrare l'uso del parametro **-Identity** per definire l'ambito e gli altri parametri sono inclusi per la completezza e per specificare l'ambito. Per informazioni dettagliate sui cmdlet **Set-CsClsConfiguration** , vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) nella documentazione Operations.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt della riga di comando:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Usare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o aggiornare una configurazione esistente. Quando si esegue **Get-CsClsConfiguration**, vengono visualizzate informazioni simili allo screenshot seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono state definite configurazioni di sito:

![Output di esempio di Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente dall'archivio locale del computer

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt della riga di comando:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Quando si usa il primo esempio in cui **Get-CsClsConfiguration** non specifica parametri, il comando fa riferimento all'Central Management store per i dati. Se specifichi il parametro-LocalStore, il comando fa riferimento al computer LocalStore invece di Central Management store.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Per recuperare un elenco di scenari attualmente definiti

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt della riga di comando:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Ad esempio, per recuperare gli scenari definiti nell'ambito globale:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Il cmdlet **Get-CsClsConfiguration** Visualizza sempre gli scenari che fanno parte di una determinata configurazione dell'ambito. Nella maggior parte dei casi, tutti gli scenari non vengono visualizzati e vengono troncati. Il comando usato qui elenca tutti gli scenari e le informazioni parziali sui provider, le impostazioni e i contrassegni usati.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt della riga di comando:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Ad esempio:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

Il comando indica a CLSAgent su ogni computer e pool della distribuzione di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte. I computer e i pool in tutti i siti sono interessati dal comando e impostano il valore di rollover del log di traccia configurato su 40 megabyte.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito del sito per il servizio di registrazione centralizzato tramite Windows PowerShell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt della riga di comando:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Ad esempio:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Come indicato nell'esempio, la posizione predefinita dei file di log è%TEMP%\Tracing. Tuttavia, poiché in realtà è CLSAgent che sta scrivendo il file e CSLAgent viene eseguito come servizio di rete, la variabile% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

Il comando indica a CLSAgent su ogni computer e pool nel sito Redmond di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte. I computer e i pool in altri siti non saranno interessati dal comando e continueranno a usare il valore di rollover del log di traccia attualmente configurato per impostazione predefinita (20 megabyte) o durante l'inizio della sessione di registrazione.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Per creare una nuova configurazione del servizio di registrazione centralizzata

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt della riga di comando:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration offre l'accesso a un numero elevato di impostazioni di configurazione facoltative. Per informazioni dettagliate sulle opzioni di configurazione, vedere [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) e [informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per i file di log, digitare:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

È consigliabile pianificare con attenzione la creazione di nuove configurazioni e come definire nuove proprietà per il servizio di registrazione centralizzata. È necessario prestare attenzione a apportare modifiche e verificare che sia possibile comprendere l'impatto sulla possibilità di registrare correttamente gli scenari di problemi. È necessario apportare modifiche alla configurazione che rafforzerà la possibilità di gestire i log in una dimensione e un periodo di rollover che consentiranno di risolvere i problemi quando si presenta.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Per rimuovere una configurazione del servizio di registrazione centralizzata esistente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Digitare quanto segue al prompt della riga di comando:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Ad esempio, per rimuovere una configurazione centralizzata del servizio di registrazione creata per aumentare il tempo di rollover del file di log, aumentare le dimensioni del file di log di rollover e impostare la posizione della cache del file di log su una condivisione di rete come segue:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Questa è la nuova configurazione creata nella procedura "per creare una nuova configurazione del servizio di registrazione centralizzata".

Se si sceglie di rimuovere una configurazione a livello di sito, il sito utilizzerà le impostazioni globali.
## <a name="see-also"></a>Vedere anche

[Configurare i provider per il servizio di registrazione centralizzato in Skype for Business 2015](configure-providers.md)

[Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business 2015](configure-scenarios.md)

[Servizio di registrazione centralizzato in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
