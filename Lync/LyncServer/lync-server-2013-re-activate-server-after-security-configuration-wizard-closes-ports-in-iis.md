---
title: Riattivare il server dopo la procedura guidata per la configurazione della sicurezza chiude le porte in IIS
description: Riattivare il server dopo la procedura guidata di configurazione della sicurezza chiude le porte in IIS.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d824845a7f89c28087a7b5d180a6ed017cb47ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579052"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Riattivare il server dopo la procedura guidata per la configurazione della sicurezza chiude le porte in IIS

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Alcuni ruoli di Lync Server 2013 eseguono servizi Web su porta Internet Information Services (IIS) 4443. Se si esegue la distribuzione guidata di Lync Server, Bootstrapper.exe oppure utilizzando il cmdlet **Enable-CsComputer** viene creata un'eccezione nel firewall e viene aperta la porta. Se si esegue la configurazione guidata di sicurezza di Windows Server 2008 R2 (o altri script di protezione avanzata), la porta 4443 verrà bloccata e i client esterni non potranno contattare i servizi Web. Per riaprire la porta è possibile modificare l'eccezione del firewall direttamente o riattivare il server.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Per riattivare il server mediante la distribuzione guidata

1.  Nella pagina distribuzione guidata di Lync Server, fare clic su **Esegui** accanto a **passaggio 2: installazione o rimozione componenti di Lync Server**.

2.  Nella pagina **Installazione componenti di Lync Server** fare clic su **Avanti**.

3.  Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato, fare clic su **Fine**.
    
    <div>
    

    > [!NOTE]
    > È inoltre possibile utilizzare bootstrapper.exe o <STRONG>Enable-CsComputer</STRONG> per riattivare il server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

