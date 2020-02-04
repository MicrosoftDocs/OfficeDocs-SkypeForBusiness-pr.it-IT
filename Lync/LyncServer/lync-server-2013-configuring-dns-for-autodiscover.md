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
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configurazione del DNS per l'individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-12_

Per supportare l'individuazione automatica per i client Lync, è necessario creare i seguenti record DNS (Domain Name System):

  - Record DNS interno per supportare i client Lync che si connettono dall'interno della rete dell'organizzazione

  - Record DNS esterno o pubblico per supportare i client Lync che si connettono da Internet

È necessario creare un record DNS interno e un record DNS esterno per ogni dominio SIP.

I record DNS possono essere un record (host) o un record CNAME, in base alla possibilità di creare nuovi certificati con il nome alternativo soggetto aggiuntivo (SAN). Se non è possibile richiedere e distribuire un nuovo certificato esterno (pubblico) con lyncdiscover. \<San nome\> di dominio, usare la procedura per l'uso della porta HTTP/TCP 80. Le procedure seguenti descrivono come creare record DNS interni ed esterni.

<div>

## <a name="to-create-dns-cname-records"></a>Per creare record CNAME DNS

1.  Accedere a un server DNS come indicato di seguito:
    
      - Per creare un record DNS interno, accedere a un server DNS della rete come membro del gruppo Domain Admins o membro del gruppo DnsAdmins.
    
      - Per creare un record DNS esterno, connettersi al provider DNS pubblico.

2.  Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

3.  Esegui una delle operazioni seguenti:
    
      - Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory, ad esempio contoso. local.
        
        <div>
        

        > [!NOTE]  
        > Questo dominio è il dominio Active Directory in cui sono installati il&nbsp;pool di Lync Server 2013 Director e il pool Front end.

        
        </div>
    
      - Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.

4.  Verificare che per il pool di Director sia presente un record di un host, come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record per il nome di dominio completo (FQDN) dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record per l'FQDN dei servizi Web esterni per il pool di Director, ad esempio lyncwebextdir.contoso.com.

5.  Verificare che per il pool Front-end sia presente un record di un host, come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record per l'FQDN dei servizi Web interni per il pool Front-End, ad esempio lyncwebpool01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record per l'FQDN dei servizi Web esterni per il pool Front-End, ad esempio lyncwebextpool01.contoso.com.

6.  Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.
    
    <div>
    

    > [!NOTE]  
    > Se si sta creando un record DNS esterno, le <STRONG>aree di ricerca inoltrate</STRONG> sono già espanse per il dominio SIP dal passaggio 3.

    
    </div>

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo alias (CNAME)**.

8.  In **nome alias**Digitare una delle opzioni seguenti:
    
      - Per un record DNS interno, digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.
    
      - Per un record DNS esterno, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.

9.  In **nome di dominio completo (FQDN) per l'host di destinazione**, eseguire una delle operazioni seguenti:
    
      - Per un record DNS interno, digitare o passare all'FQDN dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local, e quindi fare clic su **OK**.
    
      - Per un record DNS esterno, digitare o passare all'FQDN dei servizi Web esterni per il pool di Director, ad esempio lyncwebextdir.contoso.com, e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se non si usa un amministratore, usare il nome di dominio completo dei servizi Web interni ed esterni per il pool Front-end oppure, per un singolo server, il nome di dominio completo per il server front-end o Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario creare un nuovo record CNAME di individuazione automatica nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Per creare record DNS

1.  Accedere a un server DNS come indicato di seguito:
    
      - Per creare un record DNS interno, accedere a un server DNS della rete come membro del gruppo Domain Admins o membro del gruppo DnsAdmins.
    
      - Per creare un record DNS esterno, connettersi al provider DNS pubblico o al server DNS esterno.

2.  Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

3.  Esegui una delle operazioni seguenti:
    
      - Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory, ad esempio contoso. local.
        
        <div>
        

        > [!NOTE]  
        > Questo dominio è il dominio Active Directory in cui sono installati il&nbsp;pool di Lync Server 2013 Director e il pool Front end.

        
        </div>
    
      - Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.

4.  Verificare che esista un record host A (per IPv6, AAAA) per il pool di Director come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record host A (per IPv6, AAAA) per il nome di dominio completo dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record host A (per IPv6, AAAA) per il nome di dominio completo dei servizi Web esterni per il pool di Director (ad esempio, lyncwebextdir.contoso.com).

5.  Verificare che sia presente un record host A (per IPv6, AAAA) per il pool Front-End, come indicato di seguito:
    
      - Per un record DNS interno, deve esistere un record host A (per IPv6, AAAA) per l'FQDN dei servizi Web interni per il pool Front-End, ad esempio lyncwebpool01. contoso. local.
    
      - Per un record DNS esterno, deve esistere un record host A (per IPv6, AAAA) per il nome di dominio completo dei servizi Web esterni per il pool Front-End, ad esempio lyncwebextpool01.contoso.com.

6.  Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.
    
    <div>
    

    > [!NOTE]  
    > Se si sta creando un record DNS esterno, le <STRONG>aree di ricerca inoltrate</STRONG> sono già espanse per il dominio SIP dal passaggio 3.

    
    </div>

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo host (A o AAAA)**.

8.  In **nome**Digitare il nome dell'host come indicato di seguito:
    
      - Per un record DNS interno, digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.
    
      - Per un record DNS esterno, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.
    
    <div>
    

    > [!NOTE]  
    > Il nome di dominio viene considerato dalla zona in cui è definito il record e, pertanto, non deve essere immesso come parte del record A.

    
    </div>

9.  In **indirizzo IP**Digitare l'indirizzo IP come indicato di seguito:
    
      - Per un record DNS interno, digitare l'indirizzo IP dei servizi Web interni del Director oppure, se si usa un servizio di bilanciamento del carico, digitare l'IP virtuale (VIP) del bilanciamento del carico di Director.
        
        <div>
        

        > [!NOTE]  
        > Se non si usa un amministratore, digitare l'indirizzo IP del server front-end o Standard Edition oppure, se si usa un bilanciamento del carico, digitare il VIP del bilanciamento del carico del pool di front-end.

        
        </div>
    
      - Per un record DNS esterno, digitare l'indirizzo IP esterno o pubblico del proxy inverso.

10. Fare clic su **Aggiungi host**e quindi su **OK**.

11. Per creare un record aggiuntivo, ripetere i passaggi da 8 a 10.
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario creare un nuovo Lyncdiscover e lyncdiscoverinternal un record nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

    
    </div>

12. Al termine della creazione di un record (per IPv6, AAAA), fare clic su **fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

