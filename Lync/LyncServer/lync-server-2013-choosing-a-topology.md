---
title: 'Lync Server 2013: Scelta di una topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Scelta di una topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Argomento Ultima modifica:** 2013-02-21_

Quando si sceglie una topologia, è possibile usare una delle opzioni seguenti per la topologia supportata:

<div>


> [!NOTE]
> Se non diversamente specificato, se si ha esperienza con Microsoft Lync Server 2010, le linee guida sono in gran parte invariate.



</div>

  - [Singola topologia perimetrale consolidata con indirizzi IP privati e NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.



</div>

Nella tabella seguente sono riepilogate le funzionalità disponibili con le topologie di Microsoft Lync Server 2013 supportate. Le intestazioni di colonna indicano la funzionalità disponibile per una determinata opzione di configurazione del bordo. Usando l'opzione bordo scala (bilanciamento del carico DNS) come esempio, puoi vedere che supporta la disponibilità elevata, puoi usare indirizzi IP privati non instradabili (con NAT) o indirizzi IP pubblici instradabili assegnati alle interfacce esterne del bordo e ridurre i costi perché un il bilanciamento del carico hardware non è obbligatorio.

Gli scenari di failover dei bordi supportati con il bilanciamento del carico DNS sono sessioni Point-to-Point Lync-to-Lync, sessioni di conferenza di Lync, sessioni di Lync-to-PSTN e Office 365. Gli scenari di failover dei bordi che non traggono vantaggio dal bilanciamento del carico DNS sono il failover per la messaggistica unificata di Exchange utente remoto (prima di Exchange 2010 SP1), la connettività messaggistica istantanea pubblica e la Federazione con i server che eseguono le comunicazioni di Office Server.

### <a name="summary-of-edge-server-topology-options"></a>Riepilogo delle opzioni della topologia di Edge Server

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Topologia</th>
<th>Disponibilità elevata</th>
<th>Record DNS aggiuntivi necessari per il server perimetrale esterno nel pool di bordi</th>
<th>Failover Edge per le sessioni di Lync-to-Lync</th>
<th>Failover Edge per sessioni di Federazione di Lync-to-Lync EUM/PIC/OCS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bordo singolo con NAT</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Singolo bordo con IP pubblico</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Edge in scala (bilanciamento del carico DNS) tramite NAT</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Edge in scala (bilanciamento del carico DNS) tramite IP pubblico</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico hardware del bordo scalato)</p></td>
<td><p>Sì</p></td>
<td><p>No (un record DNS per ogni VIP)</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
</tbody>
</table>


**\*** Il failover per la connettività di messaggistica istantanea pubblica e la Federazione con i server che gestiscono Office Communications Server non è disponibile con il bilanciamento del carico DNS. Il failover della messaggistica unificata di Exchange (utente remoto) con il bilanciamento del carico DNS richiede Exchange Server 2010 SP1 o versioni successive.



> [!NOTE]
> Le topologie a bordo singolo e in scala (bilanciamento del carico DNS) possono essere usate:
> <ul><li><p>Indirizzi IP pubblici instradabili</p></li>
> <li><p>Indirizzo IP privato non instradabile se viene usato NAT (Symmetric Network Address Translation)</p></li>
>
> <ul><li> Se si usa l'indirizzo IP pubblico o l'indirizzo IP privato con NAT, si utilizzerà comunque lo stesso numero di indirizzi IP in base alla scelta di configurazione in Generatore di topologie. È possibile configurare l'Edge Server in modo da usare un singolo indirizzo IP con porte distinte per servizio oppure usare indirizzi IP distinti per servizio, ma usare la stessa porta (per impostazione predefinita, TCP 443).</li></ul>>
> Se si decide di usare indirizzi IP privati non instradabili con NAT:
> <ul><li><p>È necessario usare indirizzi IP privati instradabili su tutte e tre le interfacce esterne</p></li>
> <li><p>È necessario configurare il NAT simmetrico per il traffico in entrata e in uscita</p></li></ul>>
> La topologia di Edge in scala (bilanciamento del carico hardware) deve usare indirizzi IP pubblici.



Lync Server 2013 supporta l'immissione di interfacce esterne di Access, Web Conferencing e A/V Edge dietro un router o un firewall che esegue NAT (Network Address Translation) sia per le topologie di server Edge consolidate singole che in scala.

L'uso di NAT per tutte le interfacce esterne Edge richiede l'utilizzo del bilanciamento del carico DNS. Se confrontato con l'uso di bilanciamento del carico hardware, l'uso del bilanciamento del carico DNS senza NAT consente di ridurre il numero di indirizzi IP pubblici per ogni server perimetrale in un pool di bordi, come descritto nell'elenco seguente:

  - Lync Server 2013 Edge consolidato ridimensionato (bilanciamento del carico DNS) richiede tre indirizzi IP pubblici per ogni Edge Server in un pool di bordi.

  - Lync Server 2013 Edge consolidato ridimensionato (bilanciamento del carico hardware) richiede tre indirizzi IP pubblici per l'indirizzo IP virtuale di bilanciamento del carico (un requisito di tempo che non viene incrementato man mano che vengono aggiunti altri Edge Server al pool) più tre indirizzi IP pubblici per Server perimetrale in un pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisiti per l'indirizzo IP per il bordo consolidato in scala (indirizzo IP per ruolo)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero di server perimetrali per pool</th>
<th>Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico DNS)</th>
<th>Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico hardware)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6</p></td>
<td><p>3 (1 per VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9</p></td>
<td><p>3 (1 per VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 per VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15</p></td>
<td><p>3 (1 per VIP) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>Requisiti per l'indirizzo IP per il bordo consolidato in scala (singolo indirizzo IP per tutti i ruoli)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero di server perimetrali per pool</th>
<th>Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico DNS)</th>
<th>Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico hardware)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
<td><p>1 (1 per VIP) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (1 per VIP) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1 (1 per VIP) + 4</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>1 (1 per VIP) + 5</p></td>
</tr>
</tbody>
</table>


I punti decisionali principali per la selezione della topologia sono elevata disponibilità e bilanciamento del carico. Il requisito per l'elevata disponibilità può influenzare la decisione di bilanciamento del carico.

  - **Disponibilità elevata**   Se è necessaria una disponibilità elevata, distribuire almeno due server perimetrali in un pool. Un singolo pool Edge supporta fino a dodici Edge Server. Se è necessaria più capacità, è possibile distribuire più pool di bordi. Come regola generale, il 10% di una determinata base utenti richiederà l'accesso esterno.
    
    <div>
    

    > [!IMPORTANT]
    > Generatore di topologia consente di configurare un massimo di venti server Edge in un unico pool di Edge. Il numero massimo testato e supportato di Edge Server in un pool è dodici e il generatore di topologia che consente un numero maggiore di dodici non deve essere interpretato come supporto implicito per più di dodici Edge Server in un unico pool di Edge.

    
    </div>

  - **Bilanciamento del carico hardware**   Il bilanciamento del carico hardware è supportato per il bilanciamento del carico di Lync Server 2013 Edge Server quando si usano indirizzi IP instradabili pubblicamente per le interfacce esterne di Edge. Ad esempio, questo approccio dovrebbe essere usato in situazioni in cui è necessario il failover per una delle applicazioni seguenti:
    
      - Connettività per messaggistica istantanea pubblica
    
      - Federazione con società che utilizzano Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2
    
      - Accesso esterno alla messaggistica unificata di Exchange 2007 o messaggistica unificata di Exchange 2010
        
        <div>
        

        > [!IMPORTANT]
        > Il bilanciamento del carico DNS per Exchange 2010 SP1 e versioni successive è supportato per la messaggistica unificata di Exchange.

        
        </div>
    
    Queste tre applicazioni continueranno a funzionare, ma non sono consapevoli del bilanciamento del carico DNS e si connetteranno solo al primo server perimetrale nel pool. Se il server non è disponibile, la connessione non riuscirà. Ad esempio, se più Edge Server vengono distribuiti in un pool per gestire il carico di traffico federativo, un solo proxy di Access riceve effettivamente il traffico mentre gli altri sono inattivi.

<div>


> [!IMPORTANT]
> È consigliabile usare il bilanciamento del carico DNS se si sta eseguendo la Federazione con aziende che usano Lync Server 2010 e Microsoft Office 365. Tenere presente che sono presenti effetti significativi sulle prestazioni se la maggior parte dei partner federati usa Office Communications Server 2007 o Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

