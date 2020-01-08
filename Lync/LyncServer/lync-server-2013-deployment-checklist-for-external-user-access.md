---
title: "Lync Server 2013: Elenco di controllo di distribuzione per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Elenco di controllo di distribuzione per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-04_

Prima di distribuire la rete perimetrale e implementare il supporto per gli utenti esterni, è necessario che siano già stati distribuiti i server interni di Microsoft Lync Server 2013, incluso un pool Front end o un server Standard Edition. Se si prevede di distribuire gli amministratori facoltativi nella rete interna, è consigliabile distribuirli anche prima della distribuzione di Edge Server. Per informazioni dettagliate sul processo di distribuzione di Director, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.

Microsoft Lync Server 2013 include strumenti per facilitare la pianificazione e la distribuzione di server interni e Edge Server. Al termine della topologia, pubblicare la definizione della topologia risultante nell'ambiente di produzione. A questo scopo, devi essere un membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** .

  - **Strumento di pianificazione**   Office Communications Server 2007 R2 include uno strumento di pianificazione e uno strumento di pianificazione del bordo che è possibile usare per facilitare la progettazione della topologia. In Lync Server 2010 questi due strumenti sono stati combinati in un unico strumento di pianificazione con funzionalità e funzionalità aggiuntive, ad esempio la raccolta di un numero di utenti pianificato, requisiti vocali, tipi di accesso utente esterno e opzioni federative. È inoltre possibile pianificare i parametri di rete dell'infrastruttura, ad esempio indirizzi IP, tipi di bilanciamento del carico e altre considerazioni sulla rete perimetrale.

  - ****   Generatore di topologia di Lync Server 2013 Builder di topologia consente di definire la topologia e i componenti. Generatore di topologia è essenziale per la distribuzione di server che esegue Lync Server 2013. Generatore di topologia pubblica i risultati in un Central Management store usato per configurare tutti i server che usano Lync Server 2013 nell'organizzazione. Non è possibile installare Lync Server 2013 nei server senza usare generatore di topologie.

Se hai progettato la topologia di Edge durante il processo di pianificazione, incluso l'esecuzione di generatore di topologie per definire la topologia di Edge, puoi usare questi risultati per avviare la distribuzione di Edge Server. Se non è stata completata la creazione della topologia di Edge o si vogliono modificare le informazioni specificate in precedenza, è necessario terminare l'uso di generatore di topologie prima di procedere con altri passaggi di distribuzione. Per informazioni dettagliate su come compilare la topologia, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Per informazioni dettagliate sullo strumento di pianificazione e sul generatore di topologie, vedere [inizio del processo di pianificazione per Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.

La tabella seguente offre una panoramica del processo di distribuzione di Edge Server. Per esaminare le decisioni di pianificazione che devono essere effettuate prima di distribuire l'accesso degli utenti esterni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> Le informazioni nella tabella seguente sono informate su una nuova distribuzione. Se sono stati distribuiti Edge Server in un ambiente Lync Server 2010, Office Communications Server 2007 R2 o Office Communications Server 2007, vedere la pagina relativa alla <A href="migration.md">migrazione</A> per informazioni dettagliate sulla migrazione a lync Server 2013. La migrazione non è supportata da versioni precedenti a Office Communications Server 2007 R2, tra cui Office Communications Server 2007, Live Communications Server 2005 e Live Communications Server 2003.



</div>

Per migliorare le prestazioni e la sicurezza di Edge Server e per facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce la rete perimetrale e i server Edge:

  - Distribuire Edge Server solo dopo aver testato e verificato l'operazione di Lync Server 2013 all'interno dell'organizzazione.

  - È consigliabile distribuire Edge Server in un gruppo di lavoro anziché in un dominio. Questo semplifica l'installazione e mantiene i servizi di dominio Active Directory fuori dalla rete perimetrale. L'individuazione di servizi di dominio Active Directory nella rete perimetrale può presentare un rischio significativo per la sicurezza.

  - L'aggiunta di un server perimetrale a un dominio completamente presente nella rete perimetrale è supportata, ma sconsigliata. Un server perimetrale come parte del dominio interno viola i limiti di rete attendibili, dove Internet è meno attendibile, la rete perimetrale è più attendibile di Internet e la rete interna è più attendibile. Un server perimetrale come membro del dominio fa automaticamente parte della rete più attendibile, ma risiede in una rete meno attendibile (il perimetro).

<div>

## <a name="deployment-process-for-edge-servers"></a>Processo di distribuzione per Edge Server


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Autorizzazioni</th>
<th>Documentazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Creare la topologia di Edge appropriata e determinare i componenti appropriati.</p></td>
<td><ul>
<li><p>Eseguire Generatore di topologie per configurare le impostazioni del server perimetrale e creare e pubblicare la topologia e quindi usare Lync Server Management Shell per esportare il file di configurazione della topologia.</p></li>
</ul></td>
<td><p>Gruppo <strong>Domain Admins</strong> e <strong>RTCUniversalServerAdmins</strong> o <strong>CsAdmins</strong> Group</p>
<div>

> [!NOTE]  
> Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma la pubblicazione di una topologia richiede un account che sia membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> .


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia di Edge e Director in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p>Prepararsi per la configurazione.</p></td>
<td><ol>
<li><p>Verificare che i prerequisiti di sistema vengano soddisfatti.</p></li>
<li><p>Configurare gli indirizzi IP (IPv4 e IPv6, se usati) per le interfacce di rete sia interne che pubbliche in ogni server perimetrale.</p></li>
<li><p>Configurare i record DNS interni ed esterni (host A e AAAA per IPv4 e IPv6), inclusa la configurazione del suffisso DNS nel computer da distribuire come server perimetrale.</p></li>
<li><p>Opzionale Creare e installare certificati pubblici. Il tempo necessario per ottenere i certificati dipende dall'autorità di certificazione (CA) che emette il certificato. Se non si esegue questo passaggio a questo punto, è necessario eseguire questa operazione durante l'installazione di Edge Server. I servizi Edge Server non possono essere avviati finché non vengono ottenuti e installati certificati.</p></li>
<li><p>Disposizione del supporto per la connettività di messaggistica istantanea pubblica, se la distribuzione prevede il supporto delle comunicazioni con Windows Live, AOL o Yahoo! utenti.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>


</div></li>
<li><p>Supporto di Provision per il supporto XMPP e federativo per Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, se la distribuzione utilizzerà questi</p></li>
<li><p>Configurare i firewall.</p></li>
</ol></td>
<td><p>Appropriato per l'organizzazione</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparazione per l'installazione di server nella rete perimetrale per Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Configurare il proxy inverso.</p></td>
<td><ul>
<li><p>Configurare il proxy inverso (ad esempio, per Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) nella rete perimetrale, ottenere i certificati pubblici necessari e configurare il regole di pubblicazione Web nel server proxy inverso.</p>
<p>Preparare il proxy inverso per i servizi di mobilità se si è pianificati per la mobilità e si distribuiscono i servizi di mobilità nel pool Front-end o nel server Standard Edition.</p></li>
</ul></td>
<td><p>Amministratore del gruppo <strong>Administrators</strong> o reverse proxy</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurazione di server proxy inverso per Lync Server 2013</a> nella documentazione di distribuzione</p></td>
</tr>
<tr class="even">
<td><p>Configurare un Director (facoltativo).</p></td>
<td><ul>
<li><p>Opzionale Installare e configurare uno o più direttori nella rete interna.</p></li>
</ul></td>
<td><p>Gruppo <strong>amministratori</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configurazione del Director in Lync Server 2013</a> nella documentazione di distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Configurare Edge Server.</p></td>
<td><ol>
<li><p>Installare il software prerequisiti.</p></li>
<li><p>Trasportare il file di configurazione della topologia esportata in ogni Edge Server.</p></li>
<li><p>Installare il software Lync Server 2013 in ogni Edge Server.</p></li>
<li><p>Configurare gli Edge Server.</p></li>
<li><p>Richiedere e installare certificati per ogni server perimetrale.</p></li>
<li><p>Avviare i servizi Edge Server.</p></li>
</ol></td>
<td><p>Gruppo <strong>amministratori</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configurazione di Edge Server in Lync server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p>Configurare la distribuzione per l'accesso degli utenti esterni.</p></td>
<td><ol>
<li><p>Usare il pannello di controllo di Lync Server per configurare il supporto per ognuna delle opzioni seguenti (se applicabile):</p>
<ul>
<li><p>Inoltro multimediale</p></li>
<li><p>Route federativo</p></li>
<li><p>Accesso remoto agli utenti</p></li>
<li><p>Federazione con Lync Server, Office Communications Server e Live Communications Server</p></li>
<li><p>Connettività per messaggistica istantanea pubblica</p></li>
<li><p>Federazione XMPP</p></li>
<li><p>Utenti anonimi</p></li>
</ul></li>
<li><p>Configurare gli account utente per l'accesso degli utenti remoti, la Federazione, la connettività per messaggistica istantanea pubblica, il supporto utenti XMPP e Anonymous (se applicabile)</p></li>
</ol></td>
<td><p>Gruppo <strong>RTCUniversalServerAdmins</strong> o account utente assegnato al ruolo <strong>CsAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Verificare la configurazione del server perimetrale.</p></td>
<td><ol>
<li><p>Verificare la connettività del server e la replica dei dati di configurazione dai server interni.</p></li>
<li><p>Verificare che gli utenti esterni possano connettersi, inclusi gli utenti remoti, gli utenti nei domini federati, gli utenti di messaggistica istantanea pubblica e gli utenti anonimi, in base alle esigenze della distribuzione.</p></li>
<li><p>Verificare la configurazione e la comunicazione con l'analizzatore connettività remota di Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Risolvere i problemi di configurazione e comunicazione</p></li>
</ol></td>
<td><p>Per la verifica della replica, il gruppo <strong>RTCUniversalServerAdmins</strong> o l'account utente assegnato al ruolo <strong>CsAdministrator</strong></p>
<p>Per la verifica della connettività degli utenti, un utente per ogni tipo di accesso utente esterno supportato</p>
<p>Utenti remoti</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifica della distribuzione di Edge in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

