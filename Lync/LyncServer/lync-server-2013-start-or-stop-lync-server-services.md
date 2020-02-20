---
title: 'Lync Server 2013: avviare o arrestare i servizi di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc8e398a79c8541db4a2362e5419ed98fdf7f53e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Avviare o arrestare i servizi di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

È possibile utilizzare il pannello di controllo di Lync Server per avviare o arrestare tutti i servizi di Lync Server 2013 in esecuzione in un computer specifico oppure per avviare o arrestare un servizio specifico.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Per avviare o arrestare tutti i servizi di Lync Server in un computer

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013. È possibile determinare se è stato assegnato il ruolo RBAC di CsServerAdministrator o CsAdministrator eseguendo un comando simile al seguente:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4.  Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui sono in esecuzione i servizi che si desidera avviare o arrestare e quindi fare clic su di esso.

5.  Fare clic su **Azione**.

6.  Fare clic su **Avvia tutti i servizi** o **Arresta tutti i servizi**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Per avviare o arrestare un servizio specifico

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4.  Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.

5.  Fare clic su **Proprietà**.

6.  Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio da avviare o arrestare.

7.  Fare clic su **Azione**.

8.  Fare clic su **Avvia servizio** o **Arresta servizio**.

9.  Fare clic su **Chiudi**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Impedisci sessioni per i servizi in Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Gestione della topologia di Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

