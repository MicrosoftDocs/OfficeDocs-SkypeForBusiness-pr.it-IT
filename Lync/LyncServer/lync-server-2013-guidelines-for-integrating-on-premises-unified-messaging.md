---
title: "Lync Server 2013: linee guida per l'integrazione della messaggistica unificata locale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44f032f7dd7d11d70ac912b2005f3ad9f7ddad69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536923"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-25_

Di seguito sono riportate le linee guida e le procedure consigliate da considerare quando si distribuisce VoIP aziendale:

<div>


> [!IMPORTANT]  
> La messaggistica unificata di Exchange supporta IPv6 solo se si utilizza anche UCMA 4.



</div>

  - Distribuire un server di Lync Server 2013 Standard Edition o un pool Front end. Per informazioni dettagliate sull'installazione, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

  - Collaborare con gli amministratori di Exchange per verificare le attività che verranno eseguite da ognuno al fine di assicurare un'integrazione agevole e corretta.

  - Distribuire i ruoli del server cassette postali di Exchange in ogni foresta di messaggistica unificata di Exchange in cui si desidera abilitare gli utenti per la messaggistica unificata di Exchange. Per informazioni dettagliate sull'installazione dei ruoli del server Exchange, vedere la documentazione di Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando la messaggistica unificata di Exchange è installata, è configurata per l'utilizzo di un certificato autofirmato.<BR>Il certificato autofirmato, tuttavia, non consente a Lync Server 2013 e alla messaggistica unificata di Exchange di essere attendibili tra loro, per questo motivo è necessario richiedere un certificato distinto da un'autorità di certificazione attendibile per entrambi i server.

    
    </div>

  - Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange affinché consideri attendibile la foresta Lync Server 2013 e la foresta Lync Server 2013 per considerare attendibile ogni foresta di Exchange. Inoltre, impostare le impostazioni di messaggistica unificata di Exchange degli utenti sugli oggetti utente nella foresta di Lync Server 2013, in genere tramite uno script o uno strumento tra foreste, ad esempio Identity Lifecycle Manager (ILM).

  - Se necessario, installare Exchange Management Console per gestire i server di messaggistica unificata.

  - Ottenere numeri di telefono validi per Outlook Voice Access e l'operatore automatico.

  - Se si utilizza una versione della messaggistica unificata di Exchange in precedenza rispetto a Microsoft Exchange Server 2010 Service Pack 1 (SP1), i nomi di coordinate per i dial plan di messaggistica unificata di Exchange e dial plan VoIP aziendale.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Distribuzione di server di messaggistica unificata di Exchange ridondanti

<div>


> [!IMPORTANT]  
> Si consiglia di distribuire almeno due server su cui è in esecuzione il servizio di messaggistica unificata di Exchange per ogni dial plan di messaggistica unificata SIP di Exchange che viene configurato per l'organizzazione. Oltre a fornire la capacità espansa, la distribuzione di server ridondanti garantisce una disponibilità elevata. In caso di errore del server, Lync Server 2013 può essere configurato per eseguire il failover su un altro server.



</div>

Le configurazioni di esempio seguenti garantiscono resilienza della messaggistica unificata di Exchange.

**Esempio 1: resilienza della messaggistica unificata di Exchange**

![Esempio di messaggistica unificata di Exchange 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Esempio di messaggistica unificata di Exchange 1")

Nell'esempio 1 i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino. In caso di un'interruzione della messaggistica unificata di Exchange in Tukwila, i record DNS (Domain Name System) per i server 1 e 2 devono essere configurati in modo che puntino rispettivamente ai server 3 e 4. In caso di un'interruzione della messaggistica unificata di Exchange a Dublino, i record A DNS per i server 3 e 4 devono essere configurati in modo che puntino rispettivamente ai server 1 e 2.

<div>


> [!NOTE]  
> Per l'esempio 1, è anche necessario assegnare uno dei certificati seguenti in ogni server di messaggistica unificata di Exchange: 
> <UL>
> <LI>
> <P>Utilizzare un certificato con un carattere jolly nel nome alternativo del soggetto.</P>
> <LI>
> <P>Inserire il nome di dominio completo (FQDN) di ognuno dei quattro server di messaggistica unificata di Exchange nel SAN.</P></LI></UL>



</div>

**Esempio 2: resilienza della messaggistica unificata di Exchange**

![Esempio di messaggistica unificata di Exchange 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Esempio di messaggistica unificata di Exchange 2")

Nell'esempio 2, in condizioni operative standard, i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino. Tutti e quattro i server sono inclusi nel dial plan URI SIP degli utenti Tukwila, tuttavia, i server 3 e 4 sono disabilitati. In caso di interruzione della messaggistica unificata di Exchange a Tukwila, ad esempio, i server 1 e 2 di messaggistica unificata di Exchange devono essere disabilitati e i server 3 e 4 di messaggistica unificata di Exchange devono essere abilitati in modo che il traffico di messaggistica unificata di Exchange di Tukwila venga instradato ai server di Dublino.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Exchange 2013, vedere la sezione relativa alla messaggistica unificata di Exchange 2013 con Lync Server all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Microsoft Exchange Server 2010, vedere:

  - "Abilita messaggistica unificata su Exchange 2010" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) .

  - "Disabilitare la messaggistica unificata su Exchange 2010" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Processo di distribuzione per l'integrazione della messaggistica unificata locale e di Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

