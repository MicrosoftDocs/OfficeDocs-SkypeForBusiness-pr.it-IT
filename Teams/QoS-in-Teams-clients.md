---
title: Implementare la qualità del servizio nei client di Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Implementare la qualità del servizio (QoS) per i client di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 101deb10cf3d86dbc97116cad269556683d03be4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180443"
---
# <a name="set-qos-on-windows-clients"></a>Impostare QoS nei client Windows

È possibile usare il QoS basato su criteri all'interno di criteri di gruppo per impostare l'intervallo della porta di origine per il valore DSCP predefinito nel client teams. Gli intervalli di porte specificati nella tabella seguente sono un punto di partenza per creare un criterio per ogni carico di lavoro.

_Intervalli di porte iniziali consigliati_

Tipo di traffico multimediale| Intervallo di porte di origine client |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50000-50019|TCP/UDP|46|Inoltro accelerato (EF)|
|Video| 50020-50039|TCP/UDP|34|Inoltro assicurato (AF41)|
|Condivisione di applicazioni/schermi| 50040-50059|TCP/UDP|18|Inoltro assicurato (AF21)|
| | | | |

Laddove possibile, configurare le impostazioni QoS basate su criteri all'interno di un oggetto Criteri di gruppo. I passaggi seguenti sono molto simili a [configurare gli intervalli di porte e i criteri di qualità dei servizi per i clienti in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), che contiene alcuni dettagli aggiuntivi che potrebbero non essere necessari.

Per creare criteri audio QoS per i computer Windows 10 aggiunti al dominio, accedere prima a un computer in cui è stata installata la gestione dei criteri di gruppo. Aprire Gestione criteri di gruppo (fare clic sul pulsante Start, scegliere Strumenti di amministrazione e quindi Gestione criteri di gruppo) e quindi completare i passaggi seguenti:

1. In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio. Ad esempio, se tutti i computer client si trovano in un'unità organizzativa **** denominata clients, è necessario creare il nuovo criterio nell'unità organizzativa client.

2. Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.

3. Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** e quindi fare clic su **OK**.

4. Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

5. In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.

6. Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.

7. Nella pagina successiva selezionare **solo le applicazioni con il nome del file eseguibile** e immettere il nome **Teams. exe**e quindi fare clic su **Avanti**. Questa impostazione indica al criterio di assegnare priorità solo al traffico corrispondente dal client teams.

8. Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà i pacchetti.

9. Nella pagina quattro selezionare **TCP e UDP** dall'elenco **a discesa selezionare il protocollo questo criterio QoS** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente.

10. Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se hai riservato le porte 50000 tramite le porte 50019 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50000:50019**. Fare clic su **fine**.

11. Ripetere i passaggi 5-10 per creare criteri per la condivisione di video e applicazioni/desktop, sostituendo i valori appropriati nei passaggi 6 e 10.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non vengono aggiornati nei computer client. Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo la procedura seguente:

1. In ogni computer per cui si vogliono aggiornare i criteri di gruppo aprire una console dei comandi. Verificare che la console dei comandi sia impostata per l'esecuzione come amministratore.

2. Alla riga di comando, immettere

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verificare le marcature DSCP nell'oggetto Criteri di gruppo

Per verificare che i valori dell'oggetto Criteri di gruppo siano stati impostati, eseguire la procedura seguente.

1. Aprire una console di comando. Verificare che la console dei comandi sia impostata per l'esecuzione come amministratore.

2. Alla riga di comando, digitare:

   ``` powershell
   gpresult /R > gp.txt
   ```

   Questo genererà un report e lo invierà in un file di testo denominato GP. txt. In alternativa, è possibile immettere il comando seguente per produrre gli stessi dati in un report HTML più leggibile denominato GP. html:

   ``` powershell
   gpresult /H >gp.html
   ```

   ![Screenshot della finestra della console in cui è in uso il comando gpresult.] (media/Qos-in-Teams-Image3.png "Screenshot della finestra della console in cui è in uso il comando gpresult.")

3. Nel file generato cercare gli **oggetti Criteri di gruppo applicati** all'intestazione e verificare che i nomi degli oggetti Criteri di gruppo creati in precedenza si trovino nell'elenco dei criteri applicati.

4. Aprire l'editor del registro di sistema e andare a:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Verificare i valori delle voci del registro di sistema elencate nella tabella 4.

   _Tabella 4. Valori per le voci del registro di sistema di Windows per QoS_

   |          Nome          |  Tipo  |    Dati     |
   |         :---:          |:---:   |    :---:    |
   |    Nome applicazione    | REG_SZ |  Teams. exe  |
   |       Valore DSCP       | REG_SZ |     46      |
   |        IP locale        | REG_SZ |     \*      |
   | Lunghezza prefisso IP locale | REG_SZ |     \*      |
   |       Porta locale       | REG_SZ | 50000-50019 |
   |        Protocollo        | REG_SZ |     \*      |
   |       IP remoto        | REG_SZ |     \*      |
   |    Prefisso IP remoto    | REG_SZ |     \*      |
   |      Porta remota       | REG_SZ |     \*      |
   |     Tasso di accelerazione      | REG_SZ |     -1      |

5. Verificare che il valore per la voce nome applicazione sia corretto per il client in uso e verificare che sia il valore DSCP che le voci della porta locale riflettano le impostazioni nell'oggetto Criteri di gruppo.
