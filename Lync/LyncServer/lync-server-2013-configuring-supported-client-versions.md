---
title: 'Lync Server 2013: configurazione delle versioni client supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14bc6decfea38151d1f060b13fa55c81006e98e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Configurazione di versioni client supportate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-14_

In Lync Server 2013 è possibile configurare i criteri di versione client per specificare le versioni dei client supportate nell'ambiente. Inoltre, puoi usare la configurazione della versione client globale per specificare un'azione predefinita per i client che non hanno già un criterio di versione definito e, pertanto, non sono esplicitamente supportati o limitati.

È anche possibile usare i criteri di versione client per gestire gli aggiornamenti del client. Quando si impostano criteri di versione client e si usano le opzioni **Consenti e aggiorna** e **blocca e aggiorna**, i client riceveranno il software aggiornato dal servizio Windows Server Update (se si usa questo servizio) o da Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Impostazioni dei criteri di versione client

I criteri di versione client predefiniti richiedono che tutti i client eseguano Lync. Se i client nell'ambiente sono in esecuzione versioni precedenti di Communicator, potrebbe essere necessario riconfigurare le regole della versione client per impedire che i client e i dispositivi vengano bloccati o aggiornati in modo imprevisto durante la connessione a Lync Server 2013. È possibile modificare la regola predefinita oppure aggiungere una regola più alta nell'elenco dei criteri di versione client per eseguire l'override della regola predefinita. Inoltre, come vengono rilasciati gli aggiornamenti cumulativi (CUs), è necessario configurare i criteri di versione client per richiedere gli aggiornamenti più recenti. Per informazioni dettagliate, vedere [specificare le applicazioni client che è possibile usare per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) nella documentazione Operations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

