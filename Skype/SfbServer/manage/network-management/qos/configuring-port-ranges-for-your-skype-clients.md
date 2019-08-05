---
title: Configurazione di intervalli di porte e criteri di qualità dei servizi per i clienti
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Questo articolo descrive come configurare gli intervalli di porte per i clienti e configurare i criteri di qualità dei servizi in Skype for Business Server per i client in Windows 10.
ms.openlocfilehash: 4d7999634864e222dd627ea3b46a3a3da5c67fe5
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "36196066"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configurazione di intervalli di porte e di criteri di qualità dei servizi per i clienti in Skype for Business Server

Questo articolo descrive come configurare gli intervalli di porte per i clienti e configurare i criteri di qualità dei servizi in Skype for Business Server per i client in Windows 10.

## <a name="configure-port-ranges"></a>Configurare gli intervalli di porte

Per impostazione predefinita, le applicazioni client Skype for business possono usare qualsiasi porta tra le porte 1024 e 65535 quando si partecipa a una sessione di comunicazione; il motivo è che gli intervalli di porte specifici non vengono abilitati automaticamente per i client. Per poter usare la qualità del servizio, è tuttavia necessario riassegnare i vari tipi di traffico (audio, video, multimediale, condivisione applicazioni e trasferimento di file) a una serie di intervalli di porte univoci. Questa operazione può essere eseguita usando il cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Gli utenti finali non possono apportare queste modifiche. Le modifiche alle porte possono essere eseguite solo dagli amministratori tramite il cmdlet Set-CsConferencingConfiguration.


Puoi determinare gli intervalli di porte attualmente usati per le sessioni di comunicazione eseguendo il comando seguente dall'interno di Skype for Business Server Management Shell:

    Get-CsConferencingConfiguration

Supponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione di Skype for Business Server, è consigliabile recuperare le informazioni che includono questi valori di proprietà:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se si osserva attentamente l'output precedente, verranno visualizzati due elementi importanti. Prima di tutto, la proprietà ClientMediaPortRangeEnabled è impostata su false:

    ClientMediaPortRangeEnabled : False

Questo è importante perché, quando questa proprietà è impostata su false, i client Skype for Business useranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione; Questo vale indipendentemente da qualsiasi altra impostazione della porta, ad esempio ClientMediaPort o ClientVideoPort. Se si vuole limitare l'utilizzo a un set di porte specificato (e si vuole eseguire questa operazione se si prevede di implementare la qualità del servizio), è necessario prima di tutto abilitare gli intervalli di porta del supporto client. Questa operazione può essere eseguita usando il comando di Windows PowerShell seguente:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Il comando precedente consente di abilitare gli intervalli di porta multimediali del client per la raccolta globale delle impostazioni di configurazione delle conferenze; Queste impostazioni possono tuttavia essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio di conferenza Server). Per abilitare gli intervalli della porta multimediale client per un sito o un server specifico, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

In alternativa, puoi usare questo comando per abilitare simultaneamente gli intervalli di porta per tutte le impostazioni di configurazione della conferenza:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La seconda cosa importante che si noterà è che l'output di esempio mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Per implementare QoS, ognuno di questi intervalli di porte dovrà essere univoco. Ad esempio, è possibile configurare gli intervalli di porte come questo:


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


Nella tabella precedente gli intervalli di porte client rappresentano un sottoinsieme degli intervalli di porte configurati per i server. Ad esempio, nei server la condivisione delle applicazioni è stata configurata per l'uso delle porte da 40803 a 49151; nei computer client la condivisione delle applicazioni è configurata per l'uso delle porte da 42000 a 42019. Anche questa operazione viene eseguita principalmente per semplificare l'amministrazione di QoS: le porte client non devono rappresentare un sottoinsieme delle porte usate nel server. Ad esempio, nei computer client è possibile configurare la condivisione delle applicazioni per usare, per dire, le porte da 10000 a 10019. Tuttavia, è consigliabile rendere gli intervalli della porta del client un sottoinsieme degli intervalli di porte del server.

Inoltre, potresti aver notato che le porte di 8348 sono state accantonate per la condivisione delle applicazioni sui server, ma solo 20 porte sono state accantonate per la condivisione delle applicazioni nei client. È consigliabile anche questo, ma non è una regola difficile e veloce. In generale, è possibile prendere in considerazione ogni porta disponibile per rappresentare una singola sessione di comunicazione: se sono disponibili porte di 100 in un intervallo di porte, significa che il computer in questione può partecipare, al massimo, a 100 sessioni di comunicazione in qualsiasi momento. Poiché i server probabilmente parteciperanno a molte più conversazioni rispetto ai client, è opportuno aprire molte più porte nei server che nei client. L'impostazione di 20 porte per la condivisione delle applicazioni in un client significa che un utente può partecipare a 20 sessioni di condivisione applicazioni nel dispositivo specificato e contemporaneamente. Questo dovrebbe risultare sufficiente per la stragrande maggioranza degli utenti.

Per assegnare gli intervalli di porte precedenti alla raccolta globale di impostazioni di configurazione per i servizi di conferenza, è possibile usare il comando di gestione shell di Skype for Business Server seguente:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

In alternativa, usare questo comando per assegnare gli stessi intervalli di porte per tutte le impostazioni di configurazione per i servizi di conferenza:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

I singoli utenti devono disconnettersi da Skype for business e quindi accedere di nuovo prima che le modifiche abbiano effetto.

> [!NOTE]  
> Puoi anche abilitare gli intervalli di porta multimediali del client e quindi assegnare questi intervalli di porte usando un singolo comando. Ad esempio:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurare i criteri di qualità dei servizi per i client in uso in Windows 10

Oltre a specificare gli intervalli di porte per l'uso da parte dei client Skype for business, devi anche creare criteri di qualità distinti per i servizi che verranno applicati ai computer client. I criteri di qualità dei servizi creati per le conferenze, le applicazioni e i server di mediazione non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono il client Skype for business e Windows 10.

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

Per creare un criterio di qualità dei servizi audio per i computer Windows 10, accedere prima a un computer in cui è stata installata la gestione dei criteri di gruppo. Aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione criteri di gruppo**) e quindi completare la procedura seguente:

1.  In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio. Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata clients, è necessario creare il nuovo criterio nell'unità organizzativa client.

2.  Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.

3.  Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

5.  In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.

6.  Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.

7.  Nella pagina successiva selezionare **solo le applicazioni con il nome eseguibile**, immettere **Lync. exe** come nome e quindi fare clic su **Avanti**. Questa impostazione indica al criterio di assegnare la priorità solo al traffico corrispondente dal client Skype for business.

8.  Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà tali pacchetti.

9.  Nella pagina quattro selezionare **TCP e UDP** dal pulsante **Seleziona il protocollo questo criterio di QoS si applica all'elenco a** discesa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente da Skype for Business Server e dalle sue applicazioni client.

10. Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se hai riservato le porte 50020 tramite le porte 50039 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50020:50039**. Fare clic su **fine**.

Dopo aver creato i criteri QoS per l'audio, è necessario creare un secondo criterio per il video. Per creare un criterio per il video, seguire la stessa procedura di base seguita durante la creazione dei criteri audio, eseguendo queste sostituzioni:

  - Usare un nome di criterio diverso (e univoco).

  - Impostare il valore DSCP su **34** anziché su 46. Come indicato in precedenza, non è necessario usare il valore DSCP 34; devi semplicemente assegnare un valore DSCP diverso rispetto a quello usato per l'audio.

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 58000 a 58019 per il video, impostare l'intervallo di porte su questo: **58000:58019**.

Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, eseguire queste sostituzioni:

  - Usa un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Skype for Business Server**.

  - Impostare il valore DSCP su **24** anziché su 46. (Anche in questo caso, il valore non deve essere 24; è semplicemente diverso dai valori DSCP usati per l'audio e per il video.)

  - Usa l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se si hanno le porte riservate da 42000 a 42019 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42000:42019**.

Per un criterio di trasferimento file:

  - Usare un nome di criterio diverso (e univoco), ad esempio **trasferimenti di file di Skype for Business Server**.

  - Imposta il valore DSCP su **14**. (Anche in questo caso, il valore non deve essere 14, ma è semplicemente un codice DSCP univoco).

  - Usa l'intervallo di porte configurato in precedenza per l'applicazione. Ad esempio, se si hanno le porte riservate da 42020 a 42039 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42020:42039**.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non saranno stati aggiornati nei computer client. Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare i criteri di gruppo:

    Gpupdate.exe /force

Questo comando può essere eseguito da qualsiasi finestra di comando in esecuzione in credenziali di amministratore. Per eseguire una finestra di comando in credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

Tieni presente che questi criteri devono essere mirati verso i computer client. Non devono essere applicati ai server che eseguono Skype for Business Server.

Per assicurarti che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, devi anche creare una nuova voce del registro di sistema in ogni computer completando la procedura seguente:

1.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit**e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**. Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS**e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**. Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA**, quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su non **usare NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

7.  Chiudere l'editor del registro di sistema e eboot il computer.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurare la qualità del servizio nei computer con più schede di rete

Se si dispone di un computer in cui sono presenti più schede di rete, è possibile che venga eseguito occasionalmente un problema in cui i valori DSCP sono visualizzati come 0x00 invece del valore configurato. Ciò si verifica in genere nei computer in cui una o più schede di rete non sono in grado di accedere al dominio Active Directory, ad esempio se questi adapter vengono usati per una rete privata. In casi come questo, i valori DSCP verranno contrassegnati per gli adapter che possono accedere al dominio, ma non verranno contrassegnati per gli adapter che non possono accedere al dominio.

Se si vuole contrassegnare i valori DSCP per tutte le schede di rete in un computer, inclusi gli adapter che non hanno accesso al dominio, è necessario aggiungere e configurare un valore nel registro di sistema. Questa operazione può essere eseguita completando la procedura seguente:

1.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit**e quindi premere INVIO.

3.  Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.

4.  Se non viene visualizzata una chiave del registro di sistema con l'etichetta **QoS** , fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**. Dopo aver creato la nuova chiave, digitare **QoS**e quindi premere INVIO per rinominare la chiave.

5.  Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**. Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA**, quindi premere INVIO per rinominare il valore.

6.  Fare doppio clic su non **usare NLA**. Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.

Dopo aver creato e configurato il nuovo valore del registro di sistema, sarà necessario riavviare il computer per applicare le modifiche.

## <a name="see-also"></a>Vedere anche

[Creare un oggetto Criteri di gruppo in Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
