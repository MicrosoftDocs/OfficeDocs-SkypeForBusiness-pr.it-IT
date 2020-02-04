---
title: 'Lync Server 2013: Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-09-20_

<div>


> [!NOTE]  
> Il riferimento ai cmdlet di Skype for business è stato spostato in docs.microsoft.com. Facendo clic sui collegamenti seguenti si accede alla nuova pagina di docs.microsoft.com. Il contenuto è ora aperto e disponibile per i contributi della community tramite GitHub. Vuoi contribuire? Vedere il file README nel repository qui:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 ha introdotto una vasta gamma di funzionalità nuove e migliorate rispetto a quelle disponibili in Microsoft Office Communications Server 2007 R2. Un miglioramento è il modo in cui Gestisci l'implementazione. Ad esempio, c'è una nuova interfaccia utente, chiamata il pannello di controllo di Lync Server, che rappresenta un grande cambiamento rispetto a quello usato dalla maggior parte delle persone con Microsoft Management Console. L'altro importante miglioramento della gestibilità è l'inclusione di Windows PowerShell.

Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando. Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Windows PowerShell è stato introdotto per la prima volta come versione scaricabile per il sistema operativo Windows in ritardo in 2006 ed è stato incorporato come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007. Da questo punto ha continuato a crescere ed è stato incorporato nella maggior parte dei prodotti Microsoft Server, il più recente dei quali è Microsoft Lync Server 2013. Lync Server 2010 ha introdotto vicino a 550 cmdlet specifici del prodotto che è possibile usare per gestire ogni aspetto della distribuzione.

Nelle sezioni seguenti è disponibile un elenco dei cmdlet e relative descrizioni. Queste informazioni sono disponibili anche direttamente dalla riga di comando. Digitare semplicemente quanto segue al prompt dei comandi di Lync Server Management Shell:

    Get-Help <cmdlet name> -Full

Per recuperare le informazioni della Guida dal prompt dei comandi nel cmdlet **New-CsVoicePolicy**, ad esempio, digitare il comando seguente:

    Get-Help New-CsVoicePolicy -Full

Informazioni da sapere su Windows PowerShell in Lync Server 2013:

  - Per eseguire i cmdlet di Lync Server, aprire Lync Server Management Shell.
    
    <div>
    

    > [!WARNING]  
    > Se si apre una finestra di Windows PowerShell anziché Lync Server Management Shell, per impostazione predefinita non sarà possibile eseguire i cmdlet di Lync Server. Per eseguire i cmdlet di Lync Server da Windows PowerShell, digitare quanto segue al prompt dei comandi di Windows PowerShell:<BR>Import-Module Lync

    
    </div>

  - Lync Server Management Shell viene installato automaticamente in tutti i server front-end di Lync Server Enterprise Edition o in un server Standard Edition.

  - Le informazioni nuove e aggiornate, gli script di esempio e la guida per l'introduzione e per saperne di più sui cmdlet di Windows PowerShell e Microsoft Lync Server 2013 sono disponibili nel Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)di Lync Server di Windows PowerShell.

</div>

<span> </span>

</div>

</div>

</div>

