---
title: 'Lync Server 2013: distribuire i tipi di indirizzi IP in un Mediation Server'
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
ms.openlocfilehash: c76dcde03d2a85eb45f7b2c28d6b7c7d99b41b20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531483"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Distribuire i tipi di indirizzi IP in un Mediation Server per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-07-28_

Utilizzando Generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzi IP in un Mediation Server.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Per distribuire i tipi di indirizzi IP in un Mediation Server

  - In Generatore di topologie fare clic con il pulsante destro del mouse sul server all'interno di un pool in **pool di Mediation**e quindi scegliere **modifica proprietà**. In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.

  - Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare. Per una configurazione con dual stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.
    
    **Finestra di dialogo Modifica proprietà per il pool Mediation Server**
    
    ![Pagina delle proprietà generali di Lync Server con FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Pagina delle proprietà generali di Lync Server con FQDN")
    
      - **Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.
        
        <div>
        

        > [!NOTE]  
        > Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).

        
        </div>
    
      - **Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un indirizzo specifico da utilizzare nel nuovo server. Se si seleziona questa opzione è necessario immettere un valore per Indirizzo IP primario.
    
      - **Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, ad eccezione di PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.
    
      - **Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è autonomo. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.
        
        <div>
        

        > [!NOTE]  
        > L'installazione di altre schede di interfaccia di rete (NIC) per supportare la configurazione degli indirizzi IP PSTN per Lync Server 2013 non è supportata nei ruoli Mediation Server collocati. Per ulteriori informazioni sulle configurazioni NIC supportate per Lync Server 2013, vedere <A href="lync-server-2013-server-hardware-platforms.md">server hardware Platforms for Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

