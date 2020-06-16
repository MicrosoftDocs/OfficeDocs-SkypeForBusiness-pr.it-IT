---
title: Installare il pacchetto di compatibilità con le versioni precedenti di WMI
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35be17aa08cf26f93a9d4002b23dacdfb35c5143
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Installare il pacchetto di compatibilità con le versioni precedenti di WMI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Se si prova ad eseguire l'unione guidata del Generatore di topologie senza installare il pacchetto di compatibilità con le versioni precedenti di WMI, verrà visualizzato l'errore seguente:

![Messaggio di errore WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Messaggio di errore WMI")

Se si prova ad eseguire il cmdlet **Merge-CsLegacytopology** senza installare il pacchetto di compatibilità con le versioni precedenti di WMI, verrà visualizzato l'errore seguente:

![Errore del provider WMI di Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Errore del provider WMI di Windows PowerShell")

Per installare il pacchetto di compatibilità con le versioni precedenti di WMI

1.  Dal supporto di installazione, passare a \\ installazione \\ amd64 \\ \\OCSWMIBC.MSI.

2.  Installare OCSWMIBC.MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi può essere installato in qualsiasi computer del dominio in cui sono installati i componenti di base di Lync Server 2013 e Lync Server 2013 Management Shell e ha accesso alla topologia di Office Communications Server 2007 R2 (provider WMI per servizi di dominio Active Directory e SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

