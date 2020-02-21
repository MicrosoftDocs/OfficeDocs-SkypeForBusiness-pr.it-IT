---
title: 'Lync Server 2013: pianificazione della connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52bc8a563a45e75b01932ee716df90f1cf2ca7da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Pianificazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

La connettività per la messaggistica istantanea pubblica è una classe di federazione ed è configurata per consentire agli utenti interni ed esterni di Lync Server 2013 di aggiungere contatti da uno dei seguenti elementi:

  - Contatti di Messenger

  - Yahoo\! contatti

  - Contatti di AOL (America Online)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione a Microsoft Lync Public IM Connectivity (PIC USL) non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza di sottoscrizione per utente, per mese, necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale non verrà rinnovato.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone attraverso la messaggistica istantanea e la voce.</P></LI></UL>



</div>

Per questa classe di federazione è necessario tenere conto delle considerazioni seguenti per la pianificazione:

  - Gli utenti di Windows Live Messenger possono avere comunicazioni audio/visive peer-to-peer con gli utenti di Lync Server 2013, oltre alla messaggistica istantanea. I server perimetrali devono soddisfare requisiti specifici per le porte e i protocolli. Per informazioni dettagliate, vedere [Determine External a/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La messaggistica istantanea Yahoo non ha requisiti univoci, oltre a quelli utilizzati in genere nella pianificazione e nella distribuzione del server perimetrale tipico che fornisce la Federazione.

  - America Online richiede che il certificato del server perimetrale assegnato al servizio Access Edge disponga di un utilizzo chiave avanzato (EKU, client Enhanced Key Usage).

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Riepilogo dei certificati-connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Riepilogo delle porte-connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Riepilogo DNS-connettività per la messaggistica istantanea pubblica in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

