---
title: "Lync Server 2013: Impostare i certificati per l'interfaccia perimetrale esterna"
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
ms.openlocfilehash: c1c836191c19eeadd915d0263c89b52289f60fe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Impostare i certificati per l'interfaccia perimetrale esterna per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Quando si esegue la creazione guidata certificato, verificare di avere effettuato l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà usato. Per impostazione predefinita, una richiesta di certificato di Lync Server utilizzerà il modello di certificato server Web. Se si usa un account che è un membro del gruppo RTCUniversalServerAdmins per richiedere un certificato con questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'uso di tale modello.



</div>

Ogni Edge Server richiede un certificato pubblico nell'interfaccia tra la rete perimetrale e Internet e il nome dell'oggetto alternativo del certificato deve contenere i nomi esterni del servizio Access Edge e del servizio Web Conferencing Edge completamente nomi di dominio completi (FQDN).

Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Per un elenco delle autorità di certificazione pubbliche che includono certificati che soddisfano i requisiti specifici per i certificati di comunicazioni unificate e che hanno collaborato con Microsoft per verificare che funzionino con la procedura guidata certificati di Lync Server 2013, vedere l'articolo 929395 della Microsoft Knowledge Base "partner certificati per le comunicazioni unificate per Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)e per Communications Server".

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Configurazione dei certificati sulle interfacce esterne

Per configurare un certificato nell'interfaccia esterna di Edge in un sito, usare le procedure descritte in questa sezione per eseguire le operazioni seguenti:

  - Creare la richiesta di certificato per l'interfaccia esterna del server perimetrale.

  - Inviare la richiesta alla CA pubblica.

  - Importare il certificato per l'interfaccia esterna di ogni server perimetrale.

  - Assegnare il certificato per l'interfaccia esterna di ogni server perimetrale.

  - Se la distribuzione include più Edge Server, esportare il certificato insieme alla relativa chiave privata e quindi copiarlo negli altri Edge Server. Quindi, per ogni Edge Server, importalo e assegnalo come descritto in precedenza. Ripetere questa procedura per ogni server perimetrale.

È possibile richiedere certificati pubblici direttamente da un'autorità di certificazione (CA) pubblica, ad esempio dal sito Web di una CA pubblica. Le procedure descritte in questa sezione usano la creazione guidata certificato per la maggior parte delle attività di certificato. Se si è scelto di richiedere un certificato direttamente da una CA pubblica, sarà necessario modificare ogni procedura in modo appropriato per richiedere, trasportare e importare il certificato e anche per importare la catena di certificati.

Quando si richiede un certificato da una CA esterna, le credenziali fornite devono avere diritti per richiedere un certificato da tale autorità di certificazione. Ogni autorità di certificazione ha un criterio di sicurezza che definisce le credenziali, ovvero i nomi di utenti e gruppi specifici, che possono richiedere, emettere, gestire o leggere i certificati.

Se si decide di usare i certificati Microsoft Management Console (MMC) per importare la catena di certificati e il certificato, è necessario importarli nell'archivio certificati per il computer. Se vengono importati nell'archivio certificati dell'utente o del servizio, il certificato non sarà disponibile per l'assegnazione nella procedura guidata certificato di Lync Server 2013.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>Per creare la richiesta di certificato per l'interfaccia esterna del server perimetrale

1.  Nel server perimetro, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile usare la distribuzione guidata di Lync Server per richiedere il certificato. Eseguire invece la procedura descritta nella sezione "per creare una richiesta di certificato per l'interfaccia esterna dell'Edge Server per supportare la connettività di messaggistica istantanea pubblica con AOL" più avanti in questo argomento.<BR>Se si hanno più Edge Server in una posizione in un pool, è possibile eseguire la configurazione guidata certificati di Lync Server 2013 in uno dei server perimetrali.

    
    </div>

2.  Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.

3.  Nella pagina **richiesta certificato** fare clic su **certificato bordo esterno**.

4.  Nella pagina **richiesta posticipata o immediata** selezionare la casella di controllo **prepara la richiesta ora, ma inviarla in seguito** .

5.  Nella pagina **file di richiesta certificato** Digitare il percorso completo e il nome file del file in cui deve essere salvata la richiesta, ad esempio c:\\CERT\_exernal\_Edge. cer.

6.  Nella pagina **Specifica modello di certificato alternativo** , per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa il modello di certificato alternativo per l'autorità di certificazione selezionata** .

7.  Nella pagina **impostazioni di sicurezza e nome** eseguire le operazioni seguenti:
    
      - In **nome descrittivo**Digitare un nome visualizzato per il certificato.
    
      - In **bit length**specificare la lunghezza in bit (in genere, il valore predefinito è **2048**).
    
      - Verificare che la casella **di controllo contrassegna la chiave privata del certificato come esportabile** sia selezionata.

8.  Nella pagina **informazioni organizzazione** Digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio divisione o reparto.

9.  Nella pagina **informazioni geografiche** specificare le informazioni sulla posizione.

10. Nella pagina **nome oggetto/nomi oggetto alternativo** vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata. Se sono necessari altri nomi alternativi per l'oggetto, è necessario specificarli nei due passaggi successivi.

11. Nell' **impostazione del dominio SIP nella pagina nome alternativo oggetto (sans)** selezionare la casella di controllo Domain per aggiungere un SIP. \<SipDomain\> voce nell'elenco nomi alternativi oggetto.

12. Nella pagina **Configura altri nomi alternativi oggetto** specificare eventuali altri nomi alternativi per gli argomenti necessari.

13. Nella pagina **Riepilogo richieste** verificare le informazioni sul certificato da usare per generare la richiesta.

14. Dopo aver completato i comandi, eseguire le operazioni seguenti:
    
      - Per visualizzare il log per la richiesta di certificato, fare clic su **Visualizza log**.
    
      - Per completare la richiesta di certificato, fare clic su **Avanti**.

15. Nella pagina **file di richiesta certificato** eseguire le operazioni seguenti:
    
      - Per visualizzare il file della richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.
    
      - Per chiudere la procedura guidata, fare clic su **fine**.

16. Copiare il file di output in un percorso in cui è possibile inviarlo alla CA pubblica.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Per creare una richiesta di certificato per l'interfaccia esterna di Edge Server per supportare la connettività di messaggistica istantanea pubblica con AOL

1.  Quando il modello richiesto è disponibile per la CA, usare il cmdlet di Windows PowerShell seguente da su Edge Server per richiedere il certificato:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Il nome del certificato predefinito del modello fornito in Lync Server 2013 è Web Server. Specifica il nome \<\> del modello solo se devi usare un modello diverso dal modello predefinito.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario usare Windows PowerShell invece della procedura guidata certificato per richiedere che il certificato venga assegnato al bordo esterno per il servizio Access Edge. Questo perché il modello di server Web Lync Server 2013 usato dalla creazione guidata certificato per richiedere un certificato non supporta la configurazione EKU client. Prima di usare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti EKU client.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>Per inviare una richiesta a un'autorità di certificazione pubblica

1.  Aprire il file di output.

2.  Copiare e incollare il contenuto della richiesta di firma del certificato (CSR).

3.  Se richiesto, specificare quanto segue:
    
      - **Microsoft** come piattaforma server.
    
      - **IIS** come versione.
    
      - **Server Web** come tipo di utilizzo.
    
      - **PKCS7** come formato di risposta.

4.  Quando la CA pubblica ha verificato le proprie informazioni, viene visualizzato un messaggio di posta elettronica contenente il testo necessario per il certificato.

5.  Copiare il testo dal messaggio di posta elettronica e salvare il contenuto in un file di testo (txt) nel computer locale.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>Per importare il certificato per l'interfaccia esterna del server perimetrale

1.  Accedere come membro del gruppo Administrators allo stesso Edge Server in cui è stata creata la richiesta di certificato.

2.  Nella distribuzione guidata, nella pagina **Deploy Edge Server** , accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.

3.  Nella pagina **attività certificato disponibili** fare clic su **Importa un certificato da un file con estensione p7b, pfx o CER**.

4.  Nella pagina **Importa certificato** fare clic su **Sfoglia** per individuare e selezionare il certificato richiesto per l'interfaccia esterna del server perimetrale oppure digitare il percorso completo e il nome del file. Se il certificato contiene una chiave privata, selezionare il **file di certificato contiene la chiave privata del certificato** e digitare la password per la chiave privata. Fare clic su **Avanti**.

5.  Nella pagina di **Riepilogo importa certificato** esaminare il riepilogo e quindi fare clic su **Avanti**.

6.  Per **eseguire i comandi**, esaminare i risultati dell'importazione, fare clic su **Visualizza log** per altre informazioni in base alle esigenze e quindi fare clic su **fine** per completare l'importazione del certificato.

7.  Se si sta configurando un pool di Edge Server, esportare il certificato con la relativa chiave privata come indicato nella procedura "per esportare il certificato con la chiave privata per i server perimetrali in un pool" più avanti in questo argomento. Copiare il file di certificato esportato negli altri Edge Server e importarlo nell'archivio del computer in ogni server perimetrale.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Per esportare il certificato con la chiave privata per Edge Server in un pool

1.  Accedere come membro del gruppo Administrators allo stesso Edge Server in cui è stato importato il certificato.

2.  Fare clic sul pulsante **Start**, scegliere **Esegui**e digitare **MMC**.

3.  Nella console Microsoft Management Console (MMC) fare clic su **file**e quindi su **Aggiungi/Rimuovi snap-in**.

4.  In **Aggiungi o Rimuovi snap-** in fare clic su **certificati**e quindi su **Aggiungi**.

5.  Nella finestra di dialogo **certificati** selezionare **account computer**, fare clic **su Avanti**, selezionare **computer locale: (il computer in cui è in esecuzione la console)** in **selezionare il computer**, fare clic su **fine** e quindi su **OK** per completare la configurazione della console MMC.

6.  Fare doppio clic su **certificati (computer locale)** per espandere gli archivi di certificati, fare doppio clic su **personale**e quindi fare doppio clic su **certificati**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se non ci sono certificati nell'archivio personale certificati per il computer locale, non esiste alcuna chiave privata associata al certificato importato. Esaminare la procedura di richiesta e importazione. Se il problema persiste, contattare l'amministratore o il provider dell'autorità di certificazione.

    
    </div>

7.  Nell' **archivio personale certificati per il computer locale**fare clic con il pulsante destro del mouse sul certificato che si sta esportando, scegliere **tutte le attività**e quindi fare clic su **Esporta**.

8.  Nell'esportazione guidata certificati fare clic su **Avanti**, selezionare **Sì, esportare la chiave privata**e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se la selezione <STRONG>Sì, Esporta la chiave privata</STRONG> non è disponibile, la chiave privata associata al certificato non è stata contrassegnata per l'esportazione. Sarà necessario richiedere di nuovo il certificato, assicurandosi che il certificato sia contrassegnato per consentire l'esportazione della chiave privata prima di poter continuare con l'esportazione. Contattare l'amministratore o il provider dell'autorità di certificazione.

    
    </div>

9.  Nella finestra di dialogo Esporta formati di file selezionare **Personal Information Exchange-\#PKCS 12 (. PFX)** e quindi selezionare le opzioni seguenti:
    
      - Includere tutti i certificati nel percorso di certificazione, se possibile
    
      - Esportare tutte le proprietà estese
        
        <div>
        

        > [!WARNING]  
        > Quando si esporta il certificato da un server perimetrale, non selezionare <STRONG>Elimina la chiave privata se l'esportazione ha esito positivo</STRONG>. Se si seleziona questa opzione, è necessario importare il certificato e la chiave privata in questo server perimetrale.

        
        </div>

10. Fare clic su **Avanti**.

11. Digitare una password per la chiave privata, digitare di nuovo la password per confermare e quindi fare clic su **Avanti**.

12. Digitare un percorso e un nome di file per il certificato esportato, usando un'estensione di file PFX. Il percorso deve essere accessibile a tutti gli altri Edge Server nel pool o disponibile per il trasporto tramite supporti rimovibili, ad esempio un'unità flash USB. Fare clic su **Avanti**.

13. Esaminare il riepilogo in **completamento dell'esportazione guidata certificati**e quindi fare clic su **fine**.

14. Nella finestra di dialogo Esporta completata fare clic su **OK**.

15. Importare il file di certificato esportato negli altri Edge Server seguendo i passaggi descritti nella procedura "per importare il certificato per l'interfaccia esterna del server perimetrale" più indietro in questo argomento.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>Per assegnare il certificato per l'interfaccia esterna del server perimetrale

1.  In ogni server perimetrale, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di **nuovo**clic su Esegui.

2.  Nella pagina **attività certificato disponibili** fare clic su **assegna un certificato esistente**.

3.  Nella pagina **assegnazione certificato** fare clic su **Certificato perimetro esterno** e selezionare la casella di controllo **usi avanzati dei certificati** .

4.  Nella pagina **usi avanzati certificati** selezionare tutte le caselle di controllo per assegnare il certificato per tutti gli usi.

5.  Nella pagina **archivio certificati** selezionare il certificato pubblico richiesto e importato per l'interfaccia esterna del server perimetrale.
    
    <div>
    

    > [!NOTE]  
    > Se il certificato richiesto e importato non è presente nell'elenco, uno dei metodi per la ripresa dei problemi consiste nel verificare che il nome dell'oggetto e i nomi alternativi oggetto del certificato soddisfino tutti i requisiti per il certificato e, se è stato importato manualmente il certificato e catena di certificati invece di usare le procedure descritte in precedenza, il certificato si trova nell'archivio certificati corretto, ovvero nell'archivio certificati del computer, non nell'archivio certificati dell'utente o del servizio.

    
    </div>

6.  Nella pagina **Riepilogo assegnazione certificati** verificare le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.

7.  Nella pagina Completamento procedura guidata fare clic su **fine**.

8.  Dopo aver usato questa procedura per assegnare il certificato Edge, aprire lo snap-in certificato in ogni server, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati**e quindi verificare nel riquadro dei dettagli che il certificato è elencato.

9.  Se la distribuzione include più Edge Server, ripetere questa procedura per ogni server perimetrale.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

