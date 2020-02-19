---
title: 'Lync Server 2013: impostazioni di criteri di gruppo per Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cae5fdb813f7f58889dd1305b117f0e07ff294e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a>Impostazioni di criteri di gruppo per Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Nelle versioni precedenti di Lync e Office Communicator, era disponibile un modello amministrativo Communicator. adm autonomo per la configurazione delle impostazioni dei criteri di gruppo client. Per Lync 2013, sono inclusi i nuovi file dei modelli amministrativi (file con estensione ADMX e ADML) insieme al modello amministrativo di criteri di gruppo di Office. La disponibilità dei file di Lync 2013. admx e ADML consente di scaricare modelli e gestire in modo centralizzato le impostazioni di criteri di gruppo per tutti i programmi e i Language Pack di Office. Per informazioni dettagliate, vedere "file dei modelli amministrativi di Office 2013 (ADMX, ADML)" nella documentazione di <https://go.microsoft.com/fwlink/p/?linkid=267516>Office 2013 all'indirizzo.

<div>

## <a name="client-bootstrapping-policies"></a>Criteri di avvio automatico del client

Sono disponibili diversi criteri di avvio automatico del client che è consigliabile configurare prima che gli utenti accedano al server per la prima volta. Poiché questi criteri hanno effetto prima che il client esegua l'accesso e inizi a ricevere impostazioni di provisioning di tipo in-band dal server, è possibile utilizzare Criteri di gruppo per configurarli. Per ulteriori informazioni, vedere [configurazione dei criteri di avvio del client in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) nella documentazione relativa alla distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

