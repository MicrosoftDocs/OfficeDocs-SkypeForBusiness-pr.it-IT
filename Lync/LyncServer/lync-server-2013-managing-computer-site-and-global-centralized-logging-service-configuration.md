---
title: Gestione della configurazione del servizio di registrazione centralizzata di computer, siti e globali
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Gestione della configurazione del servizio di registrazione centralizzata di computer, siti e globale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-04_

Il servizio di registrazione centralizzato può essere eseguito in un ambito che include un singolo computer, un pool di computer, in un ambito del sito, ovvero un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione, o in un ambito globale (ovvero , tutti i computer e i pool della distribuzione.

Per configurare l'ambito del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell offre altre opzioni e opzioni di configurazione aggiuntive che non sono disponibili con CLSController. exe. CLSController offre un metodo rapido e conciso per eseguire comandi, ma è limitato al set di comandi disponibili per CLSController. Windows PowerShell non si limita solo al comando disponibile per il processore di comandi di CLSController e fornisce un set di comandi più ampio e un set di opzioni più completo. Ad esempio, CLSController. exe offre una delle opzioni di ambito per-computer e-pool. Con Windows PowerShell puoi indicare i computer o i pool nella maggior parte dei comandi e quando Definisci nuovi scenari (CLSController ha un numero limitato di scenari che non sono modificabili dall'utente) puoi definire un sito o un ambito globale. Questa potente funzionalità di Windows PowerShell consente di definire uno scenario di un sito o di un ambito globale, ma limita la registrazione effettiva a un computer o a un pool.<BR>Esistono differenze sostanziali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController. Windows PowerShell offre un metodo RTF per configurare e definire scenari e per riutilizzare questi scenari in modo significativo per gli scenari di risoluzione dei problemi. Mentre CLSController offre un modo rapido ed efficiente per emettere comandi e ottenere risultati, il set di comandi per CLSController è limitato dai comandi finiti disponibili dalla riga di comando. Diversamente dai cmdlet di Windows PowerShell, CLSController non è in grado di definire nuovi scenari, gestire l'ambito a livello di sito o globale e molte altre limitazioni di un set di comandi finito che non può essere configurato in modo dinamico. Mentre CLSController offre un mezzo per l'esecuzione veloce, Windows PowerShell offre un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre ciò che è possibile con CLSController.



</div>

Un singolo ambito del computer può essere definito durante l'esecuzione di un comando [Cerca-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) e [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) usando il parametro – Computers. Il parametro – Computers accetta un elenco delimitato da virgole di nomi di dominio completi (FQDN) per il computer di destinazione.

<div>


> [!TIP]
> È anche possibile definire i pool e un elenco di pool separati da virgole per cui si vogliono eseguire i comandi di registrazione.



</div>

Il sito e gli ambiti globali sono definiti nei cmdlet **nuovo-**, **set-** e **Rimuovi-** servizio di registrazione centralizzato. Gli esempi seguenti illustrano come impostare un sito e un ambito globale.

<div>


> [!IMPORTANT]
> I comandi visualizzati possono contenere parametri e concetti trattati in altre sezioni. I comandi di esempio hanno lo scopo di dimostrare l'uso del parametro <STRONG>– Identity</STRONG> per definire l'ambito e gli altri parametri sono inclusi per la completezza e per specificare l'ambito. Per informazioni dettagliate sui cmdlet <STRONG>Set-CsClsConfiguration</STRONG> , vedere <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> nella documentazione Operations.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Get-CsClsConfiguration

Usare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o aggiornare una configurazione esistente.

Quando si esegue **Get-CsClsConfiguration**, vengono visualizzate informazioni simili allo screenshot seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono state definite configurazioni di sito:

![Output di esempio di Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Output di esempio di Get-CsClsConfiguration.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente dall'archivio locale del computer

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Get-CsClsConfiguration -LocalStore

Quando si usa il primo esempio in cui **Get-CsClsConfiguration** non specifica parametri, il comando fa riferimento all'Central Management store per i dati. Se specifichi il parametro-LocalStore, il comando fa riferimento al computer LocalStore invece che a Central Management store.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Per recuperare un elenco di scenari attualmente definiti

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Ad esempio, per recuperare gli scenari definiti nell'ambito globale:
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Il cmdlet **Get-CsClsConfiguration** Visualizza sempre gli scenari che fanno parte di una determinata configurazione dell'ambito. Nella maggior parte dei casi, tutti gli scenari non vengono visualizzati e vengono troncati. Il comando usato qui elenca tutti gli scenari e le informazioni parziali sui provider, le impostazioni e i contrassegni usati.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Ad esempio:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

Il comando indica a CLSAgent su ogni computer e pool della distribuzione di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte. I computer e i pool in tutti i siti sono interessati dal comando e impostano il valore di rollover del log di traccia configurato su 40 megabyte.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito del sito per il servizio di registrazione centralizzato tramite Windows PowerShell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Ad esempio:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Come indicato nell'esempio, la posizione predefinita dei file di log è%TEMP%\Tracing. Tuttavia, poiché in realtà è CLSAgent che sta scrivendo il file e CSLAgent viene eseguito come servizio di rete, la variabile% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

    
    </div>

Il comando indica a CLSAgent su ogni computer e pool nel sito Redmond di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte. I computer e i pool in altri siti non saranno interessati dal comando e continueranno a usare il valore di rollover del log di traccia attualmente configurato per impostazione predefinita (20 megabyte) o durante l'inizio della sessione di registrazione.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>Per creare una nuova configurazione del servizio di registrazione centralizzata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-CsClsConfiguration offre l'accesso a un numero elevato di impostazioni di configurazione facoltative. Per informazioni dettagliate sulle opzioni di configurazione, vedere <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> e <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</A>.

    
    </div>
    
    Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per i file di log, digitare:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

È consigliabile pianificare con attenzione la creazione di nuove configurazioni e come definire nuove proprietà per il servizio di registrazione centralizzata. È necessario prestare attenzione a apportare modifiche e verificare che sia possibile comprendere l'impatto sulla possibilità di registrare correttamente gli scenari di problemi. È necessario apportare modifiche alla configurazione che rafforzerà la possibilità di gestire i log in una dimensione e un periodo di rollover che consentiranno di risolvere i problemi quando si presenta.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Per rimuovere una configurazione del servizio di registrazione centralizzata esistente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt della riga di comando:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Ad esempio, per rimuovere una configurazione centralizzata del servizio di registrazione creata per aumentare il tempo di rollover del file di log, aumentare le dimensioni del file di log di rollover e impostare la posizione della cache del file di log su una condivisione di rete come segue:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Questa è la nuova configurazione creata nella procedura "per creare una nuova configurazione del servizio di registrazione centralizzata".

    
    </div>

Se si sceglie di rimuovere una configurazione a livello di sito, il sito utilizzerà le impostazioni globali.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

