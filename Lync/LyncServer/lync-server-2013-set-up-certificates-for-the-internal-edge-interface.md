---
title: "Lync Server 2013: impostare i certificati per l'interfaccia perimetrale interna"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f8c5c41eba828cb6514ba6963167d708ed203d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509893"
---
# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Configurare i certificati per l'interfaccia perimetrale interna in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

<div>


> [!IMPORTANT]  
> Quando si esegue la Configurazione guidata certificati, verificare di aver eseguito l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà utilizzato. Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web. Se per la richiesta di un certificato con questo modello si utilizza un account membro del gruppo RTCUniversalServerAdmins, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'utilizzo del modello.



</div>

Per l'interfaccia interna di ogni server perimetrale è necessario un unico certificato. I certificati per l'interfaccia interna possono essere emessi da un'Autorità di certificazione (CA) globale (enterprise) interna o da una CA pubblica. Se nell'organizzazione è distribuita una CA interna, è possibile emettere il certificato per l'interfaccia interna utilizzando la CA interna, evitando la spesa legata all'utilizzo di certificati pubblici. Per la creazione dei certificati è possibile utilizzare una CA interna Windows Server 2008 o Windows Server 2008 R2.

Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Per impostare i certificati per l'interfaccia perimetrale interna presso un sito, le procedure descritte in questa sezione consentono di eseguire le attività seguenti:

1.  Scaricare la catena di certificazione CA per l'interfaccia interna in ogni server perimetrale.

2.  Importare la catena di certificazione CA per l'interfaccia interna in ogni server perimetrale.

3.  Creare la richiesta di certificato per l'interfaccia interna in un unico server perimetrale, denominato primo server perimetrale.

4.  Importare il certificato per l'interfaccia interna nel primo server perimetrale.

5.  Importare il certificato negli altri server perimetrali presenti nel sito o distribuiti e controllati dal servizio di bilanciamento del carico.

6.  Assegnare il certificato per l'interfaccia interna di ogni server perimetrale.

Se sono presenti più siti con server perimetrali, ovvero se è disponibile una topologia perimetrale con più siti, oppure insiemi distinti di server perimetrali distribuiti e controllati da servizi di bilanciamento del carico diversi, è necessario completare questi passaggi separatamente per ogni sito in cui sono presenti server perimetrali e per ogni insieme di server perimetrali distribuito e controllato da un servizio di bilanciamento del carico diverso.

<div>


> [!NOTE]  
> I passaggi per le procedure descritte in questa sezione si basano sull'utilizzo di un &nbsp; certificato di Windows server 2008 CA, di Windows server &nbsp; 2008 &nbsp; R2 CA, di Windows Server 2012 CA o di Windows Server 2012 R2 per la creazione di certificati per ogni server perimetrale. Per istruzioni dettagliate per altre CA, consultare la documentazione della CA specifica. Per impostazione predefinita, tutti gli utenti autenticati dispongono dei diritti appropriati per richiedere certificati.<BR>Per le procedure descritte in questa sezione, si presuppone che la creazione delle richieste di certificati nel server perimetrale avvenga nel corso del processo di distribuzione del server perimetrale stesso. È possibile creare richieste di certificati utilizzando il Front End Server per completare la richiesta del certificato in una fase iniziale del processo di pianificazione e distribuzione, prima di cominciare la distribuzione dei server perimetrali. A tale scopo, è necessario che il certificato richiesto sia definito con una chiave privata esportabile.<BR>Nelle procedure di questa sezione è descritto l'utilizzo di un file con estensione cer e con estensione p7b come certificato. Se si utilizza un tipo di file diverso, modificare le procedure di conseguenza.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>Per scaricare la catena di certificazione CA per l'interfaccia interna tramite il sito Web certsrv

1.  Accedere a un server Lync Server 2013 nella rete interna, ovvero non nel server perimetrale, come membro del gruppo **Administrators** .

2.  Eseguire il comando che segue. A tale scopo, fare clic sul pulsante **Start**, scegliere **Esegui** e quindi al prompt dei comandi digitare quanto segue:
    
        https://<name of your Issuing CA Server>/certsrv
    
    Ad esempio:
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Se si utilizza una CA globale (enterprise) Windows Server 2008 o Windows Server 2008 R2, è necessario digitare https anziché http.

    
    </div>

3.  Nella pagina Web certsrv della CA emittente, in **Selezionare un'attività**, fare clic su **Scarica un certificato CA, la catena di certificati o un CRL**.

4.  In **Scarica un certificato CA, la catena di certificati o un CRL** fare clic su **Esegui download catena di certificati CA**.

5.  Nella finestra di dialogo **Download del file** fare clic su **Salva**.

6.  Salvare il file con estensione p7b nell'unità disco rigido del server e quindi copiarlo in una cartella di ogni server perimetrale.
    
    <div>
    

    > [!NOTE]  
    > Il file con estensione p7b contiene tutti i certificati inclusi nel percorso di certificazione. Per visualizzare il percorso di certificazione, aprire il certificato server e fare clic sul percorso di certificazione.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>Per esportare la catena di certificazione CA per l'interfaccia interna tramite MMC

1.  È possibile esportare il certificato radice della CA da qualsiasi computer aggiunto a un dominio utilizzando Microsoft Management Console (MMC). A tale scopo, fare clic sul pulsante **Start**, scegliere **Esegui** e quindi digitare **MMC**.

2.  Nella console MMC fare clic su **File** e quindi su **Aggiungi/Rimuovi**.

3.  Nell'elenco della finestra di dialogo **Aggiungi o rimuovi snap-in** selezionare **Certificati** e quindi fare clic su **Aggiungi**. Quando richiesto, selezionare **Account del computer**. Nella finestra di dialogo **Selezione computer** selezionare **Computer locale**. Fare clic su **Fine**. Fare clic su **OK**.

4.  Espandere **Certificati (computer locale)**. Espandere **Autorità di certificazione radice attendibili** e selezionare **Certificati**.

5.  Fare clic sul certificato radice emesso dalla CA. Fare clic con il pulsante destro del mouse sul certificato, scegliere **Tutte le attività** e quindi **Esporta**. Verrà aperta l'**Esportazione guidata certificati**.

6.  Nell'**Esportazione guidata certificati** fare clic su **Avanti**.

7.  Nella finestra di dialogo **Formato file di esportazione** selezionare un formato per l'esportazione. È consigliabile utilizzare la **sintassi del messaggio crittografico standard – i \# certificati PKCS 7 (. P7B)**. Se si seleziona la **sintassi del messaggio crittografico standard – PKCS \# 7 Certificates (. P7B)**, selezionare la casella di controllo **Includi tutti i certificati nel percorso di certificazione, se possibile** , per esportare la catena di certificati, incluso il certificato della CA radice e tutti i certificati di CA intermedi. Fare clic su **Avanti**.

8.  Nella finestra di dialogo **File da esportare** digitare nell'apposito campo un percorso e un nome file (l'estensione predefinita è p7b) per il certificato esportato. Facoltativamente fare clic su **Sfoglia**, individuare una directory in cui inserire il certificato esportato e specificare un nome per tale certificato. Fare clic su **Salva**. Fare clic su **Avanti**.

9.  Esaminare il riepilogo delle azioni e fare clic su **Fine** per completare l'esportazione del certificato. Fare clic su **OK** per confermare l'avvenuta esecuzione dell'esportazione.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>Per importare la catena di certificazione della CA per l'interfaccia interna

1.  In ogni server perimetrale fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **mmc** nella casella **Apri** e quindi fare clic su **OK** per aprire Microsoft Management Console (MMC).

2.  Scegliere **Aggiungi/Rimuovi snap-in** dal menu **File** e quindi fare clic su **Aggiungi**.

3.  Nella casella **Aggiungi snap-in autonomo** fare clic su **Certificati** e quindi su **Aggiungi**.

4.  Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.

5.  Nella finestra di dialogo **Seleziona computer** assicurarsi che la casella di controllo **Computer locale (il computer su cui è in esecuzione questa console)** sia selezionata e quindi fare clic su **Fine**.

6.  Fare clic su **Chiudi** e quindi su **OK**.

7.  Nell'albero della console espandere **Certificati (computer locale)**, fare clic con il pulsante destro del mouse su **Autorità di certificazione radice disponibile nell'elenco locale**, scegliere **Tutte le attività** e quindi **Importa**.

8.  In **File da importare** all'interno della procedura guidata specificare il nome del file del certificato, ovvero il nome specificato al momento del download della catena di certificazione CA per l'interfaccia interna nella procedura precedente.

9.  Ripetere questa procedura in ogni server perimetrale.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>Per creare la richiesta di certificato per l'interfaccia interna

1.  In uno dei server perimetrali avviare la Distribuzione guidata e accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** fare clic su **Esegui**.
    
    <div>
    

    > [!NOTE]  
    > Se in una stessa posizione sono presenti più server perimetrali in pool, è possibile eseguire la Configurazione guidata certificati in uno qualsiasi del server perimetrali.<BR>Dopo la prima esecuzione del passaggio 3, il pulsante viene modificato in <STRONG>Riesegui</STRONG>. Il segno di spunta di colore verde che indica il completamento dell'attività viene visualizzato solo dopo la richiesta, l'installazione e l'assegnazione di tutti i certificati.

    
    </div>

2.  Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.

3.  Nella pagina **Richiesta di certificato** fare clic su **Avanti**.

4.  Nella pagina **Richieste immediate o ritardate** fare clic su **Prepara la richiesta per l'invio posticipato**.

5.  Nella pagina **file richiesta di certificato** Digitare il percorso completo e il nome del file in cui si desidera salvare la richiesta, ad esempio **c: \\ CERT \_ Internal \_ Edge. cer**.

6.  Nella pagina **Specifica modello di certificato alternativo** per utilizzare un modello diverso dal modello WebServer predefinito selezionare la casella di controllo **Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata**.

7.  Nella pagina **Impostazioni nome e sicurezza** eseguire le operazioni seguenti:
    
      - In **Nome descrittivo** digitare il nome da visualizzare per il certificato, ad esempio Server perimetrale interno.
    
      - In **Lunghezza bit** specificare la lunghezza in bit (di solito, l'impostazione predefinita **2048**).
        
        <div>
        

        > [!NOTE]  
        > Una lunghezza in bit più alta offre maggiore sicurezza, ma influisce negativamente sulla velocità.

        
        </div>
    
      - Se è necessario che il certificato sia esportabile, selezionare la casella di controllo **Contrassegna come esportabile la chiave di certificato privata**.

8.  Nella pagina **Informazioni sull'organizzazione** digitare il nome per l'organizzazione e l'unità organizzativa, ad esempio una divisione o un reparto.

9.  Nella pagina **Dati geografici** specificare le informazioni sulla posizione.

10. Nella pagina **Nome soggetto / Nomi soggetto alternativi** sono visualizzate le informazioni che verranno inserite automaticamente mediante la procedura guidata.

11. Nella pagina **Configura nomi soggetto alternativi aggiuntivi** specificare eventuali nomi soggetto alternativi aggiuntivi richiesti.

12. Nella pagina **Riepilogo richiesta** rivedere le informazioni relative al certificato che verranno utilizzate per la generazione della richiesta.

13. Dopo il completamento dell'esecuzione dei comandi eseguire le operazioni seguenti:
    
      - Per visualizzare il registro della richiesta di certificato, fare clic su **Visualizza registro**.
    
      - Per completare la richiesta del certificato, fare clic su **Avanti**.

14. Nella pagina **File richiesta di certificato** eseguire le operazioni seguenti:
    
      - Per visualizzare il file di richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.
    
      - Per chiudere la procedura guidata, fare clic su **Fine**.

15. Inviare il file alla CA, tramite posta elettronica o un altro metodo supportato dall'organizzazione per la CA globale (enterprise). Alla ricezione del file di risposta copiare il nuovo certificato nel computer in modo che sia disponibile per l'importazione.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>Per importare il certificato per l'interfaccia interna

1.  Accedere al server perimetrale in cui è stata creata la richiesta di certificato con un account membro del gruppo Administrators locale.

2.  Nella Distribuzione guidata, accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**, fare clic su **Riesegui**.
    
    Dopo la prima esecuzione del passaggio 3, il pulsante viene modificato in **Riesegui**. Il segno di spunta di colore verde che indica il completamento dell'attività viene visualizzato solo dopo la richiesta l'installazione e l'assegnazione di tutti i certificati.

3.  Nella pagina **Attività certificato disponibili** fare clic su **Importa un certificato da un file con estensione P7b, pfx o cer**.

4.  Nella pagina **Importa certificato** digitare il percorso completo e il nome del file del certificato richiesto e ricevuto per il server perimetrale. In alternativa, fare clic su **Sfoglia** per individuare e selezionare il file.

5.  Se si desidera importare certificati per altri membri del pool e un certificato contiene una chiave privata, selezionare la casella di controllo **Il file di certificato contiene una chiave di certificato privata** e specificare la password.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Per esportare il certificato con la chiave privata per i server perimetrali in un pool

1.  Accedere come membro del gruppo Administrators allo stesso server perimetrale in cui è stato importato il certificato.

2.  Fare clic sul pulsante **Start**, scegliere **Esegui** e digitare **MMC**.

3.  Nella console MMC scegliere **Aggiungi/Rimuovi snap-in** dal menu **File**.

4.  Nella pagina Aggiungi/Rimuovi snap-in fare clic su **Certificati** e su **Aggiungi**.

5.  Nella finestra di dialogo dello snap-in Certificati selezionare **Account del computer**. Fare clic su **Avanti**. In Seleziona computer selezionare **Computer locale (il computer in cui viene eseguita questa console)**. Fare clic su **Fine**. Fare clic su **OK** per completare la configurazione della console MMC console.

6.  Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi certificati. Fare doppio clic su **Personale** e quindi su **Certificati**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se nell'archivio personale dei certificati non sono presenti certificati per il computer locale, al certificato importato non è associata alcuna chiave privata. Rivedere i passaggi della richiesta e dell'impostazione. Se il problema persiste, rivolgersi all'amministratore o al provider dell'autorità di certificazione.

    
    </div>

7.  Nell'archivio personale dei certificati per il computer locale fare clic con il pulsante destro del mouse sul certificato che si desidera esportare. Scegliere **Tutte le attività** e quindi fare clic su **Esporta**.

8.  Nell'Esportazione guidata certificati fare clic su **Avanti**. Selezionare **Sì, esporta la chiave privata**. Fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se l'opzione <STRONG>Sì, esporta la chiave privata</STRONG> non è disponibile, la chiave privata associata al certificato non è stata contrassegnata per l'esportazione. Per continuare l'esportazione, è necessario ripetere la richiesta di certificato, verificando che il certificato stesso sia contrassegnato per l'esportazione della chiave privata. Rivolgersi all'amministratore o al provider dell'autorità di certificazione.

    
    </div>

9.  Nella finestra di dialogo formati file di esportazione selezionare **scambio di informazioni personali-PKCS \# 12 (. PFX)** e quindi selezionare le opzioni seguenti:
    
      - Se possibile, includi tutti i certificati nel percorso certificazione
    
      - Esporta tutte le proprietà estese
        
        <div>
        

        > [!WARNING]  
        > Quando si esporta un certificato da un server perimetrale, non selezionare <STRONG>Elimina la chiave privata se l'esportazione ha esito positivo</STRONG>. In caso contrario, è necessario importare nel server perimetrale il certificato e la chiave privata.

        
        </div>
    
    Fare clic su **Avanti** per continuare.

10. Se si desidera assegnare una password per proteggere la chiave privata, digitare una password per la chiave privata. Reimmettere la password per conferma. Fare clic su **Avanti**.

11. Digitare un percorso e un nome di file per il certificato esportato Assegnare al file l'estensione pfx. Il percorso deve essere accessibile per tutti gli altri server perimetrali del pool o disponibile per il trasporto mediante supporto rimovibile, ad esempio un'unità flash USB. Fare clic su **Avanti**.

12. Esaminare il riepilogo nella finestra di dialogo Completamento dell'Esportazione guidata certificati. Fare clic su **Fine**.

13. Fare clic su **OK** nella finestra di dialogo di conclusione dell'esportazione.

14. Importare il file del certificato esportato negli altri server perimetrali seguendo i passaggi descritti nella procedura di [configurazione dei certificati per l'interfaccia perimetrale esterna per le procedure di Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>Per assegnare il certificato interno nei server perimetrali

1.  In ogni server perimetrale, nella Distribuzione guidata, accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**, fare clic su **Riesegui**.

2.  Nella pagina **Attività certificato disponibili** fare clic su **Assegna un certificato esistente**.

3.  Nella pagina **Assegnazione certificato** selezionare **Edge Server interno** nell'elenco.

4.  Nella pagina **Archivio certificati** selezionare il certificato importato con la procedura precedente per il server perimetrale.

5.  Nella pagina **Riepilogo assegnazione certificato** rivedere le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.

6.  Nella pagina finale della procedura guidata fare clic su **Fine**.

7.  Dopo aver assegnato il certificato del server perimetrale interno mediante questa procedura, aprire lo snap-in Certificati in ogni server, espandere **Certificati (computer locale)**, espandere **Personale**, fare clic su **Certificati** e quindi verificare che il certificato del server perimetrale interno sia presente nel riquadro dei dettagli.

8.  Se la distribuzione include più server perimetrali, ripetere la procedura per ognuno di essi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

