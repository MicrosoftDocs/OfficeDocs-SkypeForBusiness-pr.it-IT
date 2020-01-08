---
title: 'Lync Server 2013: Definire topologie con server Director facoltativi nella topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definire topologie con server Director facoltativi nella topologia per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Gli amministratori di Lync Server 2013 possono essere server a istanza singola oppure possono essere installati come pool di più direttori con bilanciamento del carico per una maggiore disponibilità e capacità. Sono supportati sia il bilanciamento del carico hardware che il bilanciamento del carico DNS (Domain Name System). Questo argomento spiega come configurare il bilanciamento del carico DNS per i pool di Director.

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario essere connessi come utenti membri dei gruppi **RTCUniversalServerAdmins** e **Domain Admins** . È anche possibile delegare i diritti e le autorizzazioni di amministratore appropriati per l'aggiunta di ruoli server. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione sulla distribuzione di server Standard Edition o Server Enterprise Edition. Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo **RTCUniversalServerAdmins** .

In questo argomento vengono illustrati i passaggi per definire e pubblicare la topologia per le due topologie di Director:

  - Per definire il Director (istanza singola)

  - Per definire il Director (pool di più direttori)

<div>

## <a name="to-define-the-director-single-instance"></a>Per definire il Director (istanza singola)

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nella pagina di benvenuto fare clic su **Scarica topologia da distribuzione esistente**.

3.  Nella finestra di dialogo **Salva topologia come** Digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.

4.  Espandere il sito in cui si prevede di aggiungere il Director, fare clic con il pulsante destro del mouse su pool di **Director**e quindi scegliere **nuovo pool di Director**.

5.  Nella finestra di dialogo **Definisci il nome di dominio completo del pool di Director** eseguire le operazioni seguenti:
    
      - In **FQDN del pool**Digitare il nome di dominio completo per il pool di Director.
    
      - Fare clic su **pool di computer singolo**e quindi su **Avanti**.

6.  Nella finestra di dialogo **Definisci la condivisione file** eseguire una delle operazioni seguenti:
    
    1.  Per usare una condivisione file esistente, fare clic su **Usa una condivisione file definita in precedenza**, selezionare una condivisione file dall'elenco e quindi fare clic su **Avanti**.
    
    2.  Per creare una nuova condivisione di file, fare clic su **Definisci una nuova condivisione file**, digitare il nome di dominio completo relativo alla posizione della condivisione file nell' **FQDN del file server**, digitare la condivisione in **condivisione file**e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!IMPORTANT]  
    > La condivisione di file specificata o creata in questo passaggio deve esistere o crearsi prima di pubblicare la topologia.<BR>La condivisione file assegnata a un amministratore non viene effettivamente usata, quindi è possibile assegnare la condivisione file di qualsiasi pool nell'organizzazione.

    
    </div>

7.  Nella finestra di dialogo **specifica URL servizi Web** , in **URL di base esterno**, specificare il nome di dominio completo per gli amministratori e quindi fare clic su **fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il nome deve essere risolvibile dai server DNS Internet e posizionare il puntatore sull'indirizzo IP pubblico del proxy inverso, che ascolta le richieste HTTP/HTTPS per l'URL e li delega alla directory virtuale dei servizi Web esterni in tale Director.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server. Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.

    
    </div>

8.  Pubblicare la topologia.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Per definire il Director (pool di più direttori)

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nella pagina di benvenuto fare clic su **Scarica topologia da distribuzione esistente**.

3.  Nella finestra di dialogo **Salva topologia come** Digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.

4.  Espandere il sito in cui si prevede di aggiungere il Director, fare clic con il pulsante destro del mouse su pool di **Director**e quindi scegliere **nuovo pool di Director**.

5.  Nella finestra di dialogo **Definisci il nome di dominio completo del pool di Director** eseguire le operazioni seguenti:
    
      - In **FQDN del pool**Digitare il nome di dominio completo per il pool di Director.
    
      - Fare clic su **pool di computer multipli**e quindi su **Avanti**.

6.  Nella finestra di dialogo **Definisci i computer in questo pool** eseguire le operazioni seguenti:
    
      - Specificare il nome di dominio completo del computer del primo membro del pool e quindi fare clic su **Aggiungi**.
    
      - Ripetere il passaggio precedente per ogni computer che si vuole aggiungere. Al termine, fare clic su **Avanti**.

7.  Nella finestra di dialogo **Definisci la condivisione file** eseguire una delle operazioni seguenti:
    
      - Per usare una condivisione file esistente, fare clic su **Usa una condivisione file definita in precedenza**, selezionare una condivisione file dall'elenco e quindi fare clic su **Avanti**.
    
      - Per creare una nuova condivisione di file, fare clic su **Definisci una nuova condivisione file**, digitare il nome di dominio completo relativo alla posizione della condivisione file nell' **FQDN del file server**, digitare la condivisione in **condivisione file**e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!IMPORTANT]  
    > La condivisione di file specificata o creata in questo passaggio deve esistere o crearsi prima di pubblicare la topologia.<BR>La condivisione file assegnata a un amministratore non viene effettivamente usata, quindi è possibile assegnare la condivisione file di qualsiasi pool nell'organizzazione.

    
    </div>

8.  Nella finestra di dialogo **specifica URL servizi Web** , in **URL di base esterno**, specificare il nome di dominio completo per gli amministratori e quindi fare clic su **fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il nome deve essere risolvibile dai server DNS Internet e posizionare il puntatore sull'indirizzo IP pubblico del proxy inverso, che attende le richieste HTTP/HTTPS inviate all'URL e le delega alla directory virtuale dei servizi Web esterni nel pool di Director.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server. Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.

    
    </div>

9.  Pubblicare la topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

