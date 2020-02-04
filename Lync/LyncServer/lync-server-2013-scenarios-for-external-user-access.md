---
title: "Lync Server 2013: Scenari per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Scenari per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Per consentire l'accesso degli utenti esterni per Lync Server 2013, è necessario distribuire almeno un server perimetrale e un proxy inverso nella rete perimetrale. Facoltativamente, è possibile distribuire un pool di Director o Director nella rete interna.

Se è necessaria una maggiore capacità rispetto a un singolo Edge Server o se è necessaria una disponibilità elevata per la distribuzione di Edge Server, è possibile configurare il bilanciamento del carico e distribuire più Edge Server in un pool di bilanciamento del carico. Se l'organizzazione ha più centri dati, è possibile avere distribuzioni Edge Server o pool Edge in più di una posizione. Tuttavia, solo una delle distribuzioni di Edge Server può essere designata come route della Federazione.

Questa sezione definisce gli scenari per le distribuzioni di Edge Server e associa le sezioni di pianificazione ai possibili scenari. Ad esempio, se la distribuzione richiede disponibilità elevata, Federazione con contatti di messaggistica e presenza estensibili (XMPP) e mobilità Lync, è necessario selezionare le voci corrispondenti nella tabella seguente che soddisfi questi requisiti e usi l' sezioni di pianificazione a cui viene fatto riferimento per definire la distribuzione, come illustrato nel diagramma di flusso seguente.

**Processo di selezione dello scenario di distribuzione di Edge Server**

![Esempio di diagramma di flusso della distribuzione](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Esempio di diagramma di flusso della distribuzione")

Usando questo processo, puoi pianificare e documentare la configurazione di tutte le funzionalità potenziali che intendi distribuire per gli utenti. È tuttavia possibile aggiungere servizi di Federazione e mobilità dopo avere distribuito il server perimetrale e aver confermato l'operazione corretta prima di aggiungere altre funzionalità. Il processo di aggiunta di funzionalità a una distribuzione di Edge Server esistente è incluso nella sezione distribuzione. Per informazioni dettagliate sulla distribuzione, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) includendo la pianificazione per queste funzionalità durante il processo di pianificazione iniziale, è possibile prepararsi per i requisiti DNS, firewall e certificato per le funzionalità aggiunte, che consentono di acquisire i certificati e configurare preventivamente i requisiti DNS e di protocollo.

<div>


> [!TIP]  
> Se si prevede di installare gli Edge Server e il proxy inverso e quindi di aggiungere funzionalità in un secondo momento, ad esempio la Federazione e la mobilità, determinare quali certificati saranno necessari per tutti i servizi dopo la distribuzione. La pianificazione e l'acquisizione dei certificati per tutte le caratteristiche in anticipo, inizialmente distribuiti o meno, consente di evitare di dover ordinare nuovi certificati per soddisfare i requisiti della Federazione (ovvero, negli Edge Server) o del proxy inverso, ovvero per la mobilità Services).



</div>

<div>


> [!NOTE]  
> Tutti i servizi Edge vengono eseguiti in ogni Edge Server. I servizi non possono essere divisi tra due diversi Edge Server. Se si distribuisce un pool di Edge per la scalabilità, tutti i servizi Edge vengono distribuiti in ogni server perimetrale del pool. La Federazione XMPP, Office Communications Server e la federazione Lync Server, la connettività per messaggistica istantanea pubblica e la mobilità dei client sono servizi aggiuntivi che possono essere distribuiti dopo la distribuzione del primo Edge Server o del pool di Edge. Servizi mobili è una funzionalità che usa il proxy inverso. L'installazione di servizi di mobilità non consente di aggiungere funzionalità agli Edge Server, ma richiede la riconfigurazione del proxy inverso. La colonna <STRONG>obiettivo di installazione</STRONG> che elenca queste caratteristiche fornisce indicazioni per la pianificazione nella colonna associata in <STRONG>sezione o sezioni pianificazione di Edge Server</STRONG> per la pianificazione contemporanea di queste funzionalità da distribuire quando i server perimetrali sono installati e configurati.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identificare e mappare gli obiettivi di distribuzione


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Obiettivo di installazione</th>
<th>Documentazione sulla pianificazione di Edge Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>È stato deciso che un singolo server è sufficiente per i servizi Edge nell'infrastruttura. Si intende anche usare indirizzi IP privati per le interfacce esterne di Edge Server con NAT su Internet.</p>
<p>Usare questa sezione per la pianificazione se si distribuisce un singolo Edge Server nel perimetro. Si distribuirà un server perimetrale con indirizzi IP privati assegnati all'Edge Server e si utilizzerà NAT per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Singola topologia perimetrale consolidata con indirizzi IP privati e NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>È stato deciso che un singolo server è sufficiente per i servizi Edge nell'infrastruttura. Si intende anche usare indirizzi IP pubblici per le interfacce esterne di Edge Server a Internet.</p>
<p>Usare questa sezione per la pianificazione se si distribuisce un singolo Edge Server nel perimetro. Verrà distribuito un server perimetrale con indirizzi IP pubblici assegnati all'Edge Server. Al posto di NAT si userà il routing in questo scenario. L'indirizzo IP pubblico effettivo del server perimetrale viene reso disponibile per le connessioni degli utenti esterni.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>È stato deciso che l'elevata disponibilità dei servizi Edge è importante per gli utenti e si distribuiscono due o più server perimetrali in questo pool. Si intende anche usare indirizzi IP privati per le interfacce esterne di Edge Server con NAT su Internet.</p>
<p>Usare questa sezione per la pianificazione se si distribuisce un pool di Edge Server nel perimetro. Gli Edge Server verranno distribuiti con indirizzi IP privati assegnati all'Edge Server, usando il bilanciamento del carico DNS per distribuire le comunicazioni nel pool. Si utilizzerà NAT per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>È stato deciso che l'elevata disponibilità dei servizi Edge è importante per gli utenti e si distribuiscono due o più server perimetrali in questo pool. Si intende anche usare indirizzi IP pubblici per le interfacce esterne di Edge Server a Internet.</p>
<p>Usare questa sezione per la pianificazione se si distribuisce un pool di Edge Server nel perimetro. Gli Edge Server verranno distribuiti con indirizzi IP pubblici assegnati all'Edge Server, usando il bilanciamento del carico DNS per distribuire le comunicazioni nel pool. Invece di NAT, userai routing per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>È stato deciso che l'elevata disponibilità dei servizi Edge è importante per gli utenti e si distribuiscono due o più server perimetrali in questo pool usando un dispositivo di bilanciamento del carico hardware.</p>
<p>Usare questa sezione per la pianificazione se si distribuisce un pool di Edge Server nel perimetro. Gli Edge Server verranno distribuiti con indirizzi IP pubblici assegnati all'Edge Server, usando i dispositivi di bilanciamento del carico hardware per distribuire le comunicazioni nel pool. Invece di NAT, userai routing per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Gli scenari federativi consentono di pianificare la funzionalità che estenderà i tipi di partner con cui gli utenti possono comunicare.</p>
<ul>
<li><p>Federazione Lync Server</p></li>
<li><p>Office Communications Server Federation</p></li>
<li><p>Connettività per messaggistica istantanea pubblica</p></li>
<li><p>Federazione XMPP</p></li>
</ul></td>
<td><p>Pianificazione per gli scenari federativi</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Pianificazione per Lync Server 2013 e Office Communications Server Federation</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Pianificazione della connettività di messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>I servizi di mobilità vengono offerti tramite il proxy inverso. I servizi che consentono la mobilità per gli utenti esterni vengono distribuiti nel server front-end o nel pool Front-end. Per abilitare i servizi di mobilità per gli utenti esterni, è possibile creare o modificare le regole di pubblicazione esistenti nel proxy inverso.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Pianificazione della versione per dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> Nelle sezioni seguenti scenari sono disponibili architetture di riferimento, ad esempio DNS, definizioni di porta/protocollo e requisiti di certificato. Sono inclusi anche i diagrammi per le definizioni DNS, di porta/protocollo e per le esigenze dei certificati. I diagrammi forniranno un modello per compilare e distribuire ad altri team, ad esempio il team di rete dell'organizzazione, il team di infrastruttura a chiave pubblica e il team di distribuzione del server. L'obiettivo dei diagrammi è migliorare la comunicazione e garantire il successo quando si comunicano gli elementi di configurazione del server perimetrale necessari alle persone che faranno il lavoro di configurazione effettivo. È consigliabile usare i diagrammi e le architetture di riferimento associate per pianificare la distribuzione.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

