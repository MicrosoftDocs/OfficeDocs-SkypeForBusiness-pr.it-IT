---
title: Creare un record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c30164813619a271f2321db3ff3e8019067193c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Creare un record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

In questo argomento viene descritto come configurare il record DNS (Domain Name System) SRV necessario per un server perimetrale di Lync Server 2013 per il routing a un servizio di Exchange ospitato, ad esempio Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Per creare un record DNS SRV esterno per il servizio di Exchange ospitato

1.  Accedere al DNS esterno come membro del gruppo DnsAdmins.

2.  Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.

3.  Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**e selezionare il dominio SIP in cui verrà installato Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]
    > È necessario creare il record DNS SRV nel dominio SIP in cui Lync Server è o verrà installato. Quando si crea il record SRV, l'FQDN utilizzato per il campo Host che offre questo servizio deve essere l'FQDN esterno del pool di server perimetrali. Ad esempio, se l'FQDN esterno del pool di server perimetrali è edge01.contoso.net, immettere tale valore. Deve inoltre trovarsi nello stesso dominio del record DNS degli host (A).

    
    </div>

4.  Fare clic con il pulsante destro del mouse sul dominio selezionato e quindi scegliere **Altri nuovi record**.

5.  In **Tipo record di risorse** fare clic su **Posizione servizio (SRV)**, quindi su **Crea record**.

6.  In **nuovo record di risorse**fare clic su **servizio**e quindi digitare ** \_sipfederationtls**.

7.  Fare clic su **protocollo**e quindi digitare ** \_TCP**.

8.  Fare clic su **Numero porta** e quindi digitare **5061**.

9.  Fare clic su **host che offre questo servizio**e quindi digitare il nome di dominio completo (FQDN) del pool di Edge di lync Server 2013 che consente di accedere al sistema lync Server 2013 per i client esterni attendibili.
    
    <div>
    

    > [!NOTE]
    > È inoltre necessario configurare il dominio come autorevole e accettato nelle impostazioni di Exchange Online. Per informazioni dettagliate, vedere Create accepted <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>Domains at.

    
    </div>

10. Scegliere **OK**, quindi su **Fine**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Per verificare che il record DNS SRV sia stato creato correttamente

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

3.  Al prompt dei comandi eseguire il comando seguente:
    
        nslookup <FQDN Lync Edge Pool>

4.  Verificare che la risposta ricevuta venga risolta nell'indirizzo IP appropriato per l'FQDN.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare record DNS per i server proxy inversi in Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

