---
title: 'Lync Server 2013: distribuire i tipi di indirizzi IP in un front end server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9c2f59cd3ee07e565a984ebb6f19d8ff07f50e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Distribuire i tipi di indirizzi IP in un front end server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-07-28_

Utilizzando Generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzi IP in un front end server.

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Per distribuire i tipi di indirizzi IP in un Front End Server

1.  In **Pool Enterprise Edition Front End** fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **Modifica proprietà**. In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.

2.  Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare. Per una configurazione con dual stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.
    
    **Finestra di dialogo Modifica proprietà per il pool Front End Server**
    
    ![Finestra di dialogo Modifica proprietà di front end server](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Finestra di dialogo Modifica proprietà di front end server")
    
      - **Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.
        
        <div>
        

        > [!NOTE]  
        > Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).

        
        </div>
    
      - **Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un determinato indirizzo da utilizzare nel nuovo server. Se si seleziona questa opzione, sarà necessario immettere un valore per **Indirizzo IP primario**.
    
      - **Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, tranne quelle su rete PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.
    
      - **Indirizzo IP PSTN**. L'installazione di altre schede di interfaccia di rete (NIC) per supportare la configurazione degli indirizzi IP PSTN per Lync Server 2013 non è supportata nei ruoli Mediation Server collocati. Per ulteriori informazioni sulle configurazioni NIC supportate per Lync Server 2013, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

