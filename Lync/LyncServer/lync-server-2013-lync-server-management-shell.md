---
title: 'Lync Server 2013: Lync Server Management Shell'
description: 'Lync Server 2013: Lync Server Management Shell.'
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
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543182"
---
# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-09-20_

<div>


> [!NOTE]  
> La Guida di riferimento ai cmdlet di Skype for business è stata spostata in docs.microsoft.com. Facendo clic sui collegamenti riportati di seguito, è possibile utilizzare la nuova pagina di docs.microsoft.com. Il contenuto è ora Open Source e disponibile per i contributi comunitari tramite GitHub. Interessati a contribuire? Consultare il file README nel repo qui: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 è stata introdotta una serie di funzionalità nuove e migliorate rispetto a quelle disponibili in Microsoft Office Communications Server 2007 R2. Uno di questi miglioramenti riguarda la modalità di gestione dell'implementazione. Ad esempio, è presente una nuova interfaccia utente, denominata Pannello di controllo di Lync Server, che rappresenta un grande cambiamento rispetto a quello utilizzato per la maggior parte delle persone con Microsoft Management Console. L'altro importante miglioramento della gestibilità è l'inclusione di Windows PowerShell.

Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando. Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Windows PowerShell è stato introdotto per la prima volta come versione scaricabile per il sistema operativo Windows alla fine del 2006 ed è stato incorporato come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007. Da quel momento ha continuato a crescere ed è stato incorporato nella maggior parte dei prodotti Microsoft Server, il più recente dei quali è Microsoft Lync Server 2013. In Lync Server 2010 sono stati introdotti quasi 550 cmdlet specifici per il prodotto che è possibile utilizzare per gestire tutti gli aspetti della distribuzione.

Nelle sezioni seguenti è disponibile un elenco dei cmdlet e relative descrizioni. Queste informazioni sono disponibili anche direttamente dalla riga di comando. Basta digitare quanto segue al prompt dei comandi di Lync Server Management Shell:

    Get-Help <cmdlet name> -Full

Per recuperare le informazioni della Guida dal prompt dei comandi nel cmdlet **New-CsVoicePolicy**, ad esempio, digitare il comando seguente:

    Get-Help New-CsVoicePolicy -Full

Aspetti da sapere su Windows PowerShell in Lync Server 2013:

  - Per eseguire i cmdlet di Lync Server, aprire Lync Server Management Shell.
    
    <div>
    

    > [!WARNING]  
    > Se si apre una finestra di Windows PowerShell anziché Lync Server Management Shell, per impostazione predefinita non sarà possibile eseguire i cmdlet di Lync Server. Per eseguire i cmdlet di Lync Server da Windows PowerShell, digitare il comando seguente al prompt dei comandi di Windows PowerShell:<BR>Import-Module Lync

    
    </div>

  - Lync Server Management Shell viene installato automaticamente in ogni server Lync Server Enterprise Edition Front End Server o Standard Edition.

  - Le informazioni nuove e aggiornate, gli script di esempio e la guida per iniziare e saperne di più sui cmdlet di Windows PowerShell e Microsoft Lync Server 2013 sono disponibili nel Blog di Windows PowerShell per Lync Server [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) .

</div>

<span> </span>

</div>

</div>

</div>

