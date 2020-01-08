---
title: Eseguire la migrazione della rubrica
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dff13c31ecf203d6e6e4b60c22a3792475e403f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Eseguire la migrazione della rubrica

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

**Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica**

1.  Individuare il file\_\_rules\_. txt del numero di telefono\_aziendale nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa rubrica nel pool di piloti di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file del componente Web ABS. Il percorso è <STRONG>$installedDriveLetter: \Programmi\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>. Questo file può essere copiato e rinominato come &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;nella directory radice della cartella condivisa della Rubrica. Ad esempio, la rubrica condivisa in <STRONG>$serverX</STRONG>,&nbsp;il percorso sarà simile a: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  Usare un editor di testo, ad esempio Blocco note, per aprire\_il\_file\_regole\_di normalizzazione del numero di telefono aziendale. txt.

3.  Alcuni tipi di voci non funzionano correttamente in Lync Server 2013. Esaminare il file per i tipi di voci descritti in questo passaggio, modificarli come necessario e salvare le modifiche apportate alla cartella condivisa Rubrica nel pool di piloti.
    
    Le stringhe che includono gli spazi vuoti o la punteggiatura necessari causano l'errore delle regole di normalizzazione perché questi caratteri vengono rimossi dalla stringa che viene immessa nelle regole di normalizzazione. Se sono presenti stringhe che includono spazi vuoti o segni di punteggiatura necessari, è necessario modificare le stringhe. Ad esempio, la stringa seguente causerà l'errore della regola di normalizzazione:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La stringa seguente non provocherebbe l'errore della regola di normalizzazione:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

