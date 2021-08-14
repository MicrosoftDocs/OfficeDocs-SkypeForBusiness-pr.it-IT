---
title: Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i client
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
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
description: In questo articolo viene descritto come configurare gli intervalli di porte per i client e configurare i criteri qualità del servizio in Skype for Business Server per i client in esecuzione in Windows 10.
ms.openlocfilehash: 4d8736c9249bbef25438be7232d7802f3ddb3e9a
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234021"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i client in Skype for Business Server

In questo articolo viene descritto come configurare gli intervalli di porte per i client e configurare i criteri qualità del servizio in Skype for Business Server per i client in esecuzione in Windows 10.

## <a name="configure-port-ranges"></a>Configurare gli intervalli di porte

Per impostazione predefinita, Skype for Business applicazioni client possono utilizzare qualsiasi porta tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione; ciò è dovuto al fatto che intervalli di porte specifici non vengono abilitati automaticamente per i client. Per utilizzare la qualità del servizio, tuttavia, è necessario riassegnare i vari tipi di traffico (audio, video, supporti, condivisione applicazioni e trasferimento di file) a una serie di intervalli di porte univoci. A tale scopo, è possibile utilizzare il cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Gli utenti finali non possono apportare queste modifiche. Le modifiche alle porte possono essere apportate solo dagli amministratori utilizzando il cmdlet Set-CsConferencingConfiguration.


È possibile determinare gli intervalli di porte attualmente utilizzati per le sessioni di comunicazione eseguendo il comando seguente da Skype for Business Server Management Shell:

**Get-CsConferencingConfiguration**

Presupponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione Skype for Business Server, è consigliabile ottenere informazioni che includono i valori delle proprietà seguenti:

ClientMediaPortRangeEnabled : False<br/>
ClientAudioPort : 5350<br/>
ClientAudioPortRange : 40<br/>
ClientVideoPort : 5350<br/>
ClientVideoPortRange : 40<br/>
ClientAppSharingPort : 5350<br/>
ClientAppSharingPortRange : 40<br/>
ClientFileTransferPort : 5350<br/>
ClientTransferPortRange : 40<br/>

Se si osserva attentamente l'output precedente, si noteranno due aspetti importanti. Innanzitutto, la proprietà ClientMediaPortRangeEnabled è impostata su False:

**ClientMediaPortRangeEnabled : False**

Questo è importante perché, quando questa proprietà è impostata su False, i client Skype for Business utilizzeranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando partecipano a una sessione di comunicazione. ciò è vero indipendentemente da qualsiasi altra impostazione di porta (ad esempio, ClientMediaPort o ClientVideoPort). Se si desidera limitare l'utilizzo a un set di porte specificato (operazione che si desidera eseguire se si prevede di implementare la qualità del servizio), è innanzitutto necessario abilitare gli intervalli di porte multimediali client. Questa operazione può essere eseguita utilizzando il comando Windows PowerShell seguente:

**Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

Il comando precedente abilita gli intervalli di porte multimediali dei client per la raccolta globale delle impostazioni di configurazione delle conferenze. Tali impostazioni, tuttavia, possono essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio Conferencing Server). Per abilitare gli intervalli di porte multimediali dei client per un determinato sito o server, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:

**Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True**

In alternativa, è possibile usare questo comando per abilitare contemporaneamente gli intervalli di porte per tutte le impostazioni di configurazione delle conferenze:

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

Il secondo aspetto importante da osservare è l'output di esempio. Questo mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:

ClientAudioPort : 5350<br/>
ClientVideoPort : 5350<br/>
ClientAppSharingPort : 5350<br/>
ClientFileTransferPort : 5350<br/>

Per implementare QoS, è necessario che ciascuno di questi intervalli di porte sia univoco. È ad esempio possibile configurare gli intervalli di porte in questo modo:


<table>
<colgroup>
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


Nella tabella precedente gli intervalli di porte dei client rappresentano un subset degli intervalli di porte configurati per i server. Sui server, ad esempio, la condivisione applicazioni è configurata in modo da usare le porte da 40803 a 49151, mentre sui computer client la condivisione applicazioni è configurata in modo da usare le porte da 42000 a 42019. Anche questa operazione viene eseguita principalmente per semplificare l'amministrazione di QoS: le porte client non devono rappresentare un sottoinsieme delle porte utilizzate nel server. Ad esempio, nei computer client è possibile configurare la condivisione applicazioni per l'utilizzo, ad esempio, delle porte da 10000 a 10019. Tuttavia, è consigliabile rendere gli intervalli di porte client un sottoinsieme degli intervalli di porte del server.

Si sarà inoltre notato che sono state riservate 8348 porte per la condivisione applicazioni sui server e che solo 20 porte sono state messe da parte per la condivisione applicazioni sui client. Anche questo è consigliato, ma non è una regola difficile e veloce. In generale, è possibile considerare ogni porta disponibile per rappresentare una singola sessione di comunicazione: se sono disponibili 100 porte in un intervallo di porte, significa che il computer in questione potrebbe partecipare al massimo a 100 sessioni di comunicazione in un determinato momento. Poiché è probabile che i server verranno coinvolti in un numero di conversazioni di gran lunga superiore a quelle dei client, è ragionevole aprire molte più porte sui server che non sui client. La scelta di riservare 20 porte per la condivisione applicazioni su un client significa che un utente può partecipare contemporaneamente a 20 sessioni di condivisione applicazioni sul dispositivo specificato. Questa configurazione dovrebbe soddisfare la maggior parte degli utenti.

Per assegnare gli intervalli di porte precedenti alla raccolta globale di impostazioni di configurazione delle conferenze, è possibile utilizzare il comando Skype for Business Server Management Shell seguente:

**Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

In alternativa, usare il comando per assegnare questi stessi intervalli di porte per tutte le impostazioni di configurazione delle conferenze:

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

I singoli utenti devono disconnettersi da Skype for Business e quindi eseguire di nuovo l'accesso prima che queste modifiche avranno effetto.

> [!NOTE]  
> È anche possibile abilitare gli intervalli di porte multimediali dei client e quindi assegnarli con un singolo comando. Ad esempio:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurare i criteri di qualità del servizio per i client in Windows 10

Oltre a specificare gli intervalli di porte per l'utilizzo da parte dei client Skype for Business, è inoltre necessario creare criteri di qualità del servizio separati che verranno applicati ai computer client. I criteri di qualità del servizio creati per i server per conferenze, applicazioni e Mediation Server non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono Skype for Business client e Windows 10.

Nell'esempio seguente viene utilizzato questo set di intervalli di porte per creare un criterio audio e un criterio video:


<table>
<colgroup>
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

Per creare criteri audio di qualità del servizio per Windows 10 computer, accedere innanzitutto a un computer in cui è stato installato Gestione Criteri di gruppo. Aprire Gestione Criteri di gruppo (fare clic sul pulsante **Start**, scegliere **Strumenti** di amministrazione e quindi Gestione Criteri di **gruppo**), quindi eseguire la procedura seguente:

1.  In Gestione Criteri di gruppo, individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata Client, il nuovo criterio deve essere creato nell'unità organizzativa Client.

2.  Fai clic con il pulsante destro del mouse sul contenitore appropriato, quindi fai clic su Crea un oggetto Criteri di gruppo in questo dominio **e collegalo qui.**

3.  Nella finestra **di dialogo** Nuovo oggetto Criteri di gruppo digitare  un nome per il nuovo oggetto Criteri di gruppo nella casella Nome e quindi fare clic su **OK.**

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica**.

5.  Nell'Editor Gestione Criteri di gruppo espandere **Configurazione computer,** espandere Windows Impostazioni , **fare** clic con il pulsante destro del mouse su **QoS** basata su criteri e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina di apertura della finestra di dialogo **QoS** basata su criteri digitare un nome per il nuovo criterio nella **casella** Nome. Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.

7.  Nella pagina successiva selezionare **Solo** le applicazioni con questo nome eseguibile, immettere **Lync.exe** come nome e quindi fare clic su **Avanti.** Questa impostazione indica al criterio di assegnare solo la priorità al traffico corrispondente Skype for Business client.

8.  Nella terza pagina verificare che siano selezionati sia Qualsiasi indirizzo **IP** di origine che Qualsiasi indirizzo **IP** di destinazione e quindi fare clic su **Avanti.** Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.

9.  Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Skype for Business Server e dalle relative applicazioni client.

10. Sotto l'intestazione **Specifica il numero della porta di origine** selezionare **Da questo numero di porta o intervallo di porte di origine**. Nella casella di testo abbinata digitare l'intervallo di porte riservato alle trasmissioni audio. Se ad esempio è stato riservato al traffico audio l'intervallo di porte compreso tra la 50020 e la 50039, immettere l'intervallo di porte utilizzando questo formato: **50020:50039**. Fare clic su **Fine**.

Dopo aver creato il criterio QoS per l'audio, è necessario creare un secondo criterio per il video. Per creare un criterio per il video, seguire la stessa procedura base osservata per creare il criterio audio, apportandovi le modifiche seguenti:

  - Utilizzare un nome di criterio diverso (e univoco).

  - Impostare il valore DSCP su **34** anziché su 46. Come accennato, non è necessario utilizzare il valore DSCP 34, bensì è sufficiente utilizzare un valore diverso da quello specificato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 58000 a 58019 per il video, impostare l'intervallo di porte **su: 58000:58019**.

Se si decide di creare un criterio per la gestione del traffico di condivisione applicazioni, apportare le sostituzioni seguenti:

  - Utilizzare un nome di criterio diverso (e univoco), ad esempio Skype for Business Server **Condivisione applicazioni**.

  - Impostare il valore DSCP su **24** anziché su 46. Di nuovo, non è rilevante che questo valore sia 24, bensì è sufficiente che sia diverso dai valori utilizzati per l'audio e per il video.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 42000 a 42019 per la condivisione delle applicazioni, impostare l'intervallo di porte **su: 42000:42019**.

Per un criterio di trasferimento file:

  - Utilizzare un nome di criterio diverso (e univoco), ad esempio Skype for Business Server **trasferimenti di file**.

  - Impostare il valore DSCP su **14**. Di nuovo, non è rilevante che questo valore sia 14, bensì è sufficiente che sia un codice DSCP univoco.

  - Usa l'intervallo di porte configurato in precedenza per l'applicazione. Ad esempio, se sono state riservate le porte da 42020 a 42039 per la condivisione delle applicazioni, impostare l'intervallo di porte **su: 42020:42039**.

I nuovi criteri creati non saranno effettivi finché Criteri di gruppo non verrà aggiornato nei computer client. Benché Criteri di gruppo venga aggiornato automaticamente a intervalli regolari, è possibile effettuare un aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare Criteri di gruppo:

**Gpupdate.exe /force**

Questo comando può essere eseguito da qualsiasi finestra dei comandi eseguita con credenziali di amministratore. Per eseguire una finestra dei comandi con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

Tenere presente che questi criteri devono essere destinati ai computer client. Non devono essere applicati ai server che eseguono Skype for Business Server.

Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:

1.  Fare clic su **Start** quindi scegliere **Esegui**.

2.  Nella finestra **di** dialogo Esegui digitare **regedit** e quindi premere INVIO.

3.  Nell'Editor del Registro di sistema espandere **HKEY \_ LOCAL \_ MACHINE**, **SYSTEM**, **CurrentControlSet**, **services** e **quindi Tcpip**.

4.  Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do not use NLA**. Nella finestra **di dialogo Modifica** stringa digitare **1** nella casella **Dati** valore e quindi fare clic su **OK.**

7.  Chiudi l'Editor del Registro di sistema e riavvia il computer.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurare qualità del servizio nei computer con più schede di rete

Se si dispone di un computer con più schede di rete, è possibile che si esere occasionalmente a problemi in cui i valori DSCP vengono visualizzati come 0x00 anziché come valore configurato. Questo solitamente si verifica nei computer in cui una o più schede di rete non sono in grado di accedere al dominio di Active Directory, come avviene ad esempio nel caso delle schede utilizzate per una rete privata. In questi casi i valori DSCP verranno assegnati alle schede che possono accedere al dominio, ma non alle altre.

Se si desidera contrassegnare i valori DSCP per tutte le schede di rete di un computer, incluse le schede che non hanno accesso al dominio, sarà necessario aggiungere e configurare un valore al Registro di sistema. A tale scopo, effettuare la procedura seguente:

1.  Fare clic su **Start** quindi scegliere **Esegui**.

2.  Nella finestra **di** dialogo Esegui digitare **regedit** e quindi premere INVIO.

3.  Nell'Editor del Registro di sistema espandere **HKEY \_ LOCAL \_ MACHINE**, **SYSTEM**, **CurrentControlSet**, **services** e **quindi Tcpip**.

4.  Se non è presente una chiave del Registro di sistema denominata **QoS**, fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave, digitare **QoS** e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su **Do not use NLA**. Nella finestra **di dialogo Modifica** stringa digitare **1** nella casella **Dati** valore e quindi fare clic su **OK.**

Dopo aver creato e configurato il nuovo valore del Registro di sistema, sarà necessario riavviare il computer per l'applicazione delle modifiche.

## <a name="see-also"></a>Vedere anche

[Creare un oggetto Criteri di gruppo in Windows 10](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
