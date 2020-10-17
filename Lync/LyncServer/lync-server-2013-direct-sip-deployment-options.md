---
title: 'Lync Server 2013: opzioni di distribuzione SIP dirette'
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
ms.openlocfilehash: 7aaecb9bd7b5fc4f144236f83f85f9e1e192784f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529113"
---
# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Opzioni di distribuzione SIP dirette in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

In questo argomento vengono illustrate le topologie di esempio per la distribuzione di connessioni SIP dirette.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Stand-Alone di Lync Server

Se nell'organizzazione viene utilizzata una delle distribuzioni descritte in questa sezione, è possibile utilizzare Lync Server 2013 come unica soluzione di telefonia per parte o per tutte le organizzazioni. In questa sezione vengono descritte dettagliatamente le distribuzioni seguenti:

  - **Distribuzione incrementale:** Questa opzione presuppone che si disponga di un'infrastruttura PBX (Private Branch Exchange) esistente e che si desideri introdurre la voce di VoIP aziendale in modo incrementale ai gruppi o ai team più piccoli all'interno dell'organizzazione.

  - **Distribuzione di solo VoIP di Lync Server:** questa opzione presuppone che si stia valutando la possibilità di distribuire VoIP aziendale in un sito che non dispone di un'infrastruttura di telefonia tradizionale.

<div>

## <a name="incremental-deployment"></a>Distribuzione incrementale

Nella distribuzione incrementale, Lync Server 2013 è l'unica soluzione di telefonia per singoli team o reparti, mentre gli altri utenti di un'organizzazione continuano a usare un sistema PBX. Questa strategia di distribuzione incrementale consente di introdurre telefonia IP all'interno dell'organizzazione tramite programmi pilota controllati. I gruppi di lavoro i cui bisogni di comunicazione sono meglio serviti dalle comunicazioni unificate Microsoft vengono spostati in VoIP aziendale, mentre altri utenti restano nel PBX esistente. È possibile eseguire la migrazione di altri gruppi di lavoro in VoIP aziendale, in base alle esigenze.

L'opzione incrementale è consigliata se si dispone di gruppi di utenti chiaramente definiti che dispongono di requisiti di comunicazione comuni e che si prestano alla gestione centralizzata. Questa opzione è efficace anche se si dispone di team o reparti distribuiti su aree geografiche estese, in cui il risparmio delle tariffe interurbane può essere significativo. In effetti, questa opzione è utile per creare team virtuali i cui membri possono essere sparsi in tutto il mondo. È possibile creare, modificare o sciogliere tali team in risposta rapida allo spostamento dei requisiti aziendali.

Nella figura seguente viene illustrata la topologia generica per la distribuzione di VoIP aziendale dietro un sistema PBX. Questa è la topologia consigliata per la distribuzione incrementale.

**Opzione di distribuzione incrementale**

![Diagramma dell'opzione di migrazione dipartimentale](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramma dell'opzione di migrazione dipartimentale")

<div>


> [!NOTE]  
> Se si sta connettendo la distribuzione di Lync Server a un partner SIP diretto certificato, non è necessario un gateway PSTN (Public Switched Telephone Network) tra il Mediation Server e il sistema PBX. Per un elenco di partner diretti SIP certificati, vedere il sito Web Microsoft Unified Communications Open Interoperability Program all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A> .



</div>

<div>


> [!NOTE]  
> Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata). Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.



</div>

In questa topologia, i reparti o i gruppi di lavoro selezionati sono abilitati per VoIP aziendale. Un gateway PSTN collega il gruppo di lavoro abilitato VoIP (Voice over Internet Protocol) al sistema PBX. Gli utenti abilitati per VoIP aziendale, compresi i lavoratori remoti, comunicano tra la rete IP. Le chiamate effettuate da utenti di VoIP aziendale alla rete PSTN e ai colleghi che non sono abilitati per VoIP aziendale vengono instradate al gateway PSTN appropriato. Le chiamate provenienti da colleghi che sono ancora nel sistema PBX o dai chiamanti sulla rete PSTN vengono instradate al gateway PSTN, che inoltra le chiamate a Lync Server per il routing.

Sono disponibili due configurazioni consigliate per connettere VoIP aziendale a un'infrastruttura PBX esistente per l'interoperabilità: Enterprise Voice behind the PBX and Enterprise Voice di fronte al sistema PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>VoIP aziendale dietro il sistema PBX

Quando Enterprise Voice viene distribuita dietro il sistema PBX, tutte le chiamate provenienti dalla rete PSTN giungono al PBX, che instrada le chiamate agli utenti di VoIP aziendale verso un gateway PSTN e chiama gli utenti PBX al sistema PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>VoIP aziendale di fronte al sistema PBX

Quando Enterprise Voice viene distribuita davanti al sistema PBX, tutte le chiamate arrivano al gateway PSTN, che instrada le chiamate per gli utenti di VoIP aziendale a Lync Server e chiama gli utenti PBX al sistema PBX. Le chiamate alla rete PSTN da parte di utenti di VoIP aziendale e PBX vengono instradate tramite la Network IP al gateway PSTN più conveniente. Nella tabella seguente vengono illustrati i vantaggi e gli svantaggi di questa configurazione.

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
<td><p>Il sistema PBX serve ancora gli utenti non abilitati per VoIP aziendale.</p></td>
<td><p>I gateway esistenti potrebbero non supportare le caratteristiche o la capacità desiderata.</p></td>
</tr>
<tr class="even">
<td><p>Il sistema PBX gestisce tutti i dispositivi precedenti.</p></td>
<td><p>Richiede un trunk dal gateway al PBX e dal gateway al Mediation Server. Potrebbe essere necessario un numero maggiore di trunk dal provider di servizi.</p></td>
</tr>
<tr class="odd">
<td><p>Gli utenti di VoIP aziendale conservano gli stessi numeri di telefono.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Distribuzione di VoIP-Only Lync Server

Enterprise Voice fornisce nuove aziende e nuovi siti di Office per le aziende esistenti, con l'opportunità di implementare una soluzione VoIP completa senza doversi preoccupare dell'integrazione del PBX o di incorrere in sostanziali costi di distribuzione e manutenzione di un'infrastruttura IP-PBX. Questa soluzione supporta sia i lavoratori in sito che quelli remoti.

In questa distribuzione, tutte le chiamate vengono instradate sulla rete IP. Le chiamate alla rete PSTN vengono instradate al gateway PSTN appropriato. Lync 2013 o Lync Phone Edition funge da softphone. Il controllo delle chiamate remote non è disponibile e non è necessario perché non sono presenti telefoni PBX che gli utenti possono controllare. I servizi di segreteria telefonica e di operatore automatico sono disponibili tramite la distribuzione facoltativa della messaggistica unificata di Exchange.

<div>


> [!NOTE]  
> Oltre all'infrastruttura di rete necessaria per il supporto di Lync Server 2013, una distribuzione solo VoIP può utilizzare un gateway piccolo e qualificato per il supporto di macchine fax e dispositivi analogici.



</div>

Nella figura seguente viene illustrata una topologia tipica per una distribuzione solo VoIP.

**Opzione di distribuzione solo VoIP**

![Opzione di distribuzione di Vergine](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opzione di distribuzione di Vergine")

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

