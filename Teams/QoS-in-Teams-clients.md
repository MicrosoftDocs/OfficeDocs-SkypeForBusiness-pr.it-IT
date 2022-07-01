---
title: Implementare la qualità del servizio (QoS) nei client di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Informazioni su come usare la qualità del servizio (QoS) per ottimizzare il traffico di rete per il client desktop di Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563924"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementare la qualità del servizio (QoS) nei client di Microsoft Teams

È possibile utilizzare la qualità del servizio (QoS) basata su criteri all'interno di Criteri di gruppo per impostare l'intervallo delle porte di origine per il valore DSCP predefinito nel client teams. Gli intervalli di porte specificati nella tabella seguente sono un punto di partenza per creare un criterio per ogni carico di lavoro.

*Tabella 1. Intervalli di porte iniziali consigliati*

|Tipo di traffico multimediale| Intervallo di porte di origine client  |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Condivisione di applicazioni/schermi| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | | |

Ove possibile, configurare le impostazioni QoS basate su criteri all'interno di un oggetto Criteri di gruppo. I passaggi seguenti sono molto simili alla [configurazione degli intervalli di porte e ai criteri di qualità del servizio per i client in Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), che potrebbero non essere necessari.

Per creare un criterio audio QoS per i computer Windows 10 aggiunti a un dominio, accedere prima di tutto a un computer in cui è stato installato gestione Criteri di gruppo. Aprire gestione Criteri di gruppo (fare clic sul pulsante Start, scegliere Strumenti di amministrazione, quindi fare clic su Gestione Criteri di gruppo) e quindi completare la procedura seguente:

1. In gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata **Client**, il nuovo criterio deve essere creato nell'unità organizzativa Client.

1. Fare clic con il pulsante destro del mouse sul contenitore appropriato, quindi scegliere **Crea un oggetto Criteri di gruppo in questo dominio e collegarlo qui**.

1. Nella finestra di dialogo **Nuovo oggetto Criteri** di gruppo digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **Nome** e quindi fare clic su **OK**.

1. Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica**.

1. Nel Criteri di gruppo Management Editor espandere **Configurazione computer**, **Impostazioni di Windows**, fare clic con il pulsante destro del mouse **su QoS basato su** criteri e quindi scegliere **Crea nuovo criterio**.

1. Nella pagina di apertura della finestra di dialogo **QoS basata sui** criteri digitare un nome per il nuovo criterio nella casella **Nome** . Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare deselezionata **l'opzione Specifica velocità di limitazione in uscita** e quindi fare clic su **Avanti**.

1. Nella pagina successiva selezionare **Solo le applicazioni con questo nome eseguibile** , immettere il nome **Teams.exe**, quindi fare clic su **Avanti**. Questa impostazione indica al criterio di assegnare priorità solo al traffico corrispondente proveniente dal client di Teams.

1. Nella terza pagina verificare che siano selezionati Tutti gli **indirizzi IP di origine** e **Tutti gli indirizzi IP di destinazione** e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) che ha inviato i pacchetti e dal computer (indirizzo IP) che riceverà i pacchetti.

1. Nella quarta pagina selezionare **TCP e UDP** nell'elenco a discesa **Selezionare il protocollo applicato a questo criterio QoS** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente usati.

1. Sotto l'intestazione **Specificare il numero della porta di origine** selezionare **Da questa porta o intervallo di origine**. Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se si riservano le porte da 50000 a 50019 per il traffico audio, immettere l'intervallo di porte con questo formato: **50000:50019**. Fare clic su **Fine**.

1. Ripetere i passaggi da 5 a 10 per creare criteri per la condivisione di applicazioni e video/desktop, sostituendo i valori appropriati nei passaggi 6 e 10.

I nuovi criteri creati verranno applicati solo dopo l'aggiornamento di Criteri di gruppo nei computer client. Anche se Criteri di gruppo aggiorna periodicamente, è possibile forzare un aggiornamento immediato eseguendo questa procedura:

1. In ogni computer per cui si vuole aggiornare Criteri di gruppo aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).

1. Al prompt dei comandi immetti

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verificare i contrassegni DSCP nell'oggetto Criteri di gruppo

Per verificare che siano stati impostati i valori dell'oggetto Criteri di gruppo, procedere come segue:

1. Aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).

1. Al prompt dei comandi immetti

   ```console
   gpresult /R > gp.txt
   ```

   Verrà generato un report di oggetti Criteri di gruppo applicati e inviato a un file di testo denominato *gp.txt*.

   Per un report HTML più leggibile denominato *gp.html*, immettere il comando seguente:

   ```console
   gpresult /H gp.html
   ```

1. Nel file generato cercare l'intestazione **Applicato Criteri di gruppo Oggetti** e verificare che i nomi dei Criteri di gruppo oggetti creati in precedenza siano inclusi nell'elenco dei criteri applicati.

1. Apri l'editor del Registro di sistema e vai a

   Criteri software HKEY\_LOCAL\_MACHINE\\Microsoft\\Windows\\QoS\\\\

   Verificare i valori per le voci del Registro di sistema elencate nella tabella 2.

   *Tabella 2. Valori per le voci del Registro di sistema di Windows per QoS*

   |          Nome          |  Tipo  |    Dati     |
   |         :---:          | :---:  |    :---:    |
   |    Nome applicazione    | REG_SZ |  Teams.exe  |
   |       Valore DSCP       | REG_SZ |     46      |
   |        IP locale        | REG_SZ |     \*      |
   | Lunghezza prefisso IP locale | REG_SZ |     \*      |
   |       Porta locale       | REG_SZ | 50000-50019 |
   |        Protocol        | REG_SZ |     \*      |
   |       IP remoto        | REG_SZ |     \*      |
   |    Prefisso IP remoto    | REG_SZ |     \*      |
   |      Porta remota       | REG_SZ |     \*      |
   |     Velocità di limitazione      | REG_SZ |     -1      |
   | | | |

1. Verificare che il valore della voce Nome applicazione sia corretto per il client in uso e verificare che le voci Valore DSCP e Porta locale riflettano le impostazioni nell'oggetto Criteri di gruppo.


## <a name="related-topics"></a>Argomenti correlati

[Implementare la qualità del servizio (QoS) in Teams](QoS-in-Teams.md)