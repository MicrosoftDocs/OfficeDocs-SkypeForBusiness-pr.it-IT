---
title: Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i servizi di conferenza, applicazione e Mediation Server
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In questo articolo viene descritto come configurare gli intervalli di porte e i criteri di qualità dei servizi per le conferenze, l'applicazione e i Mediation Server.
ms.openlocfilehash: 8c65e36528615aca181b6aac17aab844c1a4d206
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800126"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i servizi di conferenza, applicazione e Mediation Server

In questo articolo viene descritto come configurare gli intervalli di porte e i criteri di qualità dei servizi per le conferenze, l'applicazione e i Mediation Server.

## <a name="configure-port-ranges"></a>Configurare gli intervalli di porte

Per implementare la qualità del servizio, è consigliabile configurare intervalli di porte identici per la condivisione di audio, video e applicazioni su servizi di conferenza, applicazioni e Mediation Server. Inoltre, gli intervalli di porte non devono sovrapporsi in alcun modo. Per utilizzare un semplice esempio, si supponga di utilizzare le porte da 10000 a 10999 per i video sui server per conferenze. Questo significa che è necessario anche prenotare le porte da 10000 a 10999 per i video nell'applicazione e Mediation Server. In caso contrario, QoS non funzionerà come previsto.

Analogamente, si supponga di prenotare le porte da 10000 a 10999 per il video, ma quindi di prenotare le porte da 10500 a 11999 per l'audio. Ciò può creare problemi per la qualità del servizio, in quanto gli intervalli di porte si sovrappongono. Con QoS, ogni modalità deve disporre di un insieme univoco di porte: se si utilizzano le porte da 10000 a 10999 per il video, è necessario utilizzare un intervallo diverso (ad esempio, da 11000 a 11999, per l'audio).

Per impostazione predefinita, gli intervalli di porte audio e video non si sovrappongono in Skype for Business Server; Tuttavia, gli intervalli di porte assegnati alla sovrapposizione di condivisione delle applicazioni con gli intervalli di porte audio e video. Che, a sua incirca, significa che nessuno di questi intervalli è univoco. È possibile verificare gli intervalli di porte esistenti per i servizi di conferenza, applicazione e Mediation Server eseguendo i tre comandi seguenti dall'interno di Skype for Business Server Management Shell:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Come si può vedere nei comandi precedenti, ogni tipo di porta – audio, video e condivisione applicazioni – viene assegnato due valori di proprietà distinti: l'inizio della porta e il numero di porta. La porta iniziale indica la prima porta utilizzata per tale modalità. ad esempio, se la porta audio Start è uguale a 50000, significa che la prima porta utilizzata per il traffico audio è la porta 50000. Se il numero di porta audio è 2 (che non è un valore valido, ma viene utilizzato qui a scopo illustrativo), significa che vengono allocate solo due porte per l'audio. Se la prima porta è la porta 50000 e vi sono un totale di due porte, significa che la seconda porta deve essere la porta 50001 (gli intervalli di porte devono essere contigui). Di conseguenza, l'intervallo di porte per l'audio sarebbe porte da 50000 a 50001, inclusi.<BR><br>Si noti anche che i server applicazioni e i Mediation Server supportano QoS solo per l'audio. Per questi server non è quindi necessario modificare le porte di condivisione video o applicazioni.

Se si eseguono i tre comandi precedenti, si noterà che i valori di porta predefiniti per Skype for Business Server sono configurati in questo modo:

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
<th>Server per conferenze</th>
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

Come indicato in precedenza, quando si configurano le porte di Skype for Business Server per QoS, è necessario assicurarsi che: 1) le impostazioni della porta audio siano identiche tra i vostri servizi di conferenza, applicazioni e Mediation Server; e 2) gli intervalli di porte non si sovrappongono. Se si osserva la tabella precedente, si nota che gli intervalli di porte sono identici per i tre tipi di server. Ad esempio, la porta audio iniziale corrisponde alla porta 49152 per ciascun tipo di server. Anche il numero totale di porte riservate all'audio in ciascun server è identico: 8348. Tuttavia gli intervalli di porte si sovrappongono: le porte audio iniziano in corrispondenza della porta 49152, ma lo stesso avviene per le porte riservate alla condivisione delle applicazioni. Per ottimizzare l'uso di Quality of Service, è necessario riconfigurare la condivisione delle applicazioni in modo che usi un intervallo esclusivo, ad esempio impostando l'inizio alla porta 40803 e l'uso di 8348 porte. Perché 8348 porte? Se si aggiungono questi valori insieme--40803 + 8348--questo significa che la condivisione di applicazioni utilizzerà le porte 40803 tramite la porta 49150. Poiché le porte audio iniziano con la porta 49152, gli intervalli di porte non si sovrappongono più.

Dopo aver selezionato il nuovo intervallo di porte per la condivisione delle applicazioni, è possibile apportare le modifiche utilizzando il cmdlet Set-CsConferencingServer. Questa modifica non è necessaria per i server applicazioni e i Mediation Server, perché questi server non gestiscono il traffico relativo alla condivisione applicazioni. Per questi server i valori delle porte devono essere modificati solo se si decide di riassegnare le porte usate per il traffico audio.

Per modificare i valori delle porte per la condivisione delle applicazioni in un singolo server per conferenze, eseguire un comando simile a questo da Skype for Business Server Management Shell:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se si desidera apportare queste modifiche su tutti i server per conferenze, è possibile eseguire questo comando:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Dopo aver modificato le impostazioni della porta, è necessario arrestare e quindi riavviare ogni servizio influenzato dalle modifiche.

Non è obbligatorio che i server per conferenze, i server applicazioni e i Mediation Server condividano esattamente lo stesso intervallo di porte. L'unico requisito è che ogni server abbia un intervallo di porte esclusivo. Tuttavia, in genere l'amministrazione è più semplice se si usa lo stesso intervallo di porte per tutti i server.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurare un criterio di qualità del servizio in Skype for Business Server per le conferenze, l'applicazione e i Mediation Server

La configurazione degli intervalli di porte agevola l'uso di QoS (Quality of Service) assicurando che tutto il traffico di un tipo specificato (ad esempio, tutto il traffico audio) passi attraverso lo stesso set di porte. Ciò semplifica l'identificazione e il contrassegno di un determinato pacchetto da parte del sistema: se la porta 49152 è riservata per il traffico audio, qualsiasi attraversamento di pacchetto tramite la porta 49152 può essere contrassegnato con un codice DSCP indicante che si tratta di pacchetti audio. A sua volta, ciò consente ai router di identificare il pacchetto come pacchetto audio e assegnargli una priorità più elevata rispetto ai pacchetti non contrassegnati (ad esempio i pacchetti usati per copiare un file da un server all'altro).

Tuttavia, limitando semplicemente un set di porte a un tipo di traffico specifico non si determina necessariamente l'assegnazione del codice DSCP appropriato ai pacchetti che le attraversano. Oltre a definire gli intervalli di porte, è inoltre necessario creare criteri di qualità dei servizi che specifichino il codice DSCP da associare a ogni intervallo di porte. Per Skype for Business Server, in genere significa creare due criteri: uno per l'audio e uno per il video.

I criteri di qualità dei servizi vengono creati e gestiti più facilmente tramite criteri di gruppo. Gli stessi criteri possono essere creati anche utilizzando criteri di protezione locali. Tuttavia, è necessario ripetere la stessa procedura in tutti i computer. Il set iniziale di criteri QoS (uno per l'audio e uno per il video) deve essere applicato solo ai computer Skype for Business Server che eseguono i servizi di conferenza server, server applicazioni e/o Mediation Server. Se tutti i computer si trovano nella stessa unità organizzativa di Active Directory, è sufficiente assegnare il nuovo oggetto Criteri di gruppo a quell'unità organizzativa. In alternativa, è possibile eseguire altri passaggi per assegnare il nuovo criterio ai computer specificati. ad esempio, è possibile inserire i computer idonei in un gruppo di sicurezza, quindi utilizzare il filtro di sicurezza di criteri di gruppo per applicare l'oggetto Criteri di sistema solo a quel gruppo di sicurezza.

Per creare criteri di qualità del servizio per la gestione dell'audio, accedere a un computer in cui è stata installata la gestione criteri di gruppo. Aprire Gestione Criteri di gruppo (fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Gestione Criteri di gruppo**) e quindi eseguire la procedura seguente:

1.  In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer di Skype for Business Server si trovano in un'unità organizzativa denominata Skype for Business Server, è necessario creare il nuovo criterio nell'unità organizzativa di Skype for Business Server.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi fare clic su **Crea un oggetto Criteri di gruppo in questo dominio e collegarlo qui**.

3.  Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** (ad esempio, **Skype for Business Server QoS**) e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

5.  Nell'Editor Gestione Criteri di gruppo espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina apertura della finestra di dialogo **QoS basata su criteri** Digitare un nome per il nuovo criterio (ad esempio, **Skype for Business Server QoS**) nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.

7.  Nella pagina successiva verificare che sia selezionata l'opzione **tutte le applicazioni** e quindi fare clic su **Avanti**. In questo modo ci si assicura che tutte le applicazioni abbineranno i pacchetti dell'intervallo di porte specificato al codice DSCP specificato.

8.  Nella terza pagina, verificare che siano selezionati tutti gli **indirizzi IP di origine e qualsiasi indirizzo IP di destinazione** , quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.

9.  Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente usati da Skype for Business Server e dalle sue applicazioni client.

10. Nel gruppo **Specifica il numero della porta di origine** selezionare **Da questa porta o intervallo di origine**. Nella casella di testo associata, digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se sono state riservate le porte 49152 tramite le porte 57500 per il traffico audio, immettere l'intervallo di porte utilizzando il formato seguente: **49152:57500**. Fare clic su **Fine**.

> [!NOTE]  
> Il valore DSCP di 46 è in qualche modo arbitrario: sebbene il valore DSCP 46 sia spesso usato per contrassegnare i pacchetti audio, non è obbligatorio usarlo per le comunicazioni audio. Se è già stato implementato QoS e si utilizza un codice DSCP diverso per l'audio (ad esempio, DSCP 40), è necessario configurare i criteri di qualità del servizio per l'utilizzo dello stesso codice (ovvero, 40 per l'audio). Se si sta eseguendo una nuova implementazione della Quality of Service, è consigliabile usare il codice DSCP 46 per l'audio in quando si tratta del valore comunemente usato per contrassegnare i pacchetti audio.

Dopo aver creato il criterio QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video (e, facoltativamente, un terzo criterio per la gestione del traffico di condivisione delle applicazioni). Per creare un criterio per il traffico video, seguire la stessa procedura di base usata per la creazione del criterio audio, con le distinzioni seguenti:

  - Utilizzare un nome di criterio diverso (e univoco), ad esempio **video di Skype for Business Server**.

  - Impostare il valore DSCP su **34** invece di 46. Si noti che non è obbligatorio usare il valore DSCP 34. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Utilizzare l'intervallo di porte configurata in precedenza per il traffico video. Ad esempio, se si dispone delle porte riservate da 57501 a 65535 per il video, impostare l'intervallo di porte su questo: **57501:65535**.

Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, è necessario creare un terzo criterio, eseguendo le sostituzioni seguenti:

  - Utilizzare un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Skype for Business Server**.

  - Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Utilizzare l'intervallo di porte configurata in precedenza per il traffico video. Ad esempio, se si dispone delle porte riservate da 40803 a 49151 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **40803:49151**.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non sono stati aggiornati sui computer di Skype for Business Server. Sebbene l'aggiornamento di Criteri di gruppo venga eseguito automaticamente periodicamente, è possibile imporre l'aggiornamento immediato eseguendo il comando seguente su ogni computer in cui è necessario:

    Gpupdate.exe /force

Questo comando può essere eseguito dall'interno di Skype for Business Server Management Shell o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore. Per eseguire una finestra di comando con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

Per verificare che i criteri QoS siano stati applicati, effettuare le operazioni seguenti:

1.  Su un computer con Skype for Business Server, fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  In Editor del registro di sistema espandere **computer**, espandere hKey, espandere **software**, espandere **criteri**, espandere **Microsoft**, espandere **Windows** e quindi fare clic su **QoS**. **\_ \_** In **QoS** dovrebbero essere presenti le chiavi del Registro di sistema per ognuno dei Criteri QoS creati. Ad esempio, se sono stati creati due nuovi criteri (uno denominato Skype for Business Server audio QoS e l'altro di QoS video Skype for Business Server), dovrebbero essere visualizzate le voci del registro di sistema per Skype for Business Server audio QoS e Skype for Business Server video QoS.

Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:

1.  Fare clic su **Start** quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi** e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del registro di sistema, digitare non **utilizzare NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do not use NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del registro di sistema e riavviare il computer.
