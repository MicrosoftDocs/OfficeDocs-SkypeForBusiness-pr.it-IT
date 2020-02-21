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
ms.openlocfilehash: 4e7dd3deff8a64b1dd153a9717d0ce2be2f28de8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Classi e descrizioni dello schema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

In questa sezione vengono descritte tutte le classi dello schema utilizzate da Lync Server 2013.

<div>

## <a name="schema-classes-and-descriptions"></a>Classi e descrizioni di schemi


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
<td><p>Mail-Recipient</p></td>
<td><p>Destinatario di posta elettronica di messaggistica unificata di Exchange.</p></td>
<td><p>Questa classe ausiliaria è condivisa con la messaggistica unificata di Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Questa classe è un contenitore per più contatti applicazione e non include alcun attributo.</p></td>
<td><p>Nuovo in Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Questa classe contiene la voce relativa al punto di controllo del servizio per un'istanza dei servizi per applicazioni per comunicazioni unificate</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Questa classe fornisce un'associazione tra un pool specifico e il relativo servizio applicazione.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-ApplicationServer contiene gli attributi che rappresentano le impostazioni per le istanze del servizio dell'applicazione.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (obsoleta)</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni relative all'archiviazione.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (obsoleta)</p></td>
<td><p>Questa classe rappresenta un singolo server di archiviazione della messaggistica istantanea. Viene creata un'istanza di questa classe quando un computer viene attivato come server di archiviazione della messaggistica istantanea, come nel caso di un computer in cui è installato il servizio di archiviazione della messaggistica istantanea.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Questa classe è un contenitore per più istanze di directory conferenze e non include alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per una directory conferenze specifica.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>Punto di controllo del servizio generico (SCP) per specificare il computer come server che esegue Lync Server.</p></td>
<td><p>Nuovo in Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Questa classe ausiliaria contiene le impostazioni per una banca di Microsoft Lync Web App.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Questa classe contiene gli attributi che definiscono i domini configurati della funzione di registrazione SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Questo contenitore di classi rappresenta un singolo servizio Access Edge. Poiché un servizio Access Edge viene distribuito nella rete perimetrale e i clienti in genere non consentono l'accesso ai servizi di dominio Active Directory dalla rete perimetrale, le istanze del servizio Access Edge non vengono unite alla rete Active Directory della Intranet. I proxy di accesso non vengono pertanto registrati automaticamente in Servizi di dominio Active Directory. L'amministratore deve configurare manualmente l'esistenza di ogni istanza del servizio Access Edge in servizi di dominio Active Directory.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-MCU contiene gli attributi che rappresentano le impostazioni per i server per conferenze.</p></td>
<td><p>Nuovo in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-MediationServer contiene gli attributi che rappresentano le impostazioni per i server Mediation Server.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-Server contiene gli attributi che rappresentano le impostazioni per i server SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni relative alla federazione.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Questa classe contiene tutte le impostazioni che si applicano in una distribuzione di Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (obsoleta)</p></td>
<td><p>Questa classe rappresenta un singolo criterio di riunione di Office Communications Server.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Oggetto impostazione della topologia globale locale.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Contenitore di oggetti impostazione della topologia globale.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Questa classe è un contenitore che rappresenta un'istanza di una regola di normalizzazione della località.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Questa classe viene creata dall'applicazione Operatore Conferenza e contiene gli attributi utilizzati per classificare i numeri di telefono per le conferenze in base all'area geografica.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Questa classe è un contenitore per più istanze di mapping dei contatti località e non include alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Questa classe è un contenitore che rappresenta un profilo località specifico.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (obsoleta)</p></td>
<td><p>Questa classe è un contenitore per più profili località e non include alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (obsoleta)</p></td>
<td><p>Questa classe è un contenitore per più regole di normalizzazione locale e non include alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Questa classe rappresenta un singolo server per conferenze.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Questa classe contiene più classi msRTCSIP-MCUFactory e non include alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Questa classe è un contenitore che rappresenta un componente Conferencing Server Factory per un singolo tipo di supporto. Viene creata un'istanza di questa classe quando viene attivato il primo server per conferenze per questo tipo e questo fornitore specifici.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Questa classe fornisce un'associazione tra un pool specifico e il relativo componente Conferencing Server Factory.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Questa classe contiene la voce relativa al punto di controllo del servizio di Mediation Server.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (obsoleta)</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni configurabili per le riunioni.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Contenitore in cui vengono archiviate le impostazioni per dispositivi mobili globali.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un singolo Monitoring Server.</p></td>
<td><p>Nuovo in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (obsoleta)</p></td>
<td><p>Questa classe è un contenitore che rappresenta un'istanza di Least Cost Routing a un gateway o un insieme di gateway. Queste informazioni vengono utilizzate da tutti i pool o Server Enterprise che eseguono la versione Standard Edition per instradare le chiamate in uscita alla rete PSTN nel modo più economico possibile.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (obsoleta)</p></td>
<td><p>Questa classe è un contenitore per più istanze di Least Cost Routing e non include alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (obsoleta)</p></td>
<td><p>Questa classe contiene più classi di criteri di Lync Server e non dispone di alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>Questa classe rappresenta un singolo pool di Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>Questa classe contiene più pool di Lync Server e non dispone di alcun attributo.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Questa classe rappresenta il punto di controllo del servizio di un pool. L'attributo msRTCSIP-PrimaryHomeServer degli utenti ospitati in un pool punta a un'istanza di questa classe.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>Contenitore in cui vengono archiviate le impostazioni presenza globali.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni utente gestite dai server di registrazione SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (obsoleta)</p></td>
<td><p>Questa classe è un contenitore che rappresenta un'istanza di un utilizzo di route telefonica. Una classe utilizzo di route telefonica è costituita da un campo attributo e da un campo descrizione. Il campo attributo definisce un tipo di utilizzo. Il campo descrizione consente agli amministratori di descrivere l'utilizzo di questo attributo nella route telefonica.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (obsoleta)</p></td>
<td><p>Questa classe contiene più istanze della classe msRTCSIP-RouteUsage e non include alcun attributo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-search</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che limitano e controllano l'ambito dei risultati della ricerca.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Questa classe rappresenta un singolo server che esegue Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>Questa classe contiene il contenitore delle impostazioni globali e gli oggetti msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un server per conferenze trusted.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Questa classe contiene più istanze della classe msRTCSIP-TrustedMCU e non include alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Questa classe contiene più classi msRTCSIP-TrustedProxy e non include alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Questa classe è un contenitore che rappresenta un server che esegue un server proxy. Viene creata un'istanza di questa classe quando si attiva un nuovo server proxy in un computer che fa parte di Servizi di dominio Active Directory.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un server trusted.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Questa classe è un contenitore che rappresenta un servizio trusted instradabile utilizzando un indirizzo GRUU (Globally Routable User Agent URI). Viene creata un'istanza di questa classe quando viene attivato un nuovo server considerato attendibile da Lync Server. Il server trusted deve fare parte del dominio di Active Directory.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Questa classe è un contenitore per più server GRUU e non include alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Questa classe contiene gli attributi che rappresentano le impostazioni per un server Web Components Server trusted.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Questa classe contiene più istanze della classe msRTCSIP-TrustedWebComponentServer e non include alcun attributo.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (obsoleta)</p></td>
<td><p>Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi relativi alle comunicazioni unificate.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>Questa classe contiene il punto di controllo del servizio di IIS (Internet Information Server) e identifica un server come Web Components Server.</p></td>
<td><p>Nuovo in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Questa classe fornisce un'associazione tra un pool specifico e i componenti Web che verranno utilizzati dal pool.</p></td>
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

