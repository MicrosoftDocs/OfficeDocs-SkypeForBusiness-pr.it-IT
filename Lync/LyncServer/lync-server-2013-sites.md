---
title: Siti di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Siti di Lync Server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

In Lync Server è possibile definire i *siti* della rete che contengono componenti di Lync Server. Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità. Si noti che i siti di Lync Server sono un concetto separato da siti di servizi di dominio Active Directory e siti di Microsoft Exchange Server. I siti di Lync Server non devono corrispondere ai siti di Active Directory.

<div>

## <a name="site-types"></a>Tipi di sito

Ogni sito è un *sito centrale*, che contiene almeno un pool di front end o un server Standard Edition o un sito di *succursale*. Ogni sito di succursale è associato a un sito centrale e gli utenti del sito della filiale ottengono la maggior parte delle funzionalità di Lync Server dai server del sito centrale associato.

Ogni sito di succursale contiene una delle opzioni seguenti:

  - Un *Survivable Branch Appliance (SBA)*, un server blade di livello industriale con un registrar di Lync Server e un Mediation Server in Windows Server. Il Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network). Survivable Branch Appliance è progettato per i siti di succursale con utenti compresi tra 25 e 1000.

  - Un *Survivable Branch Server (SBS)*, un server che utilizza Windows Server che soddisfa i requisiti hardware specificati e che include il software di registrazione di Lync Server e Mediation Server. Deve essere collegato a un gateway PSTN o a un trunk SIP a un provider di servizi telefonici. Il Survivable Branch Server è progettato per i siti di succursale tra gli utenti di 1000 e 5000.

  - Un gateway PSTN e, facoltativamente, un *Mediation Server*. Per informazioni dettagliate su questo e altri ruoli del server, vedere [ruoli del server in Lync server 2013](lync-server-2013-server-roles.md).

Una filiale con un collegamento WAN (Wide Area Network) resiliente a un sito centrale può usare la terza opzione, ovvero un gateway PSTN e, facoltativamente, un Mediation Server. I siti di succursale con collegamenti meno resilienti devono usare un Survivable Branch Appliance o un Survivable Branch Server, che garantiscono la resilienza in tempi di errori di rete wide-area. Ad esempio, in un sito con un Survivable Branch Appliance o un Survivable Branch Server distribuito, gli utenti possono comunque effettuare e ricevere le chiamate vocali aziendali se la WAN che connette il sito della filiale al sito centrale è in calo. Per informazioni dettagliate su Survivable Branch Appliance, Survivable Branch Server e resilienza, vedere [pianificazione della resilienza di Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="site-topologies"></a>Topologie del sito

La distribuzione deve includere almeno un sito centrale e può includere zero in molti siti di succursale. Ogni sito di succursale è affiliato a un sito centrale. Il sito centrale fornisce i servizi di Lync Server al sito della filiale che non sono ospitati localmente nel sito della filiale, ad esempio presenza e conferenza.

Se si hanno più siti, è possibile abbinare i pool Front-end in siti diversi per abilitare le abilità di ripristino di emergenza. Per informazioni dettagliate, vedere Supporto per la [disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

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

