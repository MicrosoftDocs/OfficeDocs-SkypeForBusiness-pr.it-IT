---
title: Configurazione degli intervalli di porte e qualità del servizio per i server perimetrali
ms.reviewer: null
'ms:assetid': 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)'
'ms:contentKeyID': 48184469
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: In questo articolo viene descritto come configurare gli intervalli di porte per i server perimetrali e come configurare un criterio qualità del servizio per i server A/V Edge.
---


# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i server perimetrali in Skype for Business Server

In questo articolo viene descritto come configurare gli intervalli di porte per i server perimetrali e come configurare un criterio qualità del servizio per i server A/V Edge.

## <a name="configure-port-ranges"></a>Configurare gli intervalli di porte

Con i server Perimetrali non è necessario configurare intervalli di porte separati per la condivisione di audio, video e applicazioni. Allo stesso modo, gli intervalli di porte utilizzati per i server perimetrali non devono corrispondere agli intervalli di porte utilizzati con i server per conferenze, applicazioni e Mediation Server. Prima di procedere con l'esempio, è importante sottolineare che, sebbene questa opzione esista, è consigliabile non modificare gli intervalli di porte, in quanto ciò potrebbe influire negativamente su alcuni scenari se si esce dall'intervallo di porte 50000.

Si supponga, ad esempio, di aver configurato i server per conferenze, applicazioni e Mediation Server per l'utilizzo di questi intervalli di porte:


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Tipo di pacchetto</th>
<th>Numero di porta iniziale</th>
<th>Numero di porte riservate</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Condivisione applicazioni</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Video</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totali</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Come puoi vedere, gli intervalli di porte per la condivisione di audio, video e applicazioni iniziano dalla porta 40803 e comprendono un totale di 24732 porte. Se si preferisce, è possibile configurare un determinato server perimetrale per l'utilizzo di questi valori di porta complessivi eseguendo un comando simile al seguente da Skype for Business Server Management Shell:

  **Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730**

Alternativamente, è possibile utilizzare il comando seguente per configurare simultaneamente tutti i server perimetrali all'interno dell'organizzazione:

  **Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_. Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}**

È possibile verificare le impostazioni correnti delle porte per i server perimetrali utilizzando questo Skype for Business Server Management Shell:

  **Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount**

Anche in questo caso, mentre forniamo queste opzioni, ti consigliamo vivamente di lasciare le cose come sono per la configurazione delle porte.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurare un criterio QoS per i server A/V Edge

Oltre alla creazione di criteri QoS per i Conferencing Server, server applicazioni e Mediation Server, è necessario anche creare criteri audio e video per il sito interno degli A/V Edge Server. I criteri utilizzati nei server perimetrali, tuttavia, sono diversi da quelli utilizzati nei Conferencing Server, server applicazioni e Mediation Server. Per i Server di conferenza, applicazione e Mediation Server è stato specificato un intervallo di porte di origine. con i server perimetrali, è necessario specificare un intervallo di porte di destinazione. Per questo, non è possibile applicare semplicemente i criteri QoS per conferenze, applicazioni e Mediation Server ai server perimetrali: questi criteri semplicemente non funzionano. È necessario invece creare nuovi criteri e applicarli solo ai server perimetrali.

Nella procedura seguente viene descritto il processo di creazione di oggetti Criteri di gruppo di Active Directory che possono essere utilizzati per gestire la qualità del servizio nei server perimetrali. Naturalmente, è possibile che i server perimetrali siano server autonomi che non dispongono di account di Active Directory. In questo caso, è possibile utilizzare Criteri di gruppo locali anziché Criteri di gruppo di Active Directory: l'unica differenza consiste nel fatto che è necessario creare questi criteri locali utilizzando l'Editor Criteri di gruppo locali e creare singolarmente lo stesso set di criteri in ogni server perimetrale. Per avviare l'Editor Criteri di gruppo locali in un server perimetrale, eseguire le operazioni seguenti:

1.  Fare clic su **Start** quindi scegliere **Esegui**.

2.  Nella finestra **di** dialogo Esegui digitare **gpedit.msc** e quindi premere INVIO.

Se si creano criteri basati su Active Directory, è necessario accedere a un computer in cui sia installato Gestione Criteri di gruppo. In tal caso, aprire Gestione Criteri di gruppo (fare clic sul **pulsante Start**, scegliere Strumenti **di amministrazione e** quindi Gestione Criteri di **gruppo), quindi** completare la procedura seguente:

1.  In Gestione Criteri di gruppo, individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer Skype for Business Server si trovano in un'unità organizzativa denominata Skype for Business Server, il nuovo criterio deve essere creato nell'unità organizzativa Skype for Business Server.

2.  Fai clic con il pulsante destro del mouse sul contenitore appropriato, quindi fai clic su Crea un oggetto Criteri di gruppo **in questo dominio e collegalo qui**.

3.  Nella finestra **di dialogo** Nuovo oggetto Criteri di gruppo digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **Nome**, ad esempio **Skype for Business Server Audio**, e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica**.

Da questo punto in avanti il processo è identico sia per la creazione di un criterio di Active Directory che per la creazione di un criterio locale:

1.  In Editor Gestione Criteri di gruppo o Editor Criteri di gruppo locali espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e scegliere **Crea nuovo criterio**.

2.  Nella pagina di apertura della finestra di dialogo **QoS** basata su criteri digitare un nome per il nuovo criterio, ad esempio **Skype for Business Server Audio**, nella **casella Nome.** Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.

3.  Nella pagina successiva verificare che sia selezionata l'opzione Tutte **le** applicazioni e quindi fare clic su **Avanti**. Questa impostazione indica alla rete di cercare tutti i pacchetti con DSCP 46, non solo quelli creati da un'applicazione specifica.

4.  Nella terza pagina, verificare che siano selezionati sia **Qualsiasi indirizzo IP** di origine che **Qualsiasi indirizzo IP** di destinazione e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.

5.  Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Skype for Business Server e dalle relative applicazioni client.

6.  In **Specifica il numero della porta di destinazione** selezionare **Verso questo numero di porta o intervallo di porte di destinazione**. Nella casella di testo associata, immettere l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se sono riservate le porte da 49152 a 57500 per il traffico audio, immettere l'intervallo di porte nel formato **seguente: 49152:57500**. Fare clic su **Fine**.

Dopo aver creato i criteri QoS per il traffico audio, devi creare un secondo criterio per il traffico video. Per creare un criterio per il traffico video, seguire la stessa procedura di base usata per la creazione del criterio audio, con le distinzioni seguenti:

  - Usa un nome di criterio diverso (e univoco), ad esempio **Skype for Business Server Video**.

  - Impostare il valore DSCP su **34** invece di 46. Si noti che non è obbligatorio usare il valore DSCP 34. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte su **: 57501:65535**. Anche in questo caso è necessario configurarlo come intervallo di porte di destinazione.

Se si decide di creare un criterio per la gestione del traffico di condivisione applicazioni, è necessario creare un terzo criterio, apportando le sostituzioni seguenti:

  - Utilizzare un nome di criterio diverso (e univoco), ad esempio condivisione Skype for Business Server **applicazioni**.

  - Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 40803 a 49151 per la condivisione delle applicazioni, impostare l'intervallo di porte su **: 40803:49151**.

I nuovi criteri creati verranno applicati solo dopo l'aggiornamento di Criteri di gruppo sui server perimetrali. L'aggiornamento di Criteri di gruppo viene eseguito periodicamente in modo automatico, ma è possibile forzarne l'esecuzione immediata utilizzando il comando seguente su ogni computer in cui questa operazione è necessaria:

 **Gpudate.exe /force**

Questo comando può essere eseguito dall'Skype for Business Server o da qualsiasi finestra di comando in esecuzione con credenziali di amministratore. Per eseguire una finestra di comando con credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**. Può essere necessario riavviare il server perimetrale anche dopo avere eseguito Gpudate.exe.

Per assicurarsi che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, creare anche una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:

1.  Fare clic su **Start** quindi scegliere **Esegui**.

2.  Nella finestra **di** dialogo Esegui digitare **regedit** e quindi premere INVIO.

3.  Nell'editor del Registro di sistema espandere **HKEYLOCALMACHINE\_\_**, **SYSTEM**, **CurrentControlSet**, **services** e quindi **Tcpip**.

4.  Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do no use NLA**. Nella finestra **di dialogo Modifica** stringa digitare **1** nella casella **Dati** valore e quindi fare clic su **OK**.

7.  Chiudere l'editor del Registro di sistema e riavviare il computer.
