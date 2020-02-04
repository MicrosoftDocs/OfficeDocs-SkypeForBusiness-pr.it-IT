---
title: 'Lync Server 2013: classi e descrizioni dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Classi e descrizioni dello schema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

In questa sezione vengono descritte tutte le classi dello schema usate da Lync Server 2013.

<div>

## <a name="schema-classes-and-descriptions"></a>Classi e descrizioni dello schema


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe</th>
<th>Descrizione</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Destinatario della posta elettronica</p></td>
<td><p>Destinatario della messaggistica unificata di Exchange.</p></td>
<td><p>Questa classe ausiliaria viene condivisa con la messaggistica unificata di Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Questa classe è un contenitore per più contatti dell'applicazione e non contiene alcun attributo.</p></td>
<td><p>Novità di Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Questa classe contiene la voce per il punto di controllo del servizio per un'istanza di Unified Communications Application Services (UCAS).</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Questa classe fornisce un'associazione da un pool specifico al relativo servizio applicazione.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-ApplicationServer contiene gli attributi che rappresentano le impostazioni per le istanze del servizio applicazione.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (obsoleto)</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni correlate all'archiviazione.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (obsoleto)</p></td>
<td><p>Questa classe rappresenta un singolo server di archiviazione di messaggistica istantanea. Un'istanza di questa classe viene creata quando un computer viene attivato come server di archiviazione di messaggistica istantanea, ad esempio un computer in cui è installato il servizio di archiviazione di messaggistica istantanea.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Questa classe è un contenitore per più istanze di directory conferenza e non contiene alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per una specifica directory conferenza.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>SCP (Generic Service Control Point) per specificare il computer come server che usa Lync Server.</p></td>
<td><p>Nuovo in Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Questa classe ausiliaria contiene le impostazioni per una banca di Microsoft Lync Web App.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Questa classe contiene gli attributi che definiscono i domini configurati del registrar SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Questo contenitore di classi rappresenta un singolo servizio Edge di Access. Poiché un servizio di Access Edge viene distribuito nella rete perimetrale e i clienti in genere non consentono l'accesso a servizi di dominio Active Directory dalla rete perimetrale, le istanze del servizio Access Edge non vengono unite alla rete Active Directory della Intranet. Di conseguenza, i proxy di Access non vengono registrati automaticamente in servizi di dominio Active Directory. L'amministratore deve configurare manualmente l'esistenza di ogni istanza di Access Edge Services in servizi di dominio Active Directory.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Questa classe ausiliaria per msRTCSIP-MCU contiene gli attributi che rappresentano le impostazioni per i server di conferenza.</p></td>
<td><p>Novità di Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-MediationServer contiene gli attributi che rappresentano le impostazioni per i server di mediazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-Server contiene gli attributi che rappresentano le impostazioni per i server SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni correlate alla Federazione.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Questa classe contiene tutte le impostazioni che si applicano in una distribuzione di Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (obsoleto)</p></td>
<td><p>Questa classe rappresenta un singolo criterio di riunione di Office Communications Server.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Oggetto impostazione topologia globale locale.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Contenitore per contenere gli oggetti di impostazione della topologia globale.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Questa classe è un contenitore che rappresenta un'istanza di una regola di normalizzazione della posizione.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Questa classe viene creata dall'applicazione per i servizi di conferenza e contiene gli attributi usati per categorizzare i numeri di telefono per le conferenze per area geografica.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Questa classe è un contenitore per più istanze di mapping dei contatti di posizione e non contiene alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Questa classe è un contenitore che rappresenta un profilo di posizione specifico.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (obsoleto)</p></td>
<td><p>Questa classe è un contenitore per più profili di posizione e non contiene alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (obsoleto)</p></td>
<td><p>Questa classe è un contenitore per più regole di normalizzazione locali e non contiene alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Questa classe rappresenta un singolo server di conferenza.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Questa classe contiene più classi msRTCSIP-MCUFactory e non ha attributi.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Questa classe è un contenitore che rappresenta una factory di servizi di conferenza per un singolo tipo di supporto. Viene creata un'istanza di questa classe quando viene attivato il primo server di conferenza per il tipo specifico e il fornitore.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Questa classe fornisce un'associazione da un pool specifico alla propria factory di server di conferenza.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Questa classe contiene la voce per il punto di controllo del servizio di un Mediation Server.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (obsoleto)</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni delle riunioni configurabili.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Contenitore che archivia le impostazioni di mobilità globale.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un singolo server di monitoraggio.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (obsoleto)</p></td>
<td><p>Questa classe è un contenitore che rappresenta un'istanza di una route con costi minimi a un gateway o un set di gateway. Queste informazioni vengono usate da tutti i pool o i server aziendali che usano Standard Edition per instradare le chiamate in uscita alla rete PSTN (Public Switched Telephone Network) in modo più conveniente.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (obsoleto)</p></td>
<td><p>Questa classe è un contenitore per più route di costo inferiore e non contiene alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policy (obsolete)</p></td>
<td><p>Questa classe contiene più classi di criteri di Lync Server e non ha alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>Questa classe rappresenta un singolo pool di Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>Questa classe contiene più pool di Lync Server e non ha alcun attributo.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Questa classe rappresenta il punto di controllo pointservice del controllo del servizio di un pool. Gli utenti ospitati in un pool hanno il punto di attributo msRTCSIP-PrimaryHomeServer su un'istanza della classe.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>Contenitore in cui sono archiviate le impostazioni di presenza globale.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni utente gestite dai server di registrazione SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (obsoleto)</p></td>
<td><p>Questa classe è un contenitore che rappresenta un'istanza dell'utilizzo di una route telefonica. La classe di utilizzo di una route telefonica è costituita da un campo attributo e da un campo Description. Il campo attributo definisce un tipo di utilizzo. Il campo Description consente agli amministratori di descrivere l'utilizzo di questo attributo nell'itinerario telefonico.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (obsoleto)</p></td>
<td><p>Questa classe contiene più istanze della classe msRTCSIP-RouteUsage e non ha alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-search</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che limitano e controllano l'ambito dei risultati della ricerca.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Questa classe rappresenta un singolo server in cui è in uso Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>Questa classe contiene il contenitore di impostazioni globali e gli oggetti msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un server di conferenza attendibile.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Questa classe contiene più istanze della classe msRTCSIP-TrustedMCU e non ha alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Questa classe contiene più classi msRTCSIP-TrustedProxy e non contiene alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Questa classe è un contenitore che rappresenta un server che gestisce il server proxy. Viene creata un'istanza di questa classe quando si attiva un nuovo server proxy in un computer collegato a servizi di dominio Active Directory.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un server attendibile.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Questa classe è un contenitore che rappresenta un servizio attendibile instradabile con un indirizzo GRUU (Globally User Agent URI). Viene creata un'istanza di questa classe quando viene attivato un nuovo server considerato attendibile da Lync Server. Questo server attendibile deve essere associato a un dominio Active Directory.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Questa classe è un contenitore per più server GRUU e non contiene alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un componente Web attendibile.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Questa classe contiene più istanze della classe msRTCSIP-TrustedWebComponentServer e non ha alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (obsoleto)</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi correlati alle comunicazioni unificate.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>Questa classe contiene il punto di controllo del controllo del servizio pointservice per Internet Information Server (IIS). Identifica un server come server di componenti Web.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Questa classe fornisce un'associazione da un pool specifico ai componenti Web che verranno usati dal pool.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-WebComponents contiene gli attributi che rappresentano le impostazioni per i componenti Web.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

