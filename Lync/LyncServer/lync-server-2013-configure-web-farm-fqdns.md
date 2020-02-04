---
title: 'Lync Server 2013: Configurare i nomi di dominio completi (FQDN) delle Web farm'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configurare i nomi di dominio completi (FQDN) delle Web farm per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-29_

Quando è stata definita la configurazione del server Standard Edition, del pool di front-end, del pool di Director o Director in Generatore di topologie, è possibile configurare un nome di dominio completo (FQDN) dei servizi Web esterni. Durante il processo di accesso di un client ospitato nel server standard o nel pool Front-End, i nomi FQDN dei servizi Web configurati vengono inviati tramite provisioning in banda. Se è necessario aggiungere o modificare l'URL dei servizi Web esterni, usare generatore di topologie per configurare o riconfigurare la configurazione dei servizi Web usando la procedura descritta in questo argomento.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Per configurare un nome di dominio completo del pool esterno per i servizi Web

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  In Generatore di topologia, nell'albero della console, in **front ends Standard Edition**, i Front ends e gli **amministratori**di **Enterprise Edition**, fare clic con il pulsante destro del mouse sul nome del pool che è necessario modificare e quindi scegliere **modifica proprietà**.

3.  Nella sezione **servizi Web** aggiungere o modificare il nome di **dominio completo dei servizi Web esterni**.

4.  Rivedere e modificare le **porte in attesa** sia per http che per HTTPS. Le impostazioni predefinite saranno:
    
      - **Porte in ascolto:** HTTP 8080, HTTPS 4443
    
      - **Porte pubblicate:** HTTP 80, HTTPS 443
    
    Dove le **porte in attesa** sono la porta che i servizi Web esterni verranno configurati per ricevere richieste dal proxy inverso e le porte **pubblicate** sono le porte pubblicate esternamente dal proxy inverso e vengono comunicate ai client durante il provisioning in banda.

5.  Dopo aver completato le aggiunte e gli aggiornamenti, fare clic su **OK** per continuare.

6.  Fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **pubblica**.
    
    <div>
    

    > [!IMPORTANT]  
    > Una volta completata la pubblicazione, è possibile che venga presentato un collegamento che informa che è necessario eseguire ulteriori operazioni. Il collegamento, se selezionato, apre un elenco di server interessati dalle modifiche apportate in Generatore di topologia che richiedono la ripetizione della distribuzione guidata di Lync Server in ogni server elencato per aggiornare la configurazione per i componenti aggiunti, rimossi o modificati.

    
    </div>

7.  Ripetere questi passaggi per ogni server Standard Edition, pool Front-End, pool di Director o Director nell'organizzazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

