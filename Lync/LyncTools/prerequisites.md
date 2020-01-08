---
title: Prerequisiti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74603ed20fe144ca89d3ac13bc00fef0e7d6ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>Prerequisiti

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-19_

Esistono diversi requisiti per la configurazione di hardware, software e sistema per cui è necessario eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013.

<div>

## <a name="client-hardware-requirements"></a>Requisiti hardware client

Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 nella distribuzione di Lync Server 2013, per ogni 4.500 utenti il cui carico si vuole simulare è necessario almeno un computer dedicato che soddisfi i requisiti hardware minimi seguenti:

  - 1 scheda di rete Gigabit

  - RAM da 8 GB

  - 2 unità di elaborazione centrali Dual-Core (CPU)

</div>

<div>

## <a name="client-software-requirements"></a>Requisiti software client

Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 nella distribuzione di Lync Server 2013, i sistemi operativi supportati sono i seguenti:

  - Sistema operativo Windows Server 2012

  - Sistema operativo Windows Server 2008 (64 bit Edition)

Il computer client deve soddisfare i requisiti software seguenti:

  - È necessario che sia installato [Microsoft .NET Framework 4,5](http://go.microsoft.com/fwlink/?linkid=143212) Runtime.

  - In Windows Server 2008/Windows Server 2012 la caratteristica esperienza desktop deve essere abilitata.

  - È necessario avere installato [Microsoft Visual C++ 2012 Redistributable Package](http://go.microsoft.com/fwlink/?linkid=143216) (x64).

  - Distribuzione di Lync Server 2013 completamente configurata.

<div>


> [!IMPORTANT]  
> Le raccolte di Microsoft Unified Communications Managed API (UCMA) 4,0 sono incluse nel pacchetto di installazione, quindi UCMA non è obbligatorio e non deve essere installato nei computer client.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Requisiti di configurazione

I computer che eseguono lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 devono essere configurati in base ai requisiti seguenti:

1.  È necessario avere effettuato l'accesso come membro del gruppo Domain o Admins locale.

2.  Non è possibile eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool. exe) in un computer che esegue anche i componenti di Lync Server 2013.

3.  È necessario eseguire lo strumento di creazione degli utenti di Lync Server 2013 (UserProvisioningTool. exe) nel server front-end o nel server Standard Edition in cui si trovano gli account utente. Quando lo strumento viene eseguito più volte, ogni utente abilitato per le comunicazioni unificate Microsoft deve avere un numero di telefono univoco.

4.  Le dimensioni del file di pagina devono essere gestite dal sistema oppure almeno 1,5 volte la quantità di RAM nel sistema.

</div>

</div>

<span> </span>

</div>

</div>

</div>

