---
title: Eseguire LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325a3dab058132dfe6bbf8558ebe771450f36ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>Eseguire LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

Prima di eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool. exe), è necessario creare gli utenti, i contatti e gli scenari. Per informazioni dettagliate sull'utilizzo degli strumenti per eseguire queste operazioni, vedere [creare utenti e contatti](create-users-and-contacts.md) e [configurare il profilo utente](configure-user-profile.md). L'esecuzione di questi strumenti genera anche un file in cui verrà eseguito LyncPerfTool. exe come parte di un file batch con i parametri necessari inclusi.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Esecuzione dello strumento di stress e prestazioni di Lync Server 2013

Lo strumento UserProfileGenerator. exe crea un file batch che consente di eseguire LyncPerfTool. exe registrando i contatori delle prestazioni di LyncPerfTool e caricando il file di configurazione XML. Il file batch esegue un'istanza di LyncPerfTool. exe per ogni file di configurazione. Per eseguire il file batch, eseguire le operazioni seguenti:

1.  Copiare la cartella contenente le cartelle e i file di configurazione nella directory che contiene LyncStressTool. exe su ogni computer client. Ad esempio, se i file di configurazione sono stati generati nella cartella denominata 1,28\_13.16.16, copiare tale cartella nella cartella che contiene LyncPerfTool. exe in ogni client.

2.  Passare alla cartella client numerata in modo appropriato ed eseguire lo script batch di RunClient. È sufficiente fare doppio clic sul file batch in Esplora risorse e verranno eseguiti tutti i file di configurazione per il numero di client. È inoltre possibile eseguire lo script dalla cartella client appropriata utilizzando la sintassi seguente:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Per eseguire LyncPerfTool. exe direttamente, aprire una finestra del prompt dei comandi e quindi digitare il comando seguente dalla riga di comando (quando si esegue questa operazione per la prima volta, assicurarsi di registrare i contatori delle prestazioni regsvr32/i/n/s LyncPerfToolPerf. dll, come illustrato nella nota più avanti in questo argomento): LyncPerfTool\<. exe/file: configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Per visualizzare i valori nel file di configurazione, includere il parametro/displayfile nel comando precedente, come riportato di seguito:
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Per terminare il processo, premere CTRL + C.

<div>


> [!NOTE]  
> Prima di eseguire direttamente LyncPerfTool, è necessario registrare i contatori delle prestazioni. Immettere il comando seguente per registrare i contatori delle prestazioni:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Ogni istanza di LyncPerfTool. exe avviata inizierà immediatamente la firma degli utenti, in genere a una velocità di un utente al secondo. La frequenza di accesso dell'utente di picco per il pool è pari a circa 12 al secondo. Questo significa che non è necessario avviare più di 12 istanze di LyncPerfTool contemporaneamente, mentre gli utenti continuano a eseguire l'accesso. 1000 gli utenti impiegano circa 20 minuti per accedere completamente, a una al secondo.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare utenti e contatti](create-users-and-contacts.md)  
[Configurare il profilo utente](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

