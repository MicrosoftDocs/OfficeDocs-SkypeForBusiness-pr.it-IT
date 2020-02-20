---
title: 'Lync Server 2013: scelta di una topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b91fc332c5eff86cd23393492bcd760bbda18db3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Scelta di una topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Ultimo argomento modificato:** 2013-02-21_

Quando si sceglie una topologia, è possibile utilizzare una delle opzioni di topologie supportate seguenti:

<div>


> [!NOTE]
> Se non diversamente specificato, se si ha esperienza con Microsoft Lync Server 2010, le linee guida qui sono in gran parte invariate.



</div>

  - [Singolo server perimetrale consolidato con indirizzi IP privati e NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Perimetro consolidato singolo con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.



</div>

Nella tabella seguente sono riepilogate le funzionalità disponibili con le topologie di Microsoft Lync Server 2013 supportate. Le intestazioni di colonna indicano la funzionalità disponibile per una determinata opzione di configurazione di server perimetrale. Utilizzando come esempio l'opzione di server perimetrale con scalabilità implementata e con bilanciamento del carico DNS, è possibile osservare che supporta la disponibilità elevata, può utilizzare indirizzi IP privati non instradabili (con NAT) o indirizzi IP pubblici instradabili assegnati alle interfacce esterne perimetrali e comporta una riduzione dei costi perché non è necessario un dispositivo di bilanciamento del carico hardware.

Gli scenari di failover dei server perimetrali supportati con il bilanciamento del carico DNS sono sessioni punto-punto di Lync-to-Lync, sessioni di Lync Conferencing, sessioni Lync-to-PSTN e Office 365. Gli scenari di failover dei server perimetrali che non beneficiano del bilanciamento del carico DNS sono il failover per la messaggistica unificata di Exchange (prima di Exchange 2010 SP1), la connettività per la messaggistica istantanea pubblica e la Federazione con i computer che eseguono le comunicazioni di Office Server.

### <a name="summary-of-edge-server-topology-options"></a>Riepilogo delle opzioni di topologia di server perimetrali

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
<th>Record A DNS aggiuntivi necessario per il server perimetrale esterno del pool di server perimetrali</th>
<th>Failover del server perimetrale per le sessioni Lync-to-Lync</th>
<th>Failover perimetrale per sessioni di Federazione di Lync-to-Lync EUM/PIC/OCS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Singolo perimetro con NAT</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Singolo perimetro con indirizzi IP pubblici</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Perimetro in scala (bilanciamento del carico DNS) con NAT</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Perimetro in scala (bilanciamento del carico DNS) con IP pubblico</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Hardware perimetrale in scala (con bilanciamento del carico)</p></td>
<td><p>Sì</p></td>
<td><p>No (un record A DNS per IP virtuale)</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
</tbody>
</table>


**\*** Il failover per la connettività di messaggistica istantanea pubblica e la Federazione con i server che eseguono Office Communications Server non sono disponibili con il bilanciamento del carico DNS. Il failover della messaggistica unificata di Exchange (utente remoto) utilizzando il bilanciamento del carico DNS richiede Exchange Server 2010 SP1 o versione successiva.



> [!NOTE]
> Le topologie perimetrale singola e perimetrale in scala (con bilanciamento del carico DNS) possono utilizzare:
> <ul><li><p>Indirizzi IP pubblici instradabili</p></li>
> <li><p>Indirizzo IP privato non instradabile se viene utilizzato NAT (Symmetric Network Address Translation)</p></li>
>
> <ul><li> Se si utilizza l'indirizzo IP pubblico o l'indirizzo IP privato con NAT, verrà comunque utilizzato lo stesso numero di indirizzi IP in base alla scelta di configurazione in Generatore di topologie. È possibile configurare il server perimetrale per l'utilizzo di un singolo indirizzo IP con porte distinte per servizio oppure utilizzare indirizzi IP distinti per servizio, ma utilizzare la stessa porta (per impostazione predefinita, TCP 443).</li></ul>>
> Se si decide di utilizzare indirizzi IP privati non instradabili con NAT:
> <ul><li><p>È necessario utilizzare indirizzi IP privati instradabili su tutte e tre le interfacce esterne</p></li>
> <li><p>È necessario configurare NAT simmetrico per il traffico in arrivo e in uscita</p></li></ul>>
> La topologia perimetrale in scala (con bilanciamento del carico hardware) deve utilizzare indirizzi IP pubblici.



Lync Server 2013 supporta il posizionamento di interfacce esterne di accesso, Web Conferencing e A/V Edge dietro un router o un firewall che esegue la conversione NAT (Network Address Translation) per topologie di server perimetrali consolidate singole e in scala.

L'utilizzo di NAT per tutte le interfacce esterne perimetrali richiede l'utilizzo del bilanciamento del carico DNS. In confronto all'utilizzo di un dispositivo di bilanciamento del carico hardware, il bilanciamento del carico DNS senza NAT consente di ridurre il numero di indirizzi IP pubblici per server perimetrale in un pool di server perimetrali, come descritto nell'elenco seguente:

  - Lync Server 2013 il perimetro consolidato in scala (bilanciamento del carico DNS) richiede tre indirizzi IP pubblici per ogni server perimetrale in un pool perimetrale.

  - Lync Server 2013 il perimetro consolidato in scala (bilanciamento del carico hardware) richiede tre indirizzi IP pubblici per l'indirizzo IP virtuale del dispositivo di bilanciamento del carico (un requisito di tempo che non incrementa il numero di server perimetrali aggiunti al pool) più tre indirizzi IP pubblici per Server perimetrale in un pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisiti di indirizzi IP per topologie di server perimetrali consolidati con scalabilità implementata (indirizzo IP per ruolo)

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
<td><p>6 </p></td>
<td><p>3 (1 per VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9 </p></td>
<td><p>3 (1 per VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 per VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15 </p></td>
<td><p>3 (1 per IP virtuale) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>Requisiti di indirizzi IP per topologie di server perimetrali consolidati con scalabilità implementata (singolo indirizzo IP per tutti i ruoli)

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
<td><p>1 (1 per IP virtuale) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>3 (1 per IP virtuale) + 6</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>4 (1 per IP virtuale) + 6</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>5 (1 per IP virtuale) + 6</p></td>
</tr>
</tbody>
</table>


Gli aspetti principali di cui tenere conto per la scelta della topologia sono la disponibilità elevata e il bilanciamento del carico. Il requisito di disponibilità elevata può influire sulla scelta del bilanciamento del carico.

  - **Disponibilità elevata**   Se è necessaria una disponibilità elevata, distribuire almeno due server perimetrali in un pool. Un singolo pool di server perimetrali supporterà fino a un massimo di dodici perimetri. Se è necessaria ulteriore capacità, è possibile distribuire più pool di server perimetrali. Come regola generale, il 10% del numero totale di utenti necessiterà dell'accesso esterno.
    
    <div>
    

    > [!IMPORTANT]
    > Generatore di topologie consentirà di configurare fino a venti server perimetrali in un singolo pool di Edge. Il numero massimo testato e supportato di server perimetrali in un pool è dodici e il generatore di topologie che consente un numero maggiore di dodici non dovrebbe essere interpretato come supporto implicito per più di dodici server perimetrali in un singolo pool di Edge.

    
    </div>

  - **Bilanciamento del carico hardware**   Il bilanciamento del carico hardware è supportato per il bilanciamento del carico dei server perimetrali di Lync Server 2013 quando si utilizzano indirizzi IP instradabili pubblicamente per le interfacce esterne perimetrali. Utilizzare ad esempio questo approccio in situazioni in cui è necessario il failover per le applicazioni seguenti:
    
      - Connettività per messaggistica istantanea pubblica
    
      - Federazione con società che eseguono Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2
    
      - Accesso esterno a Messaggistica unificata di Exchange 2007 o di Exchange 2010
        
        <div>
        

        > [!IMPORTANT]
        > Il bilanciamento del carico DNS per Exchange 2010 SP1 e versioni successive è supportato per la messaggistica unificata di Exchange.

        
        </div>
    
    Queste tre applicazioni continueranno a funzionare, ma non supportano il bilanciamento del carico DNS e si connetteranno solo al primo server perimetrale del pool. Se il server non è disponibile, la connessione avrà esito negativo. Se ad esempio vengono distribuiti più server perimetrali in un pool per gestire il carico del traffico federato, solo un proxy di accesso riceverà effettivamente il traffico, mentre gli altri resteranno inattivi.

<div>


> [!IMPORTANT]
> L'utilizzo del bilanciamento del carico DNS è consigliato se si sta eseguendo la Federazione con aziende che utilizzano Lync Server 2010 e Microsoft Office 365. Tenere presente che sono presenti effetti significativi sulle prestazioni se la maggior parte dei partner federati utilizza Office Communications Server 2007 o Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

