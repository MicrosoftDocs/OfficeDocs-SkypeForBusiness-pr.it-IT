---
title: 'Lync Server 2013: configurare i nomi di dominio completi della Web farm'
description: 'Lync Server 2013: configurare i nomi di dominio completi della Web farm.'
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
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566662"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configurare i nomi di dominio completi della Web farm per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-29_

Quando è stata definita la configurazione del server Standard Edition, del pool Front End, del Director o del pool di Director in Generatore di topologie, è necessario configurare un nome di dominio completo (FQDN) dei servizi Web esterni. Durante il processo di accesso di un client ospitato nel server Standard Edition o nel pool Front End, i nomi FQDN dei servizi Web configurati vengono inviati tramite il provisioning di tipo in-band. Se è necessario aggiungere o modificare l'URL dei servizi Web esterni, è possibile utilizzare Generatore di topologie per configurare o riconfigurare la configurazione dei servizi Web utilizzando la procedura descritta in questo argomento.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Per configurare l'FQDN di un pool esterno per i servizi Web

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Generatore di topologie fare clic con il pulsante destro del mouse sul nome del pool da modificare, quindi fare clic su **modifica proprietà**nell'albero della console in **Standard Edition Front**-end, **Enterprise Edition front end**e **Director**.

3.  Nella sezione **Servizi Web** aggiungere o modificare l'FQDN per i servizi**** Web esterni.

4.  Controllare e modificare i valori di **Porte di attesa** sia per HTTP che per HTTPS. I valori predefiniti saranno i seguenti:
    
      - **Porte di attesa:** HTTP 8080, HTTPS 4443
    
      - **Porte pubblicate:** HTTP 80, HTTPS 443
    
    Dove per **Porte di attesa** si intendono le porte che verranno configurate per i servizi Web esterni per ricevere le richieste dal proxy inverso e per **Porte pubblicate** si intendono le porte pubblicate esternamente dal proxy inverso e comunicate ai client durante il provisioning di tipo in-band.

5.  Dopo aver aggiunto e aggiornato le configurazioni, fare clic su **OK** per continuare.

6.  Fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **pubblica**.
    
    <div>
    

    > [!IMPORTANT]  
    > Al termine della pubblicazione, è possibile che venga visualizzato un collegamento in cui viene indicato che devono essere eseguiti passaggi aggiuntivi. Se si fa clic sul collegamento, verrà aperto un elenco dei server coinvolti dalle modifiche apportate in Generatore di topologie che richiederanno di rieseguire la distribuzione guidata di Lync Server in ogni server elencato per aggiornare la configurazione dei componenti aggiunti, rimossi o modificati.

    
    </div>

7.  Ripetere questi passaggi per ogni server Standard Edition, il pool Front End, il Director o il pool di Director nell'organizzazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

