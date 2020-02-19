---
title: Combinazione di cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d8cec58ab57d060adb1903feb4b5b3e53e7c1c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combinazione di cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-05_

Quando ci si connette a Skype for business online utilizzando Windows PowerShell, circa 40 cmdlet di Skype for business online saranno disponibili per l'utilizzo. Tuttavia, non è possibile utilizzare solo i cmdlet di 40 per la gestione di Skype for business online. Oltre ai cmdlet di Skype for business online, è possibile utilizzare anche tutti gli altri cmdlet di Windows PowerShell installati nel computer. Quando si installa Windows PowerShell 3,0, vengono installati anche centinaia di cmdlet di Windows PowerShell di base. I comandi possono combinare i cmdlet Skype for business online e tutti gli altri cmdlet disponibili nel computer.

Anche se un corso completo in Windows PowerShell 3,0 supera l'ambito di questo articolo, ecco alcuni esempi che mostrano perché si potrebbe voler combinare i cmdlet. In primo luogo, nessuno dei cmdlet di Skype for business online include un comando di stampa e non è possibile trovare tale comando nella console di Windows PowerShell. In che modo è possibile ottenere una stampa delle informazioni recuperate da un cmdlet? Un modo consiste nel recuperare le informazioni e quindi inviare tali informazioni al cmdlet **Out-Printer** :

    Get-CsTenant | Out-Printer

Poiché non sono inclusi parametri aggiuntivi, tutte le informazioni restituite dal cmdlet **Out-Printer** verranno stampate sulla stampante predefinita.

Analogamente, nessuno dei cmdlet Skype for business online include un parametro che consente di salvare i dati in un file. Ma va bene: questo comando utilizza il cmdlet **out-file** per salvare le informazioni restituite nel file di testo C:\\logs\\Tenants. txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Questo comando utilizza il cmdlet **Select-Object** per limitare i dati restituiti e visualizzati sullo schermo. In questo esempio, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) recupera le informazioni per tutti gli utenti di Skype for business online e quindi il cmdlet **Select-Object** viene utilizzato per limitare i dati visualizzati al valore di identità dell'utente e ai criteri di archiviazione seguenti:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Poiché saranno disponibili centinaia di cmdlet per l'utilizzo nel computer, potrebbe essere difficile determinare quali cmdlet sono cmdlet di Skype for business online e quali no. Per restituire un elenco dei cmdlet di Skype for business online (e solo i cmdlet di Skype for business online), è necessario innanzitutto determinare il nome del modulo di Windows PowerShell temporaneo che contiene tutti i cmdlet di Skype for business online. A tale scopo, eseguire il seguente comando dal prompt di Windows PowerShell:

    Get-Module

Sullo schermo vengono visualizzate informazioni analoghe a quelle riportate di seguito:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Il modulo con lo script ModuleType è il modulo che contiene i cmdlet Skype for business online. Per restituire un elenco di tali cmdlet, eseguire il cmdlet **Get-Command** utilizzando il nome del modulo di script come nome del modulo:

    Get-Command -Module tmp_5astd3uh.m5v

È possibile che si disponga di più moduli con un ModuleType uguale a script. In tal caso, è possibile eseguire il comando riportato di seguito per individuare il modulo che include il cmdlet **Get-CsTenant** :

    Get-Command Get-CsTenant

Il modulo restituito per il cmdlet **Get-CsTenant** sarà il modulo contenente tutti i cmdlet di Skype for business online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Vedere anche


[Introduzione a Windows PowerShell e Skype for business online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

