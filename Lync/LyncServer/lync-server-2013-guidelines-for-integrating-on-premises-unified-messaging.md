---
title: "Lync Server 2013: Linee guida per l'integrazione della messaggistica unificata locale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15973bf2055339e375e4aecc7cfd1f61ac205dbb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Linee guida per l'integrazione della messaggistica unificata locale con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-25_

Di seguito sono riportate le linee guida e le procedure consigliate per la distribuzione di VoIP aziendale:

<div>


> [!IMPORTANT]  
> La messaggistica unificata di Exchange supporta IPv6 solo se si usa anche UCMA 4.



</div>

  - Distribuire un server di Lync Server 2013 Standard Edition o un pool Front-end. Per informazioni dettagliate sull'installazione, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

  - Collaborare con gli amministratori di Exchange per confermare le attività che ognuno di voi eseguirà per garantire un'integrazione corretta e efficace.

  - Distribuire i ruoli del server cassette postali di Exchange in ogni foresta di messaggistica unificata di Exchange in cui si vuole abilitare gli utenti per la messaggistica unificata di Exchange. Per informazioni dettagliate sull'installazione dei ruoli di Exchange Server, vedere la documentazione di Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando è installata la messaggistica unificata di Exchange, è configurata per l'uso di un certificato autofirmato.<BR>Il certificato autofirmato, tuttavia, non consente a Lync Server 2013 e alla messaggistica unificata di Exchange di considerarsi attendibili, per cui è necessario richiedere un certificato distinto da un'autorità di certificazione attendibile per entrambi i server.

    
    </div>

  - Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta Lync Server 2013 e la foresta di Lync Server 2013 per considerare attendibile ogni foresta di Exchange. Inoltre, imposta le impostazioni di messaggistica unificata di Exchange degli utenti negli oggetti utente nella foresta di Lync Server 2013, in genere usando uno script o uno strumento tra insiemi di strutture, ad esempio ILM (Identity Lifecycle Manager).

  - Se necessario, installare Exchange Management Console per gestire i server di messaggistica unificata.

  - Ottenere i numeri di telefono validi per Outlook Voice Access e l'operatore automatico.

  - Se si usa una versione di messaggistica unificata di Exchange precedente a Microsoft Exchange Server 2010 Service Pack 1 (SP1), i nomi delle coordinate per i dial plan di messaggistica unificata di Exchange UM e i piani per le chiamate vocali aziendali.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Distribuzione di server Messaggistica unificata di Exchange ridondanti

<div>


> [!IMPORTANT]  
> È consigliabile distribuire un minimo di due server in cui i servizi di messaggistica unificata di Exchange sono in esecuzione per ogni dial plan di messaggistica unificata di Exchange che si configura per l'organizzazione. Oltre a fornire capacità espansa, la distribuzione di server ridondanti offre una disponibilità elevata. In caso di errore del server, Lync Server 2013 può essere configurato per il failover su un altro server.



</div>

Le configurazioni di esempio seguenti garantiscono la resilienza della messaggistica unificata di Exchange.

**Esempio 1: resilienza della messaggistica unificata di Exchange**

![Esempio di messaggistica unificata di Exchange 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "esempio di um Exchange 1")

Nell'esempio 1 i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel centro dati di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel Data Center di Dublino. In caso di interruzione della messaggistica unificata di Exchange in Tukwila, il DNS (Domain Name System) record per i server 1 e 2 deve essere configurato in modo che punti rispettivamente ai server 3 e 4. In caso di interruzione della messaggistica unificata di Exchange in Dublin, è necessario configurare i record DNS per i server 3 e 4 in modo che puntino rispettivamente ai server 1 e 2.

<div>


> [!NOTE]  
> Ad esempio 1, devi anche assegnare uno dei seguenti certificati in ogni server Messaggistica unificata di Exchange: 
> <UL>
> <LI>
> <P>Usare un certificato con un carattere jolly nel nome alternativo soggetto (SAN).</P>
> <LI>
> <P>Inserire il nome di dominio completo (FQDN) di ognuno dei quattro server di messaggistica unificata di Exchange nella SAN.</P></LI></UL>



</div>

**Esempio 2: resilienza della messaggistica unificata di Exchange**

![Esempio di messaggistica unificata di Exchange 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "esempio di um") di Exchange 2

Nell'esempio 2, in condizioni operative ordinarie i server Messaggistica unificata di Exchange 1 e 2 sono abilitati nel centro dati Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel Data Center di Dublino. Tutti e quattro i server sono inclusi nel dial plan URI SIP degli utenti di Tukwila; Tuttavia, i server 3 e 4 sono disabilitati. In caso di interruzione della messaggistica unificata di Exchange in Tukwila, ad esempio, i server di messaggistica unificata di Exchange 1 e 2 devono essere disabilitati e i server di messaggistica unificata di Exchange 3 e 4 devono essere abilitati in modo che il traffico di messaggistica unificata di Exchange venga Tukwila ai server di Dublino.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Exchange 2013, vedere "integrare la messaggistica unificata di Exchange 2013 [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)con Lync Server" all'indirizzo.

Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Microsoft Exchange Server 2010, vedere:

  - "Abilita la messaggistica unificata su Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)at.

  - "Disabilitare la messaggistica unificata su Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)in.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Processo di distribuzione per l'integrazione della messaggistica unificata locale con Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

