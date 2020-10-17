---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63b91c6a742310d14031bdadc28cbc6ca57e115
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503563"
---
# <a name="migrate-call-park-application-settings"></a>Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

La migrazione dell'applicazione Parcheggio di chiamata da Lync Server 2010 a Lync Server 2013 include il provisioning del pool di Lync Server 2013 con qualsiasi file di musica di attesa personalizzato che è stato caricato in Lync Server 2010, il ripristino delle impostazioni del livello di servizio e la reimpostazione di tutte le orbite del parcheggio di chiamata nel pool Lync Server 2013. Se nel pool di Lync Server 2010 sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool di Lync Server 2013. Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato file di musica di attesa da Lync Server 2010 a un'altra destinazione per mantenere una copia di backup separata di qualsiasi file di musica di attesa personalizzato che sono stati caricati per il parcheggio di chiamata. I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool. Per copiare i file audio da un archivio file del pool di Lync Server 2010 in un archivio file di Lync Server 2013, utilizzare il comando **xcopy** con i seguenti parametri:

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Quando tutti i file audio personalizzati sono stati copiati nell'archivio file di Lync Server 2013, è necessario configurare le impostazioni dell'applicazione Parcheggio di chiamata del pool di Lync Server 2013 e gli intervalli di orbit del parcheggio di chiamata associati al pool di Lync Server 2010 devono essere riassegnati al pool Lync Server 2013.

Le impostazioni di Parcheggio chiamata includono la soglia di timeout di pick-up, l'abilitazione o la disabilitazione della musica di attesa, il numero massimo di tentativi di pick-up chiamata e la richiesta di timeout. È necessario gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando Lync Server Management Shell per eseguire il cmdlet **Set-CsCpsConfiguration** . Non è possibile gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando il pannello di controllo di Lync Server.

**Riconfigurare le impostazioni del servizio Parcheggio chiamata**

1.  Dal front end server Lync Server 2013 aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
    <div>
    

    > [!NOTE]  
    > Se le impostazioni dell'applicazione Parcheggio di chiamata di Lync Server 2013 sono identiche alle impostazioni legacy di Lync Server 2010, è possibile ignorare l'esecuzione di questo passaggio. Se le impostazioni dell'applicazione Parcheggio di chiamata sono diverse per gli ambienti Lync Server 2013 e Lync Server 2010, utilizzare il cmdlet riportato di seguito come modello per aggiornare tali modifiche.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" " <LS2010 CPS value> -MaxCallPickupAttempts" " <LS2010 CPS pickup attempts> -OnTimeoutURI" <LS2010 CPS timeout URI> " ```

Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool di Lync Server 2010 al pool Lync Server 2013, è possibile utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell.

**Riassegnare tutti gli intervalli di codici orbit di Parcheggio chiamata utilizzando il Pannello di controllo di Lync Server**

1.  Aprire il Pannello di controllo di Lync Server.

2.  Nel riquadro sinistro, selezionare **Funzionalità vocali**.

3.  Selezionare la scheda **Parcheggio chiamata**.

4.  Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool di Lync Server 2010, modificare l'impostazione **FQDN del server di destinazione** e selezionare il pool di lync Server 2013 che elaborerà le richieste del parcheggio di chiamata.

5.  Selezionare **Commit** per salvare le modifiche.

**Riassegnare tutti gli intervalli di codici orbit di Parcheggio chiamata utilizzando Lync Server Management Shell**

1.  Aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    Questo cmdlet elenca tutti gli intervalli di codici orbit di Parcheggio chiamata nella distribuzione. Tutte le orbite del parcheggio di chiamata con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool di Lync Server 2010 devono essere riassegnate.
    
    Per riassegnare gli intervalli di orbit del parcheggio di chiamata di Lync Server 2010 al pool di Lync Server 2013, nella riga di comando digitare quanto segue:
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

Dopo aver riassegnato tutti gli intervalli di orbit del parcheggio di chiamata al pool di Lync Server 2013, il processo di migrazione per l'applicazione Parcheggio di chiamata verrà completato e il pool di Lync Server 2013 gestirà tutte le richieste future del parcheggio di chiamata.

</div>

<span> </span>

</div>

</div>

</div>

