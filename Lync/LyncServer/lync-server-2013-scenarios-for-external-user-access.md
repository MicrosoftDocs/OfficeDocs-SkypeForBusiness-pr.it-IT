---
title: "Lync Server 2013: scenari per l'accesso degli utenti esterni"
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
ms.openlocfilehash: a237a971bbf98636b81fa028c9b64721364fca07
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Scenari per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Se si fornisce l'accesso degli utenti esterni per Lync Server 2013, è necessario distribuire almeno un server perimetrale e un proxy inverso nella rete perimetrale. Facoltativamente, è possibile distribuire un server Director o un pool di server Director nella rete interna.

Se è necessaria una maggiore capacità rispetto a un singolo server perimetrale in grado di fornire o se è necessaria una disponibilità elevata per la distribuzione del server perimetrale, è possibile configurare il bilanciamento del carico e distribuire più server perimetrali in un pool con bilanciamento del carico. Se nell'organizzazione sono presenti più data center, è possibile disporre di distribuzioni di server perimetrali o pool di Edge in più di una posizione. Tuttavia, è possibile designare solo una delle distribuzioni di server perimetrali come route di Federazione.

In questa sezione vengono definiti gli scenari per le distribuzioni di server perimetrali e le sezioni di pianificazione vengono mappate ai possibili scenari. Ad esempio, se la distribuzione richiede disponibilità elevata, Federazione con contatti di messaggistica e presenza estensibili e mobilità Lync, è necessario selezionare le voci corrispondenti nella tabella seguente in grado di soddisfare questi requisiti e utilizzare la sezioni di pianificazione a cui viene fatto riferimento per definire la distribuzione, come illustrato nel diagramma di flusso seguente.

**Processo di selezione degli scenari di distribuzione di server perimetrali**

![Diagramma di flusso di distribuzione di esempio](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagramma di flusso di distribuzione di esempio")

Utilizzando questo processo, è possibile pianificare e documentare la configurazione di tutte le funzionalità possibili che si intende distribuire per gli utenti. Tuttavia, è possibile aggiungere servizi di Federazione e mobilità dopo aver distribuito il server perimetrale e aver confermato l'operazione corretta prima di aggiungere altre caratteristiche. Il processo di aggiunta di funzionalità a una distribuzione di server perimetrali esistente è incluso nella sezione distribuzione. Per informazioni dettagliate sulla distribuzione, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) includendo la pianificazione per queste funzionalità durante il processo di pianificazione iniziale, è possibile prepararsi per i requisiti DNS, del firewall e dei certificati per le caratteristiche aggiunte, che consentono di acquisire i certificati e configurare i requisiti DNS e porta/protocollo in anticipo.

<div>


> [!TIP]  
> Se si prevede di installare i server perimetrali e il proxy inverso e quindi aggiungere le funzionalità in un secondo momento (ad esempio, Federazione e mobilità), determinare quali certificati saranno necessari per tutti i servizi dopo la distribuzione. La pianificazione e l'acquisizione dei certificati per tutte le funzionalità in anticipo, inizialmente distribuite o meno, consente di evitare di dover ordinare nuovi certificati per soddisfare i requisiti di federazione, ovvero nei server perimetrali, o il proxy inverso, ovvero per la mobilità Services).



</div>

<div>


> [!NOTE]  
> Tutti i servizi perimetrali vengono eseguiti su ogni server perimetrale. Non è possibile suddividere i servizi tra due server perimetrali diversi. Se si distribuisce un pool di server perimetrali per la scalabilità, tutti i servizi perimetrali vengono distribuiti su tutti i server perimetrali del pool. La Federazione XMPP, Office Communications Server e la Federazione di Lync Server, la connettività per la messaggistica istantanea pubblica e la mobilità client sono servizi aggiuntivi che possono essere distribuiti dopo la distribuzione del primo server perimetrale o del pool di Edge. I servizi Mobility sono una funzionalità che utilizza il proxy inverso. L'installazione dei servizi per dispositivi mobili non consente di aggiungere funzionalità ai server perimetrali, ma richiede la riconfigurazione del proxy inverso. La colonna <STRONG>obiettivo di installazione</STRONG> che elenca queste caratteristiche fornisce indicazioni sulla pianificazione nella colonna associata nella <STRONG>sezione pianificazione server perimetrale o sezioni</STRONG> per la pianificazione simultanea di queste funzionalità da distribuire quando i server perimetrali sono installati e configurati.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identificazione e associazione degli obiettivi di pianificazione


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Obiettivo dell'installazione</th>
<th>Documentazione relativa alla pianificazione del server perimetrale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Si è deciso che un solo server sia sufficiente per i servizi perimetrali nell'infrastruttura. Si intende inoltre utilizzare indirizzi IP privati per le interfacce esterne dei server perimetrali con NAT su Internet.</p>
<p>Utilizzare questa sezione per la pianificazione se si sta distribuendo un singolo server perimetrale. Verrà distribuito un server perimetrale con indirizzi IP privati assegnati al server perimetrale e verrà utilizzato NAT per fornire gli indirizzi IP pubblici per gli utenti esterni su Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Singolo server perimetrale consolidato con indirizzi IP privati e NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Si è deciso che un solo server sia sufficiente per i servizi perimetrali nell'infrastruttura. Si intende inoltre utilizzare indirizzi IP pubblici per le interfacce esterne dei server perimetrali su Internet.</p>
<p>Utilizzare questa sezione per la pianificazione se si sta distribuendo un singolo server perimetrale. Verrà distribuito un server perimetrale con indirizzi IP pubblici assegnati al server perimetrale. Anziché NAT, in questo scenario si utilizzerà il routing. L'indirizzo IP pubblico effettivo del server perimetrale viene reso disponibile per le connessioni utente esterne.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Perimetro consolidato singolo con indirizzi IP pubblici in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Si è deciso che l'elevata disponibilità dei servizi perimetrali è importante per gli utenti e si distribuiranno due o più server perimetrali nel pool. Si intende inoltre utilizzare indirizzi IP privati per le interfacce esterne dei server perimetrali con NAT su Internet.</p>
<p>Utilizzare questa sezione per la pianificazione se si sta distribuendo un pool di server perimetrali. Verranno distribuiti i server perimetrali con indirizzi IP privati assegnati al server perimetrale, utilizzando il bilanciamento del carico DNS per distribuire la comunicazione nel pool. Si utilizzerà NAT per fornire indirizzi IP pubblici per gli utenti esterni in Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Si è deciso che l'elevata disponibilità dei servizi perimetrali è importante per gli utenti e si distribuiranno due o più server perimetrali nel pool. Si intende anche utilizzare indirizzi IP pubblici per le interfacce esterne del server perimetrale su Internet.</p>
<p>Utilizzare questa sezione per la pianificazione se si sta distribuendo un pool di server perimetrali. Verranno distribuiti i server perimetrali con indirizzi IP pubblici assegnati al server perimetrale, utilizzando il bilanciamento del carico DNS per distribuire le comunicazioni tra il pool. Anziché NAT, si utilizzerà il routing per fornire indirizzi IP pubblici per gli utenti esterni in Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>È stato deciso che la disponibilità elevata dei servizi perimetrali è importante per gli utenti e che verranno distribuiti due o più server perimetrali in questo pool utilizzando un dispositivo di bilanciamento del carico hardware.</p>
<p>Utilizzare questa sezione per la pianificazione se si sta distribuendo un pool di server perimetrali. Verranno distribuiti i server perimetrali con indirizzi IP pubblici assegnati al server perimetrale, utilizzando dispositivi di bilanciamento del carico hardware per distribuire le comunicazioni tra il pool. Anziché NAT, si utilizzerà il routing per fornire indirizzi IP pubblici per gli utenti esterni in Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Gli scenari di federazione consentono di pianificare la funzionalità per estendere i tipi di partner con cui possono comunicare gli utenti.</p>
<ul>
<li><p>Federazione di Lync Server</p></li>
<li><p>Federazione di Office Communications Server</p></li>
<li><p>Connettività per messaggistica istantanea pubblica</p></li>
<li><p>Federazione XMPP</p></li>
</ul></td>
<td><p>Pianificazione per gli scenari di federazione</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 e Office Communications Server Federation</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Pianificazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>I servizi Mobility vengono offerti tramite il proxy inverso. I servizi che consentono la mobilità per gli utenti esterni sono distribuiti nel front end server o nel pool Front end. Per abilitare i servizi Mobility per gli utenti esterni, creare regole di pubblicazione o modificare quelle esistenti nel proxy inverso.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Pianificazione della funzionalità per dispositivi mobili in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> Nelle sezioni Scenari di seguito sono illustrate architetture di riferimento, esempi di DNS, definizioni di porte/protocolli e requisiti di certificati. Sono inoltre inclusi diagrammi per esigenze relative a DNS, definizioni di porte/protocolli e certificati. I diagrammi offrono un modello da compilare e distribuire ad altri team (ad esempio il team di rete, il team di infrastruttura di chiave pubblica e il team di distribuzione server dell'organizzazione). L'obiettivo dei diagrammi consiste nel migliorare la comunicazione e nel garantire il corretto funzionamento quando si comunicano gli elementi di configurazione del server perimetrale necessari agli utenti che eseguono la configurazione effettiva. Si consiglia di utilizzare i diagrammi e le architetture di riferimento associate per pianificare la distribuzione.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

