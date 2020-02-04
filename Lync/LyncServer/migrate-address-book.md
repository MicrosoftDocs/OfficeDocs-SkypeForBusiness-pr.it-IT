---
title: Eseguire la migrazione della rubrica
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Eseguire la migrazione della rubrica

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

In generale, la Rubrica di Lync Server 2010 viene migrata insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi di post-migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente di Lync Server 2010:

  - Imposta la proprietà WMI **PartitionByOU** per raggruppare le voci della Rubrica per unità organizzativa.

  - Personalizzare le regole di normalizzazione della Rubrica.

  - Ha modificato il valore predefinito per il parametro **UseNormalizationRules** su false.

**Voci di Rubrica raggruppate**

Se si imposta la proprietà WMI **PartitionByOU** su true per creare rubriche per ogni ou, è necessario impostare l'attributo **msRTCSIP-GroupingId** Active Directory in utenti e contatti se si vuole continuare a raggruppare le voci della Rubrica. Potresti voler raggruppare le voci della Rubrica per limitare l'ambito delle ricerche di Rubrica. Per usare l'attributo **msRTCSIP-GroupingId** , scrivere uno script per popolare l'attributo, assegnando lo stesso valore per tutti gli utenti che si desidera raggruppare. Ad esempio, assegna un singolo valore per tutti gli utenti di un'unità organizzativa.

**Regole di normalizzazione per la Rubrica**

Se sono state personalizzate regole di normalizzazione della Rubrica nell'ambiente di Lync Server 2010, è necessario eseguire la migrazione delle regole personalizzate al pool di piloti. Se non sono state personalizzate le regole di normalizzazione della Rubrica, non è necessario eseguire la migrazione per il servizio Rubrica. Le regole di normalizzazione predefinite per Lync Server 2013 corrispondono alle regole predefinite per Lync Server 2010. Seguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.

<div>


> [!NOTE]  
> Se l'organizzazione usa il controllo delle chiamate remote e le regole di normalizzazione della rubrica personalizzate, è necessario eseguire la procedura descritta in questo argomento prima di poter usare il controllo delle chiamate remote. La procedura richiede l'appartenenza al gruppo RTCUniversalServerAdmins o i diritti equivalenti.



</div>

**UseNormalizationRules impostato su false**

Se si imposta il valore di **UseNormalizationRules** su false in modo che gli utenti possano usare i numeri di telefono come definiti in servizi di dominio Active Directory senza che Lync Server 2013 applichi regole di normalizzazione, è necessario impostare i parametri **UseNormalizationRules** e **IgnoreGenericRules** su true. Seguire la procedura più avanti in questa sezione per impostare questi parametri su true.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica

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

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Per impostare UseNormalizationRules e IgnoreGenericRules su true

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Esegui una delle operazioni seguenti:
    
      - Se la distribuzione include solo Lync Server 2013, eseguire il cmdlet seguente a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** su true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se la distribuzione include una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool di Lync Server 2013 nella topologia:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendere che la replica di Central Management store si verifichi in tutti i pool.

4.  Modificare il file delle regole di normalizzazione del\_telefono\_,\_"\_regole di normalizzazione del numero di telefono aziendale", per la distribuzione per cancellare il contenuto. Il file si trova nella condivisione file di ogni pool di Lync Server 2013. Se il file non è presente, creare un file vuoto denominato "regole di\_\_normalizzazione\_\_del numero di telefono aziendale. txt".

5.  Attendere diversi minuti per tutti i pool di front-end per leggere i nuovi file.

6.  Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 della distribuzione:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

