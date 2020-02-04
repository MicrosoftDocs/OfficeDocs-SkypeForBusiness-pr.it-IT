---
title: Cmdlet, parametri e valori di parametro di Windows PowerShell in Skype for business online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d607b4a7e7cf87a08082a820f3b3a216621de3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Cmdlet, parametri e valori di parametro di Windows PowerShell in Skype for business online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-05_

Se si ha familiarità con la finestra di comando trovata in tutte le versioni di Windows (o se si ha familiarità con MS-DOS), si avrà un vantaggio quando si impara a usare Windows PowerShell. Nella finestra di comando digitare un comando e premere INVIO. In risposta, il computer esegue un comando o un file eseguibile. Ad esempio, per restituire informazioni su tutti i file e le cartelle nella directory corrente, digitare questo comando al prompt dei comandi e quindi premere INVIO:

    dir

A sua volta, vengono restituite informazioni su tutti i file e le cartelle nella directory corrente:

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Questo è un esempio di risultato quando si digita solo il nome di un comando o di un file eseguibile. Tuttavia, molti dei comandi eseguiti dall'interno della finestra di comando accettano anche *argomenti*. Gli argomenti sono altre parti di informazioni passate al comando, che modificano il comportamento del comando. Ad esempio, se si vogliono solo visualizzare i nomi dei file e delle cartelle nella directory corrente, non sono disponibili altre informazioni, come le dimensioni del file o della cartella, o la data e l'ora in cui è stata creata la cartella o la cartella. In questo caso, quando si eseguirà il comando dir si aggiungerà l'argomento **/b** :

    dir /b

Quando Includi l'argomento **/b** , il comando **dir** riporta solo i nomi delle cartelle e dei file trovati nella directory corrente:

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

Nel comando precedente l'argomento **/b** rappresenta le uniche informazioni necessarie per limitare i dati restituiti ai nomi di file e cartelle. Questo avviene spesso con i comandi della riga di comando: la mera presenza di un argomento è tutto ciò che serve per modificare il comportamento del comando. Ossia includere l'argomento **/b** per nascondere altre informazioni oppure escludere l'argomento **/b** per visualizzare le informazioni aggiuntive. In altri casi, tuttavia, devi specificare un *valore di argomento*. Un valore di argomento contiene informazioni aggiuntive passate all'argomento stesso. Ad esempio, l'argomento **/o** consente di specificare come si vuole ordinare il comando dir per l'ordinamento dei dati restituiti. Tra le altre opzioni, puoi usare il valore dell'argomento **e** per ordinare per estensione di file o per il valore dell'argomento **s** per ordinare in base alle dimensioni del file. Ad esempio, questo comando Ordina i dati restituiti per estensione di file. Nota in che modo il valore dell'argomento **e** viene incluso subito dopo l'argomento **/o** :

    dir /oe

Usando la cartella di esempio, i dati restituiti avranno un aspetto simile al seguente, con i file ordinati alfabeticamente per estensione di file:

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

In alternativa, per individuare esattamente le informazioni di cui si sta parlando:

configurazione. **documento**  
RHDSetup. **exe**  
pldok. **log**

Anche se Windows PowerShell usa terminologia diversa, l'approccio di base per l'uso di Windows PowerShell è lo stesso che usare la finestra di comando: si digita comandi, si includono gli argomenti e i valori di argomento necessari e quindi si preme INVIO per eseguire questi comandi. Come notato, tuttavia, Windows PowerShell usa una terminologia diversa rispetto alla shell dei comandi. In Windows PowerShell i comandi eseguiti sono noti come *cmdlet*. A sua volta, gli argomenti passati a un cmdlet sono noti come *parametri*e i valori passati a un parametro sono noti come *valori di parametro*.

Le definizioni precedenti sono in qualche modo semplificate. I cmdlet sono essenzialmente mini-applicazioni che possono essere eseguite solo all'interno dell'ambiente Windows PowerShell. Tuttavia, puoi anche eseguire altri comandi e applicazioni da Windows PowerShell, incluso la maggior parte dei comandi e delle applicazioni che possono essere eseguiti da una finestra di comando. Se ad esempio si vuole avviare il blocco note da Windows PowerShell, è sufficiente digitare il codice seguente e premere INVIO:

    notepad.exe

Quando si tratta di gestire Skype for business online, la maggior parte degli amministratori si affiderà ai cmdlet di Windows PowerShell per eseguire attività amministrative. Al momento, esistono pochissimi altri tipi di comandi o applicazioni che possono essere usati per gestire Skype for business online. Talvolta i cmdlet di Skype for business online possono essere usati senza argomenti aggiuntivi (, come indicato, gli argomenti sono noti come parametri in Windows PowerShell). Il comando seguente, ad esempio, chiama il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) senza parametri aggiuntivi. Di per sé, il comando restituisce informazioni su tutti gli utenti di Skype for business online:

    Get-CsOnlineUser

Tuttavia, la maggior parte dei cmdlet di Skype for business online accetta anche i parametri e i valori dei parametri. Prendere in considerazione il comando seguente:

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

Questo comando è costituito da tre parti:

  - Il cmdlet **Get-CsOnlineUser**.

  - Il parametro Identity. Tieni presente che in Windows PowerShell i parametri sono sempre prenotati con un trattino (-). Questo significa che, per questo stesso cmdlet, il parametro UnassignedUser verrebbe indicato usando la sintassi seguente:
    
        -UnassignedUser
    
    Questo è utile per saperlo, non solo perché i parametri devono essere prenotati con un trattino, ma anche perché si differenzia dalla finestra di comando, in cui gli argomenti sono preattivati con una barra (/):
    
    ```console 
    /b
    ```

  - Il valore del parametro **kenmyer@litwareinc.com**.

Questo comando, incidentalmente, restituisce informazioni su un utente specifico: l'utente con l'identità, kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Vedere anche


[Introduzione a Windows Powershell e Skype for Business online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

