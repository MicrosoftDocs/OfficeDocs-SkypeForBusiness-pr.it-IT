---
title: 'Lync Server 2013: Installare gli strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1115d5848806f95d35a158f36b7689967cec5d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Installare gli strumenti di amministrazione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Questo argomento descrive come installare gli strumenti di amministrazione che è necessario usare per distribuire e gestire Lync Server 2013. Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server che esegue Lync Server 2013. È inoltre possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate. È consigliabile installare gli strumenti di amministrazione in un computer che si trova nello stesso dominio o foresta della distribuzione di Lync Server 2013 in corso, in modo da verificare che la procedura di preparazione dei servizi di dominio Active Directory sia già presente completa, che consente di usare gli strumenti di amministrazione nel computer in un secondo momento per pubblicare la topologia.

Verificare che i requisiti per l'infrastruttura, il sistema operativo, il software e i diritti di amministratore vengano riesaminati prima di installare o utilizzare gli strumenti di amministrazione di Lync Server 2013. Per informazioni dettagliate sui requisiti dell'infrastruttura, vedere [requisiti dell'infrastruttura per gli strumenti amministrativi in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Per informazioni dettagliate sui requisiti del sistema operativo e del software per installare gli strumenti di amministrazione di Lync Server 2013, vedere [supporto dei sistemi operativi per server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md)e [supporto e requisiti aggiuntivi del server in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per installare e usare gli strumenti, vedere [diritti di amministratore e autorizzazioni necessarie per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa da un'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Lync Server nella finestra di dialogo Imposta. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Lync Server 2013 verrà distribuito nell'unità.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Per installare gli strumenti di amministrazione di Lync Server 2013

1.  Accedere come amministratore locale (requisito minimo) al computer in cui si vogliono installare gli strumenti di amministrazione. Se è stato effettuato l'accesso come utente standard nei sistemi operativi Windows Vista o Windows 7 e il controllo dell'account utente è abilitato, verrà richiesto l'amministratore locale o un nome utente e una password equivalenti al dominio.

2.  Individuare il supporto di installazione nel computer e quindi fare doppio clic \\su Setup\\amd64\\Setup. exe.

3.  Se viene richiesto di installare Microsoft Visual C++ 2008 distribuibili, fare clic su **Sì**.

4.  Nella pagina **percorso di installazione di Microsoft Lync Server 2013** fare clic su **OK**. Cambiare il percorso in un'altra posizione o in un'altra unità se è necessario installare i file in un'altra posizione.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa da un'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Lync Server 2013 nella finestra di dialogo Imposta. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Lync Server 2013 verrà distribuito in questa unità.

    
    </div>

5.  Nella pagina **contratto di licenza con l'utente finale** verificare le condizioni di licenza, fare clic su **Accetto**e quindi fare clic su **OK**. Questo passaggio è obbligatorio prima di poter continuare.

6.  Nella pagina **Microsoft Lync Server 2013-distribuzione guidata** fare clic su **installa strumenti amministratore**.

7.  Dopo aver completato l'installazione, fare clic su **Esci**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Aprire gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Strumenti di amministrazione di Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

