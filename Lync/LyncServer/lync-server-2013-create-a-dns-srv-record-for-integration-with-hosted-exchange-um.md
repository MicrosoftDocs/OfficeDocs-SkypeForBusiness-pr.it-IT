---
title: Creare un Record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata
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
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Creare un Record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

Questo argomento descrive come configurare il record SRV DNS (Domain Name System) obbligatorio per un server perimetrale di Lync Server 2013 per l'instradamento a un servizio di Exchange ospitata, come Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Per creare un record SRV DNS esterno per il servizio di Exchange ospitata

1.  Accedere al server DNS esterno come membro del gruppo DnsAdmins.

2.  Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

3.  Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e selezionare il dominio SIP in cui verrà installato Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]
    > È necessario creare il record SRV DNS nel dominio SIP in cui Lync Server è o verrà installato. Quando si crea il record SRV, il nome di dominio completo usato per l'host che offre questo campo del servizio deve essere il nome di dominio completo esterno del pool di bordi. Ad esempio, se il nome di dominio completo esterno del pool di Edge è edge01.contoso.net, immettere il valore. Deve anche essere nello stesso dominio del record host DNS (A).

    
    </div>

4.  Fare clic con il pulsante destro del mouse sul dominio selezionato e quindi scegliere **altri nuovi record**.

5.  In **tipo di record risorse**fare clic su **posizione servizio (SRV)** e quindi fare clic su **Crea record**.

6.  In **nuovo record di risorse**fare clic su **servizio**e quindi digitare ** \_sipfederationtls**.

7.  Fare clic su **protocollo**e quindi digitare ** \_TCP**.

8.  Fare clic su **numero di porta**e quindi digitare **5061**.

9.  Fare clic su **host che offre questo servizio**e quindi digitare il nome di dominio completo (FQDN) del pool di Edge di lync Server 2013 che consente l'accesso al sistema lync Server 2013 per i client esterni attendibili.
    
    <div>
    

    > [!NOTE]
    > Il dominio deve essere configurato anche come dominio autorevole accettato nelle impostazioni di Exchange Online. Per informazioni dettagliate, vedere Creare domini accettati <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.

    
    </div>

10. Fare clic su **OK**e quindi su **fine**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Per verificare che il record SRV DNS sia stato creato correttamente

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

3.  Al prompt dei comandi eseguire il comando seguente:
    
        nslookup <FQDN Lync Edge Pool>

4.  Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare record DNS per server proxy inversi in Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

