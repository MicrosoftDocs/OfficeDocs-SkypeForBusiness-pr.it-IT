---
title: Combinazione dei cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in
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
ms.openlocfilehash: e7d0dd6070eb3c69b23f03e56bf542025c221b15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combinazione dei cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-05_

Quando ci si connette a Skype for business online con Windows PowerShell, saranno disponibili circa 40 cmdlet Skype for business online per l'uso. Tuttavia, non si è limitati a usare solo i cmdlet di 40 per la gestione di Skype for business online. Oltre ai cmdlet di Skype for business online, è possibile usare anche altri cmdlet di Windows PowerShell installati nel computer. Quando si installa Windows PowerShell 3,0, vengono installati anche centinaia di cmdlet di Windows PowerShell principali. I comandi possono combinare e abbinare i cmdlet di Skype for business online e gli eventuali altri cmdlet disponibili nel computer.

Anche se un corso completo in Windows PowerShell 3,0 supera l'ambito di questo articolo, ecco alcuni esempi che illustrano il motivo per cui potresti voler combinare i cmdlet. Prima di tutto, nessuno dei cmdlet di Skype for business online include un comando stampa e non è possibile trovare tale comando nella console di Windows PowerShell. Come si ottiene una stampa delle informazioni recuperate da un cmdlet? Un modo consiste nel recuperare le informazioni e quindi inviarle al cmdlet **Out-Printer** :

    Get-CsTenant | Out-Printer

Poiché non sono inclusi parametri aggiuntivi, tutte le informazioni restituite dal cmdlet **Out-Printer** verranno stampate nella stampante predefinita.

Allo stesso modo, nessuno dei cmdlet di Skype for business online include un parametro che consente di salvare i dati in un file. Ma va bene: questo comando usa il cmdlet **out-file** per salvare le informazioni restituite nel file di testo C:\\logs\\Tenants. txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Questo comando usa il cmdlet **Select-Object** per limitare i dati restituiti e visualizzati sullo schermo. In questo esempio, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) recupera le informazioni per tutti gli utenti di Skype for business online e quindi il cmdlet **Select-Object** viene usato per limitare i dati visualizzati al valore di identità dell'utente e ai relativi criteri di archiviazione:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Poiché ci saranno centinaia di cmdlet disponibili per l'uso nel computer, potresti avere difficoltà a determinare quali cmdlet sono i cmdlet Skype for business online e quali no. Per restituire un elenco dei cmdlet di Skype for business online (e solo i cmdlet di Skype for business online), devi prima determinare il nome del modulo di Windows PowerShell temporaneo che contiene tutti i cmdlet di Skype for business online. A questo scopo, Esegui questo comando dal prompt di Windows PowerShell:

    Get-Module

Le informazioni simili a quelle seguenti verranno visualizzate sullo schermo:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Il modulo con lo script ModuleType è il modulo che contiene i cmdlet di Skype for business online. Per restituire un elenco di questi cmdlet, eseguire il cmdlet **Get-Command** usando il nome del modulo di script come nome del modulo:

    Get-Command -Module tmp_5astd3uh.m5v

È possibile che si disponga di più moduli con un ModuleType uguale a script. In questo caso, puoi eseguire il comando seguente per scoprire il modulo che include il cmdlet **Get-CsTenant** :

    Get-Command Get-CsTenant

Il modulo restituito per il cmdlet **Get-CsTenant** sarà il modulo contenente tutti i cmdlet di Skype for business online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Vedere anche


[Introduzione a Windows Powershell e Skype for Business online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

