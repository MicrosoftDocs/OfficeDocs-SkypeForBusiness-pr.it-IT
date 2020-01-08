---
title: Esempio di raccolta dei requisiti per il controllo dell'ammissione alle chiamate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e17d9abb0387f0d77c696487558dec0c915b1651
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Questo esempio illustra come pianificare e implementare il controllo di ammissione di chiamata (CAC). Ad alto livello, è costituito dalle attività seguenti:

1.  Identificare tutti gli hub di rete e le dorsali (note come *aree di rete*).

2.  Identificare il sito centrale di Lync Server che gestirà CAC per ogni area di rete.

3.  Identificare e definire i *siti di rete* connessi a ogni area di rete.

4.  Per ogni sito di rete la cui connessione alla WAN è vincolata da larghezza di banda, descrivere la capacità di larghezza di banda della connessione WAN e i limiti di larghezza di banda che l'amministratore di rete ha impostato per il traffico multimediale di Lync Server, se applicabile. Non è necessario includere siti la cui connessione alla rete WAN non è vincolata da larghezza di banda.

5.  Associare ogni subnet della rete a un sito di rete.

6.  Mappare i collegamenti tra le aree di rete. Per ogni collegamento, Descrivi la sua capacità di larghezza di banda e i limiti che l'amministratore di rete ha inserito nel traffico multimediale di Lync Server.

7.  Definire una route tra ogni coppia di aree di rete.

<div>

## <a name="gather-the-required-information"></a>Raccogliere le informazioni necessarie

Per preparare il controllo di ammissione alle chiamate, raccogliere le informazioni descritte nei passaggi seguenti:

1.  Identificare le aree di rete. Un'area di rete rappresenta un backbone di rete o un hub di rete.
    
    Un backbone di rete o un hub di rete fa parte dell'infrastruttura di rete di computer che interconnette vari elementi di rete, fornendo un percorso per lo scambio di informazioni tra LAN o subnet diverse. Una backbone può legare insieme diverse reti, da una piccola posizione a un'area geografica ampia. La capacità della colonna vertebrale è in genere maggiore rispetto a quella delle reti connesse.
    
    La topologia di esempio include tre aree di rete: Nord America, EMEA e APAC. Un'area di rete contiene una raccolta di siti di rete. Collaborare con l'amministratore di rete per definire le aree di rete per l'organizzazione.

2.  Identificare il sito centrale associato di ogni area di rete. Un sito centrale contiene almeno un server front-end ed è la distribuzione di Lync Server che gestirà CAC per tutto il traffico multimediale che passa attraverso la connessione WAN dell'area di rete.
    
    **Esempio di rete aziendale divisa in tre aree di rete**
    
    ![Esempio di topologia di rete con 3](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "esempio di topologia di rete con 3 aree di") rete  
    
    <div>
    

    > [!NOTE]
    > Una rete MPLS (Multiprotocol Label Switching) deve essere rappresentata come area di rete in cui ogni posizione geografica contiene un sito di rete corrispondente. Per informazioni dettagliate, vedere l'argomento "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">controllo ammissione chiamata in rete MPLS con Lync Server 2013</A>" nella documentazione relativa alla pianificazione.

    
    </div>
    
    Nella topologia di rete di esempio precedente sono presenti tre aree di rete, ognuna con un sito centrale di Lync Server che gestisce CAC. Il sito centrale appropriato per un'area geografica di rete viene scelto dalle vicinanze geografiche. Poiché il traffico multimediale sarà più pesante nelle aree di rete, la proprietà per le vicinanze geografiche lo rende autonomo e continuerà a essere funzionante anche se altri siti centrali diventano non disponibili.
    
    In questo esempio, una distribuzione di Lync Server denominata Chicago è il sito centrale per l'area Nord America.
    
    Tutti gli utenti di Lync in Nord America vengono ospitati nei server della distribuzione di Chicago. La tabella seguente mostra i siti centrali per tutte e tre le aree di rete.
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>Aree di rete e relativi siti centrali associati
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Area di rete</th>
    <th>Sito centrale</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>America del Nord</p></td>
    <td><p>Chicago</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>Londra</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>Pechino</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > A seconda della topologia di Lync Server, è possibile assegnare lo stesso sito centrale a più aree di rete.

    
    </div>

3.  Per ogni area geografica di rete, identificare tutti i siti di rete (uffici o posizioni) le cui connessioni WAN non sono vincolate da larghezza di banda. Poiché questi siti non sono vincolati alla larghezza di banda, non è necessario applicare i criteri di larghezza di banda CAC.
    
    Nell'esempio illustrato nella tabella seguente tre siti di rete non dispongono di collegamenti WAN con larghezza di banda limitata: New York, Chicago e Detroit.
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>Siti di rete non vincolati dalla larghezza di banda WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sito di rete</th>
    <th>Area di rete</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>New York</p></td>
    <td><p>America del Nord</p></td>
    </tr>
    <tr class="even">
    <td><p>Chicago</p></td>
    <td><p>America del Nord</p></td>
    </tr>
    <tr class="odd">
    <td><p>Detroit</p></td>
    <td><p>America del Nord</p></td>
    </tr>
    </tbody>
    </table>


4.  Per ogni area geografica di rete, identificare tutti i siti di rete che si connettono all'area di rete tramite collegamenti WAN con larghezza di banda limitata.
    
    Per garantire la qualità audio e video, è consigliabile che i siti di rete con vincoli di larghezza di banda dispongano delle WAN monitorate e dei criteri di larghezza di banda CAC che limitano il flusso di traffico multimediale (vocale o video) da e verso l'area di rete.
    
    Nell'esempio illustrato nella tabella seguente sono disponibili tre siti di rete vincolati da larghezza di banda WAN: Portland, Reno e Albuquerque.
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>Siti di rete vincolati da larghezza di banda WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sito di rete</th>
    <th>Area di rete</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>America del Nord</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>America del Nord</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>America del Nord</p></td>
    </tr>
    </tbody>
    </table>
    
    **Area di rete CAC Nord America con tre siti di rete non vincolati per larghezza di banda (Chicago, New York e Detroit) e tre siti di rete vincolati dalla larghezza di banda WAN (Portland, Reno e Albuquerque)**
    
    ![Siti di rete di esempio vincolati da siti di rete di esempio di larghezza di banda WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "vincolati da larghezza di banda WAN")  

5.  Per ogni collegamento WAN con larghezza di banda limitata, determinare le operazioni seguenti:
    
      - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causa il superamento di questo limite, Lync Server non consente l'avvio della sessione.
    
      - Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.
    
      - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee. Se una nuova sessione video causerà il superamento di questo limite, Lync Server non consente l'avvio della sessione.
    
      - Limite di larghezza di banda che si vuole impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>Siti di rete con informazioni sui vincoli di larghezza di banda WAN (larghezza di banda in Kbps)
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sito di rete</th>
    <th>Area di rete</th>
    <th>Limite di BW</th>
    <th>Limite audio</th>
    <th>Limite della sessione audio</th>
    <th>Limite video</th>
    <th>Limite di sessione video</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>America del Nord</p></td>
    <td><p>5.000</p></td>
    <td><p>2.000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>America del Nord</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>America del Nord</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>New York</p></td>
    <td><p>America del Nord</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>America del Nord</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>America del Nord</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    </tr>
    </tbody>
    </table>


6.  Per ogni subnet della rete, specificare il sito di rete associato.
    
    <div>
    

    > [!IMPORTANT]
    > Ogni subnet della rete deve essere associata a un sito di rete, anche se il sito di rete non è vincolato alla larghezza di banda. Questo perché il controllo di ammissione delle chiamate usa le informazioni sulla subnet per determinare in quale sito di rete si trova un endpoint. Quando vengono determinate le posizioni di entrambe le parti della sessione, il controllo di ammissione delle chiamate può determinare se è disponibile una larghezza di banda sufficiente per stabilire una chiamata. Quando viene stabilita una sessione su un collegamento che non contiene limiti di larghezza di banda, viene generato un avviso.<BR>Se si distribuiscono server Edge audio/video, gli indirizzi IP pubblici di ogni Edge Server devono essere associati al sito di rete in cui è distribuito il server perimetrale. Ogni indirizzo IP pubblico di un/V Edge Server deve essere aggiunto alle impostazioni di configurazione della rete come subnet con una subnet mask di 32. Ad esempio, se si distribuisce un/V Edge Server a Chicago, per ogni indirizzo IP esterno di questi server è possibile creare una subnet con una subnet mask di 32 e associare il sito di rete a Chicago con tali subnet. Per informazioni dettagliate sugli indirizzi IP pubblici, vedere <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinare i requisiti per il firewall e la porta a/V esterni per Lync Server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Viene generato un avviso KHI (Key Health Indicator), che specifica un elenco di indirizzi IP presenti nella rete, ma che non sono associati a una subnet oppure che la subnet che include gli indirizzi IP non è associata a un sito di rete. Questo avviso non verrà generato più di una volta entro un periodo di 8 ore. Di seguito sono riportate le informazioni relative agli avvisi e un esempio:<BR><STRONG>Origine:</STRONG> Servizio di criteri di larghezza di banda CS (Core)<BR><STRONG>Numero evento:</STRONG> 36034<BR><STRONG>Livello:</STRONG> 2<BR><STRONG>Descrizione:</STRONG> Le subnet per gli indirizzi IP seguenti: &lt;l'elenco di indirizzi&gt; IP non è configurato o le subnet non sono associate a un sito di rete.<BR><STRONG>Causa:</STRONG> Le subnet per gli indirizzi IP corrispondenti sono mancanti nelle impostazioni di configurazione della rete o le subnet non sono associate a un sito di rete.<BR><STRONG>Risoluzione:</STRONG> Aggiungere subnet che corrispondono all'elenco precedente di indirizzi IP nelle impostazioni di configurazione della rete e associare ogni subnet a un sito di rete.<BR>Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete. Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema come segue: 
    > <OL>
    > <LI>
    > <P>Assicurarsi che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</P>
    > <LI>
    > <P>Assicurarsi che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate a un sito di rete.</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>Siti di rete e subnet associate (larghezza di banda in Kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sito di rete</th>
    <th>Area di rete</th>
    <th>Limite di BW</th>
    <th>Limite audio</th>
    <th>Limite della sessione audio</th>
    <th>Limite video</th>
    <th>Limite di sessione video</th>
    <th>Subnet</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>America del Nord</p></td>
    <td><p>5.000</p></td>
    <td><p>2.000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>America del Nord</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23, 172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>America del Nord</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>New York</p></td>
    <td><p>America del Nord</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>America del Nord</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>157.57.211.0/23, 172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>America del Nord</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>(nessun limite)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  Nel controllo di ammissione alle chiamate di Lync Server le connessioni tra le aree di rete sono chiamate *collegamenti di area geografica*. Per ogni collegamento all'area geografica, determinare quanto segue, come per i siti di rete:
    
      - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causa il superamento di questo limite, Lync Server non consente l'avvio della sessione.
    
      - Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.
    
      - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee. Se una nuova sessione video causerà il superamento di questo limite, Lync Server non consente l'avvio della sessione.
    
      - Limite di larghezza di banda che si vuole impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.
    
    **Collegamenti all'area di rete con limiti di larghezza di banda associati**
    
    ![Esempio di limitazioni tra 3 aree](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "esempio di limitazioni tra 3 aree geografiche")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>Informazioni sulla larghezza di banda del collegamento geografica (larghezza di banda in Kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome collegamento area geografica</th>
    <th>First Region</th>
    <th>Second Region</th>
    <th>Limite di BW</th>
    <th>Limite audio</th>
    <th>Limite della sessione audio</th>
    <th>Limite video</th>
    <th>Limite di sessione video</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-COLLEGAMENTO</p></td>
    <td><p>America del Nord</p></td>
    <td><p>EMEA</p></td>
    <td><p>50.000</p></td>
    <td><p>20.000</p></td>
    <td><p>175</p></td>
    <td><p>14.000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-COLLEGAMENTO</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25.000</p></td>
    <td><p>10.000</p></td>
    <td><p>175</p></td>
    <td><p>7.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  Definire una route tra ogni coppia di aree di rete.
    
    <div>
    

    > [!NOTE]
    > Sono necessari due collegamenti per la route tra il Nord America e le aree APAC perché non è presente un collegamento all'area geografica che li connette direttamente.

    
    </div>
    
    ### <a name="region-routes"></a>Route di area geografica
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome route dell'area geografica</th>
    <th>First Region</th>
    <th>Second Region</th>
    <th>Collegamenti all'area geografica</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ROUTE</p></td>
    <td><p>America del Nord</p></td>
    <td><p>EMEA</p></td>
    <td><p>NA-EMEA-COLLEGAMENTO</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-ROUTE</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC-COLLEGAMENTO</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-ROUTE</p></td>
    <td><p>America del Nord</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-LINK, EMEA-APAC-LINK</p></td>
    </tr>
    </tbody>
    </table>


9.  Per ogni coppia di siti di rete collegati direttamente da un singolo collegamento (denominato collegamento *tra siti* ), determinare le operazioni seguenti:
    
      - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causa il superamento di questo limite, Lync Server non consente l'avvio della sessione.
    
      - Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.
    
      - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee. Se una nuova sessione video causerà il superamento di questo limite, Lync Server non consente l'avvio della sessione.
    
      - Limite di larghezza di banda che si vuole impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.
    
    **Area di rete CAC Nord America che mostra le capacità di larghezza di banda e i limiti di larghezza di banda per il collegamento tra siti tra Reno e Albuquerque**
    
    ![Siti di rete vincolati da siti di rete di esempio di larghezza di banda WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "vincolati da un esempio di larghezza di banda WAN")  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>Informazioni sulla larghezza di banda per un collegamento intersito tra due siti di rete (larghezza di banda in Kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome collegamento tra siti</th>
    <th>Primo sito</th>
    <th>Secondo sito</th>
    <th>Limite di BW</th>
    <th>Limite audio</th>
    <th>Limite della sessione audio</th>
    <th>Limite video</th>
    <th>Limite di sessione video</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-albu-collegamento intersito</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>20.000</p></td>
    <td><p>12.000</p></td>
    <td><p>175</p></td>
    <td><p>5.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>Operazioni successive

Dopo aver raccolto le informazioni necessarie, è possibile eseguire la distribuzione di CAC usando il pannello di controllo di Lync Server Management Shell o Lync Server.

<div>


> [!NOTE]
> Anche se è possibile eseguire la maggior parte delle attività di configurazione della rete tramite il pannello di controllo di Lync Server, per creare subnet e collegamenti intersito, è necessario usare Lync Server Management Shell. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet <STRONG>New-CsNetworkSubnet</STRONG> e il cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

