---
title: Riattivare il server dopo la chiusura delle porte in IIS da parte della Configurazione guidata impostazioni di sicurezza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Riattivare il server dopo la chiusura delle porte in IIS da parte della Configurazione guidata impostazioni di sicurezza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Alcuni ruoli di Lync Server 2013 eseguono servizi Web in una porta Internet Information Services (IIS) 4443. Eseguendo la distribuzione guidata di Lync Server, Bootstrapper. exe oppure usando il cmdlet **Enable-CsComputer** viene creata un'eccezione nel firewall e viene aperta la porta. Se si esegue la configurazione guidata di Windows Server 2008 R2 (o altri script di protezione avanzata), la porta 4443 verrà bloccata e i client esterni non saranno in grado di contattare i servizi Web. Per riaprire la porta, è possibile modificare l'eccezione del firewall direttamente o riattivare il server.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Per riattivare il server tramite la distribuzione guidata

1.  Nella pagina distribuzione guidata di Lync Server fare clic su **Esegui** accanto al **passaggio 2: configurare o rimuovere i componenti di Lync Server**.

2.  Nella pagina **Setup Lync Server Components** fare clic su **Avanti**.

3.  Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come completato, fare clic su **fine**.
    
    <div>
    

    > [!NOTE]
    > È anche possibile usare Bootstrapper. exe o <STRONG>Enable-CsComputer</STRONG> per riattivare il server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

