---
title: Implementare la qualità del servizio (QoS) nei Microsoft Teams client
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Informazioni su come usare la qualità del servizio (QoS) per ottimizzare il traffico di rete per Microsoft Teams client desktop.
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
ms.openlocfilehash: c283a66db274bc8723d429631bf265fdb0f5206b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606015"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementare la qualità del servizio (QoS) nei Microsoft Teams client

È possibile usare la qualità del servizio (QoS) basata su criteri all'interno di Criteri di gruppo per impostare l'intervallo di porte di origine per il valore DSCP predefinito nel client Teams client. Gli intervalli di porta specificati nella tabella seguente sono un punto di partenza per creare un criterio per ogni carico di lavoro.

*Tabella 1. Intervalli di porta iniziali consigliati*

|Tipo di traffico multimediale| Intervallo di porte di origine client  |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Condivisione di applicazioni/schermi| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | | |

Se possibile, configurare le impostazioni QoS basate su criteri all'interno di un oggetto Criteri di gruppo. La procedura seguente è molto simile alla configurazione degli intervalli di porte e ai criteri di qualità del servizio per i client in [Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), che include alcuni dettagli aggiuntivi che potrebbero non essere necessari.

Per creare criteri audio QoS per i computer Windows 10 di dominio, accedere prima di tutto a un computer in cui è installato Gestione Criteri di gruppo. Aprire Gestione Criteri di gruppo (fare clic sul pulsante Start, scegliere Strumenti di amministrazione e quindi fare clic su Gestione Criteri di gruppo) e quindi completare la procedura seguente:

1. In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata **Client,** il nuovo criterio deve essere creato nell'unità organizzativa Client.

1. Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere Crea un oggetto Criteri di gruppo in questo dominio **e collegarlo qui.**

1. Nella finestra **di dialogo** Nuovo oggetto Criteri di gruppo digitare  un nome per il nuovo oggetto Criteri di gruppo nella casella Nome e quindi fare clic su **OK.**

1. Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica**.

1. Nell'Editor Gestione Criteri di gruppo espandere **Configurazione computer**, espandere **Windows Impostazioni**, fare clic con il pulsante destro del mouse su **QoS** basata su criteri e quindi scegliere **Crea nuovo criterio**.

1. Nella pagina di apertura della finestra di dialogo **QoS** basata su criteri digitare un nome per il nuovo criterio nella **casella** Nome. Selezionare **Specifica valore DSCP** e impostare il valore su **46.** Lasciare **deselezionata l'opzione Specifica** velocità in uscita e quindi fare clic su **Avanti.**

1. Nella pagina successiva selezionare **Solo** le applicazioni con questo nome eseguibile **e** immettere il nomeTeams.exee quindi fare clic su **Avanti.** Questa impostazione indica ai criteri di assegnare la priorità solo al traffico corrispondente dal client Teams client.

1. Nella terza pagina verificare che siano selezionate le opzioni Qualsiasi indirizzo **IP** di origine e Qualsiasi indirizzo **IP** di destinazione e quindi fare clic su **Avanti.** Queste due impostazioni assicurano che i pacchetti siano gestiti indipendentemente dal computer (indirizzo IP) che ha inviato i pacchetti e dal computer (indirizzo IP) che riceverà i pacchetti.

1. Nella pagina quattro selezionare **TCP e UDP** nell'elenco a discesa Selezionare il protocollo a cui si applica il criterio **QoS.** TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente usati.

1. Sotto **l'intestazione Specificare il numero di porta di origine** selezionare Da questa porta o intervallo di **origine.** Nella casella di testo accanto digitare l'intervallo di porte riservato alle trasmissioni audio. Ad esempio, se le porte da 50000 a 50019 sono riservate per il traffico audio, immettere l'intervallo di porte nel formato **50000:50019.** Fare clic **su Fine.**

1. Ripetere i passaggi da 5 a 10 per creare criteri per Condivisione video e applicazioni/desktop, sostituendo i valori appropriati nei passaggi 6 e 10.

I nuovi criteri creati non saranno applicati fino a quando i Criteri di gruppo non saranno stati aggiornati nei computer client. Anche se i Criteri di gruppo vengono aggiornati periodicamente da soli, è possibile forzare un aggiornamento immediato seguendo questa procedura:

1. In ogni computer per cui si desidera aggiornare Criteri di gruppo aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).

1. Al prompt dei comandi immettere

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verificare i contrassegni DSCP nell'oggetto Criteri di gruppo

Per verificare che i valori dell'oggetto Criteri di gruppo siano stati impostati, eseguire la procedura seguente:

1. Aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).

1. Al prompt dei comandi immettere

   ```console
   gpresult /R > gp.txt
   ```

   Verrà generato un report degli oggetti Criteri di gruppo applicati e verrà inviato a un file di testo denominato *gp.txt*.

   Per un report HTML più leggibile denominato *gp.html*, immettere il comando seguente:

   ```console
   gpresult /H gp.html
   ```

1. Nel file generato cercare l'intestazione Oggetti Criteri di gruppo applicati e verificare che i nomi degli oggetti Criteri di gruppo creati in precedenza siano presenti nell'elenco dei criteri applicati. 

1. Aprire l'editor del Registro di sistema e passare a

   HKEY \_ LOCAL MACHINE Software Policies Microsoft Windows \_ \\ \\ \\ \\ \\ QoS

   Verificare i valori per le voci del Registro di sistema elencate nella tabella 2.

   *Tabella 2. Valori per le Windows del Registro di sistema per QoS*

   |          Nome          |  Tipo  |    Dati     |
   |         :---:          | :---:  |    :---:    |
   |    Nome applicazione    | REG_SZ |  Teams.exe  |
   |       Valore DSCP       | REG_SZ |     46      |
   |        IP locale        | REG_SZ |     \*      |
   | Lunghezza prefisso IP locale | REG_SZ |     \*      |
   |       Porta locale       | REG_SZ | 50000-50019 |
   |        Protocollo        | REG_SZ |     \*      |
   |       IP remoto        | REG_SZ |     \*      |
   |    Prefisso IP remoto    | REG_SZ |     \*      |
   |      Porta remota       | REG_SZ |     \*      |
   |     Velocità      | REG_SZ |     -1      |
   | | | |

1. Verificare che il valore della voce Nome applicazione sia corretto per il client in uso e verificare che le voci Valore DSCP e Porta locale riflettano le impostazioni nell'oggetto Criteri di gruppo.


## <a name="related-topics"></a>Argomenti correlati

[Implementare la qualità del servizio (QoS) in Teams](QoS-in-Teams.md)