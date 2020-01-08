---
title: 'Lync Server 2013: Configurazione dei criteri di Qualità del servizio (QoS) per server per conferenze, server applicazioni e Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a79835fb19f5a30a11eac4859f133aeec5c8cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurazione dei criteri di Qualità del servizio (QoS) in Lync Server 2013 per server per conferenze, server applicazioni e Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-23_

La configurazione degli intervalli di porte facilita l'uso della qualità del servizio garantendo che tutto il traffico di un tipo specificato, ad esempio tutto il traffico audio, scorra nello stesso set di porte. In questo modo, il sistema può identificare e contrassegnare un pacchetto specifico: se la porta 49152 è riservata per il traffico audio, il pacchetto che viaggia attraverso la porta 49152 potrà essere contrassegnato con un codice DSCP che indica che si tratta di un pacchetto audio. A sua volta, questo consente ai router di identificare il pacchetto come pacchetto audio e di dargli una priorità maggiore rispetto ai pacchetti non contrassegnati, ad esempio i pacchetti usati per copiare un file da un server a un altro.

Tuttavia, limitando semplicemente un set di porte a un tipo specifico di traffico, i pacchetti che viaggiano attraverso tali porte vengono contrassegnati con il codice DSCP appropriato. Oltre a definire gli intervalli di porte, devi anche creare criteri di qualità dei servizi che specificano il codice DSCP da associare a ogni intervallo di porte. Per Microsoft Lync Server 2013 che in genere significa creare due criteri: uno per l'audio e uno per il video.

I criteri per la qualità dei servizi vengono creati e gestiti in modo più semplice e gestito tramite il criterio di gruppo. Questi stessi criteri possono essere creati anche usando criteri di sicurezza locali. Tuttavia, questo richiede di ripetere la stessa procedura in tutti i computer. Il set iniziale di criteri QoS (uno per l'audio e uno per il video) deve essere applicato solo ai computer Lync Server che eseguono i servizi di conferenza server, Application Server e/o Mediation Server. Se tutti questi computer si trovano nella stessa UO di Active Directory, è possibile assegnare semplicemente il nuovo oggetto Criteri di gruppo a tale OU. In alternativa, è possibile eseguire altre operazioni per assegnare il nuovo criterio ai computer specificati. ad esempio, è possibile inserire i computer appropriati in un gruppo di sicurezza, quindi usare i filtri di sicurezza per i criteri di gruppo per applicare l'oggetto GPO solo al gruppo di sicurezza.

Per creare criteri di qualità dei servizi per la gestione dell'audio, accedere a un computer in cui è stata installata la gestione dei criteri di gruppo. Aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione criteri di gruppo**) e quindi completare la procedura seguente:

1.  In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio. Ad esempio, se tutti i computer di Lync Server si trovano in un'unità organizzativa denominata Lync Server, il nuovo criterio deve essere creato nell'unità organizzativa di Lync Server.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.

3.  Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** , ad esempio **QoS Lync Server**, quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

5.  In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **criteri**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio (ad esempio, **Lync Server QoS**) nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.

7.  Nella pagina successiva verificare che sia selezionata l'opzione **tutte le applicazioni** e quindi fare clic su **Avanti**. Questo assicura semplicemente che tutte le applicazioni corrispondano ai pacchetti dall'intervallo di porte specificato con il codice DSCP specificato.

8.  Nella terza pagina verificare che sia selezionato l' **indirizzo IP di origine e qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà tali pacchetti.

9.  Nella pagina quattro selezionare **TCP e UDP** dal pulsante **Seleziona il protocollo questo criterio di QoS si applica all'elenco a** discesa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente da Lync Server e dalle sue applicazioni client.

10. Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se hai riservato le porte 49152 tramite le porte 57500 per il traffico audio, immetti l'intervallo di porte usando questo formato: **49152:57500**. Fare clic su **fine**.

<div>


> [!NOTE]  
> Il valore DSCP di 46 è alquanto arbitrario: anche se DSCP 46 viene spesso usato per contrassegnare i pacchetti audio, non è necessario usare DSCP 46 per le comunicazioni audio. Se è già stato implementato QoS e si usa un codice DSCP diverso per l'audio (ad esempio, DSCP 40), è necessario configurare i criteri di qualità del servizio per usare lo stesso codice (ad es., 40 per l'audio). Se si sta solo implementando la qualità del servizio, è consigliabile usare DSCP 46 per l'audio, semplicemente perché tale valore viene usato in genere per contrassegnare i pacchetti audio.



</div>

Dopo aver creato i criteri QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video (e, facoltativamente, un terzo criterio per la gestione del traffico di condivisione delle applicazioni). Per creare un criterio per il video, seguire la stessa procedura di base seguita durante la creazione dei criteri audio, eseguendo queste sostituzioni:

  - Usare un nome di criterio diverso (e univoco), ad esempio **Lync Server video**.

  - Impostare il valore DSCP su **34** anziché su 46. Si noti che non è necessario usare un valore DSCP di 34. L'unico requisito consiste nell'usare un valore DSCP diverso per il video rispetto a quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte su questo: **57501:65535**.

Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, è necessario creare un terzo criterio, eseguendo le sostituzioni seguenti:

  - Usare un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Lync Server**.

  - Impostare il valore DSCP su **24** anziché su 46. Di nuovo, non è necessario usare un valore DSCP pari a 24. L'unico requisito consiste nell'usare un valore DSCP diverso per la condivisione delle applicazioni rispetto a quello usato per l'audio o per il video.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se si hanno le porte riservate da 40803 a 49151 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **40803:49151**.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non saranno stati aggiornati nei computer di Lync Server. Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare i criteri di gruppo:

    Gpupdate.exe /force

Questo comando può essere eseguito dall'interno di Lync Server Management Shell o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore. Per eseguire una finestra di comando in credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

Per verificare che i nuovi criteri QoS siano stati applicati, eseguire le operazioni seguenti:

1.  In un computer Lync Server fare clic su **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  In Editor del registro di sistema espandere **computer**, espandere **HKEY\_\_local**computer, espandere **software**, espandere **criteri**, **Microsoft**, espandere **Windows**e quindi fare clic su **QoS**. In **QoS** dovresti vedere le chiavi del registro di sistema per ogni criterio QoS appena creato. Se ad esempio sono stati creati due nuovi criteri (uno denominato QoS audio di Lync Server e l'altro QoS di Lync Server video), è consigliabile eseguire le voci del registro di sistema per il QoS audio di Lync Server e il QoS video di Lync Server.

Per assicurarti che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, devi anche creare una nuova voce del registro di sistema in ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**. Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**. Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su non **usare NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del registro di sistema e riavviare il computer.

</div>

<span> </span>

</div>

</div>

</div>

