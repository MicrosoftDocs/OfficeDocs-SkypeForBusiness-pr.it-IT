---
title: 'Lync Server 2013: configurazione dei criteri di qualità del servizio per i client in esecuzione in Windows 7 o Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd058e2903160f1c9f4ea06e30959b63953ab01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534973"
---
# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configurazione dei criteri di qualità del servizio in Lync Server 2013 per i client in esecuzione in Windows 7 o Windows 8

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-03-29_

Oltre a specificare gli intervalli di porte per l'utilizzo da parte dei client di Lync, è inoltre necessario creare criteri di qualità del servizio distinti che verranno applicati ai computer client. I criteri di qualità dei servizi creati per le conferenze, l'applicazione e i Mediation Server non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono il client Lync 2013 e Windows 7 o Windows 8.

Nell'esempio seguente viene utilizzato questo set di intervalli di porte per creare un criterio audio e un criterio video:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di traffico client</th>
<th>Inizio intervallo porte</th>
<th>Intervallo porte</th>
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


Per creare un criterio audio di qualità del servizio per i computer Windows 7 o Windows 8, accedere innanzitutto a un computer in cui è stata installata la gestione criteri di gruppo. Aprire Gestione Criteri di gruppo (fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Gestione Criteri di gruppo**) e quindi eseguire la procedura seguente:

1.  In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Se ad esempio tutti i computer client appartengono a un'unità organizzativa denominata Client, il nuovo criterio dovrà essere creato in tale unità organizzativa Client.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e scegliere **Crea un oggetto Criteri di gruppo in questo dominio e crea qui un collegamento**.

3.  Nella finestra di dialogo **Nuovo oggetto Criteri di gruppo** digitare il nome da assegnare al nuovo oggetto Criteri di gruppo nella casella **Nome** (ad esempio, **Lync Audio**) e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul nuovo criterio e quindi su **Modifica**.

5.  In Editor Gestione Criteri di gruppo espandere **Configurazione computer**, **Criteri** e **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e quindi scegliere **Crea nuovo criterio**.

6.  Nella finestra di dialogo **QoS basata su criteri** della pagina di apertura digitare un nome per il nuovo criterio (ad esempio, **Lync Audio**) nella casella **Nome**. Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare **Specifica velocità in uscita** non selezionato e quindi fare clic su **Avanti**.

7. Nella pagina successiva selezionare solo le **applicazioni con il nome del file eseguibile** e immettere il nome **Lync.exe**, quindi fare clic su **Avanti**. Questa impostazione indica al criterio di assegnare una priorità solo al traffico corrispondente proveniente dal client Lync.

8.  Nella terza pagina verificare che **Qualsiasi indirizzo IP di origine** e **Qualsiasi indirizzo IP di destinazione** siano entrambi selezionati e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) che li invia e dal computer (indirizzo IP) che li riceve.

9.  Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Lync Server e dalle sue applicazioni client.

10. Sotto l'intestazione **Specifica il numero della porta di origine** selezionare **Da questo numero di porta o intervallo di porte di origine**. Nella casella di testo abbinata digitare l'intervallo di porte riservato alle trasmissioni audio. Se ad esempio è stato riservato al traffico audio l'intervallo di porte compreso tra la 50020 e la 50039, immettere l'intervallo di porte utilizzando questo formato: **50020:50039**. Fare clic su **Fine**.

Dopo aver creato il criterio QoS per l'audio, è necessario creare un secondo criterio per il video. Per creare un criterio per il video, seguire la stessa procedura base osservata per creare il criterio audio, apportandovi le modifiche seguenti:

  - Utilizzare un nome criterio diverso e univoco (ad esempio, **Lync Video**).

  - Impostare il valore DSCP su **34** anziché su 46. Come accennato, non è necessario utilizzare il valore DSCP 34, bensì è sufficiente utilizzare un valore diverso da quello specificato per l'audio.

  - Utilizzare l'intervallo di porte precedentemente configurato per il traffico video. Se ad esempio al video sono state riservate le porte da 58000 a 58019, impostare l'intervallo di porte in questo modo: **58000:58019**.

Se si decide di creare un criterio per la gestione del traffico della condivisione applicazioni, effettuare queste sostituzioni:

  - Utilizzare un nome criterio diverso e univoco (ad esempio, **Condivisione applicazioni Lync Server**).

  - Impostare il valore DSCP su **24** anziché su 46. Di nuovo, non è rilevante che questo valore sia 24, bensì è sufficiente che sia diverso dai valori utilizzati per l'audio e per il video.

  - Utilizzare l'intervallo di porte precedentemente configurato per il traffico video. Se ad esempio alla condivisione delle applicazioni sono state riservate le porte da 42000 a 42019, impostare l'intervallo di porte in questo modo: **42000:42019**.

Per un criterio di trasferimento file:

  - Utilizzare un nome criterio diverso e univoco (ad esempio, **Trasferimenti file di Lync Server**).

  - Impostare il valore DSCP su **14**. Di nuovo, non è rilevante che questo valore sia 14, bensì è sufficiente che sia un codice DSCP univoco.

  - Utilizzare l'intervallo di porte configurata in precedenza per l'applicazione. Se ad esempio alla condivisione delle applicazioni sono state riservate le porte da 42020 a 42039, impostare l'intervallo di porte in questo modo: **42020:42039**.

I nuovi criteri creati non saranno effettivi finché Criteri di gruppo non verrà aggiornato nei computer client. Benché Criteri di gruppo venga aggiornato automaticamente a intervalli regolari, è possibile effettuare un aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare Criteri di gruppo:

    Gpudate.exe /force

Questo comando può essere eseguito da qualsiasi finestra dei comandi eseguita con credenziali di amministratore. Per eseguire una finestra dei comandi con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

Tenere presente che questi criteri devono essere indirizzati verso i computer client. Non devono essere applicati ai server che eseguono Lync Server.

Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do not use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del Registro di sistema e quindi riavviare il computer.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurazione della qualità del servizio in computer con più schede di rete

Se si dispone di un computer dotato di più schede di rete può verificarsi talvolta un problema per il quale i DSCP risultano avere valore 0x00 anziché il valore configurato. Questo solitamente si verifica nei computer in cui una o più schede di rete non sono in grado di accedere al dominio di Active Directory, come avviene ad esempio nel caso delle schede utilizzate per una rete privata. In questi casi i valori DSCP verranno assegnati alle schede che possono accedere al dominio, ma non alle altre.

Se si desidera che i valori DSCP vengano assegnati a tutte le schede di rete di un computer, comprese quelle che non hanno accesso al dominio, sarà necessario aggiungere un valore al Registro di sistema e configurarlo. A tale scopo, è possibile eseguire la procedura seguente.

1.  Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Se non è presente una chiave del Registro di sistema denominata **QoS**, fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do not use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.

Dopo aver creato e configurato il nuovo valore del Registro di sistema, sarà necessario riavviare il computer per rendere effettive le modifiche.

</div>

</div>

<span> </span>

</div>

</div>

</div>

