---
title: 'Lync Server 2013: elenco di controllo della distribuzione per E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9a48ba3d999e55106298d7419e4590147e1e9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Elenco di controllo della distribuzione per E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Per pianificare efficacemente la 9-1-1 avanzata (E9-1-1), assicurarsi di includere i requisiti di distribuzione seguenti:

  - Prerequisiti per la distribuzione di E9-1-1.

  - Passaggi necessari per distribuire E9-1-1.

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>Prerequisiti di distribuzione per E9-1-1

Prima di distribuire E9-1-1, è necessario che siano già stati distribuiti i server interni di Lync Server, inclusi un Central Management store, un pool Front end o un server Standard Edition, uno o più server di mediazione o pool di Mediation Server e i client di Lync Server. Inoltre, una distribuzione di E9-1-1 richiede un trunk SIP per un provider di servizi E9-1-1 qualificato o un gateway ELIN (Emergency Location Identification Number) per la rete PSTN (Public Switched Telephone Network). Lync Server supporta l'uso dei provider di servizi E9-1-1 solo all'interno degli Stati Uniti.

</div>

<div>

## <a name="deployment-process"></a>Processo di distribuzione

La tabella seguente offre una panoramica del processo di distribuzione di E9-1-1. Per informazioni dettagliate sui passaggi di distribuzione, vedere [configurare 9-1-1 avanzato in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) nella documentazione relativa alla distribuzione.


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
<th>Ruoli</th>
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurare l'utilizzo delle voci, le rotte e le configurazioni trunk</p></td>
<td><ol>
<li><p>Creare un nuovo record di utilizzo PSTN. Si tratta dello stesso nome usato per l'impostazione <strong>utilizzo PSTN</strong> nei criteri posizione.</p></li>
<li><p>Creare o assegnare una route vocale al record di utilizzo PSTN creato nel passaggio precedente e quindi posizionare l'attributo gateway sul trunk SIP E9-1-1 o sul gateway ELIN.</p></li>
<li><p>Per un provider di servizi E9-1-1 trunk SIP, imposta il trunk che gestirà le chiamate E9-1-1 tramite il SIP per passare i dati di PIDF-LO usando il cmdlet <strong>Set-CsTrunkConfiguration-EnablePIDFLOSupport</strong> .</p></li>
<li><p>Facoltativamente, per un provider di servizi E9-1-1 trunk SIP, crea o assegna una route PSTN locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà usata se la connessione al provider di servizi E9-1-1 non è disponibile. Se supportata dal provider di servizi E9-1-1, assegna una regola di configurazione trunk al gateway che converte la stringa di chiamata di 911 nel numero di chiamata diretta (DID) del centro di risposta alle chiamate di emergenza nazionali/regionali (ECRC).</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurare una route vocale E9-1-1 in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Creare criteri di posizione e assegnarli a utenti e subnet</p></td>
<td><ol>
<li><p>Esaminare il criterio della posizione globale.</p></li>
<li><p>Creare un criterio di posizione con un ambito a livello di utente; in alternativa, se l'organizzazione ha più di un sito con diversi usi di emergenza, crea un criterio di posizione con un ambito a livello di rete.</p></li>
<li><p>Assegnare i criteri di posizione ai siti di rete.</p></li>
<li><p>Aggiungere le subnet appropriate al sito di rete.</p></li>
<li><p>Opzionale Assegnare i criteri di posizione ai criteri degli utenti.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (ad eccezione della creazione di criteri di posizione)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Creare criteri di posizione in Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Aggiungere un criterio di posizione a un sito di rete in Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associare subnet a siti di rete per E9-1-1 in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurare il database di percorso</p></td>
<td><ol>
<li><p>Popolare il database con un mapping degli elementi di rete alle posizioni.</p></li>
<li><p>Per i gateway ELIN, aggiungere i numeri ELIN alla colonna &lt;CompanyName&gt; .</p></li>
<li><p>Configurare la connessione al provider di servizi E9-1-1 per la convalida degli indirizzi.</p></li>
<li><p>Convalidare gli indirizzi con il provider di servizi E9-1-1.</p></li>
<li><p>Pubblicare il database aggiornato.</p></li>
<li><p>Per i gateway ELIN, caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore PSTN.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configurare il database della posizione in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare le funzionalità avanzate (facoltativo)</p></td>
<td><ol>
<li><p>Configurare l'URL per l'applicazione SNMP.</p></li>
<li><p>Configurare l'URL per la posizione del servizio informazioni sulla posizione secondaria.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Configurare un'applicazione SNMP in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurare un servizio di informazioni sulla posizione secondaria in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

