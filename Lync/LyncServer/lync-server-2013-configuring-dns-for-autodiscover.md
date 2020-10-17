---
title: "Lync Server 2013: configurazione del DNS per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 249993e68930db1eb5dd5159633a73f80cef8c05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520053"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configurazione del DNS per l'individuazione automatica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-12_

Per supportare l'individuazione automatica per i client Lync, è necessario creare i seguenti record DNS (Domain Name System):

  - Un record DNS interno per supportare i client Lync che si connettono dall'interno della rete dell'organizzazione

  - Un record DNS esterno, o pubblico, per supportare i client Lync che si connettono da Internet

È necessario creare un record DNS interno e un record DNS esterno per ogni dominio SIP.

I record DNS possono essere record A (host) o CNAME, in base alla possibilità di creare nuovi certificati con il nome alternativo soggetto (SAN). Se non è possibile richiedere e distribuire un nuovo certificato esterno (pubblico) con lyncdiscover.\<domain name\> SAN, utilizzare la procedura per l'utilizzo della porta HTTP/TCP 80. Nelle procedure riportate di seguito viene descritto come creare record DNS interni ed esterni.

<div>

## <a name="to-create-dns-cname-records"></a>Per creare record CNAME DNS

1.  Eseguire l'accesso a un server DNS come indicato di seguito:
    
      - Per creare un record DNS interno, eseguire l'accesso a un server DNS della rete come membro del gruppo Domain Admins o DnsAdmins.
    
      - Per creare un record DNS esterno, connettersi al provider DNS pubblico.

2.  Aprire lo snap-in amministrativo DNS. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi fare clic su **DNS**.

3.  Eseguire una delle operazioni seguenti:
    
      - Per un record DNS interno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio Active Directory, ad esempio contoso.local.
        
        <div>
        

        > [!NOTE]  
        > Questo dominio è il dominio di Active Directory in cui &nbsp; sono installati il pool di server Director e il pool Front End di Lync 2013.

        
        </div>
    
      - Per un record DNS esterno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com.

4.  Verificare che esista un record host A per il pool di server Director, come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record host A per il nome di dominio completo (FQDN) dei servizi Web interni per il pool di server Director, ad esempio lyncwebdir01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record host A per l'FQDN dei servizi Web esterni per il pool di server Director (ad esempio, lyncwebextdir.contoso.com).

5.  Verificare che esista un record host A per il pool Front End, come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record host A per il nome di dominio completo interno dei servizi Web per il pool Front End, ad esempio lyncwebpool01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record host A per l'FQDN dei servizi Web esterni per il pool Front End (ad esempio, lyncwebextpool01.contoso.com).

6.  Per un record DNS interno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com.
    
    <div>
    

    > [!NOTE]  
    > Se si desidera creare un record DNS esterno, l'espansione di <STRONG>Zone di ricerca diretta</STRONG> per il dominio SIP è stata già eseguita al passaggio 3.

    
    </div>

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **Nuovo alias (CNAME)**.

8.  In **Nome alias** digitare uno dei nomi seguenti:
    
      - Per un record DNS interno, digitare lyncdiscoverinternal come nome host per l'URL del servizio di individuazione automatica interno.
    
      - Per un record DNS esterno, digitare lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.

9.  In **Nome di dominio completo (FQDN) per host destinazione** eseguire una delle operazioni seguenti:
    
      - Per un record DNS interno, digitare o passare all'FQDN dei servizi Web interni per il pool di server Director, ad esempio lyncwebdir01. contoso. local, e quindi fare clic su **OK**.
    
      - Per un record DNS esterno, digitare o passare all'FQDN dei servizi Web esterni per il pool di server Director, ad esempio lyncwebextdir.contoso.com, e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se non si utilizza un Director, utilizzare l'FQDN dei servizi Web interni ed esterni per il pool Front end oppure, per un singolo server, il nome di dominio completo per il server front end server o Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Per creare record A DNS

1.  Eseguire l'accesso a un server DNS come indicato di seguito:
    
      - Per creare un record DNS interno, eseguire l'accesso a un server DNS della rete come membro del gruppo Domain Admins o DnsAdmins.
    
      - Per creare un record DNS esterno, connettersi al provider DNS pubblico o al server DNS esterno.

2.  Aprire lo snap-in amministrativo DNS. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi fare clic su **DNS**.

3.  Eseguire una delle operazioni seguenti:
    
      - Per un record DNS interno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio Active Directory, ad esempio contoso.local.
        
        <div>
        

        > [!NOTE]  
        > Questo dominio è il dominio di Active Directory in cui &nbsp; sono installati il pool di server Director e il pool Front End di Lync 2013.

        
        </div>
    
      - Per un record DNS esterno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com.

4.  Verificare che esista un record host A (per IPv6, AAAA) per il pool di server Director, come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record host A (per IPv6, AAAA) per l'FQDN dei servizi Web interni per il pool di server Director, ad esempio lyncwebdir01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record host A (per IPv6, AAAA) per l'FQDN dei servizi Web esterni per il pool di server Director (ad esempio, lyncwebextdir.contoso.com).

5.  Verificare che esista un record host A (per IPv6, AAAA) per il pool Front End, come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record host A (per IPv6, AAAA) per l'FQDN dei servizi Web interni per il pool Front End, ad esempio lyncwebpool01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record host A (per IPv6, AAAA) per l'FQDN dei servizi Web esterni per il pool Front End (ad esempio, lyncwebextpool01.contoso.com).

6.  Per un record DNS interno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com.
    
    <div>
    

    > [!NOTE]  
    > Se si desidera creare un record DNS esterno, l'espansione di <STRONG>Zone di ricerca diretta</STRONG> per il dominio SIP è stata già eseguita al passaggio 3.

    
    </div>

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **Nuovo host (A o AAAA)**.

8.  In **Nome** digitare il nome host come indicato di seguito:
    
      - Per un record DNS interno, digitare lyncdiscoverinternal come nome host per l'URL del servizio di individuazione automatica interno.
    
      - Per un record DNS esterno, digitare lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.
    
    <div>
    

    > [!NOTE]  
    > Il nome di dominio viene dedotto in base alla zona in cui è definito il record e non è necessario pertanto immetterlo come parte del record A.

    
    </div>

9.  In **Indirizzo IP** digitare l'indirizzo IP come indicato di seguito:
    
      - Per un record DNS interno, digitare l'indirizzo IP dei servizi Web interni del server Director (oppure, se si utilizza un servizio di bilanciamento del carico, digitare l'IP virtuale (VIP) del sistema di bilanciamento del carico del Director).
        
        <div>
        

        > [!NOTE]  
        > Se non si utilizza un Director, digitare l'indirizzo IP del server front end server o Standard Edition oppure, se si utilizza un bilanciamento del carico, digitare il VIP del bilanciamento del carico del pool Front end.

        
        </div>
    
      - Per un record DNS esterno, digitare l'indirizzo IP esterno o pubblico del proxy inverso.

10. Fare clic su **Aggiungi host** e quindi su **OK**.

11. Per creare un record A aggiuntivo, ripetere i passaggi da 8 a 10.
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario creare un nuovo Lyncdiscover e lyncdiscoverinternal un record nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

    
    </div>

12. Dopo aver terminato di creare i record A (per IPv6, AAAA), fare clic su **Fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

