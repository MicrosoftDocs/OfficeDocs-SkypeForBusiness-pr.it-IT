---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba55ec7ff54858d3324df2ab8794176a5dc7a10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

La migrazione dell'applicazione Call Park da Lync Server 2010 a Lync Server 2013 include il provisioning del pool Lync Server 2013 con qualsiasi musica personalizzata nei file di blocco caricati in Lync Server 2010, il ripristino delle impostazioni del livello di servizio e la nuova destinazione tutto il parcheggio delle chiamate orbita sul pool di Lync Server 2013. Se i file personalizzati per la musica in attesa sono stati configurati nel pool di Lync Server 2010, questi file devono essere copiati nel nuovo pool di Lync Server 2013. Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato su file musicali in blocco da Lync Server 2010 a un'altra destinazione per mantenere una copia di backup separata di tutti i file di musica in attesa personalizzati caricati per Call Park. I file personalizzati per la musica in blocco per l'applicazione Parcheggio di chiamata sono archiviati nell'archivio di file del pool. Per copiare i file audio da un archivio di file del pool di Lync Server 2010 in un archivio di file di Lync Server 2013, usare il comando **xcopy** con i parametri seguenti:

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Quando tutti i file audio personalizzati sono stati copiati nell'archivio di file di Lync Server 2013, è necessario configurare le impostazioni dell'applicazione di parcheggio per le chiamate del pool di Lync Server 2013 e gli intervalli di orbita del parcheggio di chiamata associati al pool Lync Server 2010 devono essere riassegnati a pool di Lync Server 2013.

Le impostazioni delle applicazioni di Call Park includono la soglia di timeout del prelievo, l'abilitazione o la disabilitazione della musica in attesa, i tentativi di ritiro massimo delle chiamate e la richiesta di timeout. Per eseguire il cmdlet **Set-CsCpsConfiguration** , è necessario gestire le impostazioni delle applicazioni di Call Park tramite Lync Server Management Shell. Non è possibile gestire le impostazioni delle applicazioni di Call Park tramite il pannello di controllo di Lync Server.

**Riconfigurare le impostazioni del servizio di parcheggio delle chiamate**

1.  Dal server front-end di Lync Server 2013 aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
    <div>
    

    > [!NOTE]  
    > Se le impostazioni delle applicazioni di parcheggio per le chiamate di Lync Server 2013 sono identiche alle impostazioni legacy di Lync Server 2010, è possibile ignorare l'eseguire questo passaggio. Se le impostazioni delle applicazioni di Call Park sono diverse per gli ambienti Lync Server 2013 e Lync Server 2010, usare il cmdlet seguente come modello per aggiornare tali modifiche.

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool Lync Server 2010 al pool Lync Server 2013, è possibile usare il pannello di controllo di Lync Server o Lync Server Management Shell.

**Riassegnare tutti gli intervalli di orbit del parcheggio di chiamata tramite il pannello di controllo di Lync Server**

1.  Aprire il pannello di controllo di Lync Server.

2.  Nel riquadro sinistro selezionare **funzionalità vocali**.

3.  Selezionare la scheda **parcheggio chiamate** .

4.  Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool di Lync Server 2010, modificare il **nome di dominio completo dell'impostazione del server di destinazione** e selezionare il pool di lync Server 2013 che elaborerà le richieste del parcheggio di chiamata.

5.  Selezionare **conferma** per salvare le modifiche.

**Riassegnare tutti gli intervalli di orbit del parcheggio di chiamata tramite Lync Server Management Shell**

1.  Aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsCallParkOrbit
    
    Questo cmdlet elenca tutti gli intervalli di orbit del parcheggio delle chiamate nella distribuzione. Tutte le orbite del parcheggio delle chiamate con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool di Lync Server 2010 devono essere riassegnati.
    
    Per riassegnare gli intervalli di Orbit Park di chiamata di Lync Server 2010 al pool Lync Server 2013, nella riga di comando digitare quanto segue:
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

Dopo aver riassegnato tutti gli intervalli di orbit del parcheggio di chiamata al pool di Lync Server 2013, il processo di migrazione per l'applicazione di parcheggio di chiamata verrà completato e il pool di Lync Server 2013 gestirà tutte le richieste future di Call Park.

</div>

<span> </span>

</div>

</div>

</div>

