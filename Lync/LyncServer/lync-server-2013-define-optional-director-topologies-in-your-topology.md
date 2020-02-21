---
title: 'Lync Server 2013: definire topologie di Director opzionali nella topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0448ddfdb9988b791ff14dff89ab4c122df1d38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definire topologie Director opzionali nella topologia per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

I direttori di Lync Server 2013 possono essere server a istanza singola oppure possono essere installati come pool di più direttori con bilanciamento del carico per una maggiore disponibilità e capacità. Sono supportati sia il bilanciamento del carico hardware sia il bilanciamento del carico DNS (Domain Name System). In questo argomento viene descritto come configurare il bilanciamento del carico DNS per i pool di server Director.

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo server, è necessario accedere come utente membro dei gruppi **RTCUniversalServerAdmins** e **Domain Admins**. È anche possibile delegare i diritti e le autorizzazioni di amministratore appropriate per l'aggiunta dei ruoli server. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione di server Standard Edition o Server Enterprise Edition. Per poter apportare altre modifiche alla configurazione, è richiesta solo l'appartenenza al gruppo **RTCUniversalServerAdmins**.

In questo argomento vengono descritti i passaggi necessari per definire e pubblicare la topologia per le due topologie del Director:

  - Per definire il Director (istanza singola)

  - Per definire il Director (più pool di server Director)

<div>

## <a name="to-define-the-director-single-instance"></a>Per definire il Director (istanza singola)

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nella pagina di benvenuto fare clic su **Scarica topologia dalla distribuzione esistente**.

3.  Nella finestra di dialogo **Salva topologia con nome** digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.

4.  Espandere il sito in cui si intende aggiungere il Director, fare clic con il pulsante destro del mouse su **Pool di server Director** e quindi fare clic su **Nuovo pool di server Director**.

5.  Nella finestra di dialogo **Definire l'FQDN del pool di server Director** eseguire le operazioni seguenti:
    
      - In **FQDN pool** digitare l'FQDN del pool di server Director.
    
      - Fare clic su **Pool computer singolo** e quindi fare clic su **Avanti**.

6.  Nella finestra di dialogo **Definire condivisione file** eseguire una delle operazioni seguenti:
    
    1.  Per utilizzare una condivisione file esistente, fare clic su **Utilizza condivisione file definita in precedenza**, selezionare una condivisione file nell'elenco e quindi fare clic su **Avanti**.
    
    2.  Per creare una nuova condivisione file, fare clic su **Definisci nuova condivisione file**, digitare l'FQDN del percorso della condivisione file in **FQDN file server**, digitare il nome della condivisione in **Condivisione file** e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!IMPORTANT]  
    > La condivisione file specificata o creata in questo passaggio deve esistere o essere creata prima della pubblicazione della topologia.<BR>La condivisione file assegnata a un Director in realtà non viene utilizzata, pertanto è possibile assegnare la condivisione file di qualsiasi pool all'interno dell'organizzazione.

    
    </div>

7.  Nella finestra di dialogo **Specificare l'URL dei servizi Web**, in **URL di base esterno** specificare l'FQDN per i server Director e quindi fare clic su **Fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il nome deve essere risolvibile dai server DNS Internet e puntare all'indirizzo IP pubblico del proxy inverso, che resta in attesa delle richieste HTTP/HTTPS a tale URL e le trasmette tramite proxy alla directory virtuale dei servizi Web esterni in tale Director.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco. Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server. Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end. Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.

    
    </div>

8.  Pubblicare la topologia.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Per definire il Director (pool di più server Director)

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nella pagina di benvenuto fare clic su **Scarica topologia dalla distribuzione esistente**.

3.  Nella finestra di dialogo **Salva topologia con nome** digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.

4.  Espandere il sito in cui si intende aggiungere il Director, fare clic con il pulsante destro del mouse su **Pool di server Director** e quindi fare clic su **Nuovo pool di server Director**.

5.  Nella finestra di dialogo **Definire l'FQDN del pool di server Director** eseguire le operazioni seguenti:
    
      - In **FQDN pool** digitare l'FQDN del pool di server Director.
    
      - Fare clic su **Pool di più computer** e quindi su **Avanti**.

6.  Nella finestra di dialogo **Definire i computer nel pool corrente** eseguire le operazioni seguenti:
    
      - Specificare l'FQDN del computer del primo membro del pool e quindi fare clic su **Aggiungi**.
    
      - Ripetere il passaggio precedente per ogni computer da aggiungere. Al termine, fare clic su **Avanti**.

7.  Nella finestra di dialogo **Definire condivisione file** eseguire una delle operazioni seguenti:
    
      - Per utilizzare una condivisione file esistente, fare clic su **Utilizza condivisione file definita in precedenza**, selezionare una condivisione file nell'elenco e quindi fare clic su **Avanti**.
    
      - Per creare una nuova condivisione file, fare clic su **Definisci nuova condivisione file**, digitare l'FQDN del percorso della condivisione file in **FQDN file server**, digitare il nome della condivisione in **Condivisione file** e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!IMPORTANT]  
    > La condivisione file specificata o creata in questo passaggio deve esistere o essere creata prima della pubblicazione della topologia.<BR>La condivisione file assegnata a un Director in realtà non viene utilizzata, pertanto è possibile assegnare la condivisione file di qualsiasi pool all'interno dell'organizzazione.

    
    </div>

8.  Nella finestra di dialogo **Specificare l'URL dei servizi Web**, in **URL di base esterno**, specificare l'FQDN dei Director e quindi fare clic su **Fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il nome deve essere risolvibile dai server DNS Internet e puntare all'indirizzo IP pubblico del proxy inverso che è in attesa delle richieste HTTP/HTTPS inviate a tale URL e le trasmette mediante proxy alla directory virtuale dei Servizi Web esterni su tale pool di server Director.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco. Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server. Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end. Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.

    
    </div>

9.  Pubblicare la topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

