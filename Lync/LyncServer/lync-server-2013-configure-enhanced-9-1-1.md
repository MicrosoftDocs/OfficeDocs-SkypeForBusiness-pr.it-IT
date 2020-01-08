---
title: 'Lync Server 2013: Configurare i servizi di emergenza avanzati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Configurare i servizi di emergenza avanzati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

Enhanced 9-1-1 (E9-1-1) è una funzionalità di notifica di emergenza che associa il numero di telefono della parte chiamante a un indirizzo civico o stradale. Usando queste informazioni, il PSAP (Public Safety Answering Point) può immediatamente inviare i servizi di emergenza al chiamante in difficoltà.

Per supportare E9-1-1, Lync Server 2013 deve essere in grado di associare correttamente una posizione a un client e verificare che queste informazioni vengano usate per instradare la chiamata di emergenza al PSAP più vicino.

Per informazioni dettagliate sulla pianificazione di una distribuzione di E9-1-1, vedere [pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

<div>


> [!IMPORTANT]  
> Lync Server 2013 supporta solo E9-1-1 negli Stati Uniti. Per distribuire E9-1-1, è necessario configurare una connessione SIP a un provider di servizi E9-1-1 qualificato oppure distribuire un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone). Per informazioni dettagliate, vedere <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) e Mediation Server in Lync server 2013</A>. Per informazioni dettagliate sulla configurazione delle connessioni trunk, vedere <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurare un trunk con il bypass multimediale in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurare una route vocale E9-1-1 in Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Creare criteri di posizione in Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Configurare le informazioni sul sito per E9-1-1 in Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Configurare le funzionalità di E9-1-1 avanzate in Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

