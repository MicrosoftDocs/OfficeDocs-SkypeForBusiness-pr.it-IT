---
title: 'Lync Server 2013: installazione di software facoltativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a493fed33fff897ea2cccc2a89c0d55c5b8a8097
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Installazione di software facoltativo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Lo strumento di pianificazione di Microsoft Lync Server 2013 è progettato per l'esportazione in Microsoft Excel e Microsoft Visio. Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione del progetto.

<div>

## <a name="optional-software"></a>Software facoltativo

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

L'esportazione della progettazione in Microsoft Excel consente di creare un report che visualizza sette schede nel foglio di calcolo:

  - Riepilogo: Visualizza le informazioni sulla configurazione del sito, inclusi il conteggio degli utenti, le impostazioni della capacità e le informazioni sul profilo del server.

  - Profilo hardware: Visualizza un report sulle configurazioni hardware consigliate per i server specificati nella topologia, tra cui CPU, memoria, disco e interfaccia di rete. Sono incluse anche la quantità e le specifiche consigliate per i componenti server. Ogni server viene inoltre definito dal sito per ottenere una rappresentazione completa dei requisiti del server per sito.

  - Requisiti per le porte: Visualizza un report di tutte le porte abilitate e l'associazione a Domain Name System Load Balancing (DNS LB) e hardware load balancers (HLB). È consigliabile usare questo report per pianificare le configurazioni firewall e DNS LB e HLB.

  - Report di riepilogo: Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete Edge Server.

  - Report certificati: Visualizza il nome dell'oggetto e i nomi alternativi oggetto necessari per i certificati necessari per l'uso dei server perimetrali.

  - Report firewall: Visualizza le porte di origine e di destinazione e gli indirizzi IP per le interfacce esterne ed interne.

  - Report DNS: Visualizza il nome di dominio completo (FQDN) e gli indirizzi IP/VIP necessari per ogni voce DNS creata.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

L'esportazione della progettazione in Microsoft Visio crea un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate. Il diagramma importato può essere modificato e ridisposto per soddisfare le esigenze della documentazione. Il diagramma di Visio tipico includerà:

<div>


> [!NOTE]  
> Se la struttura è abbastanza grande da richiedere più di tre server front-end, verrà creata una pagina aggiuntiva per il pool Front-End, i server front-end, il computer in cui sono in esecuzione SQL Server, gli indirizzi IP e i nomi di dominio completi.



</div>

  - Topologia globale-diagramma dei siti di Lync Server 2013 configurati.

  - Scheda nome sito: Visualizza la topologia di configurazione del sito con Edge Server, firewall, PSTN (Public Switched Telephone Network) con gateway e la distribuzione del server interno. La distribuzione interna è costituita da server e pool configurati, inclusi i pool Front-End, i server basati su SQL Server, i servizi di dominio Active Directory, i direttori, i server di messaggistica unificata di Exchange, i server cassette postali di Exchange, i server di Office Web Apps Mediation Server e server di chat permanenti.

  - Diagramma di rete perimetrale: diagramma che descrive la configurazione del server perimetrale con gli indirizzi IP associati e i nomi di dominio completi. Sono inclusi anche il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware. Vengono inoltre visualizzati i direttori e il server front-end o il pool Front-End, con il DNS LB o HLB associato e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e il nome di dominio completo.

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Installazione dello strumento di pianificazione in Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

