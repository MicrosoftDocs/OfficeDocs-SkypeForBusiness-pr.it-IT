---
title: 'Lync Server 2013: elenco di controllo di distribuzione per il servizio E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38e2cffcaa54df8d9a7bc3715d609ac4bc7d7b8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Elenco di controllo di distribuzione per il servizio E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Per pianificare in modo efficace la funzionalità Enhanced 9-1-1 (E9-1-1), assicurarsi di includere i requisiti di distribuzione seguenti:

  - Prerequisiti per la distribuzione di E9-1-1.

  - Passaggi necessari per la distribuzione di E9-1-1.

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>Prerequisiti per la distribuzione di E9-1-1

Prima di distribuire il servizio E9-1-1, è necessario che siano già stati distribuiti i server interni di Lync Server, tra cui un archivio di gestione centrale, un pool Front end o un server Standard Edition, uno o più Mediation Server o pool di Mediation, nonché i client di Lync Server. Inoltre, una distribuzione di E9-1-1 richiede un trunk SIP a un provider di servizi E9-1-1 qualificato o a un gateway ELIN (Emergency Location Identification Number) per la rete PSTN (Public Switched Telephone Network). Lync Server supporta l'utilizzo di provider di servizi E9-1-1 solo all'interno degli Stati Uniti.

</div>

<div>

## <a name="deployment-process"></a>Processo di distribuzione

Nella tabella seguente viene fornita una panoramica del processo di distribuzione di E9-1-1. Per informazioni dettagliate sui passaggi di distribuzione, vedere [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) nella documentazione relativa alla distribuzione.


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
<th>Documentazione relativa alla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurare gli utilizzi vocali, le route e le configurazioni trunk</p></td>
<td><ol>
<li><p>Creare un nuovo record di utilizzo PSTN. Si tratta dello stesso nome utilizzato per l'impostazione di <strong>utilizzo PSTN</strong> nei criteri percorso.</p></li>
<li><p>Creare o assegnare una route vocale al record di utilizzo PSTN creato nel passaggio precedente e quindi fare in modo che l'attributo del gateway punti al trunk SIP E9-1-1 o al gateway ELIN.</p></li>
<li><p>Per un provider di servizi E9-1-1 trunk SIP, impostare il trunk che gestirà le chiamate E9-1-1 sul SIP per passare i dati di PIDF-LO tramite il cmdlet <strong>Set-CsTrunkConfiguration – EnablePIDFLOSupport</strong> .</p></li>
<li><p>Facoltativamente, per un provider di servizi E9-1-1 trunk SIP creare o assegnare una route PSTN locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà utilizzata se la connessione al provider di servizi E9-1-1 non è disponibile. Se supportato dal provider di servizi E9-1-1, assegnare una regola di configurazione trunk al gateway che converte la stringa di composizione 911 nel numero DID (Direct Inward Dialing) del National/Regional Emergency Call Response Center (ECRC).</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurare una route vocale E9-1-1 in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Creare criteri percorso e assegnarli a utenti e subnet</p></td>
<td><ol>
<li><p>Esaminare il criterio percorso globale.</p></li>
<li><p>Creare un criterio percorso con un ambito a livello di utente. in alternativa, se l'organizzazione dispone di più siti con usi di emergenza diversi, creare un criterio percorso con un ambito a livello di rete.</p></li>
<li><p>Assegnare il criterio percorso ai siti di rete.</p></li>
<li><p>Aggiungere le subnet appropriate al sito di rete.</p></li>
<li><p>Optional Assegnare i criteri percorso ai criteri utente.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (eccetto per la creazione di criteri percorso)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Creare criteri percorso in Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Aggiungere un criterio percorso a un sito di rete in Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associare subnet a siti di rete per il servizio E9-1-1 in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurare il database delle posizioni</p></td>
<td><ol>
<li><p>Popolare il database con il mapping degli elementi di rete ai percorsi.</p></li>
<li><p>Per i gateway ELIN, aggiungere i numeri ELIN alla colonna &lt;CompanyName&gt; .</p></li>
<li><p>Configurare la connessione al provider di servizi E9-1-1 per la convalida degli indirizzi.</p></li>
<li><p>Convalidare gli indirizzi con il provider di servizi E9-1-1.</p></li>
<li><p>Pubblicare il database aggiornato.</p></li>
<li><p>Per i gateway ELIN, caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore PSTN.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configurare il database delle posizioni in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare le funzionalità avanzate (facoltativo)</p></td>
<td><ol>
<li><p>Configurare l'URL per l'applicazione SNMP.</p></li>
<li><p>Configurare l'URL per la posizione del servizio informazioni percorso secondario.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Configurare un'applicazione SNMP in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurare un servizio informazioni percorso secondario in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

