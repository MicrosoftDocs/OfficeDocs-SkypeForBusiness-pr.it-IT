---
title: Configurazione dei criteri di qualità del servizio per i server A/V Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69b9beb119ebd7189c31f9e239ac45409758ba00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515693"
---
# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Configurazione dei criteri di qualità del servizio per i server A/V Edge in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Oltre alla creazione di criteri QoS per i Conferencing Server, server applicazioni e Mediation Server, è necessario anche creare criteri audio e video per il sito interno degli A/V Edge Server. I criteri utilizzati nei server perimetrali, tuttavia, sono diversi da quelli utilizzati nei Conferencing Server, server applicazioni e Mediation Server. Per i Conferencing Server, server applicazioni e Mediation Server è stato specificato un intervallo di porte di origine, mentre con i server perimetrali è necessario specificare un intervallo di porte di destinazione. Di conseguenza, non è possibile applicare semplicemente criteri QoS dei Conferencing Server, server applicazioni e Mediation Server ai server perimetrali poiché non funzionerebbero. È necessario invece creare nuovi criteri e applicarli solo ai server perimetrali.

Nella procedura seguente viene descritto il processo per creare oggetti Criteri di gruppo di Active Directory da utilizzare per gestire la Qualità del Servizio (QoS) sui server perimetrali. È naturalmente possibile che i server perimetrali siano server indipendenti che non dispongono di account di Active Directory. In questo caso, è possibile utilizzare Criteri di gruppo locali invece di Criteri di gruppo di Active Directory. L'unica differenza è che questi criteri locali devono essere creati mediante l'Editor Criteri di gruppo locali ed è necessario creare singolarmente lo stesso set di criteri su ogni server perimetrale. Per avviare l'Editor Criteri di gruppo locali su un server perimetrale, eseguire le operazioni seguenti:

1.  Fare clic su **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare **gpedit.msc**, quindi premere INVIO.

Se si creano criteri basati su Active Directory, è necessario accedere a un computer in cui sia installato Gestione Criteri di gruppo. In questo caso, aprire Gestione Criteri di gruppo facendo su **Start**, scegliendo **Strumenti di amministrazione** e **Gestione Criteri di gruppo**, quindi eseguire la procedura seguente:

1.  In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer Lync Server si trovano in un'unità organizzativa denominata Lync Server, il nuovo criterio deve essere creato nell'unità organizzativa Lync Server.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e scegliere **Crea un oggetto Criteri di gruppo in questo dominio e crea qui un collegamento**.

3.  Nella nuova finestra di dialogo **Nuovo oggetto Criteri di gruppo** digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **Nome** (ad esempio, **Lync Server Audio**) e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e scegliere **Modifica**.

Da questo punto in avanti il processo è identico sia per la creazione di un criterio di Active Directory che per la creazione di un criterio locale:

1.  In Editor Gestione Criteri di gruppo o Editor Criteri di gruppo locali espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e scegliere **Crea nuovo criterio**.

2.  Nella pagina iniziale della finestra di dialogo **QoS basata su criteri** digitare un nome per il nuovo criterio, ad esempio **Lync Server Audio**, nella casella **Nome**. Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare deselezionata l'opzione **Specifica velocità in uscita** e fare clic su **Avanti**.

3.  Nella pagina successiva verificare che l'opzione **Tutte le applicazioni** sia selezionata, quindi fare clic su **Avanti**. Questa impostazione indica alla rete di cercare tutti i pacchetti contrassegnati con il valore DSCP 46, non solo i pacchetti creati da un'applicazione specifica.

4.  Nella terza pagina verificare che **Qualsiasi indirizzo IP di origine** e **Qualsiasi indirizzo IP di destinazione** siano entrambi selezionati e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) che li invia e dal computer (indirizzo IP) che li riceve.

5.  Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Lync Server e dalle sue applicazioni client.

6.  In **Specifica il numero della porta di destinazione** selezionare **Verso questo numero di porta o intervallo di porte di destinazione**. Nella casella di testo associata, immettere l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se sono state riservate le porte da 49152 a 57500 per il traffico audio, immettere l'intervallo di porte nel formato: **49152:57500**. Fare clic su **Fine**.

Dopo avere creato il criterio QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video. Per creare un criterio per il video, seguire la stessa procedura utilizzata per la creazione del criterio audio, con le seguenti sostituzioni:

  - Utilizzare un nome di criterio diverso e univoco, ad esempio **Lync Server Video**.

  - Impostare il valore DSCP su **34** anziché su 46. Tenere presente che non è essenziale utilizzare il valore DSCP 34. L'unico requisito è che si utilizzi un valore DSCP diverso per il video e per l'audio.

  - Utilizzare l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte su **57501:65535**. Anche in questo caso è necessario configurarlo come intervallo di porte di destinazione.

Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, è necessario creare un terzo criterio, con le seguenti sostituzioni:

  - Usare un nome diverso (e univoco) per il criterio (ad esempio, **Lync Server Application Sharing**).

  - Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Utilizzare l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 40803 a 49151 per la condivisione di applicazioni, impostare questo intervallo di porte su **40803:49151**.

I nuovi criteri creati verranno applicati solo dopo l'aggiornamento di Criteri di gruppo sui server perimetrali. L'aggiornamento di Criteri di gruppo viene eseguito periodicamente in modo automatico, ma è possibile forzarne l'esecuzione immediata utilizzando il comando seguente su ogni computer in cui questa operazione è necessaria:

    Gpudate.exe /force

Questo comando può essere eseguito dall'interno del Lync Server o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore. Per eseguire una finestra di comando con credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**. Può essere necessario riavviare il server perimetrale anche dopo avere eseguito Gpudate.exe.

Per assicurarsi che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, creare anche una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do no use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del Registro di sistema e riavviare il computer.

</div>

<span> </span>

</div>

</div>

</div>

