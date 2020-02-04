---
title: 'Lync Server 2013: Opzioni di distribuzione SIP diretta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88dd5a576e467fbca25e9f467bd168fd6401d17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Opzioni di distribuzione SIP diretta in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

In questo argomento vengono fornite topologie ad esempio per la distribuzione di connessioni SIP dirette.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server autonomo

Se l'organizzazione usa una delle distribuzioni descritte in questa sezione, è possibile usare Lync Server 2013 come unica soluzione per la telefonia per parte o tutta l'organizzazione. Questa sezione descrive in dettaglio le distribuzioni seguenti:

  - **Distribuzione incrementale:** Questa opzione presuppone che si disponga di un'infrastruttura PBX (Private Branch Exchange) esistente e che si voglia inserire in modo incrementale la voce aziendale in gruppi o team più piccoli all'interno dell'organizzazione.

  - **Distribuzione solo VoIP di Lync Server:** questa opzione presuppone che si stia pensando di distribuire Enterprise Voice in un sito che non ha un'infrastruttura di telefonia tradizionale.

<div>

## <a name="incremental-deployment"></a>Distribuzione incrementale

Nella distribuzione incrementale Lync Server 2013 è l'unica soluzione di telefonia per singoli team o reparti, mentre gli altri utenti di un'organizzazione continuano a usare un PBX. Questa strategia di distribuzione incrementale offre un modo per introdurre la telefonia IP nella tua azienda attraverso programmi pilota controllati. I gruppi di lavoro le cui esigenze di comunicazione sono meglio serviti da Microsoft Unified Communications vengono spostati in Enterprise Voice, mentre altri utenti restano nel PBX esistente. È possibile eseguire la migrazione di altri gruppi di lavoro a VoIP aziendale, se necessario.

L'opzione incrementale è consigliata se sono presenti gruppi di utenti chiaramente definiti con requisiti di comunicazione comuni e che si prestano alla gestione centralizzata. Questa opzione è efficace anche se sono presenti team o reparti distribuiti su aree geografiche estese, in cui i risparmi in spese interurbane possono essere significativi. In realtà, questa opzione è utile per creare team virtuali i cui membri potrebbero essere sparsi in tutto il mondo. È possibile creare, modificare o sciogliere tali team in risposta rapida a requisiti aziendali mutevoli.

La figura seguente mostra la topologia generica per la distribuzione di VoIP aziendale dietro un PBX. Questa è la topologia consigliata per la distribuzione incrementale.

**Opzione di distribuzione incrementale**

![Diagramma dell'opzione di migrazione dipartimentale (di reparto)](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramma dell'opzione di migrazione dipartimentale (di reparto)")

<div>


> [!NOTE]  
> Se si connette la distribuzione di Lync Server a un partner SIP diretto certificato, non è necessario un gateway PSTN (Public Switched Telephone Network) tra il Mediation Server e il PBX. Per un elenco dei partner SIP diretti certificati, vedere il sito Web Microsoft Unified Communications Open Interoperability Program <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.



</div>

<div>


> [!NOTE]  
> Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.



</div>

In questa topologia sono abilitati i reparti o i gruppi di lavoro selezionati per VoIP aziendale. Un gateway PSTN collega il gruppo di lavoro abilitato VoIP (Voice over Internet Protocol) al PBX. Gli utenti abilitati per VoIP aziendale, inclusi i dipendenti remoti, comunicano tramite la rete IP. Le chiamate effettuate dagli utenti di VoIP aziendale alla rete PSTN e ai colleghi che non sono abilitate per VoIP aziendale vengono instradate al gateway PSTN appropriato. Le chiamate di colleghi che si trovano ancora nel sistema PBX o dai chiamanti della rete PSTN vengono instradate al gateway PSTN, che inoltra le chiamate a Lync Server per il routing.

Esistono due configurazioni consigliate per connettere Enterprise Voice a un'infrastruttura PBX esistente per l'interoperabilità: VoIP aziendale dietro il PBX e VoIP aziendale davanti al PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>VoIP aziendale dietro il PBX

Quando Enterprise Voice viene distribuita dietro il PBX, tutte le chiamate dalla rete PSTN arrivano al PBX, che instrada le chiamate agli utenti di VoIP aziendale a un gateway PSTN e chiama gli utenti PBX al PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>VoIP aziendale davanti al PBX

Quando Enterprise Voice viene distribuita davanti al PBX, tutte le chiamate arrivano al gateway PSTN, che instrada le chiamate per gli utenti di VoIP aziendale a Lync Server e chiama gli utenti PBX al PBX. Le chiamate alla rete PSTN sia dagli utenti VoIP aziendali che da quelli PBX vengono instradate tramite il network IP al gateway PSTN più efficiente rispetto ai costi. La tabella seguente mostra i vantaggi e gli svantaggi di questa configurazione.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Vantaggi e svantaggi della distribuzione di VoIP aziendale davanti al PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Vantaggi</th>
<th>Svantaggi</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Il PBX serve ancora agli utenti non abilitati per VoIP aziendale.</p></td>
<td><p>I gateway esistenti potrebbero non supportare le caratteristiche o le capacità desiderate.</p></td>
</tr>
<tr class="even">
<td><p>PBX gestisce tutti i dispositivi precedenti.</p></td>
<td><p>Richiede un trunk dal gateway al PBX e dal gateway al server Mediation. Potrebbe essere necessario un numero maggiore di Trunks dal provider di servizi.</p></td>
</tr>
<tr class="odd">
<td><p>Gli utenti di VoIP aziendale mantengono gli stessi numeri di telefono.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Distribuzione solo VoIP di Lync Server

Enterprise Voice offre nuove aziende e nuovi siti di Office per le aziende esistenti, con l'opportunità di implementare una soluzione VoIP completa senza doversi preoccupare dell'integrazione PBX o di incorrere in una sostanziale distribuzione e manutenzione costi di un'infrastruttura IP-PBX. Questa soluzione supporta sia i lavoratori in loco che i dipendenti remoti.

In questa distribuzione tutte le chiamate vengono instradate tramite la rete IP. Le chiamate alla rete PSTN vengono instradate al gateway PSTN appropriato. Lync 2013 o Lync Phone Edition funge da softphone. Il controllo delle chiamate remote non è disponibile e non è necessario perché non ci sono telefoni PBX da controllare dagli utenti. I servizi di segreteria telefonica e di operatore automatico sono disponibili tramite la distribuzione facoltativa della messaggistica unificata di Exchange.

<div>


> [!NOTE]  
> Oltre all'infrastruttura di rete necessaria per supportare Lync Server 2013, una distribuzione solo VoIP può usare un piccolo gateway qualificato per il supporto di fax e dispositivi analogici.



</div>

La figura seguente mostra una topologia tipica per una distribuzione solo VoIP.

**Opzione di distribuzione solo VoIP**

![Opzione di distribuzione vergine](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opzione di distribuzione vergine")

<div>


> [!NOTE]  
> Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

