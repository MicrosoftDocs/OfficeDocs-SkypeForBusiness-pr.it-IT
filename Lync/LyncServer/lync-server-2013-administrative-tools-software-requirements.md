---
title: 'Lync Server 2013: requisiti software per gli strumenti di amministrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d1532acc21bc788adc8e52bfd1d562509e105ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Requisiti software per gli strumenti di amministrazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

In questo argomento viene descritto il software necessario per installare e utilizzare gli strumenti di amministrazione di Lync Server 2013 oltre ai requisiti del sistema operativo.

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Per Lync Server 2013 è necessaria l'edizione a 64 bit di Microsoft .NET Framework 4,5.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Windows PowerShell 3,0 è necessario per l'esecuzione di qualsiasi componente di Microsoft Lync Server 2013. Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer versione 4.5

Lync Server 2013 utilizza la tecnologia Windows Installer per installare, disinstallare e gestire diversi ruoli del server. Windows Installer versione 4.5 è disponibile come componente ridistribuibile per il sistema operativo Windows Server. Windows Installer 4,5 viene fornito con Windows Server 2012 R2, Windows Server 2012 e Windows Server 2008 R2 e questo significa che non è necessario scaricare l'utilità per tutti i computer che eseguono Lync Server 2013. (Lync Server 2013 può essere installato solo nei computer che eseguono Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2).

Tuttavia, se si desidera installare Lync Server Management Shell o il generatore di topologie di Lync Server in una workstation amministratore, potrebbe essere necessario scaricare Windows Installer 4,5. Tale utilità viene fornita con Windows 7 e Windows 2008 R2, ma non con le versioni precedenti del sistema operativo Windows. È possibile scaricare Windows Installer 4,5 dall'area download Microsoft all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=197395>.

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Plug-in del browser Microsoft Silverlight 5

Il pannello di controllo di Lync Server 2013 è uno strumento basato sul Web e richiede l'installazione della versione più recente del plug-in per il browser Microsoft Silverlight 5. Quando si avvia il pannello di controllo di Lync Server 2013, se il software non è installato o se è installata una versione precedente, il pannello di controllo di Lync Server 2013 richiede l'installazione della versione desiderata.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Supporto del sistema operativo per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Requisiti dell'infrastruttura degli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

