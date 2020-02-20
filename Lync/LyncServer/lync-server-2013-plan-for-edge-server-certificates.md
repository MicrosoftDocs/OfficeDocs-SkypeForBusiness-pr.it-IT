---
title: 'Lync Server 2013: pianificare i certificati del server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e2cf257b3bc6a17377ca5649307e4b2ba7bb5c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Pianificare i certificati dei server perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-05_

La creazione di certificati per Edge è semplificata in Lync Server 2013.

**Diagramma di flusso dei certificati per i server perimetrali**

![a5fc20db-7ced-4364-B577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-B577-6a709a8367cd")

Creare un singolo certificato pubblico, verificare di disporre di una chiave privata esportabile definita per il certificato e assegnarlo alle interfacce esterne dei server perimetrali seguenti utilizzando la Configurazione guidata certificati:

<div>


> [!IMPORTANT]  
> I certificati con caratteri jolly non sono supportati in Lync Server, tranne se utilizzati per riepilogare gli URL semplici tramite il proxy inverso. È necessario definire SANs (Subject Alternate Names) distinti per ogni nome di dominio SIP, servizio Web Conferencing Edge, servizio A/V Edge e dominio XMPP offerti dalla distribuzione.



</div>

<div>


> [!NOTE]  
> Introdotti in Lync Server 2013, la gestione dei certificati di autenticazione audio/video in anticipo rispetto alla data di scadenza del certificato corrente richiede una pianificazione aggiuntiva. Invece di un certificato con più scopi per l'interfaccia perimetrale esterna, sono necessari due certificati, uno assegnato al servizio Access Edge e il servizio Web Conferencing Edge e un certificato per il servizio A/V Edge. Per ulteriori informazioni, vedere <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> In caso di un pool di server perimetrali, esportare il certificato con la chiave privata in ogni server perimetrale e assegnare il certificato a ogni servizio server perimetrale. Fare lo stesso per il certificato del server perimetrale interno, esportando il certificato con la chiave privata e assegnando a ogni interfaccia perimetrale interna.



</div>

  - Verificare di disporre di una chiave privata esportabile assegnata per il certificato

  - Servizio Access Edge (denominato **Access Edge SIP esterno** nella configurazione guidata certificati)

  - Servizio Web Conferencing Edge (denominato **Web Conferencing Edge esterno** nella configurazione guidata certificati)

  - Servizio di autenticazione A/V (denominato **A/V Edge Server esterno** nella Configurazione guidata certificati)

Creare un singolo certificato interno con chiave privata esportabile, copiarlo e assegnarlo a ciascuna delle interfacce interne del server perimetrale:

  - Server perimetrale (denominato **Edge Server interno** nella Configurazione guidata certificati)

<div>


> [!IMPORTANT]  
> È possibile utilizzare certificati separati e distinti per ogni servizio server perimetrale. Se si desidera utilizzare la nuova funzionalità di certificazione per il certificato del servizio A/V Edge, è consigliabile scegliere certificati distinti. Nel caso di questa funzionalità, è consigliabile separare il certificato del servizio A/V Edge dal servizio Access Edge e il servizio Web Conferencing Edge. Se si sceglie di richiedere, acquisire e assegnare certificati distinti per ogni servizio, è necessario richiedere che la chiave privata sia esportabile per il servizio A/V Edge (di nuovo, questo è il servizio di autenticazione A/V) e assegnare lo stesso certificato all'interfaccia esterna a/V Edge in ogni server perimetrale.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Modifiche apportate in Lync Server 2013 che influiscono sulla pianificazione del server perimetrale](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

