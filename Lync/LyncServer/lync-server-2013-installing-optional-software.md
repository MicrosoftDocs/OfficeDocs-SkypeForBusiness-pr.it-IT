---
title: 'Lync Server 2013: installazione di software facoltativo'
description: 'Lync Server 2013: installazione di software facoltativo.'
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
ms.openlocfilehash: 7423c0d54b762fb4af7cedc8d7ba8745fd94bdf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573912"
---
# <a name="installing-optional-software-in-lync-server-2013"></a>Installazione di software facoltativo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Microsoft Lync Server 2013, strumento di pianificazione è progettato per l'esportazione in Microsoft Excel e Microsoft Visio. Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione del progetto.

<div>

## <a name="optional-software"></a>Software facoltativo

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

L'esportazione del progetto in Microsoft Excel consente di creare un report in cui vengono visualizzate sette schede nel foglio di calcolo:

  - Riepilogo: consente di visualizzare informazioni sulla configurazione del sito, inclusi il numero di utenti, le impostazioni di capacità e le informazioni sui profili del server.

  - Profilo hardware – Visualizza un rapporto delle configurazioni hardware consigliate per i server specificati nella topologia, inclusi disco, CPU, memoria, e interfaccia di rete. Sono incluse anche la quantità e le specifiche consigliate per i componenti del server. Ogni server è inoltre definito dal sito per fornire una rappresentazione completa dei requisiti del server in base al sito.

  - Requisiti per le porte: consente di visualizzare un report di tutte le porte abilitate e l'associazione al bilanciamento del carico del sistema DNS (Domain Name System) e ai sistemi di bilanciamento del carico hardware (HLB). È consigliabile utilizzare questo report per pianificare le configurazioni di firewall e di LB e di HLB di DNS.

  - Report riepilogativo – Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete del server perimetrale.

  - Report certificati – Visualizza il nome del soggetto e i nomi alternativi del soggetto necessari per i certificati necessari per ottenere i server perimetrali in esecuzione.

  - Report firewall – Visualizza le porte di origine e di destinazione e gli indirizzi IP per le interfacce sia esterne che interne.

  - Report DNS: consente di visualizzare gli indirizzi FQDN (Fully Qualified Domain Name) e IP/VIP necessari per ogni voce DNS creata.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

L'esportazione del progetto in Microsoft Visio consente di creare un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate. Il diagramma importato può essere modificato e riorganizzato in base alle specifiche esigenze per la documentazione. Il diagramma di Visio tipico includerà:

<div>


> [!NOTE]  
> Se il progetto è sufficientemente grande da richiedere più di tre Front End Server, verrà creata una pagina aggiuntiva per il pool Front End, i Front End Server, il computer che esegue SQL Server, gli indirizzi IP e i nomi FQDN.



</div>

  - Topologia globale – diagramma dei siti di Lync Server 2013 configurati.

  - Scheda nome sito – Visualizza la topologia di configurazione del sito con server perimetrale, firewall, rete PSTN (Public Switched Telephone Network) con gateway e la distribuzione interna del server. La distribuzione interna è costituita da server e pool configurati, inclusi i pool Front End, i server basati su SQL Server, i servizi di dominio Active Directory, i direttori, i server di messaggistica unificata di Exchange, i server cassette postali di Exchange, i server Office Web Apps, i Mediation Server e i server Chat persistente.

  - Diagramma di rete perimetrale – diagramma che illustra la configurazione del server perimetrale con gli indirizzi IP e gli FQDN associati. Sono inoltre inclusi il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware. Vengono inoltre visualizzati i direttori e il front end server o il pool Front End, con DNS LB o HLB associato e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e il nome di dominio completo.

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

