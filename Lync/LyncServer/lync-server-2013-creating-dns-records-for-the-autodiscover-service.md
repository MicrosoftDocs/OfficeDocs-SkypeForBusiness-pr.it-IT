---
title: 'Lync Server 2013: Creazione di record DNS per il servizio di individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5307251e9c3dea202b08b48bf45e109ef19449ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-20_

Gli utenti di Lync mobile dovranno abilitare l'individuazione automatica e parte della creazione di alcuni record DNS (Domain Name System). A seconda delle esigenze, è necessario quanto segue:

  - Un record DNS interno che supporta gli utenti di dispositivi mobili che si connettono dall'interno della rete dell'organizzazione.

  - Un record DNS esterno o pubblico per supportare gli utenti di dispositivi mobili che si connettono da Internet

Perché entrambi? È necessario creare sia un record DNS interno che un record DNS esterno per ogni dominio SIP.

I record DNS creati possono essere un record (host) o un record CNAME. Per semplificare la creazione di questi record DNS interni ed esterni, è possibile procedere come segue. Per altre informazioni sui requisiti DNS per gli utenti di dispositivi mobili, è possibile consultare i [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Creazione di un record CNAME DNS interno

1.  Per creare un record DNS interno, è necessario accedere a un server DNS della rete con un account di dominio che sia un membro del gruppo Domain Admins o un membro del gruppo DnsAdmins.

2.  Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

3.  Nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory in cui sono installati il pool di Lync Server 2013 Director e il pool Front end. (ad esempio, contoso. local).

4.  Verificare se per il pool di Director è presente un record host (AAAA per IPv6) per un record DNS interno, è necessario che sia presente un record per il nome di dominio completo dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local. Se non è presente, è possibile che non si stia usando un pool di Director e che sia necessario usare il nome di dominio completo per il pool di front end o anche un FQDN di un singolo server, se questa è la configurazione.

5.  Tenendo presente questo aspetto, verificare se per il pool di front end esiste un record (AAAA per IPv6) ospitante per un record DNS interno, deve esistere un record host A (o AAAA) per il nome di dominio completo dei servizi Web interni per il pool di front-end, ad esempio , lyncwebpool01. contoso. local). In caso contrario, è necessario prendere nota del nome di dominio completo per il server front-end o Standard Edition.

6.  Una volta che si sa quali sono i record host A (o AAAA), nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo alias (CNAME)**.

8.  In **nome alias**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.

9.  In **nome di dominio completo (FQDN) per l'host di destinazione**Digitare o passare all'FQDN dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local, e quindi fare clic su **OK**.

10. È necessario creare un nuovo record CNAME di individuazione automatica nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Creazione di un record CNAME DNS esterno

1.  Per creare un record CNAME DNS esterno, è necessario connettersi al provider DNS pubblico e seguire i passaggi descritti di seguito. Non è possibile descrivere esattamente il punto in cui ci si trova nell'ambiente del provider DNS perché potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma ci auguriamo che questi passaggi siano utili.

2.  Accedere al provider DNS esterno con un account che può creare record DNS in tale ambiente.

3.  Dovresti avere già un dominio SIP creato per questo ambiente. Espandi l' **area di ricerca diretta** per il dominio SIP oppure selezionala in base all'interfaccia DNS esterna in uso.

4.  Si dovrebbe già vedere un record host (AAAA per IPv6) per il pool di Director (ad esempio lyncwebexdir01.contoso.com), quindi verificare che sia presente. In caso contrario, potresti non usare un pool di Director. In questo caso, è necessario usare il nome di dominio completo del pool Front-end oppure, se si esegue questa operazione per un singolo server, per il server front-end o per il server Standard Edition.

5.  Sarà inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool di front-end (ad esempio lyncwebextpool01.contoso.com) o un nome di dominio completo per il nome di dominio completo del server singolo se non si dispone di un pool Front-end. Come indicato nel passaggio precedente, se non si dispone di un pool di Director, sarà necessario eseguire questa operazione.

6.  A questo punto, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo alias (CNAME)** , che può essere un'opzione di menu o un collegamento, a seconda del formato del provider DNS.

7.  Dovrebbe essere presente una qualche forma di casella di testo **nome alias** con il DNS interno, devi immettere Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterna.

8.  Dovrebbe essere disponibile anche una forma di un **nome di dominio completo (FQDN) per** la casella di testo host di destinazione, ecco dove si immetterà l'FQDN dei servizi Web esterni per il pool di Director (ad esempio, lyncwebexdir01.contoso.com) e quindi fare clic su OK o su qualsiasi azione nel DNS esterno per accettare la creazione di questa voce. Come indicato nel passaggio 4, in precedenza, se non si dispone di un pool di Director, sarà necessario usare il nome di dominio completo del pool di front end o il nome di dominio completo a server singolo configurato, in base alle esigenze.

9.  È necessario creare un nuovo record CNAME di individuazione automatica nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Creazione di un record DNS interno

1.  Per creare un record DNS interno, accedere a un server DNS della rete con un account di dominio membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

2.  Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

3.  Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory, ad esempio contoso. local, in cui sono installati il pool di Lync Server 2013 Director e il pool Front end.

4.  Verificare se per il pool di Director è presente un record host (AAAA per IPv6) per un record DNS interno, è necessario che sia presente un record per il nome di dominio completo dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local. Se non è presente, è possibile che non si usi un pool di Director e che sia necessario usare l'indirizzo IP per il pool Front-end o anche un singolo indirizzo IP del server, se questa è la configurazione.

5.  Tenendo presente questo aspetto, verificare se per il pool di front end esiste un record (AAAA per IPv6) ospitante per un record DNS interno, deve esistere un record host A (o AAAA) per il nome di dominio completo dei servizi Web interni per il pool di front-end, ad esempio , lyncwebpool01. contoso. local). In caso contrario, è necessario prendere nota dell'indirizzo IP per il server front-end o Standard Edition.

6.  Una volta che si sa quali sono i record host A (o AAAA), nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo host (A o AAAA)**.

8.  In **nome**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.

9.  In **indirizzo IP**Digitare l'indirizzo IP dei servizi Web interni del Director (oppure, se si usa un servizio di bilanciamento del carico, digitare l'IP virtuale (VIP) del bilanciamento del carico del direttore). Come indicato nel passaggio 4, se non si usa un Director, potrebbe essere necessario immettere l'indirizzo IP del server front-end o Standard Edition oppure, se si usa un bilanciamento del carico, digitare il VIP del bilanciamento del carico del pool di front-end.

10. Fare clic su **Aggiungi host**e quindi su **OK**.

11. Per creare un record A o AAAA aggiuntivo, ripetere i passaggi da 8 a 10, tenendo presente che è necessario creare nuovi record di individuazione automatica a o AAAA nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

12. Al termine della creazione di un record (per IPv6, AAAA), fare clic su **fine**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Creazione di un record DNS esterno

1.  Per creare un record DNS esterno, connettersi al provider DNS pubblico e seguire i passaggi. Non è possibile descrivere esattamente il punto in cui ci si trova nell'ambiente del provider DNS perché potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma ci auguriamo che questi passaggi siano utili.

2.  È necessario avere effettuato l'accesso come account che può creare record DNS in quell'ambiente.

3.  Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com. Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.

4.  Si dovrebbe già vedere un record host (AAAA per IPv6) per il pool di Director (ad esempio lyncwebexdir01.contoso.com), quindi verificare che sia presente e quale sia l'indirizzo IP. In caso contrario, potresti non usare un pool di Director. In questo caso, è necessario usare l'indirizzo IP del pool Front-end oppure, se si esegue questa operazione per un singolo server, per il server front-end o per il server Standard Edition. Tieni presente che i server potrebbero essere anche dietro a un dispositivo di bilanciamento del carico oppure usando un proxy inverso. Prendere nota degli indirizzi IP anche per seguire i passaggi seguenti.

5.  È inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool di front end (ad esempio lyncwebextpool01.contoso.com) o un indirizzo IP per l'installazione di Lync a server singolo se si non hanno pool Front-end. Come indicato nel passaggio precedente, se non si dispone di un pool di Director, sarà necessario eseguire questa operazione.

6.  Ora, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo host a o AAAA** (può trattarsi di un'opzione di menu o di un collegamento, a seconda del formato del provider DNS).

7.  Dovrebbe essere disponibile una posizione in cui immettere un **nome**, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.

8.  Dovrebbe essere anche disponibile una casella di testo per l' **indirizzo IP** , che consente di immettere l'IP per il pool di Director (ad esempio, lyncwebexdir01.contoso.com) o eventualmente per l'IP del servizio di bilanciamento del carico del pool (o di un IP proxy inverso che conduce allo stesso), quindi fare clic su OK o eseguire qualsiasi azione nel DNS esterno per accettare la creazione di questa voce. Come indicato nel passaggio 4, in precedenza, se non si dispone di un pool di Director, è necessario usare l'indirizzo IP del pool Front-end o l'indirizzo IP a server singolo configurato, in base alle esigenze.

9.  È necessario creare un nuovo record di individuazione automatica a o AAAA nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

