---
title: 'Lync Server 2013: Pianificare i certificati dei server perimetrali'
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
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Pianificare i certificati dei server perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-05_

La creazione di certificati per Edge è semplificata in Lync Server 2013.

**Diagramma di flusso Certificati per Edge Server**

![a5fc20db-7ced-4364-B577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-B577-6a709a8367cd")

Creare un singolo certificato pubblico, verificare di avere una chiave privata esportabile definita per il certificato e assegnarla alle interfacce esterne di Edge Server seguenti tramite la creazione guidata certificato:

<div>


> [!IMPORTANT]  
> I certificati con caratteri jolly non sono supportati in Lync Server, ad eccezione di quelli usati per riepilogare gli URL semplici tramite il proxy inverso. È necessario definire SANs per ogni nome di dominio SIP, Web Conferencing Edge service, A/V Edge e il dominio XMPP offerti dalla distribuzione.



</div>

<div>


> [!NOTE]  
> Introdotti in Lync Server 2013, i certificati di autenticazione audio/video in anticipo rispetto all'ora di scadenza del certificato corrente richiedono una pianificazione aggiuntiva. Invece di un certificato con più scopi per l'interfaccia perimetrale esterna, sono necessari due certificati, uno assegnato al servizio Access Edge e Web Conferencing Edge e un certificato per il servizio A/V Edge. Per ulteriori informazioni, vedere <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">gestione dei certificati di staging AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> In caso di pool di Edge Server, è possibile esportare il certificato con la chiave privata in ogni Edge Server e assegnare il certificato a ogni servizio Edge Server. Eseguire la stessa operazione per il certificato Internal Edge Server, esportando il certificato con la chiave privata e assegnando a ogni interfaccia Edge interna.



</div>

  - Verificare di avere una chiave privata esportabile assegnata per il certificato

  - Access Edge Services (denominato Edge di **accesso SIP esterno** nella procedura guidata certificato)

  - Web Conferencing Edge Services (denominato **Web Conferencing Edge esterno** nella procedura guidata certificati)

  - Servizio di autenticazione a/V (denominato a **/v Edge External** nella procedura guidata certificato)

Creare un singolo certificato interno con una chiave privata esportabile, copiarla e assegnarla a ognuna delle interfacce interne del server perimetrale:

  - Edge Server (denominato **Edge Internal** nella creazione guidata certificato)

<div>


> [!IMPORTANT]  
> È possibile usare certificati distinti per ogni servizio Edge Server. Un buon motivo per scegliere i certificati distinti è se si vuole usare la nuova caratteristica di certificato rotante per il certificato del servizio A/V Edge. Nel caso di questa caratteristica, è consigliabile disaccoppiare il certificato A/V Edge service da Access Edge service e Web Conferencing Edge service. Se si sceglie di richiedere, acquisire e assegnare certificati distinti per ogni servizio, è necessario richiedere che la chiave privata sia esportabile per il servizio A/V Edge (di nuovo, si tratta in realtà del servizio di autenticazione A/V) e assegnare lo stesso certificato all'interfaccia esterna di un/V Edge in ogni server perimetrale.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione di certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Modifiche introdotte in Lync Server 2013 che incidono sulla pianificazione dei server perimetrali](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

