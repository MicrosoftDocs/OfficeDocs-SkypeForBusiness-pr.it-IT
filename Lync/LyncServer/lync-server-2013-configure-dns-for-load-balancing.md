---
title: 'Lync Server 2013: Configurare DNS per il bilanciamento del carico'
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
ms.openlocfilehash: f5b68bf226c71d65835791577ab9a45f18b2a10e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Configurare DNS per il bilanciamento del carico in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

Il bilanciamento del carico DNS (Domain Name System) bilancia il traffico di rete univoco per Lync Server 2013, ad esempio il traffico SIP e il traffico multimediale. Il bilanciamento del carico DNS è supportato per i pool Front-End, i pool di bordi, i pool di direttori e i pool di mediazione autonomi. Un pool configurato per l'uso del bilanciamento del carico DNS deve avere due nomi di dominio completi (FQDN) definiti: l'FQDN del pool normale usato dal bilanciamento del carico DNS (ad esempio, pool1.contoso.com) e che viene risolto nell'IPs fisico dei server nel pool e un altro nome di dominio completo per i servizi Web del pool, ad esempio web1.contoso.net, che viene risolto nell'indirizzo IP virtuale del pool. Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

<div>


> [!NOTE]  
> Il bilanciamento del carico hardware è ancora necessario per il traffico HTTPS da client a server.



</div>

Per poter usare il bilanciamento del carico DNS, è necessario eseguire le operazioni seguenti:

1.  Eseguire l'override del nome FQDN del pool di servizi Web interni.
    
    <div>
    

    > [!WARNING]  
    > Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.

    
    </div>

2.  Creare record host DNS per risolvere il nome di dominio completo del pool agli indirizzi IP di tutti i server del pool.

3.  Abilitare la randomizzazione degli indirizzi IP o, per Windows Server DNS, abilitare Round Robin.
    
    <div>
    

    > [!NOTE]  
    > Il Round Robin deve essere abilitato per impostazione predefinita.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>Per ignorare l'FQDN dei servizi Web interni

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il nodo Pool di front end di Enterprise Edition.

3.  Fare clic con il pulsante destro del mouse sul pool, scegliere **modifica proprietà**e quindi fare clic su **servizi Web**.

4.  Sotto **servizi Web interni**selezionare la casella di controllo **Sostituisci FQDN** .

5.  Digitare il nome di dominio completo del pool che viene risolto negli indirizzi IP fisici dei server nel pool.

6.  Sotto **servizi Web esterni**Digitare il nome di dominio completo del pool esterno che viene risolto negli indirizzi IP virtuali del pool e quindi fare clic su **OK**.

7.  Nell'albero della console fare clic su **Lync Server 2013**e quindi, nel riquadro **azioni** , fare clic su **Pubblica topologia**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>Per creare record host DNS (A) per tutti i server di pool interni

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **DNS**.

2.  In **gestore DNS**fare clic sul server DNS che gestisce i record per espanderlo.

3.  Fare clic su **Inoltra aree di ricerca** per espanderlo.

4.  Fare clic con il pulsante destro del mouse sul dominio DNS a cui è necessario aggiungere i record e quindi scegliere **nuovo host (a o AAAA)**.

5.  Nella casella **nome** Digitare il nome del record host (il nome del dominio verrà accodato automaticamente).

6.  Nella casella indirizzo IP digitare l'indirizzo IP del server front-end individuale e quindi selezionare **Crea record puntatore associato (PTR)** o **consentire a qualsiasi utente autenticato di aggiornare i record DNS con lo stesso nome proprietario**, se applicabile.

7.  Continuare a creare record per tutti i server front-end membri che parteciperanno al bilanciamento del carico DNS.
    
    Ad esempio, se si ha un pool denominato pool1.contoso.com e tre server front-end, si creeranno le voci DNS seguenti:
    
    
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
    
    Per informazioni dettagliate sulla creazione di record host DNS (A), vedere [configurare i record host DNS per Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Per abilitare Round Robin per Windows Server

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **DNS**.

2.  Espandere **DNS**, fare clic con il pulsante destro del mouse sul server DNS che si vuole configurare e quindi scegliere **Proprietà**.

3.  Fare clic sulla scheda **Avanzate** , selezionare **Abilita Round Robin** e **abilitare l'ordinamento per netmask**e quindi fare clic su **OK**.
    
    ![Finestra di dialogo del round robin DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Finestra di dialogo del round robin DNS")

<div>


> [!NOTE]  
> Questa caratteristica deve essere abilitata per impostazione predefinita.



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

