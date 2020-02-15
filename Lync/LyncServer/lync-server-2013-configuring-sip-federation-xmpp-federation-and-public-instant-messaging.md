---
title: Configurazione di federazione SIP, Federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d97966d0a5062b133e9802f97ff77934ba29300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configurazione di federazione SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

La federazione, la connettività per la messaggistica istantanea pubblica e il protocollo XMPP (Extensible Messaging and Presence Protocol) definiscono una classe diversa di utenti esterni, ovvero gli utenti federati. Gli utenti di una distribuzione di Lync Server federata o di una distribuzione XMPP dispongono dell'accesso a un insieme limitato di servizi e vengono autenticati dalla distribuzione esterna. Gli utenti remoti sono membri della distribuzione di Lync Server e hanno accesso a tutti i servizi offerti dalla distribuzione.

<div>


> [!NOTE]
> Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.



</div>

La connettività per la messaggistica istantanea pubblica è un tipo speciale di federazione che consente a un client di Lync Server di accedere ai partner di messaggistica istantanea pubblica configurati utilizzando Lync 2013. I partner di connettività per la messaggistica istantanea pubblica correnti sono:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

Una configurazione di connettività per la messaggistica istantanea pubblica consente agli utenti di Lync di accedere agli utenti di connettività per la messaggistica istantanea pubblica mediante:

  - Messaggistica istantanea e presenza

  - Visibilità dei contatti di connettività per la messaggistica istantanea pubblica nel client Lync

  - Conversazioni di messaggistica istantanea dirette con i contatti

  - Chiamate audio e video con utenti di Windows Live

La federazione di Lync Server definisce un accordo tra la distribuzione locale di Lync Server e altre distribuzioni di Office Communications Server 2007 R2 o Lync Server. Una configurazione federata di Lync Server consente agli utenti di Lync di accedere agli utenti federati mediante:

  - Messaggistica istantanea e presenza

  - Creazione di contatti federati nel client Lync

La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (Extensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di Lync di accedere agli utenti di dominio XMPP consentiti mediante:

  - Messaggistica istantanea e presenza (solo diretta)

  - Creazione di contatti federati XMPP nel client Lync.

<div>


> [!IMPORTANT]
> La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Processo di distribuzione della federazione esterna dei server perimetrali, della connettività per la messaggistica istantanea pubblica e degli utenti XMPP


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
<td><p>Determinare le opzioni da aggiungere alla distribuzione di server perimetrali esistente</p></td>
<td><p>Eseguire Generatore di topologie per modificare le impostazioni del server perimetrale e creare e pubblicare la topologia. La topologia perimetrale esistente consente di replicare le modifiche dall'archivio di gestione centrale al server perimetrale.</p></td>
<td><p>Gruppi Domain Admins e RTCUniversalServerAdmins</p>



> [!NOTE]
> È possibile modificare una topologia utilizzando un account membro del gruppo degli utenti locali, ma per la pubblicazione di una topologia è necessario un account membro dei gruppi Domain Admins e RTCUniversalServerAdmins.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia Edge e Director in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Effettuare la preparazione per l'impostazione</p></td>
<td><ol>
<li><p>Verificare che vengano soddisfatti i prerequisiti del sistema.</p></li>
<li><p>Configurare i record DNS interni ed esterni per supportare la connettività per la messaggistica istantanea pubblica, la federazione di Lync e la federazione XMPP</p></li>
<li><p>Configurare le porte e i protocolli sul firewall per supportare i tipi di federazione da distribuire</p></li>
<li><p>Ottenere e installare certificati pubblici. Il tempo necessario per ottenere i certificati dipende dall'autorità di certificazione (CA) che emette il certificato. Tale passaggio è facoltativo a questo punto della distribuzione. Se non si esegue questo passaggio in questa fase, sarà necessario eseguirlo durante la configurazione dei server perimetrali. Il servizio del server perimetrale non può essere avviato finché non si ottengono i certificati.</p></li>
</ol></td>
<td><p>A seconda dell'organizzazione, in quanto questi ruoli in genere sono divisi tra numerosi gruppi di lavoro</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Impostare i server perimetrali per gli scenari di federazione</p></td>
<td><ol>
<li><p>Trasportare in ogni server perimetrale il file di configurazione della topologia esportato o consentire il completamento della replica.</p></li>
<li><p>Eseguire di nuovo la Distribuzione guidata per installare i componenti per il supporto della federazione</p></li>
<li><p>Configurare i server perimetrali.</p></li>
<li><p>Richiedere e installare i certificati per ogni server perimetrale.</p></li>
<li><p>Riavviare i servizi dei server perimetrali.</p></li>
</ol></td>
<td><p>Gruppo Administrators</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configurazione della Federazione di Lync in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurazione della Federazione XMPP in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare il supporto per l'accesso degli utenti esterni</p></td>
<td><ol>
<li><p>Utilizzo dell'accesso utente esterno del pannello di controllo di Lync Server</p></li>
<li><p>Configurare i criteri di accesso esterno per consentire le comunicazioni con gli utenti federati o gli utenti pubblici.</p></li>
<li><p>Configurare i domini federati SIP per consentire o bloccare i domini</p></li>
<li><p>Abilitare i provider federati SIP per i provider di connettività per la messaggistica istantanea pubblica.</p></li>
<li><p>Configurare i partner federati XMPP per ogni dominio XMPP.</p></li>
</ol></td>
<td><p>Gruppo RTCUniversalServerAdmins o account utente assegnato al ruolo CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare la configurazione dei server perimetrali</p></td>
<td><p>Verificare la connettività dei server e la replica dei dati di configurazione dai server interni.</p></td>
<td><p>Per la verifica della replica, gruppo RTCUniversalServerAdmins o account utente assegnato al ruolo CSAdministrator. Per la verifica della connettività degli utenti, un utente per ogni tipo di utente federato</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifica della distribuzione di Edge in Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

