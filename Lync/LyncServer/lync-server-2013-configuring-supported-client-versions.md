---
title: 'Lync Server 2013: configurazione delle versioni client supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc604efae64d907879ad175b13d7fec9c6b9d99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Configurazione delle versioni client supportate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-14_

In Lync Server 2013, è possibile configurare i criteri versione client per specificare le versioni dei client supportati nell'ambiente in uso. È inoltre possibile utilizzare la configurazione della versione client globale per specificare un'azione predefinita per i client che non dispongono già di criteri di versione definiti e che pertanto non sono esplicitamente supportati o esclusi.

È inoltre possibile utilizzare i criteri di versione client per gestire gli aggiornamenti client. Quando si impostano i criteri di versione client e si utilizzano le opzioni **Consenti e aggiorna** e **Blocca e aggiorna**, i client riceveranno il software aggiornato da Windows Server Update Service, se si utilizza tale servizio, o da Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Impostazioni dei criteri di versione client

I criteri di versione client predefiniti richiedono che tutti i client eseguano Lync. Se i client nell'ambiente eseguono versioni precedenti di Communicator, potrebbe essere necessario riconfigurare le regole di versione client per impedire che i client e i dispositivi vengano bloccati o aggiornati in modo imprevisto durante la connessione a Lync Server 2013. È possibile modificare la regola predefinita oppure aggiungere una regola più in alto nell'elenco Criteri versione client per ignorare la regola predefinita. Inoltre, con il rilascio di aggiornamenti cumulativi (UC), è necessario configurare i criteri di versione client per richiedere gli aggiornamenti più recenti. Per ulteriori informazioni, vedere [impostazione delle applicazioni client che è possibile utilizzare per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) nella documentazione relativa alle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

