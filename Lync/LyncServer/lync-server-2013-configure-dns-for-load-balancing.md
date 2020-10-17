---
title: 'Lync Server 2013: configurare DNS per il bilanciamento del carico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831968516ef155d6ad018f33bfa27226f58292dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537143"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Configurare il DNS per il bilanciamento del carico in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.

Il bilanciamento del carico DNS (Domain Name System) bilancia il traffico di rete univoco per Lync Server 2013, ad esempio il traffico SIP e il traffico multimediale. Il bilanciamento del carico DNS è supportato per pool Front End, pool di server perimetrali, pool di server Director e pool Mediation Server autonomi. Un pool configurato per l'utilizzo del bilanciamento del carico DNS deve disporre di due nomi di dominio completi (FQDN) definiti: FQDN del pool regolare utilizzato dal bilanciamento del carico DNS (ad esempio, pool1.contoso.com) e che viene risolto negli indirizzi IP fisici dei server del pool e un altro FQDN per i servizi Web del pool (ad esempio, web1.contoso.net), che viene risolto nell'indirizzo IP virtuale del pool. Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

<div>


> [!NOTE]  
> Per il traffico HTTPS da client a server è ancora necessario utilizzare il bilanciamento del carico hardware.



</div>

Prima di poter utilizzare il bilanciamento del carico DNS, è necessario eseguire le operazioni seguenti:

1.  Eseguire l'override del nome FQDN del pool di servizi Web interni.
    
    <div>
    

    > [!WARNING]  
    > Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.

    
    </div>

2.  Creare record host A DNS per risolvere l'FQDN del pool negli indirizzi IP di tutti i server inclusi nel pool.

3.  Abilitare la sequenza casuale degli indirizzi IP oppure, per DNS di Windows Server, abilitare il round robin.
    
    <div>
    

    > [!NOTE]  
    > Il round robin è abilitato per impostazione predefinita.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>Per sostituire l'FQDN dei servizi Web interni

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nell'albero della console espandere il nodo Pool Enterprise Edition Front End.

3.  Fare clic con il pulsante destro del mouse sul pool, scegliere **Modifica proprietà** e quindi fare clic su **Servizi Web**.

4.  Sotto **Servizi Web interni** selezionare la casella di controllo **Sostituisci FQDN**.

5.  Digitare l'FQDN del pool che viene risolto negli indirizzi IP fisici dei server del pool.

6.  Sotto **Servizi Web esterni** digitare l'FQDN del pool esterno che viene risolto negli indirizzi IP virtuali del pool e quindi fare clic su **OK**.

7.  Nell'albero della console fare clic su **Lync Server 2013**e quindi nel riquadro **Azioni** fare clic su **Pubblica topologia**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>Per creare i record host (A) DNS per tutti i server del pool interno

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **DNS**.

2.  In **Gestore DNS** fare clic sul server DNS che gestisce i record per espanderlo.

3.  Fare clic sulla voce **Zone di ricerca diretta** per espanderla.

4.  Fare clic con il pulsante destro del mouse sul dominio DNS a cui aggiungere i record e quindi scegliere **Nuovo host (A o AAAA)**.

5.  Nella casella **nome** Digitare il nome del record host (il nome di dominio verrà automaticamente accodato).

6.  Nella casella Indirizzo IP digitare l'indirizzo IP del singolo Front End Server e quindi selezionare **Crea record puntatore (PTR) associato** o **Consenti a tutti gli utenti autenticati di aggiornare i record DNS con lo stesso nome proprietario**, se applicabile.

7.  Continuare a creare i record per tutti i Front End Server membri che parteciperanno al bilanciamento del carico DNS.
    
    Se ad esempio si dispone di un pool denominato pool1.contoso.com e di tre Front End Server, sarà necessario creare le voci DNS seguenti:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>Tipo</th>
    <th>Dati</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    Per informazioni dettagliate sulla creazione di record host DNS (A), vedere [configure DNS Host Records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Per abilitare il round robin per Windows Server

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **DNS**.

2.  Espandere **DNS**, fare clic con il pulsante destro del mouse sul server DNS che si desidera configurare e quindi scegliere **Proprietà**.

3.  Fare clic sulla scheda **Avanzate**, selezionare **Attiva round robin** e **Attiva ordinamento netmask ** e quindi fare clic su **OK**.
    
    ![Finestra di dialogo Round Robin DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Finestra di dialogo Round Robin DNS")

<div>


> [!NOTE]  
> Questa funzionalità è abilitata per impostazione predefinita.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

