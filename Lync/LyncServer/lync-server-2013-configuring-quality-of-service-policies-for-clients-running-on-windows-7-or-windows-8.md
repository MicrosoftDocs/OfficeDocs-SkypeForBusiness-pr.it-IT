---
title: 'Lync Server 2013: configurare i criteri di qualità dei servizi per i client in uso in Windows 7 o Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365ce7a48a3c30a9e810d44edc1b7130ceb2643b
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "40982249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configurazione di criteri di qualità dei servizi in Lync Server 2013 per i client in uso in Windows 7 o Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-03-29_

Oltre a specificare gli intervalli di porte per l'uso da parte dei client Lync, devi anche creare criteri di qualità distinti per i servizi che verranno applicati ai computer client. I criteri di qualità dei servizi creati per le conferenze, le applicazioni e i server di mediazione non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono il client Lync 2013 e Windows 7 o Windows 8.

Nell'esempio seguente viene usato questo set di intervalli di porte per creare un criterio audio e un criterio video:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di traffico client</th>
<th>Inizio porta</th>
<th>Intervallo di porte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Video</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Condivisione applicazioni</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Trasferimento di file</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


Per creare un criterio di qualità dei servizi audio per i computer Windows 7 o Windows 8, prima di tutto accedere a un computer in cui è stata installata la gestione di criteri di gruppo. Aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione criteri di gruppo**) e quindi completare la procedura seguente:

1.  In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio. Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata clients, il nuovo criterio deve essere creato nell'unità organizzativa client.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.

3.  Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** , ad esempio **audio Lync**, e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

5.  In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **criteri**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio, ad esempio **audio Lync**, nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.

7. Nella pagina successiva selezionare **solo le applicazioni con il nome eseguibile** e immettere il nome **Lync. exe**e quindi fare clic su **Avanti**. Questa impostazione indica al criterio di assegnare la priorità solo al traffico corrispondente dal client Lync.

8.  Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà tali pacchetti.

9.  Nella pagina quattro selezionare **TCP e UDP** dal pulsante **Seleziona il protocollo questo criterio di QoS si applica all'elenco a** discesa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente da Lync Server e dalle sue applicazioni client.

10. Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se hai riservato le porte 50020 tramite le porte 50039 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50020:50039**. Fare clic su **fine**.

Dopo aver creato i criteri QoS per l'audio, è necessario creare un secondo criterio per il video. Per creare un criterio per il video, seguire la stessa procedura di base seguita durante la creazione dei criteri audio, eseguendo queste sostituzioni:

  - Usare un nome di criterio diverso (e univoco), ad esempio **Lync video**.

  - Impostare il valore DSCP su **34** anziché su 46. Come indicato in precedenza, non è necessario usare il valore DSCP 34; devi semplicemente assegnare un valore DSCP diverso rispetto a quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 58000 a 58019 per il video, impostare l'intervallo di porte su questo: **58000:58019**.

Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, eseguire queste sostituzioni:

  - Usare un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Lync Server**.

  - Impostare il valore DSCP su **24** anziché su 46. (Anche in questo caso, il valore non deve essere 24; è semplicemente diverso dai valori DSCP usati per l'audio e per il video.)

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se si hanno le porte riservate da 42000 a 42019 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42000:42019**.

Per un criterio di trasferimento file:

  - Usare un nome di criterio diverso (e univoco), ad esempio i **trasferimenti di file di Lync Server**.

  - Imposta il valore DSCP su **14**. (Anche in questo caso, il valore non deve essere 14, ma è semplicemente un codice DSCP univoco).

  - Usa l'intervallo di porte configurato in precedenza per l'applicazione. Ad esempio, se si hanno le porte riservate da 42020 a 42039 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42020:42039**.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non saranno stati aggiornati nei computer client. Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare i criteri di gruppo:

    Gpudate.exe /force

Questo comando può essere eseguito da qualsiasi finestra di comando in esecuzione in credenziali di amministratore. Per eseguire una finestra di comando in credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

Tieni presente che questi criteri devono essere mirati verso i computer client. Non devono essere applicati ai server che eseguono Lync Server.

Per assicurarti che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, devi anche creare una nuova voce del registro di sistema in ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**. Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**. Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su non **usare NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del registro di sistema e riavviare il computer.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurazione della qualità del servizio nei computer con più schede di rete

Se si dispone di un computer in cui sono presenti più schede di rete, è possibile che si verifichino occasionalmente problemi in cui i valori DSCP sono visualizzati come 0x00 invece del valore configurato. Ciò si verifica in genere nei computer in cui una o più schede di rete non sono in grado di accedere al dominio Active Directory, ad esempio se questi adapter vengono usati per una rete privata. In casi come questo, i valori DSCP verranno contrassegnati per gli adapter che possono accedere al dominio, ma non verranno contrassegnati per gli adapter che non possono accedere al dominio.

Se si vuole contrassegnare i valori DSCP per tutte le schede di rete in un computer, inclusi gli adapter che non hanno accesso al dominio, è necessario aggiungere e configurare un valore per il registro di sistema. Questa operazione può essere eseguita completando la procedura seguente:

1.  Fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Se non viene visualizzata una chiave del registro di sistema con l'etichetta **QoS** , fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**. Dopo aver creato la nuova chiave, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**. Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su non **usare NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

Dopo aver creato e configurato il nuovo valore del registro di sistema, sarà necessario riavviare il computer in modo che le modifiche abbiano effetto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

