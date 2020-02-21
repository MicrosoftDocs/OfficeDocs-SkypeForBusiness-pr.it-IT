---
title: 'Lync Server 2013: installare gli strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8805c82c26eb97da8537b33cda8346f5942de1c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Installare gli strumenti di amministrazione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

In questo argomento viene descritto come installare gli strumenti di amministrazione necessari per la distribuzione e la gestione di Lync Server 2013. Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server che esegue Lync Server 2013. Inoltre, è possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate. È consigliabile installare gli strumenti di amministrazione in un computer che si trova nello stesso dominio o foresta della distribuzione di Lync Server 2013 che si sta creando, perché in questo modo si verifica che i passaggi di preparazione di Active Directory Domain Services siano già disponibili completata, che consente di utilizzare gli strumenti di amministrazione di quel computer in un secondo momento per pubblicare la topologia.

Prima di installare o utilizzare gli strumenti di amministrazione di Lync Server 2013, verificare che vengano esaminati i requisiti relativi ai diritti dell'infrastruttura, del sistema operativo, del software e di amministratore. Per informazioni dettagliate sui requisiti dell'infrastruttura, vedere [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Per informazioni dettagliate sui requisiti software e del sistema operativo per l'installazione degli strumenti di amministrazione di Lync Server 2013, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per l'installazione e l'utilizzo degli strumenti, vedere [autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Se l'organizzazione richiede che Internet Information Services (IIS) e tutti i servizi Web si trovino in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione per i file di Lync Server nella finestra di dialogo del programma di installazione. Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, anche gli altri file di Lync Server 2013 verranno distribuiti nell'unità.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Per installare gli strumenti di amministrazione di Lync Server 2013

1.  Eseguire l'accesso come amministratore locale (requisito minimo) al computer in cui si desidera installare gli strumenti di amministrazione. Se si è connessi come utente standard al sistema operativo Windows Vista o Windows 7 e il controllo dell'account utente è abilitato, verrà richiesto di specificare nome utente e password di amministratore locale o di un account di dominio equivalente.

2.  Individuare il supporto di installazione nel computer in uso e quindi fare doppio \\clic\\su\\Setup amd64 Setup. exe.

3.  Se viene chiesto di installare Microsoft Visual C++ 2008 Distributable, fare clic su **Sì**.

4.  Nella pagina **percorso di installazione di Microsoft Lync Server 2013** fare clic su **OK**. Sostituire il percorso indicato con un altro percorso o un'altra unità se è necessario installare i file in una diversa posizione.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Lync Server 2013 nella finestra di dialogo Imposta. Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, anche gli altri file di Lync Server 2013 verranno distribuiti nell'unità.

    
    </div>

5.  Nella pagina **Contratto di licenza con l'utente finale** leggere le condizioni di licenza, fare clic su **Accetto** e quindi su **OK**. Questo passaggio è obbligatorio per poter continuare.

6.  Nella pagina **Microsoft Lync Server 2013-Deployment Wizard** fare clic su **installa strumenti di amministrazione**.

7.  Al termine dell'installazione fare clic su **Esci**.

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

