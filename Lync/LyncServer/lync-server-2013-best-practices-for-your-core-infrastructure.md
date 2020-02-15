---
title: "Lync Server 2013: procedure consigliate per l'infrastruttura di base"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd53ac85ec544af58c1f94f7397a030f6b10fdb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Procedure consigliate per l'infrastruttura di base in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-27_

È probabile che siano già state intraprese azioni per progettare la tolleranza di errore nel sistema, ad esempio garantendo la ridondanza hardware, prendendo precauzioni in caso di interruzioni dell'alimentazione, installando con regolarità gli aggiornamenti antivirus e della sicurezza e monitorando l'attività dei server. Queste procedure traggono vantaggio non solo dell'infrastruttura di Microsoft Lync Server 2013, ma anche dell'intera rete. Se non sono state implementate queste procedure, è consigliabile farlo prima di distribuire Lync Server 2013.

Per proteggere i server della distribuzione di Lync Server 2013 da un danno accidentale o intenzionale che potrebbe causare tempi di inattività, prendere le seguenti precauzioni:

  - Installare con regolarità gli aggiornamenti della sicurezza nei server. Sottoscrivendo il servizio Microsoft Security Notification Service, è possibile ricevere una notifica immediata ogni volta che vengono pubblicati bollettini sulla sicurezza per i prodotti Microsoft. Per effettuare la sottoscrizione, visitare il sito Web Microsoft Technical Security [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)Notifications all'indirizzo.

  - Verificare che i diritti di accesso siano configurati correttamente.

  - Posizionare i server in un ambiente fisico con accesso consentito soltanto a personale autorizzato. Verificare che in tutti i server sia installato il software antivirus appropriato. Mantenere il software aggiornato con i file delle impronte digitali dei virus più recenti. Utilizzare la funzionalità di aggiornamento automatico dell'applicazione antivirus per mantenere costantemente aggiornate le impronte digitali dei virus.

  - Si consiglia di disabilitare i servizi del sistema operativo Windows Server che non sono necessari nei computer in cui si installa Lync Server 2013.

  - Crittografare i sistemi operativi e le unità disco in cui sono archiviati i dati con un sistema di crittografia dell'intero volume, a meno che non sia possibile garantire il controllo completo e costante dei server, l'isolamento fisico totale e la rimozione delle autorizzazioni appropriata e sicura per le unità disco sostituite o guaste.

  - Disabilitare tutte le porte DMA (Direct Memory Access) esterne del server, a meno che non sia possibile garantire un controllo rigoroso dell'accesso fisico ai server. Gli attacchi basati su DMA, che possono essere eseguiti piuttosto facilmente, rendono vulnerabili le informazioni riservate, ad esempio le chiavi di crittografia private.

</div>

<span> </span>

</div>

</div>

</div>

