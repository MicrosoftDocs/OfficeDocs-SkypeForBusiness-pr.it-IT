---
title: Configurazione del servizio di registrazione centralizzata del computer, del sito e globale
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
ms.openlocfilehash: f8b7dfb9d96e452fc18dc5a7a962a18802388410
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505853"
---
# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Gestione del computer, del sito e della configurazione del servizio di registrazione centralizzata globale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-04_

Il servizio di registrazione centralizzato può essere eseguito in un ambito che include un singolo computer, un pool di computer, in un ambito di sito, ovvero un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione, oppure in un ambito globale (ovvero tutti i computer e i pool della distribuzione).

Per configurare l'ambito del servizio di registrazione centralizzato mediante Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno dei due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell offre altre opzioni e altre opzioni di configurazione che non sono disponibili tramite CLSController.exe. CLSController offre un metodo rapido e sintetico per eseguire i comandi, tuttavia è limitato al set di comandi disponibili per CLSController. Windows PowerShell non è limitato solo al comando disponibile per il processore dei comandi di CLSController e fornisce un insieme più ampio di comandi e un insieme più ricco di opzioni. Ad esempio, CLSController.exe offre opzioni sull'ambito, ovvero computer e pool. Con Windows PowerShell, è possibile indicare i computer o i pool nella maggior parte dei comandi e quando si definiscono nuovi scenari (CLSController dispone di un numero finito di scenari che non sono modificabili dall'utente) è possibile definire un sito o un ambito globale. Questa potente funzionalità di Windows PowerShell consente di definire uno scenario a un sito o a un ambito globale, ma limitare la registrazione effettiva a un computer o a un pool.<BR>Sono presenti differenze fondamentali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController. Windows PowerShell fornisce un metodo RTF per la configurazione e la definizione degli scenari e per riutilizzare tali scenari in modo significativo per gli scenari di risoluzione dei problemi. Mentre CLSController non offre un modo rapido ed efficiente per eseguire comandi e ottenere risultati, il set di comandi di CLSController è limitato dal numero finito di comandi disponibili dalla riga di comando. A differenza dei cmdlet di Windows PowerShell, CLSController non è in grado di definire nuovi scenari, gestire gli ambiti a livello di sito o globale e molte altre limitazioni di un set di comandi finiti che non può essere configurato dinamicamente. Mentre CLSController fornisce un mezzo per l'esecuzione rapida, Windows PowerShell fornisce un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre ciò che è possibile con CLSController.



</div>

È possibile definire un singolo ambito del computer durante l'esecuzione di un comando [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) e [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) tramite il parametro – Computers. Il parametro –Computers accetta un elenco con valori separati da virgole di nomi di dominio completi dei computer di destinazione.

<div>


> [!TIP]
> È inoltre possibile definire –Pools e un elenco di valori separati da virgole di pool in cui si desidera eseguire i comandi di registrazione.



</div>

I siti e gli ambiti globali sono definiti nei cmdlet **New-**, **set-** e **Remove-** centralizzated Logging Service. Negli esempi seguenti viene illustrato come impostare un ambito a livello di sito o globale.

<div>


> [!IMPORTANT]
> I comandi illustrati possono contenere i parametri e concetti trattati in altre sezioni. I comandi di esempio servono a illustrare l'uso del parametro <STRONG>–Identity</STRONG> per definire l'ambito e gli altri parametri sono inclusi per completezza e per specificare l'ambito. Per dettagli sui cmdlet <STRONG>Set-CsClsConfiguration</STRONG>, vedere <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> nella documentazione sulle operazioni.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt dei comandi:
    
        Get-CsClsConfiguration

Usare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o aggiornarne una esistente.

Quando si esegue **Get-CsClsConfiguration**, vengono visualizzate informazioni analoghe alla schermata seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono state definite configurazioni di sito:

![Output di esempio da Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Output di esempio da Get-CsClsConfiguration.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Per recuperare la configurazione del servizio di registrazione centralizzata corrente dall'archivio locale del computer

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt dei comandi:
    
        Get-CsClsConfiguration -LocalStore

Quando si utilizza il primo esempio in cui **Get-CsClsConfiguration** non specifica alcun parametro, il comando fa riferimento all'archivio di gestione centrale per i dati. Se si specifica il parametro – LocalStore, il comando fa riferimento al computer LocalStore anziché all'archivio di gestione centrale.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Per recuperare un elenco di scenari attualmente definiti

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt dei comandi:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Ad esempio, per recuperare gli scenari definiti nell'ambito globale:
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Il cmdlet **Get-CsClsConfiguration** visualizza sempre gli scenari che fanno parte della configurazione di un determinato ambito. Nella maggior parte dei casi, non sono visualizzati tutti gli scenari e sono presenti troncamenti. Il comando usato in questo caso elenca tutti gli scenari e informazioni parziali sui provider, le impostazioni e i flag in uso.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt dei comandi:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Esempio:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

Il comando indica al CLSAgent in ogni computer e pool della distribuzione di impostare le dimensioni del valore di rollover per il file di traccia su 40 megabyte. Il comando si applica a tutti i computer e i pool in tutti i siti e imposta il valore di rollover del log di traccia configurato su 40 megabyte.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Per aggiornare un ambito del sito per il servizio di registrazione centralizzato tramite Windows PowerShell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt dei comandi:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Esempio:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Come si nota nell'esempio, il percorso predefinito dei file di log è %TEMP%\Tracing. Tuttavia, poiché il file viene in effetti scritto da CLSAgent il quale viene eseguito con l'account Servizio di rete, la variabile %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

    
    </div>

Il comando indica al CLSAgent in ogni computer e pool del sito Redmond di impostare le dimensioni del valore di rollover per il file di traccia su 40 megabyte. I computer e i pool in altri siti non verranno modificati dal comando e continueranno a usare il valore di rollover del log di traccia definito per impostazione predefinita (20 megabyte) o durante l'avvio della sessione di registrazione.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>Per creare una nuova configurazione del servizio di registrazione centralizzata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt dei comandi:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-CsClsConfiguration offre accesso a numerose impostazioni di configurazione facoltative. Per informazioni dettagliate sulle opzioni di configurazione, vedere <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> e <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</A>.

    
    </div>
    
    Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per tali file, occorre digitare quanto segue:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

È consigliabile pianificare attentamente la creazione di nuove configurazioni e la modalità di definizione di nuove proprietà per il servizio di registrazione centralizzato. È anche opportuno prestare attenzione alle modifiche che vi si apportano accertandosi di comprenderne l'impatto sulla capacità di registrare correttamente gli scenari dei problemi. È consigliabile apportare alla configurazione modifiche in grado di migliorare la gestione dei log con dimensioni e periodi di rollover che consentano di risolvere i problemi quando si verificano.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Per rimuovere una configurazione del servizio di registrazione centralizzata esistente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Digitare quanto segue al prompt dei comandi:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Ad esempio, per rimuovere una configurazione del servizio di registrazione centralizzata creata per aumentare il tempo di rollover dei file di registro, aumentare le dimensioni del file di registro di rollover e impostare il percorso della cache dei file di registro su una condivisione di rete, come indicato di seguito:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Questa è la nuova configurazione creata nella procedura "per creare una nuova configurazione del servizio di registrazione centralizzata".

    
    </div>

Se si sceglie di rimuovere una configurazione a livello di sito, il sito userà le impostazioni globali.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

