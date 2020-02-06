---
title: Configurazione di intervalli di porte e di criteri di qualità dei servizi per le conferenze, le applicazioni e i Mediation Server
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Questo articolo descrive come configurare gli intervalli di porte e i criteri di qualità dei servizi per le conferenze, le applicazioni e i server di mediazione.
ms.openlocfilehash: 76373407a8087e3646668d7ce9952c83c500af97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817445"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configurazione di intervalli di porte e di criteri di qualità dei servizi per le conferenze, le applicazioni e i Mediation Server

Questo articolo descrive come configurare gli intervalli di porte e i criteri di qualità dei servizi per le conferenze, le applicazioni e i server di mediazione.

## <a name="configure-port-ranges"></a>Configurare gli intervalli di porte

Per implementare la qualità del servizio, è consigliabile configurare intervalli di porte identici per la condivisione di audio, video e applicazioni in servizi di conferenza, applicazioni e mediazione; Inoltre, questi intervalli di porte non devono sovrapporsi in alcun modo. Per usare un semplice esempio, supponiamo di usare le porte da 10000 a 10999 per il video nei server di conferenza. Ciò significa che devi anche prenotare le porte da 10000 a 10999 per il video nell'applicazione e nei server di mediazione. In caso contrario, QoS non funzionerà come previsto.

Allo stesso modo, supponiamo di prenotare le porte da 10000 a 10999 per il video, ma di prenotare le porte da 10500 a 11999 per l'audio. Ciò può creare problemi per la qualità del servizio, perché gli intervalli di porte si sovrappongono. Con QoS ogni modalità deve avere un set di porte univoco: se si usano le porte da 10000 a 10999 per il video, è necessario usare un intervallo diverso, ad esempio da 11000 a 11999, per l'audio.

Per impostazione predefinita, gli intervalli di porte audio e video non si sovrappongono in Skype for Business Server; Tuttavia, gli intervalli di porte assegnati alla sovrapposizione di condivisione delle applicazioni con gli intervalli di porte audio e video. Il che, a sua volta, indica che nessuno di questi intervalli è univoco. Puoi verificare gli intervalli di porte esistenti per i servizi di conferenza, applicazione e mediazione eseguendo i tre comandi seguenti in Skype for Business Server Management Shell:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Come si può vedere nei comandi precedenti, ogni tipo di porta-audio, video e condivisione applicazioni-viene assegnato due valori di proprietà distinti: l'inizio della porta e il numero di porta. L'inizio della porta indica la prima porta usata per tale modalità; ad esempio, se la porta audio Start è uguale a 50000, significa che la prima porta usata per il traffico audio è la porta 50000. Se il numero di porta audio è 2 (che non è un valore valido, ma viene usato qui per scopi di illustrazione), significa che solo due porte vengono allocate per l'audio. Se la prima porta è la porta 50000 e sono presenti un totale di due porte, significa che la seconda porta deve essere la porta 50001 (gli intervalli di porta devono essere contigui). Di conseguenza, l'intervallo di porte per l'audio sarebbe porte da 50000 a 50001, inclusi.<BR><br>Nota anche che Application Server e Mediation Server supportano solo QoS per l'audio; non è necessario modificare le porte di condivisione di video o applicazioni nei server delle applicazioni o nei server di mediazione.

Se esegui i tre comandi precedenti, vedrai che i valori di porta predefiniti per Skype for Business Server sono configurati in questo modo:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Proprietà</th>
<th>Server delle conferenze</th>
<th>Server applicazioni</th>
<th>Mediation Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

Come indicato in precedenza, quando si configurano le porte di Skype for Business Server per QoS, è necessario assicurarsi che: 1) le impostazioni della porta audio siano identiche tra i servizi di conferenza, applicazione e Mediation Server; e 2) gli intervalli di porte non si sovrappongono. Se si guarda attentamente la tabella precedente, si vedrà che gli intervalli di porta sono identici tra i tre tipi di server. Ad esempio, la porta audio iniziale è impostata su porta 49152 su ogni tipo di server e il numero totale di porte riservate per l'audio in ogni server è identico: 8348. Tuttavia, gli intervalli di porte si sovrappongono: le porte audio iniziano dalla porta 49152, ma anche le porte sono riservate per la condivisione delle applicazioni. Per usare in modo ottimale la qualità del servizio, la condivisione delle applicazioni deve essere riconfigurata in modo da usare un intervallo di porte univoco. Ad esempio, puoi configurare la condivisione delle applicazioni per iniziare dalla porta 40803 e usare le porte di 8348. (Perché le porte di 8348? Se Aggiungi questi valori insieme, 40803 + 8348, significa che la condivisione delle applicazioni userà le porte 40803 tramite la porta 49150. Poiché le porte audio non iniziano fino alla porta 49152, non si avranno più intervalli di porte sovrapposti.

Dopo aver selezionato il nuovo intervallo di porte per la condivisione delle applicazioni, è possibile apportare le modifiche usando il cmdlet Set-CsConferencingServer. Questa modifica non deve essere eseguita nei server delle applicazioni o nei server di mediazione, perché questi server non gestiscono il traffico di condivisione delle applicazioni. È necessario modificare i valori di porta solo in questi server se si decide di riassegnare le porte usate per il traffico audio.

Per modificare i valori di porta per la condivisione delle applicazioni in un unico server di conferenza, eseguire un comando simile a questo da Skype for Business Server Management Shell:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se si vogliono apportare queste modifiche in tutti i server dei servizi di conferenza, è possibile eseguire questo comando:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Dopo aver modificato le impostazioni della porta, è necessario interrompere e quindi riavviare ogni servizio interessato dalle modifiche.

Non è obbligatorio che i server di conferenza, i server delle applicazioni e i Mediation Server condividano esattamente lo stesso intervallo di porte; l'unico requisito vero è l'impostazione degli intervalli di porte univoci in tutti i server. Tuttavia, l'amministrazione sarà in genere più semplice se usi lo stesso set di porte in tutti i server.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurare un criterio di qualità dei servizi in Skype for Business Server per le conferenze, le applicazioni e i Mediation Server

La configurazione degli intervalli di porte facilita l'uso della qualità del servizio garantendo che tutto il traffico di un tipo specificato, ad esempio tutto il traffico audio, scorra nello stesso set di porte. In questo modo, il sistema può identificare e contrassegnare un pacchetto specifico: se la porta 49152 è riservata per il traffico audio, il pacchetto che viaggia attraverso la porta 49152 potrà essere contrassegnato con un codice DSCP che indica che si tratta di un pacchetto audio. A sua volta, questo consente ai router di identificare il pacchetto come pacchetto audio e di dargli una priorità maggiore rispetto ai pacchetti non contrassegnati, ad esempio i pacchetti usati per copiare un file da un server a un altro.

Tuttavia, limitando semplicemente un set di porte a un tipo specifico di traffico, i pacchetti che viaggiano attraverso tali porte vengono contrassegnati con il codice DSCP appropriato. Oltre a definire gli intervalli di porte, devi anche creare criteri di qualità dei servizi che specificano il codice DSCP da associare a ogni intervallo di porte. Per Skype for Business Server, in genere significa creare due criteri: uno per l'audio e uno per il video.

I criteri per la qualità dei servizi vengono creati e gestiti in modo più semplice, usando il criterio di gruppo. Questi stessi criteri possono essere creati anche usando criteri di sicurezza locali. Tuttavia, questo richiede di ripetere la stessa procedura in tutti i computer. Il set iniziale di criteri QoS (uno per l'audio e uno per il video) deve essere applicato solo ai computer di Skype for Business Server che eseguono i servizi di conferenza server, Application Server e/o Mediation Server. Se tutti questi computer si trovano nella stessa UO di Active Directory, è possibile assegnare semplicemente il nuovo oggetto Criteri di gruppo a tale OU. In alternativa, è possibile eseguire altre operazioni per assegnare il nuovo criterio ai computer specificati. ad esempio, è possibile inserire i computer appropriati in un gruppo di sicurezza, quindi usare i filtri di sicurezza per i criteri di gruppo per applicare l'oggetto GPO solo al gruppo di sicurezza.

Per creare criteri di qualità dei servizi per la gestione dell'audio, accedere a un computer in cui è stata installata la gestione dei criteri di gruppo. Aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione criteri di gruppo**) e quindi completare la procedura seguente:

1.  In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio. Ad esempio, se tutti i computer di Skype for Business Server si trovano in un'unità organizzativa denominata Skype for Business Server, il nuovo criterio deve essere creato nella OU di Skype for Business Server.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.

3.  Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** , ad esempio **Skype for Business Server QoS**, e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

5.  In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **criteri**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio, ad esempio **Skype for Business Server QoS**, nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.

7.  Nella pagina successiva verificare che sia selezionata l'opzione **tutte le applicazioni** e quindi fare clic su **Avanti**. Questo assicura semplicemente che tutte le applicazioni corrispondano ai pacchetti dall'intervallo di porte specificato con il codice DSCP specificato.

8.  Nella terza pagina verificare che sia selezionato l' **indirizzo IP di origine e qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà tali pacchetti.

9.  Nella pagina quattro selezionare **TCP e UDP** dal pulsante **Seleziona il protocollo questo criterio di QoS si applica all'elenco a** discesa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente da Skype for Business Server e dalle sue applicazioni client.

10. Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se hai riservato le porte 49152 tramite le porte 57500 per il traffico audio, immetti l'intervallo di porte usando questo formato: **49152:57500**. Fare clic su **fine**.

> [!NOTE]  
> Il valore DSCP di 46 è alquanto arbitrario: anche se DSCP 46 viene spesso usato per contrassegnare i pacchetti audio, non è necessario usare DSCP 46 per le comunicazioni audio. Se è già stato implementato QoS e si usa un codice DSCP diverso per l'audio (ad esempio, DSCP 40), è necessario configurare i criteri di qualità del servizio per usare lo stesso codice (ad es., 40 per l'audio). Se si sta solo implementando la qualità del servizio, è consigliabile usare DSCP 46 per l'audio, semplicemente perché tale valore viene usato in genere per contrassegnare i pacchetti audio.

Dopo aver creato i criteri QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video (e, facoltativamente, un terzo criterio per la gestione del traffico di condivisione delle applicazioni). Per creare un criterio per il video, seguire la stessa procedura di base seguita durante la creazione dei criteri audio, eseguendo queste sostituzioni:

  - Usare un nome di criterio diverso (e univoco), ad esempio **Skype for Business Server video**.

  - Impostare il valore DSCP su **34** anziché su 46. Si noti che non è necessario usare un valore DSCP di 34. L'unico requisito consiste nell'usare un valore DSCP diverso per il video rispetto a quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte su questo: **57501:65535**.

Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, è necessario creare un terzo criterio, eseguendo le sostituzioni seguenti:

  - Usa un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Skype for Business Server**.

  - Impostare il valore DSCP su **24** anziché su 46. Di nuovo, non è necessario usare un valore DSCP pari a 24. L'unico requisito consiste nell'usare un valore DSCP diverso per la condivisione delle applicazioni rispetto a quello usato per l'audio o per il video.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se si hanno le porte riservate da 40803 a 49151 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **40803:49151**.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non saranno stati aggiornati nei computer di Skype for Business Server. Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare i criteri di gruppo:

    Gpupdate.exe /force

Questo comando può essere eseguito dall'interno di Skype for Business Server Management Shell o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore. Per eseguire una finestra di comando in credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

Per verificare che i nuovi criteri QoS siano stati applicati, eseguire le operazioni seguenti:

1.  In un computer con Skype for Business Server fare clic su **Start**e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit**e quindi premere INVIO.

3.  In Editor del registro di sistema espandere **computer**, espandere **HKEY\_\_local**computer, espandere **software**, espandere **criteri**, **Microsoft**, espandere **Windows**e quindi fare clic su **QoS**. In **QoS** dovresti vedere le chiavi del registro di sistema per ogni criterio QoS appena creato. Ad esempio, se hai creato due nuovi criteri (uno denominato Skype for Business Server audio QoS e l'altro denominato Skype for Business Server video QoS), dovresti vedere le voci del registro di sistema per Skype for Business Server audio QoS e Skype for Business Server video QoS.

Per assicurarti che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, devi anche creare una nuova voce del registro di sistema in ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit**e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**. Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS**e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**. Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA**, quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su non **usare NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del registro di sistema e riavviare il computer.
