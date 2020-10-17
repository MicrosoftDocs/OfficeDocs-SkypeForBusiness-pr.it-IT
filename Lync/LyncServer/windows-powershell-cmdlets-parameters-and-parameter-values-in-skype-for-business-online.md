---
title: Cmdlet di Windows PowerShell, parametri e valori dei parametri in Skype for business online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ad45c9deecf364c273ff64e939c4379d169f3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499963"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Cmdlet di Windows PowerShell, parametri e valori dei parametri in Skype for business online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-05_

Se si ha familiarità con la finestra di comando trovata in tutte le versioni di Windows (o se si ha familiarità con MS-DOS), si avrà un vantaggio quando si tratta di imparare a usare Windows PowerShell. Nella finestra di comando, digitare un comando e premere INVIO. In risposta, il computer esegue un comando o un file eseguibile. Ad esempio, per restituire informazioni su tutti i file e le cartelle nella directory corrente, digitare questo comando al prompt dei comandi e quindi premere INVIO:

```console
dir
```

A sua scelta, vengono riportate informazioni su tutti i file e le cartelle presenti nella directory corrente:

```console
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

Questo è un esempio di un risultato quando si digita solo il nome di un comando o di un file eseguibile. Tuttavia, molti dei comandi eseguiti dall'interno della finestra di comando accettano anche *argomenti*. Gli argomenti sono altre informazioni passate al comando, che modificano il comportamento del comando. Ad esempio, se si desidera visualizzare solo i nomi dei file e delle cartelle nella directory corrente, non sono presenti altre informazioni, quali le dimensioni del file o della cartella, oppure la data e l'ora in cui è stata creata la cartella o la cartella. In questo caso, è necessario aggiungere l'argomento **/b** quando si esegue il comando dir:

```console
dir /b
```

Quando si include l'argomento **/b** , il comando **dir** riporta solo i nomi delle cartelle e dei file trovati nella directory corrente:

```console
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
```

Nel comando precedente, l'argomento **/b** è l'unica informazione necessaria per limitare i dati restituiti ai nomi di file e cartelle. Questo accade spesso con i comandi della riga di comando: la mera presenza di un argomento è tutto ciò che è necessario per modificare il comportamento del comando. (Ovvero, è necessario includere l'argomento **/b** per nascondere altre informazioni oppure escludere l'argomento **/b** per visualizzare le informazioni aggiuntive). In altri casi, tuttavia, è necessario specificare un *valore di argomento*. Un valore di argomento è costituito da informazioni aggiuntive passate all'argomento stesso. Ad esempio, l'argomento **/o** consente di specificare in che modo si desidera che il comando dir ordini i dati restituiti. Tra le altre opzioni, è possibile utilizzare il valore dell'argomento **e** per ordinare in base all'estensione di file o al valore dell'argomento **s** per ordinare in base alle dimensioni dei file. Ad esempio, questo comando consente di ordinare i dati restituiti in base all'estensione del file. Si noti che il valore dell'argomento **e** è incluso subito dopo l'argomento **/o** :

```console
dir /oe
```

Utilizzando la cartella di esempio, i dati restituiti avranno l'aspetto seguente, con i file ordinati in ordine alfabetico in base all'estensione dei file:

```console
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

In alternativa, per individuare esattamente gli elementi di cui si parla:

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Anche se Windows PowerShell utilizza una terminologia diversa, l'approccio di base all'utilizzo di Windows PowerShell equivale all'utilizzo della finestra di comando: si digitano comandi, si includono argomenti e valori di argomento necessari e quindi si preme INVIO per eseguire tali comandi. Come indicato, tuttavia, Windows PowerShell utilizza una terminologia diversa da quella utilizzata dalla shell dei comandi. In Windows PowerShell, i comandi eseguiti sono noti come *cmdlet*. A sua insaputa, gli argomenti passati a un cmdlet sono noti come *parametri*e i valori passati a un parametro sono noti come *valori dei*parametri.

Le definizioni precedenti sono piuttosto semplificate. I cmdlet sono essenzialmente mini-applicazioni che possono essere eseguite solo all'interno dell'ambiente di Windows PowerShell. Tuttavia, è anche possibile eseguire altri comandi e applicazioni dall'interno di Windows PowerShell, inclusa la maggior parte dei comandi e delle applicazioni che possono essere eseguiti da una finestra di comando. Ad esempio, se si desidera avviare il blocco note dall'interno di Windows PowerShell, è sufficiente digitare quanto segue e premere INVIO:

```console
notepad.exe
```

Quando si tratta di gestire Skype for business online, la maggior parte degli amministratori si affiderà ai cmdlet di Windows PowerShell per eseguire le attività amministrative. Al momento, esistono pochissimi altri tipi di comandi o applicazioni che possono essere utilizzati per gestire Skype for business online. In alcuni casi, è possibile utilizzare i cmdlet Skype for business online senza argomenti aggiuntivi (gli argomenti, come indicato, sono noti come parametri in Windows PowerShell). Ad esempio, il comando seguente consente di chiamare il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) senza parametri aggiuntivi. Da solo, il comando restituisce le informazioni su tutti gli utenti di Skype for business online:

```powershell
Get-CsOnlineUser
```

Tuttavia, la maggior parte dei cmdlet di Skype for business online accettano anche parametri (e valori dei parametri). Si consideri il seguente comando:

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

Questo comando è costituito da tre parti:

  - Il cmdlet **Get-CsOnlineUser**.

  - Il parametro Identity. Si noti che, in Windows PowerShell, i parametri sono sempre preattivati con un trattino (-). Questo significa che, per questo stesso cmdlet, il parametro UnassignedUser verrebbe indicato utilizzando la sintassi seguente:
    
    ```powershell
    -UnassignedUser
    ```
    
    Questo è utile per sapere, non solo perché i parametri devono essere precostituiti con un trattino, ma anche perché questo è diverso dalla finestra di comando, in cui gli argomenti sono prefaced con una barra (/):
    
    ```console
    /b
    ```

  - Il valore del parametro **kenmyer@litwareinc.com**.

Questo comando, tra l'altro, restituisce informazioni su un utente specifico, ovvero l'utente con l'identità kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Vedere anche


[Introduzione a Windows PowerShell e Skype for business online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

