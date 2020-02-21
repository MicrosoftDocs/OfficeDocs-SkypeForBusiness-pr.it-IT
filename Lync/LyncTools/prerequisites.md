---
title: Prerequisiti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4f10cb1bdf5733dbe54519325475871be10564
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>Prerequisiti

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-19_

Sono disponibili diversi requisiti di configurazione hardware, software e di sistema che è necessario eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013.

<div>

## <a name="client-hardware-requirements"></a>Requisiti hardware client

Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 nella distribuzione di Lync Server 2013, per tutti gli utenti di 4.500 di cui si desidera simulare il carico, è necessario almeno un computer dedicato che soddisfi i requisiti hardware minimi seguenti:

  - 1 scheda di rete Gigabit

  - RAM da 8 GB

  - 2 unità di elaborazione centrale Dual Core (CPU)

</div>

<div>

## <a name="client-software-requirements"></a>Requisiti software client

Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 nella distribuzione di Lync Server 2013, i sistemi operativi supportati sono i seguenti:

  - Sistema operativo Windows Server 2012

  - Sistema operativo Windows Server 2008 (versione 64 bit)

Il computer client deve soddisfare i requisiti software seguenti:

  - È necessario che sia installato [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) Runtime.

  - In Windows Server 2008/Windows Server 2012, è necessario abilitare la funzionalità Desktop Experience.

  - È necessario che [Microsoft Visual C++ 2012 Redistributable Package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) sia installato.

  - Distribuzione di Lync Server 2013 completamente configurata.

<div>


> [!IMPORTANT]  
> Le raccolte di Microsoft Unified Communications Managed API (UCMA) 4,0 sono incluse nel pacchetto di installazione, pertanto UCMA non è necessario e non deve essere installato nei computer client.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Requisiti di configurazione

I computer in cui verrà eseguito lo strumento di stress e prestazioni di Lync Server 2013 devono essere configurati in base ai requisiti seguenti:

1.  È necessario essere connessi come membri del gruppo Domain o local Admins.

2.  Lync Server 2013 stress and Performance Tool (LyncPerfTool. exe) non può essere eseguito in un computer che esegue anche i componenti di Lync Server 2013.

3.  È necessario eseguire lo strumento di creazione degli utenti di Lync Server 2013 (UserProvisioningTool. exe) nel front end server o nel server Standard Edition in cui si trovano gli account utente. Quando lo strumento viene eseguito più volte, tutti gli utenti abilitati per le comunicazioni unificate di Microsoft devono disporre di un numero di telefono univoco.

4.  Le dimensioni del file di paging devono essere gestite dal sistema o devono essere almeno 1,5 volte la quantità di RAM del sistema.

</div>

</div>

<span> </span>

</div>

</div>

</div>

