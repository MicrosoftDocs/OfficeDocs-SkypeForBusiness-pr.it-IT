---
title: 'Lync Server 2013: creazione di record DNS per il servizio di individuazione automatica'
description: 'Lync Server 2013: creazione di record DNS per il servizio di individuazione automatica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563102"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-20_

Gli utenti di Lync mobile avranno bisogno di abilitare l'individuazione automatica e una parte di esso implica la creazione di alcuni record DNS (Domain Name System). In base alle proprie esigenze, è necessario quanto segue:

  - Un record DNS interno per supportare gli utenti mobili che si connettono dall'interno della rete dell'organizzazione.

  - Un record DNS esterno, o pubblico, per supportare gli utenti di dispositivi mobili che si connettono da Internet

Perché entrambi? È necessario creare sia un record DNS interno che un record DNS esterno per ogni dominio SIP.

I record DNS creati possono essere record A (host) o CNAME. Per ottenere assistenza, è possibile procedere come creare questi record DNS interni ed esterni. Per ulteriori informazioni sui requisiti DNS per gli utenti mobili, è possibile consultare i [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Creazione di un record CNAME DNS interno

1.  Per creare un record DNS interno, è necessario eseguire l'accesso a un server DNS della rete con un account di dominio che sia un membro del gruppo Domain Admins o un membro del gruppo DnsAdmins.

2.  Aprire lo snap-in amministrativo DNS. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi fare clic su **DNS**.

3.  Nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio Active Directory in cui sono installati il pool di 2013 server Director e il pool Front end. (ad esempio, contoso. local).

4.  Controllare e vedere se esiste un record host A (AAAA per IPv6) per il pool di server Director per un record DNS interno, deve esistere un record host a per il nome di dominio completo (FQDN) dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local. Se non è presente, è possibile che non si utilizzi un pool di server Director e che sia necessario utilizzare il nome di dominio completo del pool Front end o persino un FQDN di un singolo computer, se questa è la configurazione.

5.  Tenendo presente questo avviso, verificare se esiste un record host A (AAAA per IPv6) per il pool Front end per un record DNS interno, deve esistere un record host A (o AAAA) per l'FQDN dei servizi Web interni per il pool Front End, ad esempio lyncwebpool01. contoso. local. In caso contrario, è necessario prendere nota del nome di dominio completo del server front end server o Standard Edition.

6.  Dopo aver saputo quali record host A (o AAAA) esistono, nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio SIP, ad esempio contoso.com.

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **Nuovo alias (CNAME)**.

8.  In **nome alias**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.

9.  In **nome di dominio completo (FQDN) per host di destinazione**Digitare o passare all'FQDN dei servizi Web interni per il pool di server Director, ad esempio lyncwebdir01. contoso. local, e quindi fare clic su **OK**.

10. È necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Creazione di un record CNAME DNS esterno

1.  Per creare un record CNAME DNS esterno, è necessario connettersi al provider DNS pubblico e quindi seguire i passaggi. Non è possibile descrivere esattamente la posizione in cui si sta nell'ambiente del provider DNS, in quanto potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma è possibile che questi passaggi siano utili.

2.  Accedere al provider DNS esterno con un account che possa creare record DNS in tale ambiente.

3.  È già necessario disporre di un dominio SIP creato per questo ambiente. Espandere la **zona di ricerca diretta** per il dominio SIP oppure selezionarla in base all'interfaccia DNS esterna utilizzata.

4.  È già necessario visualizzare un record host A (AAAA per IPv6) per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com), quindi verificare che sia presente. In caso contrario, potrebbe non essere utilizzato un pool di server Director. In tal caso, è necessario utilizzare il nome di dominio completo del pool Front end oppure se si esegue questa operazione per un singolo server, per il server Front-End o per il server Standard Edition.

5.  È inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool Front End (ad esempio lyncwebextpool01.contoso.com) oppure un FQDN per l'FQDN a server singolo se non si dispone di un pool Front end. Come indicato nel passaggio precedente, è necessario eseguire le seguenti operazione se non si dispone di un pool di server Director.

6.  A questo punto, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo alias (CNAME)** (può essere un'opzione di menu o un collegamento, a seconda del formato del provider DNS).

7.  La casella di testo **nome alias** dovrebbe essere una forma come con il DNS interno, è necessario immettere Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.

8.  È inoltre necessario disporre di una forma di un **nome di dominio completo (FQDN) per** la casella di testo host di destinazione, in cui è possibile immettere l'FQDN dei servizi Web esterni per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com) e quindi fare clic su OK o su qualsiasi azione nel DNS esterno per accettare la creazione di questa voce. Come indicato nel passaggio 4, in alto, se non si dispone di un pool di server Director, è necessario utilizzare il nome di dominio completo del pool Front end o il nome di dominio completo (FQDN) che è stato configurato, a seconda dei casi.

9.  Sarà necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Creazione di un record A DNS interno

1.  Per creare un record DNS interno, eseguire l'accesso a un server DNS della rete con un account di dominio che sia membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

2.  Aprire lo snap-in amministrativo DNS. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi fare clic su **DNS**.

3.  Per un record DNS interno, nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio Active Directory, ad esempio contoso. local, in cui sono installati il pool di server Director e il pool Front End di Lync 2013.

4.  Controllare e vedere se esiste un record host A (AAAA per IPv6) per il pool di server Director per un record DNS interno, deve esistere un record host a per il nome di dominio completo (FQDN) dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local. Se non è presente, è possibile che non si utilizzi un pool di server Director e che sia necessario utilizzare l'indirizzo IP per il pool Front end o persino un indirizzo IP di un singolo computer, se questa è la configurazione.

5.  Tenendo presente questo avviso, verificare se esiste un record host A (AAAA per IPv6) per il pool Front end per un record DNS interno, deve esistere un record host A (o AAAA) per l'FQDN dei servizi Web interni per il pool Front End, ad esempio lyncwebpool01. contoso. local. In caso contrario, è necessario prendere nota dell'indirizzo IP per il front end server o il server Standard Edition.

6.  Dopo aver saputo quali record host A (o AAAA) esistono, nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio SIP, ad esempio contoso.com.

7.  Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **Nuovo host (A o AAAA)**.

8.  In **nome**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.

9.  In **indirizzo IP**Digitare l'indirizzo IP dei servizi Web interni del Director (oppure, se si utilizza un servizio di bilanciamento del carico, digitare l'IP virtuale (VIP) del bilanciamento del carico del server Director). Come indicato nel passaggio 4 precedente, se non si utilizza un Director, potrebbe essere necessario immettere l'indirizzo IP del server front end server o Standard Edition oppure, se si utilizza un bilanciamento del carico, digitare il VIP del bilanciamento del carico del pool Front end.

10. Fare clic su **Aggiungi host** e quindi su **OK**.

11. Per creare un record A o AAAA aggiuntivo, ripetere i passaggi da 8 a 10, tenendo presente che sarà necessario creare nuovi record a o AAAA di individuazione automatica nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.

12. Dopo aver terminato di creare i record A (per IPv6, AAAA), fare clic su **Fine**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Creazione di un record A DNS esterno

1.  Per creare un record DNS esterno, connettersi al provider DNS pubblico e quindi seguire i passaggi. Non è possibile descrivere esattamente la posizione in cui si sta nell'ambiente del provider DNS, in quanto potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma è possibile che questi passaggi siano utili.

2.  È necessario essere connessi come account in grado di creare record DNS in tale ambiente.

3.  Per un record DNS esterno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com. Per un record DNS esterno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com.

4.  È già necessario visualizzare un record host A (AAAA per IPv6) per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com), quindi verificare che sia presente e cosa sia l'indirizzo IP. In caso contrario, potrebbe non essere utilizzato un pool di server Director. In tal caso, è necessario utilizzare l'indirizzo IP del pool Front end oppure se si esegue questa operazione per un singolo server, per il server Front-End o per il server Standard Edition. Tenere presente che i server possono anche essere dietro un sistema di bilanciamento del carico o tramite un proxy inverso. Prendere nota degli indirizzi IP, nonché per i passaggi riportati di seguito.

5.  È inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool Front End, ad esempio lyncwebextpool01.contoso.com, oppure un indirizzo IP per l'installazione di Lync a server singolo, se non si dispone di un pool Front end. Come indicato nel passaggio precedente, è necessario eseguire le seguenti operazione se non si dispone di un pool di server Director.

6.  A questo punto, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo host a o AAAA** (può essere un'opzione di menu o un collegamento, a seconda del formato del provider DNS).

7.  È necessario specificare un **nome**, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.

8.  Ci dovrebbe essere anche una casella di testo **indirizzo IP** , ecco dove è possibile immettere l'IP per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com) o eventualmente l'IP del servizio di bilanciamento del carico del pool (o un IP proxy inverso che conduce allo stesso) e quindi fare clic su OK o su qualsiasi azione nel DNS esterno per accettare la creazione di questa voce. Come indicato nel passaggio 4, in alto, se non si dispone di un pool di server Director, è necessario utilizzare l'indirizzo IP del pool Front end o l'indirizzo IP a un singolo utente configurato, in base alle esigenze.

9.  Sarà necessario creare un nuovo record di individuazione automatica a o AAAA nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

