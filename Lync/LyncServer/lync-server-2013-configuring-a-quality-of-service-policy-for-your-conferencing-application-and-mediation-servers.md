---
title: "Lync Server 2013: configurazione dei criteri di qualità del servizio per le conferenze, l'applicazione e i Mediation Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37462eb9f15553138dc6bb7285a5d0786dbc4b57
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurazione dei criteri di qualità del servizio in Lync Server 2013 per i servizi di conferenza, applicazione e Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-23_

La configurazione degli intervalli di porte agevola l'uso di QoS (Quality of Service) assicurando che tutto il traffico di un tipo specificato (ad esempio, tutto il traffico audio) passi attraverso lo stesso set di porte. Ciò semplifica l'identificazione e il contrassegno di un determinato pacchetto da parte del sistema: se la porta 49152 è riservata per il traffico audio, qualsiasi attraversamento di pacchetto tramite la porta 49152 può essere contrassegnato con un codice DSCP indicante che si tratta di pacchetti audio. A sua volta, ciò consente ai router di identificare il pacchetto come pacchetto audio e assegnargli una priorità più elevata rispetto ai pacchetti non contrassegnati (ad esempio i pacchetti usati per copiare un file da un server all'altro).

Tuttavia, limitando semplicemente un set di porte a un tipo di traffico specifico non si determina necessariamente l'assegnazione del codice DSCP appropriato ai pacchetti che le attraversano. Oltre a definire gli intervalli di porte è anche necessario creare criteri QoS (Quality of Service) che specificano il codice DSCP da associare a ogni intervallo di porte. Per Microsoft Lync Server 2013 che in genere significa creare due criteri: uno per l'audio e uno per il video.

I criteri di qualità dei servizi vengono creati e gestiti in modo più semplice tramite criteri di gruppo. Gli stessi criteri possono essere creati anche utilizzando criteri di protezione locali. Tuttavia, è necessario ripetere la stessa procedura in tutti i computer. Il set iniziale di criteri QoS (uno per l'audio e uno per il video) deve essere applicato solo ai computer Lync Server che eseguono i servizi di conferenza server, server applicazioni e/o Mediation Server. Se tutti questi computer si trovano nella stessa unità organizzativa di Active Directory, è sufficiente assegnare il nuovo oggetto Criteri di gruppo a quell'unità organizzativa. In alternativa, è possibile eseguire altri passaggi per assegnare il nuovo criterio ai computer specificati. ad esempio, è possibile inserire i computer idonei in un gruppo di sicurezza, quindi utilizzare il filtro di sicurezza di criteri di gruppo per applicare l'oggetto Criteri di sistema solo a quel gruppo di sicurezza.

Per creare un criterio QoS (Quality of Service) per la gestione dell'audio, accedere a un computer in cui è installato Gestione Criteri di gruppo. Aprire Gestione Criteri di gruppo (fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Gestione Criteri di gruppo**) e quindi eseguire la procedura seguente:

1.  In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer Lync Server si trovano in un'unità organizzativa denominata Lync Server, il nuovo criterio deve essere creato nell'unità organizzativa Lync Server.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e scegliere **Crea un oggetto Criteri di gruppo in questo dominio e crea qui un collegamento**.

3.  Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** (ad esempio, **Lync Server QoS**) e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica**.

5.  Nell'Editor Gestione Criteri di gruppo espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina apertura della finestra di dialogo **QoS basata su criteri** Digitare un nome per il nuovo criterio (ad esempio, **Lync Server QoS**) nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.

7.  Nella pagina successiva, accertarsi che l'opzione **Tutte le applicazioni** sia selezionata e quindi fare clic su **Avanti**. In questo modo ci si assicura che tutte le applicazioni abbineranno i pacchetti dell'intervallo di porte specificato al codice DSCP specificato.

8.  Nella terza pagina accertarsi che entrambe le opzioni **Qualsiasi indirizzo IP di origine e Qualsiasi indirizzo IP di destinazione** siano selezionate e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.

9.  Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Lync Server e dalle sue applicazioni client.

10. Nel gruppo **Specifica il numero della porta di origine** selezionare **Da questa porta o intervallo di origine**. Nella casella di testo associata, digitare l'intervallo di porte riservato per le trasmissioni audio. Se ad esempio sono state riservate le porte da 49152 a 57500 per il traffico audio, immettere l'intervallo in questo formato **49152:57500**. Fare clic su **Fine**.

<div>


> [!NOTE]  
> Il valore DSCP di 46 è in qualche modo arbitrario: sebbene il valore DSCP 46 sia spesso usato per contrassegnare i pacchetti audio, non è obbligatorio usarlo per le comunicazioni audio. Se si è già implementata la QoS e si usa un codice DSCP diverso per l'audio (ad esempio, DSCP 40) è necessario configurare il criterio Quality of Service per l'uso dello stesso codice (ovvero 40 per l'audio). Se si sta eseguendo una nuova implementazione della Quality of Service, è consigliabile usare il codice DSCP 46 per l'audio in quando si tratta del valore comunemente usato per contrassegnare i pacchetti audio.



</div>

Dopo aver creato il criterio QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video (ed eventualmente un terzo criterio per la gestione del traffico di condivisione delle applicazioni). Per creare un criterio per il traffico video, seguire la stessa procedura di base usata per la creazione del criterio audio, con le distinzioni seguenti:

  - Usare un nome diverso (e univoco) per il criterio (ad esempio, **Lync Server Video**).

  - Impostare il valore DSCP su **34** invece di 46. Si noti che non è obbligatorio usare il valore DSCP 34. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Usare l'intervallo di porte configurato in precedenza per il traffico video. Se ad esempio, sono state riservate le porte da 57501 a 65535 per i contenuti video, impostare l'intervallo di porte su: **57501:65535**.

Se si decide di creare un criterio per gestire il traffico di condivisione delle applicazioni, è necessario creare un terzo criterio con le distinzioni seguenti:

  - Usare un nome diverso (e univoco) per il criterio (ad esempio, **Lync Server Application Sharing**).

  - Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Usare l'intervallo di porte configurato in precedenza per il traffico video. Se ad esempio sono state riservate le porte da 40803 a 49151 per il video, impostare l'intervallo di porte su: **40803:49151**.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non sono stati aggiornati nei computer di Lync Server. Sebbene l'aggiornamento di Criteri di gruppo venga eseguito automaticamente periodicamente, è possibile imporre l'aggiornamento immediato eseguendo il comando seguente su ogni computer in cui è necessario:

    Gpupdate.exe /force

Questo comando può essere eseguito dall'interno di Lync Server Management Shell o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore. Per eseguire una finestra di comando con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

Per verificare che i criteri QoS siano stati applicati, effettuare le operazioni seguenti:

1.  In un computer Lync Server fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.

3.  In Editor del registro di sistema espandere **computer**, espandere **HKEY\_\_**, espandere **software**, espandere **criteri**, espandere **Microsoft**, espandere **Windows**e quindi fare clic su **QoS**. In **QoS** dovrebbero essere presenti le chiavi del Registro di sistema per ognuno dei Criteri QoS creati. Ad esempio, se sono stati creati due nuovi criteri (uno denominato Lync Server audio QoS e un altro QoS denominato Lync Server video), è consigliabile utilizzare le voci del registro di sistema per Lync Server audio QoS e Lync Server video QoS.

Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare **regedit**, quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do not use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del Registro di sistema e riavviare il computer.

</div>

<span> </span>

</div>

</div>

</div>

