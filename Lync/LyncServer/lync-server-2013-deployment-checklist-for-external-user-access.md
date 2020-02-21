---
title: "Lync Server 2013: elenco di controllo di distribuzione per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f2897434eb275b82ef9ab4ef78e32e99e8d0a5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Elenco di controllo di distribuzione per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-04_

Prima di distribuire la rete perimetrale e implementare il supporto per gli utenti esterni, è necessario che siano già stati distribuiti i server interni di Microsoft Lync Server 2013, tra cui un pool Front end o un server Standard Edition. Se si prevede di distribuire i Director facoltativi nella rete interna, è consigliabile distribuirli anche prima di distribuire i server perimetrali. Per informazioni dettagliate sul processo di distribuzione del Director, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.

Microsoft Lync Server 2013 include strumenti che facilitano la pianificazione e la distribuzione di entrambi i server interni e server perimetrali. Al completamento della topologia, pubblicare la definizione di topologia risultante nell'ambiente di produzione. A tale scopo, è necessario essere membri dei gruppi **Domain Admins** e **RTCUniversalServerAdmins**.

  - **Strumento di pianificazione**   Office Communications Server 2007 R2 includeva uno strumento di pianificazione e uno strumento di pianificazione Edge che è possibile utilizzare per semplificare la progettazione della topologia. In Lync Server 2010, questi due strumenti sono stati combinati in un unico strumento di pianificazione con caratteristiche e funzionalità aggiuntive, ad esempio la raccolta dei conteggi degli utenti pianificati, i requisiti vocali, i tipi di accesso degli utenti esterni e le opzioni di Federazione. Inoltre, è possibile pianificare i parametri di rete di un'infrastruttura, inclusi gli indirizzi IP, i tipi di servizio di bilanciamento del carico e altre considerazioni in merito alle reti perimetrali.

  - **Generatore di**   topologie in Generatore di topologie Lync Server 2013 consente di definire la topologia e i componenti. Generatore di topologie è essenziale per la distribuzione di server che eseguono Lync Server 2013. Il generatore di topologie pubblica i risultati in un archivio di gestione centrale utilizzato per configurare tutti i server che eseguono Lync Server 2013 nell'organizzazione. Non è possibile installare Lync Server 2013 nei server senza l'utilizzo di generatore di topologie.

Se è stata progettata la topologia perimetrale durante il processo di pianificazione, incluso l'esecuzione di generatore di topologie per definire la topologia perimetrale, è possibile utilizzare tali risultati per avviare la distribuzione del server perimetrale. Se la topologia perimetrale non è stata completata o si desidera modificare le informazioni precedentemente specificate, è necessario completare l'esecuzione di generatore di topologie prima di procedere con altri passaggi di distribuzione. Per informazioni dettagliate su come creare la topologia, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Per informazioni dettagliate sullo strumento di pianificazione e sul generatore di topologie, vedere [beginning the Planning Process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.

Nella tabella riportata di seguito viene fornita una panoramica del processo di distribuzione dei server perimetrali. Per esaminare le decisioni di pianificazione che devono essere apportate prima di distribuire l'accesso degli utenti esterni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> Le informazioni riportate nella tabella seguente fanno riferimento a una nuova distribuzione. Se sono stati distribuiti server perimetrali in un ambiente Lync Server 2010, Office Communications Server 2007 R2 o Office Communications Server 2007, vedere la pagina relativa alla <A href="migration.md">migrazione</A> per informazioni dettagliate sulla migrazione a lync Server 2013. La migrazione non è supportata da una versione precedente a Office Communications Server 2007 R2, tra cui Office Communications Server 2007, Live Communications Server 2005 e Live Communications Server 2003.



</div>

Per migliorare la sicurezza e le prestazioni dei server perimetrali e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuiscono la rete perimetrale e i server perimetrali:

  - Distribuire i server perimetrali solo dopo aver testato e verificato l'operazione di Lync Server 2013 all'interno dell'organizzazione.

  - Si consiglia di distribuire i server perimetrali in un gruppo di lavoro anziché in un dominio. In questo modo si semplifica l'installazione e si mantengono i Servizi di dominio Active Directory (AD DS) al di fuori della rete perimetrale. La presenza dei servizi AD DS nella rete perimetrale può infatti costituire un rischio di sicurezza significativo.

  - L'unione di un server perimetrale a un dominio situato interamente nella rete perimetrale è supportata ma non consigliata. Un server perimetrale come parte del dominio interno viola i limiti di attendibilità della rete, in cui Internet presenta attendibilità minima, la rete perimetrale attendibilità superiore e la rete interna attendibilità massima. Un server perimetrale come membro del dominio fa automaticamente parte della rete più attendibile, ma risiede in una rete meno attendibile (il perimetro).

<div>

## <a name="deployment-process-for-edge-servers"></a>Processo di distribuzione dei server perimetrali


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
<td><p>Creare la topologia perimetrale appropriata e determinare i componenti appropriati.</p></td>
<td><ul>
<li><p>Eseguire Generatore di topologie per configurare le impostazioni del server perimetrale e creare e pubblicare la topologia e quindi utilizzare Lync Server Management Shell per esportare il file di configurazione della topologia.</p></li>
</ul></td>
<td><p>Gruppo <strong>Domain Admins</strong> e gruppo <strong>RTCUniversalServerAdmins</strong> o <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> È possibile definire una topologia utilizzando un account membro del gruppo degli utenti locali, ma per la pubblicazione di una topologia è necessario un account membro dei gruppi <STRONG>Domain Admins</STRONG> e <STRONG>RTCUniversalServerAdmins</STRONG>.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia Edge e Director in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p>Preparare la configurazione.</p></td>
<td><ol>
<li><p>Verificare che vengano soddisfatti i prerequisiti del sistema.</p></li>
<li><p>Configurare gli indirizzi IP (IPv4 e IPv6, se utilizzati) per le interfacce di rete interne e pubbliche in ogni server perimetrale.</p></li>
<li><p>Configurare record DNS interni ed esterni (host A e AAAA per IPv4 e IPv6), inclusa la configurazione del suffisso DNS nel computer da distribuire come server perimetrale.</p></li>
<li><p>(Facoltativo) Creare e installare certificati pubblici. Il tempo necessario per ottenere i certificati dipende dall'Autorità di certificazione (CA) che emette il certificato. Se non si esegue questo passaggio in questa fase, sarà necessario eseguirlo durante l'installazione dei server perimetrali. I servizi dei server perimetrali non possono essere avviati se non si ottengono e installano i certificati.</p></li>
<li><p>Fornire il supporto per la connettività per messaggistica istantanea pubblica se la distribuzione deve supportare le comunicazioni con utenti di Windows Live, AOL o Yahoo!.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>


</div></li>
<li><p>Provisioning del supporto per il supporto di XMPP e federativo per Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, se la distribuzione utilizzerà questi</p></li>
<li><p>Configurare i firewall.</p></li>
</ol></td>
<td><p>In base all'organizzazione</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparazione per l'installazione dei server nella rete perimetrale per Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Configurare il proxy inverso.</p></td>
<td><ul>
<li><p>Configurare il proxy inverso (ad esempio, per Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) nella rete perimetrale, ottenere i certificati pubblici necessari e configurare la regole di pubblicazione Web nel server proxy inverso.</p>
<p>Preparare il proxy inverso per i servizi dei dispositivi mobili se si intende utilizzare tali dispositivi e distribuire i servizi nel pool Front End o nel server Standard Edition.</p></li>
</ul></td>
<td><p>Gruppo <strong>Administrators</strong> o amministratore del proxy inverso</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurazione dei server proxy inversi per Lync server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p>Configurare un server Director (facoltativo).</p></td>
<td><ul>
<li><p>(Facoltativo) Installare e configurare uno o più Director nella rete interna.</p></li>
</ul></td>
<td><p>Gruppo <strong>Administrators</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configurazione del Director in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Configurare i server perimetrali.</p></td>
<td><ol>
<li><p>Installare i prerequisiti software.</p></li>
<li><p>Trasportare in ogni server perimetrale il file di configurazione della topologia esportato.</p></li>
<li><p>Installare il software Lync Server 2013 in ogni server perimetrale.</p></li>
<li><p>Configurare i server perimetrali.</p></li>
<li><p>Richiedere e installare i certificati per ogni server perimetrale.</p></li>
<li><p>Avviare i servizi dei server perimetrali.</p></li>
</ol></td>
<td><p>Gruppo <strong>Administrators</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configurazione dei server perimetrali in Lync server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="even">
<td><p>Configurare la distribuzione per l'accesso degli utenti esterni.</p></td>
<td><ol>
<li><p>Utilizzare il pannello di controllo di Lync Server per configurare il supporto per ognuna delle seguenti operazioni:</p>
<ul>
<li><p>Media relay</p></li>
<li><p>Route di federazione</p></li>
<li><p>Accesso degli utenti remoti</p></li>
<li><p>Federazione con Lync Server, Office Communications Server e Live Communications Server</p></li>
<li><p>Connettività per messaggistica istantanea pubblica</p></li>
<li><p>Federazione XMPP</p></li>
<li><p>Utenti anonimi</p></li>
</ul></li>
<li><p>Configurare gli account utente per l'accesso degli utenti remoti, la federazione, la connettività per messaggistica istantanea pubblica e il supporto degli utenti anonimi (in base alle esigenze)</p></li>
</ol></td>
<td><p>Gruppo <strong>RTCUniversalServerAdmins</strong> o account utente assegnato al ruolo <strong>CSAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a> nella documentazione relativa alla distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Verificare la configurazione dei server perimetrali.</p></td>
<td><ol>
<li><p>Verificare la connettività dei server e la replica dei dati di configurazione dai server interni.</p></li>
<li><p>Verificare che gli utenti esterni possano connettersi, inclusi gli utenti remoti, gli utenti di domini federati, gli utenti di messaggistica istantanea pubblica e gli utenti anonimi, a seconda dei requisiti della distribuzione.</p></li>
<li><p>Verificare la configurazione e la comunicazione tramite l'analizzatore connettività remota di Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Risolvere i problemi di comunicazione e configurazione</p></li>
</ol></td>
<td><p>Per la verifica della replica, il gruppo <strong>RTCUniversalServerAdmins</strong> o l'account utente assegnato al ruolo <strong>CSAdministrator</strong></p>
<p>Per la verifica della connettività degli utenti, un utente per ogni tipo di accesso degli utenti esterni supportato</p>
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

