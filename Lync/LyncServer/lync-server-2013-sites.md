---
title: Siti di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3e420a1fad89692133df4422138b43d4d7210e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Siti di Lync Server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-16_

In Lync Server, è possibile definire i *siti* della rete che contengono componenti di Lync Server. Un sito è un insieme di computer connessi attraverso una rete a bassa latenza e alta velocità, come una singola rete LAN o due reti connesse tramite una rete a fibra ottica ad alta velocità. Si noti che i siti di Lync Server sono un concetto separato dai siti di servizi di dominio Active Directory e dai siti di Microsoft Exchange Server. I siti di Lync Server non devono corrispondere ai siti di Active Directory.

<div>

## <a name="site-types"></a>Tipi di sito

Ogni sito è un *sito centrale*, che contiene almeno un pool Front end o un server Standard Edition o un *sito di succursale*. Ogni sito di succursale è associato a un solo sito centrale e gli utenti del sito di succursale ottengono la maggior parte delle funzionalità di Lync Server dai server nel sito centrale associato.

Ogni sito di succursale contiene uno degli elementi seguenti:

  - Un *Survivable Branch Appliance (SBA)*, che è un server blade standard del settore con un registrar di Lync Server e un Mediation Server in esecuzione su Windows Server. Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network). Il Survivable Branch Appliance è stato creato per i siti di succursale con gli utenti compresi tra 25 e 1000.

  - Un *Survivable Branch Server (SBS)*, che è un server che esegue Windows Server che soddisfa i requisiti hardware specificati, e che dispone di un software di registrazione di Lync Server e Mediation Server installato su di esso. Deve connettersi a un gateway PSTN o a un trunk SIP verso un provider di servizi telefonici. Il Survivable Branch Server è progettato per siti di succursale aventi da 1000 a 5000 utenti.

  - Un gateway PSTN e, facoltativamente, un *Mediation Server*. Per informazioni dettagliate su questo e altri ruoli del server, vedere [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).

In un sito di succursale con un collegamento WAN (Wide Area Network) resiliente a un sito centrale è possibile utilizzare la terza opzione, ovvero un gateway PSTN e facoltativamente un Mediation Server. I siti di succursale con collegamenti con resilienza inferiore devono utilizzare un Survivable Branch Appliance o un Survivable Branch Server, che forniscono resilienza in periodi di problemi di rete a aree estese. Ad esempio, in un sito con un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere chiamate vocali di VoIP aziendale se la rete WAN che collega il sito di succursale al sito centrale è inattivo. Per informazioni dettagliate sul Survivable Branch Appliance, sul Survivable Branch Server e sulla resilienza, vedere [Planning for Enterprise Voice resilienzy in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="site-topologies"></a>Topologie di siti

La distribuzione deve includere almeno un sito centrale e può includere da zero a numerosi siti di succursale. Ogni sito di succursale è affiliato a un sito centrale. Nel sito centrale sono disponibili i servizi di Lync Server per il sito di succursale che non sono ospitati localmente nel sito di succursale, ad esempio la presenza e le conferenze.

Se sono disponibili più siti, sarà possibile accoppiare i pool Front End su siti diversi per abilitare le funzionalità di ripristino di emergenza. Per informazioni dettagliate, vedere Supporto per la [disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Ruoli del server in Lync Server 2013](lync-server-2013-server-roles.md)  
[Supporto per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Pianificazione della resilienza di VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

