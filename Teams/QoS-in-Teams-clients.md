---
title: Implementare la qualità del servizio nei client di Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implementare la qualità del servizio (QoS) per i client di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3447f86be825099b7fada63fecd1b106f94cd80a
ms.sourcegitcommit: 2b76e6a9a6ba0eb391e4adba5402eb572d1dc61f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/18/2019
ms.locfileid: "40303868"
---
# <a name="set-qos-on-windows-clients"></a>Configurare QoS nei client di Windows

È possibile usare il QoS basato su criteri all'interno di criteri di gruppo per impostare l'intervallo della porta di origine per il valore DSCP predefinito nel client teams. Gli intervalli di porte specificati nella tabella seguente sono un punto di partenza per creare un criterio per ogni carico di lavoro.

*Tabella 1. Intervalli di porte iniziali consigliati*

|Tipo di traffico multimediale| Intervallo di porte di origine client |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50000-50019|TCP/UDP|46|Inoltro accelerato (EF)|
|Video| 50020-50039|TCP/UDP|34|Inoltro assicurato (AF41)|
|Condivisione di applicazioni/schermi| 50040-50059|TCP/UDP|18|Inoltro assicurato (AF21)|
| | | | | |

Laddove possibile, configurare le impostazioni QoS basate su criteri all'interno di un oggetto Criteri di gruppo. I passaggi seguenti sono molto simili a [configurare gli intervalli di porte e i criteri di qualità dei servizi per i clienti in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), che contiene alcuni dettagli aggiuntivi che potrebbero non essere necessari.

Per creare criteri audio QoS per i computer Windows 10 aggiunti al dominio, accedere prima a un computer in cui è stata installata la gestione dei criteri di gruppo. Aprire Gestione criteri di gruppo (fare clic sul pulsante Start, scegliere Strumenti di amministrazione e quindi Gestione criteri di gruppo) e quindi completare i passaggi seguenti:

1. In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio. Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata **clients**, è necessario creare il nuovo criterio nell'unità organizzativa client.

1. Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.

1. Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** e quindi fare clic su **OK**.

1. Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.

1. In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.

1. Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio nella casella **nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.

1. Nella pagina successiva selezionare **solo le applicazioni con il nome del file eseguibile** e immettere il nome **Teams. exe**e quindi fare clic su **Avanti**. Questa impostazione indica al criterio di assegnare priorità solo al traffico corrispondente dal client teams.

1. Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà i pacchetti.

1. Nella pagina quattro selezionare **TCP e UDP** dall'elenco **a discesa selezionare il protocollo questo criterio QoS** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente.

1. Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se hai riservato le porte 50000 tramite le porte 50019 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50000:50019**. Fare clic su **fine**.

1. Ripetere i passaggi 5-10 per creare criteri per la condivisione di video e applicazioni/desktop, sostituendo i valori appropriati nei passaggi 6 e 10.

I nuovi criteri creati non avranno effetto finché i criteri di gruppo non vengono aggiornati nei computer client. Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo la procedura seguente:

1. In ogni computer per cui si vogliono aggiornare i criteri di gruppo aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).

1. Alla riga di comando, immettere

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verificare le marcature DSCP nell'oggetto Criteri di gruppo

Per verificare che i valori dell'oggetto Criteri di gruppo siano stati impostati, eseguire la procedura seguente:

1. Aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).

1. Alla riga di comando, immettere

   ```console
   gpresult /R > gp.txt
   ```

   Questo genererà un report degli oggetti Criteri di stato applicati e lo invierà a un file di testo denominato *GP. txt*.

   Per un report HTML più leggibile denominato *GP. html*, immettere il comando seguente:

   ```console
   gpresult /H gp.html
   ```

1. Nel file generato cercare gli **oggetti Criteri di gruppo applicati** all'intestazione e verificare che i nomi degli oggetti Criteri di gruppo creati in precedenza si trovino nell'elenco dei criteri applicati.

1. Aprire l'editor del registro di sistema e andare a

   Criteri\_\\di\_Microsoft\\\\Windows\\\\QoS di HKEY local machine software

   Verificare i valori delle voci del registro di sistema elencate nella tabella 2.

   *Tabella 2. Valori per le voci del registro di sistema di Windows per QoS*

   |          Nome          |  Tipo  |    Dati     |
   |         :---:          | :---:  |    :---:    |
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
   | | | |

1. Verificare che il valore per la voce nome applicazione sia corretto per il client in uso e verificare che sia il valore DSCP che le voci della porta locale riflettano le impostazioni nell'oggetto Criteri di gruppo.
