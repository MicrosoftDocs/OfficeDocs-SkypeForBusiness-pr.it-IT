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
ms.openlocfilehash: ba7608b6d08fa028e86e995e0bdb646167860182
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Eseguire la migrazione della rubrica

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

In generale, la Rubrica di Lync Server 2010 viene migrata insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi dopo la migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente Lync Server 2010:

  - Impostazione della proprietà WMI **PartitionbyOU** per raggruppare le voci della Rubrica per unità organizzativa.

  - Personalizzazione delle regole di normalizzazione della Rubrica.

  - Impostazione del valore predefinito del parametro **UseNormalizationRules** su False.

**Voci della Rubrica raggruppate**

Se la proprietà WMI **PartitionbyOU** è stata impostata su True per creare una Rubrica per ogni unità organizzativa e si desidera continuare a raggruppare le voci della Rubrica, è necessario impostare l'attributo di Active Directory **msRTCSIP-GroupingId** per utenti e contatti. Per limitare l'ambito delle ricerche nella Rubrica è consigliabile raggruppare le voci della Rubrica. Per utilizzare l'attributo **msRTCSIP-GroupingId**, creare uno script per popolare l'attributo, assegnando lo stesso valore per tutti gli utenti che si desidera raggruppare. Ad esempio, assegnare un unico valore a tutti gli utenti di un'unità organizzativa.

**Regole di normalizzazione della Rubrica**

Se sono state personalizzate le regole di normalizzazione della Rubrica nell'ambiente Lync Server 2010, è necessario eseguire la migrazione delle regole personalizzate nel pool pilota. Se non è stata personalizzata alcuna regola di normalizzazione della Rubrica, non sarà necessario effettuare alcuna migrazione per il servizio Rubrica. Le regole di normalizzazione predefinite per Lync Server 2013 sono le stesse delle regole predefinite per Lync Server 2010. Eseguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.

<div>


> [!NOTE]  
> Se nell'organizzazione viene utilizzato il controllo delle chiamate remote e le regole di normalizzazione della Rubrica sono state personalizzate, prima di utilizzare il controllo delle chiamate remote è necessario eseguire la procedura descritta in questo argomento. L'esecuzione della procedura richiede l'appartenenza al gruppo RTCUniversalServerAdmins o diritti equivalenti.



</div>

**UseNormalizationRules impostato su False**

Se si imposta il valore di **UseNormalizationRules** su false in modo che gli utenti possano utilizzare i numeri di telefono come definito in servizi di dominio Active Directory senza che Lync Server 2013 applichi regole di normalizzazione, è necessario impostare i parametri **UseNormalizationRules** e **IgnoreGenericRules** su true. Eseguire la procedura descritta più avanti in questa sezione per impostare tali parametri su True.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica

1.  Individuare il file\_\_rules\_. txt del numero di telefono\_della società nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa della Rubrica nel pool pilota di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file dei componenti Web del Servizio Rubrica. Il percorso è <STRONG>$installedDriveLetter:\Programmi\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>. Questo file può essere copiato e rinominato come &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;nella directory radice della cartella condivisa della Rubrica. Ad esempio, la rubrica condivisa in <STRONG>$serverX</STRONG>,&nbsp;il percorso sarà analogo al seguente: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  Utilizzare un editor di testo, ad esempio Blocco note, per aprire\_il\_file\_\_Rules. txt del numero di telefono dell'azienda.

3.  Alcuni tipi di voci non funzioneranno correttamente in Lync Server 2013. Cercare all'interno del file i tipi di voci descritti in questo passaggio, modificarli secondo necessità e salvare le modifiche nella cartella condivisa della Rubrica all'interno del pool pilota.
    
    Le stringhe che includono spazi o caratteri di punteggiatura necessari provocano un errore nelle regole di normalizzazione poiché tali caratteri vengono rimossi dalla stringa utilizzata come input nelle regole di normalizzazione. Se sono presenti stringhe che includono spazi o caratteri di punteggiatura necessari, è necessario modificare le stringhe. La stringa seguente, ad esempio, genererà un errore nelle regola di normalizzazione:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La stringa seguente non causerebbe alcun errore della regola di normalizzazione:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Per impostare UseNormalizationRules e IgnoreGenericRules su True

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire una delle operazioni seguenti:
    
      - Se la distribuzione include solo Lync Server 2013, eseguire il seguente cmdlet a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** su true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se nella distribuzione è inclusa una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool Lync Server 2013 nella topologia:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendere che la replica dell'archivio di gestione centrale venga eseguita in tutti i pool.

4.  Modificare il file delle regole di normalizzazione del\_telefono\_,\_"\_regole di normalizzazione del numero di telefono dell'azienda. txt", per la distribuzione per cancellare il contenuto. Il file si trova nella condivisione file di ogni pool di Lync Server 2013. Se il file non è presente, creare un file vuoto denominato "\_Company number\_\_Phone\_Rules. txt".

5.  Attendere alcuni minuti per tutti i pool Front end per leggere i nuovi file.

6.  Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 nella distribuzione:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

