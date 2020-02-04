---
title: 'Lync Server 2013: Distribuire i tipi di indirizzi IP in un Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Distribuire i tipi di indirizzi IP in un Mediation Server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-07-28_

Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un Mediation Server.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Per distribuire i tipi di indirizzo IP in un Mediation Server

  - In Generatore di topologia, in **pool di mediazione**, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**. In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .

  - Nella finestra di dialogo **modifica proprietà** selezionare il tipo di indirizzo IP che si vuole configurare. Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.
    
    **Finestra di dialogo Modifica proprietà per il pool di Mediation Server**
    
    ![Pagina delle proprietà generali di Lync Server con FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Pagina delle proprietà generali di Lync Server con FQDN")
    
      - **Usare tutti gli indirizzi IP configurati**. Selezionare questa opzione se si vuole consentire l'uso di qualsiasi indirizzo IP definito nel computer.
        
        <div>
        

        > [!NOTE]  
        > Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).

        
        </div>
    
      - **Limitare l'utilizzo del servizio agli indirizzi IP selezionati**. Selezionare questa opzione per specificare un indirizzo specifico da usare nel nuovo server. Se si seleziona questa opzione, è necessario immettere un valore per l'indirizzo IP principale.
    
      - **Indirizzo IP principale**. Immettere un indirizzo IP che il server userà per tutte le comunicazioni eccetto PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo di selezione.
    
      - **Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è autonomo. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.
        
        <div>
        

        > [!NOTE]  
        > L'installazione di altre schede di interfaccia di rete (NIC) per supportare la configurazione degli indirizzi IP PSTN per Lync Server 2013 non è supportata nei ruoli di Mediation Server collocati. Per altre informazioni sulle configurazioni di NIC supportate per Lync Server 2013, vedere <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware del server per Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

