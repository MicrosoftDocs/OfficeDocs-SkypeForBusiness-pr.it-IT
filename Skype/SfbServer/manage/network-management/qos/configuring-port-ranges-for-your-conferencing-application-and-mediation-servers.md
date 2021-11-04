---
title: Configurazione degli intervalli di porte e dei criteri qualità del servizio per i server per conferenze, applicazioni e Mediation Server
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: In questo articolo viene descritto come configurare gli intervalli di porte e un criterio qualità del servizio per i server per conferenze, applicazioni e Mediation Server.
ms.openlocfilehash: 6785756af5c79eb27d2b4e15b86155d1d58bbc88
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760724"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configurazione degli intervalli di porte e dei criteri qualità del servizio per i server per conferenze, applicazioni e Mediation Server

In questo articolo viene descritto come configurare gli intervalli di porte e un criterio qualità del servizio per i server per conferenze, applicazioni e Mediation Server.

## <a name="configure-port-ranges"></a>Configurare gli intervalli di porte

Per implementare la qualità del servizio, è consigliabile configurare intervalli di porte identici per la condivisione di audio, video e applicazioni nei server Di conferenza, Applicazione e Mediation Server. inoltre, tali intervalli di porte non devono sovrapporsi in alcun modo. Per utilizzare un semplice esempio, si supponga di utilizzare le porte da 10000 a 10999 per i video sui server per conferenze. Ciò significa che è necessario riservare anche le porte da 10000 a 10999 per i video nei server Applicazioni e Mediation Server. In caso contrario, QoS non funzionerà come previsto.

Analogamente, si supponga di riservare le porte da 10000 a 10999 per i video, ma di riservare le porte da 10500 a 11999 per l'audio. Ciò può creare problemi per qualità del servizio, perché gli intervalli di porte si sovrappongono. Con QoS, ogni modalità deve avere un set univoco di porte: se usi le porte da 10000 a 10999 per i video, dovrai usare un intervallo diverso (ad esempio, da 11000 a 11999 per l'audio).

Per impostazione predefinita, gli intervalli di porte audio e video non si sovrappongono in Skype for Business Server; Tuttavia, gli intervalli di porte assegnati alla condivisione delle applicazioni si sovrappongono sia agli intervalli di porte audio che video. Ciò significa che nessuno di questi intervalli è univoco. È possibile verificare gli intervalli di porte esistenti per i server per conferenze, applicazioni e Mediation Server eseguendo i tre comandi seguenti da Skype for Business Server Management Shell:

  Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
  Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
  Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Come puoi vedere nei comandi precedenti, a ogni tipo di porta, audio, video e condivisione di applicazioni, vengono assegnati due valori di proprietà distinti: l'inizio della porta e il numero di porte. L'inizio della porta indica la prima porta utilizzata per tale modalità. Ad esempio, se l'inizio della porta audio è uguale a 50000, significa che la prima porta utilizzata per il traffico audio è la porta 50000. Se il numero di porte audio è 2 (che non è un valore valido, ma viene usato qui a scopo illustrativo), significa che solo due porte vengono allocate per l'audio. Se la prima porta è la porta 50000 e sono presenti un totale di due porte, significa che la seconda deve essere la porta 50001 (gli intervalli di porte devono essere contigui). Di conseguenza, l'intervallo di porte per l'audio è compreso tra 50000 e 50001, inclusi.<BR><br>Si noti anche che i server applicazioni e i Mediation Server supportano QoS solo per l'audio. Per questi server non è quindi necessario modificare le porte di condivisione video o applicazioni.

Se esegui i tre comandi precedenti, vedrai che i valori di porta predefiniti per Skype for Business Server sono configurati in questo modo:

<table>
<colgroup>
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

Come indicato in precedenza, quando si configurano le porte di Skype for Business Server per QoS, è necessario verificare che: 1) le impostazioni delle porte audio siano identiche tra i server di conferenza, applicazioni e Mediation Server. e 2) gli intervalli di porte non si sovrappongono. Se si osserva la tabella precedente, si nota che gli intervalli di porte sono identici per i tre tipi di server. Ad esempio, la porta audio iniziale corrisponde alla porta 49152 per ciascun tipo di server. Anche il numero totale di porte riservate all'audio in ciascun server è identico: 8348. Tuttavia gli intervalli di porte si sovrappongono: le porte audio iniziano in corrispondenza della porta 49152, ma lo stesso avviene per le porte riservate alla condivisione delle applicazioni. Per ottimizzare l'uso di Quality of Service, è necessario riconfigurare la condivisione delle applicazioni in modo che usi un intervallo esclusivo, ad esempio impostando l'inizio alla porta 40803 e l'uso di 8348 porte. Perché 8348 porte? Se si sommano questi valori , 40803 + 8348, significa che la condivisione applicazioni utilizzerà le porte 40803 tramite la porta 49150. Poiché le porte audio iniziano con la porta 49152, gli intervalli di porte non si sovrappongono più.

Dopo aver selezionato il nuovo intervallo di porte per la condivisione delle applicazioni, è possibile apportare la modifica utilizzando il cmdlet Set-CsConferencingServer. Questa modifica non è necessaria per i server applicazioni e i Mediation Server, perché questi server non gestiscono il traffico relativo alla condivisione applicazioni. Per questi server i valori delle porte devono essere modificati solo se si decide di riassegnare le porte usate per il traffico audio.

Per modificare i valori delle porte per la condivisione di applicazioni in un singolo server per conferenze, eseguire un comando simile al seguente da Skype for Business Server Management Shell:

  **Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348**

Se si desidera apportare queste modifiche in tutti i server per conferenze, è possibile eseguire invece questo comando:

  **Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_. Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}**

Dopo aver modificato le impostazioni della porta, è consigliabile arrestare e riavviare ogni servizio interessato dalle modifiche.

Non è obbligatorio che i server per conferenze, i server applicazioni e i Mediation Server condividano esattamente lo stesso intervallo di porte. L'unico requisito è che ogni server abbia un intervallo di porte esclusivo. Tuttavia, in genere l'amministrazione è più semplice se si usa lo stesso intervallo di porte per tutti i server.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurare un criterio qualità del servizio in Skype for Business Server per i server per conferenze, applicazioni e Mediation Server

La configurazione degli intervalli di porte agevola l'uso di QoS (Quality of Service) assicurando che tutto il traffico di un tipo specificato (ad esempio, tutto il traffico audio) passi attraverso lo stesso set di porte. Ciò semplifica l'identificazione e il contrassegno di un determinato pacchetto da parte del sistema: se la porta 49152 è riservata per il traffico audio, qualsiasi attraversamento di pacchetto tramite la porta 49152 può essere contrassegnato con un codice DSCP indicante che si tratta di pacchetti audio. A sua volta, ciò consente ai router di identificare il pacchetto come pacchetto audio e assegnargli una priorità più elevata rispetto ai pacchetti non contrassegnati (ad esempio i pacchetti usati per copiare un file da un server all'altro).

Tuttavia, limitando semplicemente un set di porte a un tipo di traffico specifico non si determina necessariamente l'assegnazione del codice DSCP appropriato ai pacchetti che le attraversano. Oltre a definire gli intervalli di porte, è inoltre necessario creare criteri qualità del servizio che specificano il codice DSCP da associare a ogni intervallo di porte. Ad Skype for Business Server, in genere significa creare due criteri: uno per l'audio e uno per il video.

I criteri di qualità del servizio vengono creati e gestiti più facilmente tramite Criteri di gruppo. Questi stessi criteri possono essere creati anche utilizzando criteri di sicurezza locali. Ciò richiede tuttavia di ripetere la stessa procedura in ogni computer. Il set iniziale di criteri QoS (uno per l'audio e uno per video) deve essere applicato solo ai computer Skype for Business Server che eseguono i servizi Conferencing Server, Application Server e/o Mediation Server. Se tutti questi computer si trovano nella stessa unità organizzativa di Active Directory, è sufficiente assegnare il nuovo oggetto Criteri di gruppo a tale unità organizzativa. In alternativa, è possibile eseguire altri passaggi per impostare il nuovo criterio come destinazione per i computer specificati. ad esempio, è possibile inserire i computer appropriati in un gruppo di sicurezza, quindi utilizzare il filtro di protezione di Criteri di gruppo per applicare l'oggetto Criteri di gruppo solo a tale gruppo di sicurezza.

Per creare criteri di qualità del servizio per la gestione dell'audio, accedere a un computer in cui è stato installato Gestione Criteri di gruppo. Aprire Gestione Criteri di gruppo (fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Gestione Criteri di gruppo**) e quindi eseguire la procedura seguente:

1.  In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer Skype for Business Server si trovano in un'unità organizzativa denominata Skype for Business Server, il nuovo criterio deve essere creato nell'unità organizzativa Skype for Business Server.

2.  Fai clic con il pulsante destro del mouse sul contenitore appropriato, quindi fai clic su Crea un oggetto Criteri di gruppo in questo dominio **e collegalo qui.**

3.  Nella finestra **di** dialogo Nuovo oggetto Criteri di gruppo digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **Nome,** ad esempio **Skype for Business Server QoS,** e quindi fare clic su **OK.**

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica**.

5.  Nell'Editor Gestione Criteri di gruppo espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina di apertura della finestra di dialogo **QoS** basata su criteri digitare un nome per il nuovo criterio, ad esempio **Skype for Business Server QoS,** nella casella **Nome.** Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.

7.  Nella pagina successiva verificare che sia selezionata l'opzione Tutte **le** applicazioni e quindi fare clic su **Avanti.** In questo modo ci si assicura che tutte le applicazioni abbineranno i pacchetti dell'intervallo di porte specificato al codice DSCP specificato.

8.  Nella terza pagina verificare che siano selezionati sia Qualsiasi indirizzo IP di origine che Qualsiasi indirizzo **IP** di destinazione e quindi fare clic su **Avanti.** Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.

9.  Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Skype for Business Server e dalle relative applicazioni client.

10. Nel gruppo **Specifica il numero della porta di origine** selezionare **Da questa porta o intervallo di origine**. Nella casella di testo associata, digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se sono riservate le porte da 49152 a 57500 per il traffico audio, immettere l'intervallo di porte utilizzando il formato **seguente: 49152:57500**. Fare clic su **Fine**.

> [!NOTE]  
> Il valore DSCP di 46 è in qualche modo arbitrario: sebbene il valore DSCP 46 sia spesso usato per contrassegnare i pacchetti audio, non è obbligatorio usarlo per le comunicazioni audio. Se hai già implementato QoS e stai usando un codice DSCP diverso per l'audio (ad esempio, DSCP 40), devi configurare i criteri qualità del servizio per usare lo stesso codice (ad esempio, 40 per l'audio). Se si sta eseguendo una nuova implementazione della Quality of Service, è consigliabile usare il codice DSCP 46 per l'audio in quando si tratta del valore comunemente usato per contrassegnare i pacchetti audio.

Dopo aver creato i criteri QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video (e, facoltativamente, un terzo criterio per la gestione del traffico di condivisione delle applicazioni). Per creare un criterio per il traffico video, seguire la stessa procedura di base usata per la creazione del criterio audio, con le distinzioni seguenti:

  - Usa un nome di criterio diverso (e univoco), ad esempio **Skype for Business Server Video**.

  - Impostare il valore DSCP su **34** invece di 46. Si noti che non è obbligatorio usare il valore DSCP 34. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte **su: 57501:65535**.

Se si decide di creare un criterio per la gestione del traffico di condivisione applicazioni, è necessario creare un terzo criterio, apportando le sostituzioni seguenti:

  - Utilizzare un nome di criterio diverso (e univoco), ad esempio Skype for Business Server **Condivisione applicazioni**.

  - Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 40803 a 49151 per la condivisione delle applicazioni, impostare l'intervallo di porte **su: 40803:49151**.

I nuovi criteri creati avranno effetto solo dopo l'aggiornamento di Criteri di gruppo nei Skype for Business Server computer. Sebbene l'aggiornamento di Criteri di gruppo venga eseguito automaticamente periodicamente, è possibile imporre l'aggiornamento immediato eseguendo il comando seguente su ogni computer in cui è necessario:

  **Gpupdate.exe /force**

Questo comando può essere eseguito da Skype for Business Server Management Shell o da qualsiasi finestra di comando in esecuzione con credenziali di amministratore. Per eseguire una finestra di comando con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

Per verificare che i criteri QoS siano stati applicati, effettuare le operazioni seguenti:

1.  In un Skype for Business Server computer fare clic sul **pulsante Start** e quindi scegliere **Esegui.**

2.  Nella finestra **di** dialogo Esegui digitare **regedit** e quindi premere INVIO.

3.  Nell'Editor del Registro di sistema espandere **Computer**, **HKEY \_ LOCAL \_ MACHINE**, **SOFTWARE**, **Criteri**, **Microsoft**, Windows **e** quindi fare clic su **QoS**. In **QoS** dovrebbero essere presenti le chiavi del Registro di sistema per ognuno dei Criteri QoS creati. Ad esempio, se sono stati creati due nuovi criteri (uno denominato QoS audio Skype for Business Server e l'altro QoS video Skype for Business Server), dovrebbero essere presenti voci del Registro di sistema per QoS audio Skype for Business Server e QoS video Skype for Business Server.

Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:

1.  Fare clic su **Start** quindi scegliere **Esegui**.

2.  Nella finestra **di** dialogo Esegui digitare **regedit** e quindi premere INVIO.

3.  Nell'Editor del Registro di sistema espandere **HKEY \_ LOCAL \_ MACHINE**, **SYSTEM**, **CurrentControlSet**, **services** e **quindi Tcpip**.

4.  Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do not use NLA**. Nella finestra **di dialogo Modifica** stringa digitare **1** nella casella **Dati** valore e quindi fare clic su **OK.**

7.  Chiudere l'editor del Registro di sistema e riavviare il computer.
