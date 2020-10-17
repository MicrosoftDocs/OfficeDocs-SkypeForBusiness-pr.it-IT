---
title: "Lync Server 2013: configurare i certificati per l'interfaccia perimetrale esterna"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a190c50ece2b2e5be0f8597851541c71cfbb4e49
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509883"
---
# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Configurare i certificati per l'interfaccia perimetrale esterna per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Quando si esegue la Configurazione guidata certificati, verificare di aver eseguito l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà utilizzato. Per impostazione predefinita, una richiesta di certificato di Lync Server utilizzerà il modello di certificato del server Web. Se per la richiesta di certificato con questo modello si utilizza un account membro del gruppo RTCUniversalServerAdmins, verificare che al gruppo siano assegnate le autorizzazioni di registrazione necessarie per l'utilizzo del modello.



</div>

Per ogni server perimetrale è necessario un certificato pubblico nell'interfaccia tra la rete perimetrale e Internet e il nome alternativo soggetto del certificato deve contenere i nomi esterni dei nomi di dominio completi (FQDN) del servizio Access Edge e del servizio Web Conferencing Edge.

Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Per un elenco delle autorità di certificazione pubbliche che forniscono certificati conformi ai requisiti specifici per i certificati di comunicazione unificata e che hanno collaborato con Microsoft per verificare che funzionino con la configurazione guidata certificati di Lync Server 2013, vedere l'articolo 929395 della Microsoft Knowledge Base "partner di certificati per comunicazioni unificate per Exchange Server e per Communications Server" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Configurazione dei certificati nelle interfacce esterne

Per configurare un certificato sull'interfaccia perimetrale esterna di un sito, utilizzare le procedure in questa sezione per eseguire le operazioni seguenti:

  - Creare la richiesta di certificato per l'interfaccia esterna del server perimetrale.

  - Inviare la richiesta alla CA pubblica.

  - Importare il certificato per l'interfaccia esterna di ogni server perimetrale.

  - Assegnare il certificato per l'interfaccia esterna di ogni server perimetrale.

  - Se la distribuzione include più server perimetrali, esportare il certificato insieme alla relativa chiave privata, quindi copiarlo negli altri server perimetrali. Per ogni server perimetrale, quindi, importarlo e assegnarlo come descritto in precedenza. Ripetere questa procedura per ogni Edge Server.

È possibile richiedere certificati pubblici direttamente a un'autorità di certificazione (CA) pubblica, ad esempio dal sito Web di una CA pubblica. Le procedure in questa sezione utilizzano la Configurazione guidata certificati per la maggior parte delle attività correlate ai certificati. Se si sceglie di richiedere un certificato direttamente a una CA pubblica, sarà necessario modificare ogni procedura nel modo appropriato per richiedere, trasferire e importare il certificato, nonché importare la catena di certificati.

Quando si richiede un certificato a una CA esterna, le credenziali fornite devono disporre dei diritti necessari per richiedere un certificato a tale CA. Per ogni CA esistono criteri di sicurezza che definiscono le credenziali, ovvero i nomi di utenti e gruppi specifici, cui è consentito richiedere, emettere, gestire o leggere certificati.

Se si decide di utilizzare la console MMC (Microsoft Management Console) Certificati per importare la catena di certificati e il certificato, è necessario importarli nell'archivio certificarti per il computer. Se vengono importati nell'archivio certificati utente o del servizio, il certificato non sarà disponibile per l'assegnazione nella procedura guidata per il certificato di Lync Server 2013.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>Per creare la richiesta di certificato per l'interfaccia esterna del server perimetrale

1.  Nel server perimetrale, nella Distribuzione guidata fare clic su **Riesegui** accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile utilizzare la Distribuzione guidata di Lync Server per richiedere il certificato. Eseguire invece i passaggi della procedura "Per creare una richiesta di certificato per l'interfaccia esterna del server perimetrale per il supporto della connettività di messaggistica istantanea pubblica con AOL" più avanti in questo argomento.<BR>Se si dispone di più server perimetrali in un'unica posizione in un pool, è possibile eseguire la configurazione guidata certificati di Lync Server 2013 su uno dei server perimetrali.

    
    </div>

2.  Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.

3.  Nella pagina **Richiesta di certificato** fare clic su **Certificato perimetro esterno**.

4.  Nella pagina **Richieste immediate o ritardate** selezionare la casella di controllo **Prepara la richiesta per l'invio posticipato**.

5.  Nella pagina **file richiesta di certificato** Digitare il percorso completo e il nome del file in cui deve essere salvata la richiesta (ad esempio, c: \\ CERT \_ esterni \_ Edge. cer).

6.  Nella pagina **Specifica modello di certificato alternativo**, per utilizzare un modello diverso dal modello Web Server predefinito selezionare la casella di controllo **Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata**.

7.  Nella pagina **Impostazioni nome e sicurezza** eseguire le operazioni seguenti:
    
      - In **Nome descrittivo** digitare un nome visualizzato per il certificato.
    
      - In **Lunghezza bit** specificare la lunghezza in bit (di solito, l'impostazione predefinita **2048**).
    
      - Verificare che la casella di controllo **Contrassegna come esportabile la chiave di certificato privata** sia selezionata.

8.  Nella pagina **Informazioni sull'organizzazione** digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio una divisione o un reparto.

9.  Nella pagina **Dati geografici** specificare le informazioni sulla posizione.

10. Nella pagina **Nome soggetto / Nomi soggetto alternativi** verranno visualizzate le informazioni compilate automaticamente dalla procedura guidata. Se sono necessari ulteriori nomi alternativi soggetto, specificarli nei prossimi due passaggi.

11. Nella pagina **impostazione dominio SIP su nomi soggetto alternativi (San)** selezionare la casella di controllo Domain per aggiungere un SIP.\<sipdomain\> voce all'elenco dei nomi alternativi del soggetto.

12. Nella pagina **Configura nomi soggetto alternativi aggiuntivi** specificare eventuali ulteriori nomi alternativi soggetto necessari.

13. Nella pagina **Riepilogo richiesta** esaminare le informazioni sul certificato da utilizzare per generare la richiesta.

14. Al termine dell'esecuzione dei comandi, eseguire le operazioni seguenti:
    
      - Per visualizzare il registro per la richiesta del certificato, fare clic su **Visualizza registro**.
    
      - Per completare la richiesta del certificato, fare clic su **Avanti**.

15. Nella pagina **File richiesta di certificato** eseguire le operazioni seguenti:
    
      - Per visualizzare il file di richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.
    
      - Per chiudere la procedura guidata, fare clic su **Fine**.

16. Copiare il file di output in un percorso da cui possa essere inoltrato alla CA pubblica.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Per creare una richiesta di certificato per l'interfaccia esterna del server perimetrale per il supporto della connettività di messaggistica istantanea pubblica con AOL

1.  Quando il modello richiesto è disponibile per la CA, utilizzare il cmdlet di Windows PowerShell seguente dal server perimetrale per richiedere il certificato:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Il nome del certificato predefinito del modello fornito in Lync Server 2013 è il server Web. Specificare solo \<template name\> se è necessario utilizzare un modello diverso dal modello predefinito.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario utilizzare Windows PowerShell anziché la procedura guidata per richiedere il certificato da assegnare al server perimetrale esterno per il servizio Access Edge. Ciò è dovuto al fatto che il modello del server Web Lync Server 2013 utilizzato dalla procedura guidata certificate per richiedere un certificato non supporta la configurazione EKU client. Prima di utilizzare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti l'EKU client.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>Per inviare una richiesta a un'autorità di certificazione pubblica

1.  Aprire il file di output.

2.  Copiare e incollare il contenuto della richiesta di firma del certificato (CSR).

3.  Se richiesto, specificare le impostazioni seguenti:
    
      - **Microsoft** come piattaforma server.
    
      - **IIS** come versione.
    
      - **Server Web** come tipo di utilizzo.
    
      - **PKCS7** come formato della risposta.

4.  Dopo la verifica delle informazioni da parte della CA pubblica, si riceverà un messaggio di posta elettronica contenente il testo richiesto per il certificato.

5.  Copiare il testo dal messaggio di posta elettronica e salvarne il contenuto in un file di testo (con estensione txt) nel computer locale.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>Per importare il certificato per l'interfaccia esterna del server perimetrale

1.  Accedere come membro del gruppo Administrators al server perimetrale in cui è stata creata la richiesta di certificato.

2.  Nella pagina **Distribuisci Edge Server** della Distribuzione guidata fare clic su **Riesegui** accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.

3.  Nella pagina **Attività certificato disponibili** fare clic su **Importa un certificato da un file con estensione p7b, pfx o cer**.

4.  Nella pagina **Importa certificato** fare clic su **Sfoglia** per individuare e selezionare il certificato richiesto per l'interfaccia esterna del server perimetrale, In alternativa, è possibile digitare il percorso completo e il nome di file. Se il certificato contiene una chiave privata, selezionare **Il file di certificato contiene una chiave di certificato privata** e digitare la password per la chiave privata. Fare clic su **Avanti**.

5.  Nella pagina **Riepilogo importazione certificato** verificare le informazioni di riepilogo e quindi fare clic su **Avanti**.

6.  In **Esecuzione comandi in corso** controllare i risultati dell'impostazione, fare clic su **Visualizza registro** per ulteriori informazioni eventualmente necessarie e quindi fare clic su **Fine** per completare l'importazione del certificato.

7.  Se si sta configurando un pool di server perimetrali, esportare il certificato con la relativa chiave privata come descritto nella procedura "Per esportare il certificato con la chiave privata per i server perimetrali in un pool" di seguito in questo argomento. Copiare il file del certificato esportato negli altri server perimetrali e importarlo nell'archivio del computer in ogni server perimetrale.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Per esportare il certificato con la chiave privata per i server perimetrali in un pool

1.  Accedere come membro del gruppo Administrators allo stesso server perimetrale in cui è stato importato il certificato.

2.  Fare clic sul pulsante **Start**, scegliere **Esegui** e quindi digitare **MMC**.

3.  Nella console MMC scegliere **Aggiungi/Rimuovi snap-in** dal menu **File**.

4.  In **Aggiungi o rimuovi snap-in** fare clic su **Certificati** e quindi su **Aggiungi**.

5.  Nella finestra di dialogo **Certificati** selezionare **Account computer**, fare clic su **Avanti**, selezionare **Computer locale (il computer su cui è in esecuzione questa console)** in **Selezione computer**, fare clic su **Fine** e quindi fare clic su **OK** per completare la configurazione della console MMC.

6.  Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi di certificati, fare doppio clic su **Personale** e quindi doppio clic su **Certificati**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'archivio dei certificati personali per il computer locale non contiene alcun certificato, non esiste una chiave privata associata al certificato importato. Controllare la richiesta e i passaggi di importazione. Se il problema persiste, contattare l'amministratore o il provider dell'autorità di certificazione.

    
    </div>

7.  Nell'archivio dei certificati personali per il computer locale**** fare clic con il pulsante destro del mouse sul certificato da esportare, scegliere **Tutte le attività** e quindi fare clic su **Esporta**.

8.  Nell'Esportazione guidata certificati fare clic su **Avanti**, selezionare **Sì, esporta la chiave privata** e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se l'opzione <STRONG>Sì, esporta la chiave privata</STRONG> non è disponibile, la chiave privata associata al certificato non è stata contrassegnata per l'esportazione. Sarà necessario richiedere di nuovo il certificato, assicurandosi che il certificato sia contrassegnato per consentire l'esportazione della chiave privata prima di poter continuare con l'esportazione. Contattare l'amministratore o il provider dell'autorità di certificazione.

    
    </div>

9.  Nella finestra di dialogo formati file di esportazione selezionare **scambio di informazioni personali-PKCS \# 12 (. PFX)** e quindi selezionare le opzioni seguenti:
    
      - Se possibile, includi tutti i certificati nel percorso certificazione
    
      - Esporta tutte le proprietà estese
        
        <div>
        

        > [!WARNING]  
        > Quando si esporta il certificato da un server perimetrale, non selezionare <STRONG>Elimina la chiave privata se l'esportazione ha esito positivo</STRONG>. Se si seleziona questa opzione sarà necessario importare il certificato e la chiave privata in questo server perimetrale.

        
        </div>

10. Fare clic su **Avanti**.

11. Digitare una password per la chiave privata, digitarla di nuovo per confermare e quindi fare clic su **Avanti**.

12. Digitare un percorso e il nome di file per il certificato esportato, utilizzando l'estensione di file pfx. Il percorso deve essere accessibile per tutti i server perimetrali nel pool o essere disponibile per il trasferimento con un supporto rimovibile, come un'unità flash USB. Fare clic su **Avanti**.

13. Controllare le informazioni di riepilogo in **Completamento dell'Esportazione guidata certificati** e quindi fare clic su **Fine**.

14. Nella finestra di dialogo di completamento dell'esportazione fare clic su **OK**.

15. Importare il file del certificato esportato negli altri server perimetrali seguendo i passaggi descritti nella procedura “Per importare il certificato per l'interfaccia esterna del server perimetrale” più indietro in questo argomento.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>Per assegnare il certificato per l'interfaccia esterna del server perimetrale

1.  In ogni server perimetrale, nella Distribuzione guidata fare clic su **Esegui** accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.

2.  Nella pagina **Attività certificato disponibili** fare clic su **Assegna un certificato esistente**.

3.  Nella pagina **Assegnazione certificato** fare clic su **Certificato perimetro esterno** e selezionare la casella di controllo **Utilizzi avanzati certificato**.

4.  Nella pagina **Utilizzi avanzati certificato** selezionare tutte le caselle di controllo per assegnare il certificato a tutti i tipi di utilizzo.

5.  Nella pagina **Archivio certificati** selezionare il certificato pubblico richiesto e importato per l'interfaccia esterna del server perimetrale.
    
    <div>
    

    > [!NOTE]  
    > Se il certificato richiesto e importato non è incluso nell'elenco, uno dei metodi per risolvere il problema consiste nel verificare che il nome soggetto e i nomi alternativi soggetto del certificato soddisfino tutti i requisiti per il certificato. Se il certificato e la catena di certificati sono stati importanti manualmente anziché tramite le procedure precedenti, è necessario verificare che il certificato si trovi nell'archivio corretto, ovvero l'archivio del computer e non quello dell'utente o del servizio.

    
    </div>

6.  Nella pagina **Riepilogo assegnazione certificato** controllare le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.

7.  Nella pagina finale della procedura guidata fare clic su **Fine**.

8.  Dopo aver assegnato il certificato del server perimetrale interno mediante questa procedura, aprire lo snap-in Certificati in ogni server, espandere **Certificati (computer locale)**, espandere **Personale**, fare clic su **Certificati** e quindi verificare che il certificato sia presente nel riquadro dei dettagli.

9.  Se la distribuzione include più server perimetrali, ripetere la procedura per ogni server perimetrale.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

