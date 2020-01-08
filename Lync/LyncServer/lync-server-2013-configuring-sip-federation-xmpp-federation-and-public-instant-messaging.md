---
title: Configurazione di federazione SIP, federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configurazione di federazione SIP, federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

Federazione, connettività di messaggistica istantanea pubblica e protocollo XMPP (Extensible Messaging and Presence Protocol) definiscono una classe diversa di utenti esterni: utenti federati. Gli utenti di una distribuzione di Lync Server federata o di una distribuzione XMPP hanno accesso a un set limitato di servizi e vengono autenticati dalla distribuzione esterna. Gli utenti remoti sono membri della distribuzione di Lync Server e hanno accesso a tutti i servizi offerti dalla distribuzione.

<div>


> [!NOTE]
> Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.



</div>

La connettività di messaggistica istantanea pubblica è un tipo speciale di federazione che consente a un client Lync Server di accedere ai partner di messaggistica istantanea pubblica configurati tramite Lync 2013. I partner di connettività di messaggistica istantanea pubblica correnti sono:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

Una configurazione della connettività di messaggistica istantanea pubblica consente agli utenti di Lync di accedere agli utenti di connettività di messaggistica istantanea pubblica tramite:

  - Messaggistica istantanea e presenza

  - Visibilità dei contatti della connettività di messaggistica istantanea pubblica nel client Lync

  - Conversazioni ISTANTANEe da persona a persona con contatti

  - Chiamate audio e video con utenti Windows Live

La Federazione di Lync Server definisce un accordo tra la distribuzione di Lync Server e altre distribuzioni di Office Communications Server 2007 R2 o Lync Server. Una configurazione federata di Lync Server consente agli utenti di Lync di accedere agli utenti federati:

  - Messaggistica istantanea e presenza

  - Creazione di contatti federati nel client Lync

La Federazione XMPP definisce una distribuzione esterna basata sul protocollo di messaggistica e presenza estensibile. Una configurazione XMPP consente agli utenti di Lync di accedere agli utenti di domini XMPP consentiti:

  - Messaggistica istantanea e presenza: solo persona a persona

  - Creazione di contatti federati XMPP nel client Lync

<div>


> [!IMPORTANT]
> La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk. Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Federazione esterna Edge Server, connettività di messaggistica istantanea pubblica e processo di distribuzione degli utenti XMPP


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
<td><p>Determinare le opzioni da aggiungere alla distribuzione di Edge esistente</p></td>
<td><p>Eseguire Generatore di topologie per modificare le impostazioni del server perimetrale e creare e pubblicare la topologia. La topologia di Edge esistente ripeterà le modifiche da Central Management store a Edge Server.</p></td>
<td><p>Gruppo amministratori di dominio e gruppo RTCUniversalServerAdmins</p>



> [!NOTE]
> È possibile modificare una topologia usando un account che è un membro del gruppo utenti locali, ma la pubblicazione di una topologia richiede un account membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia di server perimetrali e server Director in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Preparare la configurazione</p></td>
<td><ol>
<li><p>Verificare che i prerequisiti di sistema vengano soddisfatti.</p></li>
<li><p>Configurare i record DNS interni ed esterni per supportare la connettività di messaggistica istantanea pubblica, la federazione Lync e la Federazione XMPP</p></li>
<li><p>Configurare le porte e i protocolli nel firewall per supportare i tipi di federazione che si stanno distribuendo</p></li>
<li><p>Ottenere e installare i certificati pubblici. Il tempo necessario per ottenere i certificati dipende dall'autorità di certificazione (CA) che emette il certificato. Questo passaggio è facoltativo a questo punto della distribuzione. Se non si esegue questo passaggio a questo punto, è necessario eseguire questa operazione durante la configurazione di Edge Server. Impossibile avviare il servizio Edge Server fino a quando non vengono ottenuti i certificati</p></li>
</ol></td>
<td><p>Come appropriato per l'organizzazione, poiché questi ruoli sono in genere divisi tra numerosi gruppi di lavoro</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurare Edge Server per gli scenari federativi</p></td>
<td><ol>
<li><p>Trasportare il file di configurazione della topologia esportata in ogni Edge Server o consentire il completamento della replica</p></li>
<li><p>Eseguire di nuovo la distribuzione guidata per installare i componenti di supporto per la Federazione</p></li>
<li><p>Configurare gli Edge Server</p></li>
<li><p>Richiedere e installare certificati per ogni server perimetrale</p></li>
<li><p>Riavviare i servizi Edge Server</p></li>
</ol></td>
<td><p>Gruppo amministratori</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configurazione della federazione di Lync in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurazione della federazione di XMPP in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare il supporto per l'accesso degli utenti esterni.</p></td>
<td><ol>
<li><p>Usare l'accesso degli utenti esterni del pannello di controllo di Lync Server</p></li>
<li><p>Configurare i criteri di accesso esterno per abilitare le comunicazioni con utenti federati o utenti pubblici</p></li>
<li><p>Configurare i domini federati SIP per consentire o bloccare i domini</p></li>
<li><p>Abilitare i provider federati SIP per i provider di connettività di messaggistica istantanea pubblici</p></li>
<li><p>Configurare partner federati XMPP per dominio XMPP</p></li>
</ol></td>
<td><p>Gruppo RTCUniversalServerAdmins o account utente assegnato al ruolo CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare la configurazione del server perimetrale</p></td>
<td><p>Verificare la connettività del server e la replica dei dati di configurazione dai server interni</p></td>
<td><p>Per la verifica della replica, il gruppo RTCUniversalServerAdmins o l'account utente assegnato alla verifica CSAdministrator roleFor della connettività degli utenti, un utente per ogni tipo di utente federato</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifica della distribuzione dei componenti perimetrali in Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

