---
title: Configurazione di un criterio di qualità dei servizi per i server A/V Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Configurazione di un criterio di qualità dei servizi per i server A/V Edge in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Oltre a creare criteri QoS per le conferenze, le applicazioni e i server di mediazione, devi anche creare criteri audio e video per il lato interno dei server A/V Edge. I criteri usati nei server perimetrali, tuttavia, sono diversi rispetto ai criteri usati nei server di conferenza, applicazione e mediazione. Per i server di conferenza, applicazione e mediazione è stato specificato un intervallo di porte di origine; con Edge Server è necessario specificare un intervallo di porte di destinazione. Per questo motivo, non è possibile applicare semplicemente i criteri di QoS per i servizi di conferenza, applicazione e mediazione per i server perimetrali: questi criteri non funzionano semplicemente. È invece necessario creare nuovi criteri e applicare tali criteri solo ai server perimetrali.

La procedura seguente descrive il processo per la creazione di oggetti Criteri di gruppo di Active Directory che possono essere usati per gestire la qualità del servizio in Edge Server. Naturalmente, è possibile che gli Edge Server siano server autonomi che non dispongono di account di Active Directory. In questo caso, è possibile usare criteri di gruppo locali invece di criteri di gruppo di Active Directory: l'unica differenza è che è necessario creare questi criteri locali usando l'Editor criteri di gruppo locali e creare individualmente lo stesso set di criteri in ogni server perimetrale. Per avviare l'Editor criteri di gruppo locali in un server perimetrale, eseguire le operazioni seguenti:

1.  Fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **gpedit. msc** e quindi premere INVIO.

Se si creano criteri basati su Active Directory, è necessario accedere a un computer in cui è stata installata la gestione dei criteri di gruppo. In questo caso, aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi **Gestione criteri di gruppo**) e quindi completare la procedura seguente:

1.  In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio. Ad esempio, se tutti i computer di Lync Server si trovano in un'unità organizzativa denominata Lync Server, il nuovo criterio deve essere creato nell'unità organizzativa di Lync Server.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.

3.  Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** , ad esempio **audio Lync Server**, quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

Da qui il processo è identico, indipendentemente dal fatto che si crei un criterio Active Directory o un criterio locale:

1.  Nell'Editor gestione criteri di gruppo o nell'Editor criteri di gruppo locali espandere **Configurazione computer**, espandere **criteri**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basato su criteri**e quindi scegliere **Crea nuovo criterio**.

2.  Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio, ad esempio **Lync Server audio**, nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.

3.  Nella pagina successiva verificare che sia selezionata l'opzione **tutte le applicazioni** e quindi fare clic su **Avanti**. Questa impostazione indica alla rete di cercare tutti i pacchetti con un contrassegno DSCP di 46, non solo i pacchetti creati da un'applicazione specifica.

4.  Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà tali pacchetti.

5.  Nella pagina quattro selezionare **TCP e UDP** dal pulsante **Seleziona il protocollo questo criterio di QoS si applica all'elenco a** discesa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente da Lync Server e dalle sue applicazioni client.

6.  Sotto il titolo **specificare il numero di porta di destinazione**selezionare **dalla porta di destinazione o dall'intervallo**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se hai riservato le porte 49152 tramite le porte 57500 per il traffico audio, immetti l'intervallo di porte usando questo formato: **49152:57500**. Fare clic su **fine**.

Dopo aver creato i criteri QoS per il traffico audio, è consigliabile creare un secondo criterio per il traffico video. Per creare un criterio per il video, seguire la stessa procedura di base seguita durante la creazione dei criteri audio, eseguendo queste sostituzioni:

  - Usare un nome di criterio diverso (e univoco), ad esempio **Lync Server video**.

  - Impostare il valore DSCP su **34** anziché su 46. Si noti che non è necessario usare un valore DSCP di 34. L'unico requisito consiste nell'usare un valore DSCP diverso per il video rispetto a quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte su questo: **57501:65535**. Anche in questo caso, questa operazione deve essere configurata come intervallo di porte di destinazione.

Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, è necessario creare un terzo criterio, eseguendo le sostituzioni seguenti:

  - Usare un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Lync Server**.

  - Impostare il valore DSCP su **24** anziché su 46. Di nuovo, non è necessario usare un valore DSCP pari a 24. L'unico requisito consiste nell'usare un valore DSCP diverso per la condivisione delle applicazioni rispetto a quello usato per l'audio o per il video.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se si hanno le porte riservate da 40803 a 49151 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **40803:49151**.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non saranno stati aggiornati in un server perimetrale. Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare i criteri di gruppo:

    Gpudate.exe /force

Questo comando può essere eseguito dall'interno del server Lync o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore. Per eseguire una finestra di comando in credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**. Tieni presente che potresti dover riavviare l'Edge Server anche dopo aver eseguito GPUdate. exe.

Per assicurarti che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, devi anche creare una nuova voce del registro di sistema in ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**. Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**. Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **non usare NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del registro di sistema e riavviare il computer.

</div>

<span> </span>

</div>

</div>

</div>

