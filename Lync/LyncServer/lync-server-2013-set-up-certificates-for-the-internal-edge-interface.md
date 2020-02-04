---
title: "Lync Server 2013: Impostare i certificati per l'interfaccia perimetrale interna"
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
ms.openlocfilehash: ea6e462bdc629308493799c857ecb6b2434dc268
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Impostare i certificati per l'interfaccia perimetrale interna in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

<div>


> [!IMPORTANT]  
> Quando si esegue la creazione guidata certificato, verificare di avere effettuato l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà usato. Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web. Se si usa un account che è un membro del gruppo RTCUniversalServerAdmins per richiedere un certificato con questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'uso di tale modello.



</div>

È necessario un singolo certificato nell'interfaccia interna di ogni server perimetrale. I certificati per l'interfaccia interna possono essere emessi da un'autorità di certificazione (CA) aziendale interna o da una CA pubblica. Se l'organizzazione ha una CA interna distribuita, è possibile salvarla a spese dell'uso di certificati pubblici usando la CA interna per emettere il certificato per l'interfaccia interna. Per creare questi certificati, è possibile usare una CA interna di Windows Server 2008 o una CA Windows Server 2008 R2.

Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Per configurare i certificati sull'interfaccia Edge interna di un sito, usare le procedure descritte in questa sezione per eseguire le operazioni seguenti:

1.  Scaricare la catena di certificazione CA per l'interfaccia interna di ogni server perimetrale.

2.  Importare la catena di certificazione CA per l'interfaccia interna in ogni server perimetrale.

3.  Creare la richiesta di certificato per l'interfaccia interna, in un server perimetrale, denominata First Edge Server.

4.  Importare il certificato per l'interfaccia interna nel primo server perimetrale.

5.  Importare il certificato sugli altri server perimetrali di questo sito (o distribuiti dietro questo bilanciamento del carico).

6.  Assegnare il certificato per l'interfaccia interna di ogni server perimetrale.

Se si hanno più siti con Edge Server, ossia una topologia a più siti, o Set distinti di server perimetrali distribuiti con diversi tipi di bilanciamento del carico, è necessario seguire questi passaggi per ogni sito con Edge Server e per ogni set di Edge Server distribuiti dietro un diverso bilanciamento del carico.

<div>


> [!NOTE]  
> La procedura per le procedure in questa sezione si basa sull'uso di una&nbsp;CA di windows Server 2008&nbsp;,&nbsp;di una CA, di Windows Server 2008 R2, di Windows Server 2012 CA o di Windows Server 2012 R2 per creare un certificato per ogni server perimetrale. Per istruzioni dettagliate per qualsiasi altra autorità di certificazione, consultare la documentazione relativa a tale CA. Per impostazione predefinita, tutti gli utenti autenticati dispongono dei diritti utente appropriati per richiedere certificati.<BR>Le procedure descritte in questa sezione si basano sulla creazione di richieste di certificato nell'Edge Server come parte del processo di distribuzione di Edge Server. È possibile creare richieste di certificato con il server front-end. Puoi eseguire questa operazione per completare la richiesta di certificato all'inizio del processo di pianificazione e distribuzione, prima di iniziare la distribuzione degli Edge Server. A questo scopo, devi assicurarti che il certificato richiesto sia definito con una chiave privata esportabile.<BR>Le procedure descritte in questa sezione descrivono l'uso di un file con estensione CER e p7b per il certificato. Se si usa un tipo di file diverso, modificare le procedure in base alle esigenze.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>Per scaricare la catena di certificazione CA per l'interfaccia interna tramite il sito Web di certsrv

1.  Accedere a un server Lync Server 2013 nella rete interna, ovvero non nel server perimetrale, come membro del gruppo **Administrators** .

2.  Eseguire il comando seguente al prompt dei comandi facendo clic sul pulsante **Start**, scegliendo **Esegui**e digitando quanto segue:
    
        https://<name of your Issuing CA Server>/certsrv
    
    Ad esempio:
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Se si usa una CA di Windows Server 2008 o Windows Server 2008 R2 Enterprise, è necessario usare HTTPS e non http.

    
    </div>

3.  Nella pagina Web certsrv della CA emittente, in **selezionare un'attività**, fare clic su **Scarica un certificato CA, una catena di certificati o un CRL**.

4.  In **scaricare un certificato CA, una catena di certificati o un CRL**fare clic su **Scarica catena di certificati CA**.

5.  Nella finestra di dialogo **Download file** fare clic su **Salva**.

6.  Salvare il file con estensione p7b nell'unità disco rigido del server e quindi copiarlo in una cartella in ogni server perimetrale.
    
    <div>
    

    > [!NOTE]  
    > Il file con estensione p7b contiene tutti i certificati presenti nel percorso di certificazione. Per visualizzare il percorso di certificazione, aprire il certificato del server e fare clic sul percorso di certificazione.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>Per esportare la catena di certificazione CA per l'interfaccia interna tramite MMC

1.  È possibile esportare il certificato radice della CA da qualsiasi computer unito a un dominio usando Microsoft Management Console (MMC). Fare clic sul pulsante **Start**, scegliere **Esegui**e quindi digitare **MMC**.

2.  Nella console MMC fare clic su **file**, quindi su **Aggiungi/Rimuovi**.

3.  Nell'elenco **Aggiungi o Rimuovi snap-** in selezionare **certificati**, quindi fare clic su **Aggiungi**. Quando richiesto, selezionare **account computer**. Nella finestra di dialogo **Seleziona computer** selezionare **computer locale**. Fare clic su **fine**. Fare clic su **OK**.

4.  Espandere **certificati (computer locale)**. Espandere **autorità di certificazione radice attendibili**, selezionare **certificati**.

5.  Fare clic sul certificato radice emesso dalla CA. Fare clic con il pulsante destro del mouse sul certificato, selezionare **tutte le attività**, quindi **Esporta**. Verrà aperta l' **esportazione guidata certificati** .

6.  Nell' **esportazione guidata certificati**fare clic su **Avanti**.

7.  Nella finestra di dialogo **Esporta formato file** selezionare un formato da esportare. È consigliabile la **sintassi del messaggio crittografico standard: \#i certificati PKCS 7 (. P7B)**. Se si seleziona la **sintassi del messaggio crittografico standard, \#ovvero i certificati PKCS 7 (. P7B)** selezionare la casella di controllo **Includi tutti i certificati nel percorso di certificazione, se possibile** , per esportare la catena di certificati, incluso il certificato della CA radice e gli eventuali certificati intermedi della CA. Fare clic su **Avanti**.

8.  Nella finestra **di dialogo file da esportare** nella voce nome file digitare un percorso e un nome file (l'estensione predefinita è p7b) per il certificato esportato. Facoltativamente, fare clic su **Sfoglia**, individuare una directory in cui inserire il certificato esportato e specificare un nome per il certificato esportato. Fai clic su **Salva**. Fare clic su **Avanti**.

9.  Esaminare il riepilogo delle azioni e fare clic su **fine** per completare l'esportazione del certificato. Fare clic su **OK** per confermare l'esportazione riuscita.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>Per importare la catena di certificazione CA per l'interfaccia interna

1.  In ogni server perimetrale aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella **Apri** e quindi facendo clic su **OK**.

2.  Nel menu **file** fare clic su **Aggiungi/Rimuovi snap-in**e quindi fare clic su **Aggiungi**.

3.  Nella casella **Add standalone snap-** in fare clic su **certificati**e quindi fare clic su **Aggiungi**.

4.  Nella finestra di dialogo di **snap-in certificato** fare clic su **account computer**e quindi su **Avanti**.

5.  Nella finestra di dialogo **Seleziona computer** verificare che la casella di controllo computer **locale: (il computer in cui è in uso questa console)** sia selezionata e quindi fare clic su **fine**.

6.  Fare clic su **Chiudi**e quindi su **OK**.

7.  Nell'albero della console espandere **certificati (computer locale)**, fare clic con il pulsante destro del mouse su **autorità di certificazione radice attendibili**, scegliere **tutte le attività**e quindi fare clic su **Importa**.

8.  Nella procedura guidata, in **file da importare**, specificare il nome del file del certificato, ovvero il nome specificato quando è stata scaricata la catena di certificazione CA per l'interfaccia interna nella procedura precedente.

9.  Ripetere questa procedura in ogni server perimetrale.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>Per creare la richiesta di certificato per l'interfaccia interna

1.  In uno dei server perimetrali avviare la distribuzione guidata e, accanto al **passaggio 3: richiedere, installare o assegnare certificati**, fare clic su **Esegui**.
    
    <div>
    

    > [!NOTE]  
    > Se si hanno più Edge Server in una posizione in un pool, è possibile eseguire la procedura guidata certificato in uno dei server perimetrali.<BR>Dopo aver eseguito il passaggio 3 la prima volta, il pulsante viene modificato di <STRONG>nuovo in esecuzione</STRONG>e un segno di spunta verde che indica che il completamento dell'attività non viene visualizzato finché tutti i certificati di richiesta non sono stati richiesti, installati e assegnati.

    
    </div>

2.  Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.

3.  Nella pagina **richiesta certificato** fare clic su **Avanti**.

4.  Nella pagina **richieste immediate o posticipate** fare clic su **prepara la richiesta ora, ma inviarla**in un secondo momento.

5.  Nella pagina **file di richiesta certificato** Digitare il percorso completo e il nome del file a cui deve essere salvata la richiesta, ad esempio **c:\\CERT\_Internal\_Edge. cer**.

6.  Nella pagina **Specifica modello di certificato alternativo** , per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa il modello di certificato alternativo per l'autorità di certificazione selezionata** .

7.  Nella pagina **impostazioni di sicurezza e nome** eseguire le operazioni seguenti:
    
      - In **nome descrittivo**Digitare un nome visualizzato per il certificato, ad esempio bordo interno.
    
      - In **bit length**specificare la lunghezza in bit (in genere, il valore predefinito è **2048**).
        
        <div>
        

        > [!NOTE]  
        > Le lunghezze di bit più alte offrono maggiore sicurezza, ma hanno un impatto negativo sulla velocità.

        
        </div>
    
      - Se il certificato deve essere esportabile, selezionare la casella di controllo **contrassegna la chiave privata del certificato come esportabile** .

8.  Nella pagina **informazioni organizzazione** Digitare il nome dell'organizzazione e dell'unità organizzativa (ad esempio, divisione o reparto).

9.  Nella pagina **informazioni geografiche** specificare le informazioni sulla posizione.

10. Nella pagina **nome oggetto/nomi oggetto alternativo** vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata.

11. Nella pagina **Configura altri nomi alternativi oggetto** specificare eventuali altri nomi alternativi per gli argomenti necessari.

12. Nella pagina **Riepilogo richieste** verificare le informazioni sul certificato che verranno usate per generare la richiesta.

13. Dopo aver completato i comandi, eseguire le operazioni seguenti:
    
      - Per visualizzare il log per la richiesta di certificato, fare clic su **Visualizza log**.
    
      - Per completare la richiesta di certificato, fare clic su **Avanti**.

14. Nella pagina **file di richiesta certificato** eseguire le operazioni seguenti:
    
      - Per visualizzare il file della richiesta di firma del certificato (CSR) generato, fare clic su **Visualizza**.
    
      - Per chiudere la procedura guidata, fare clic su **fine**.

15. Inviare il file alla CA (tramite posta elettronica o altro metodo supportato dall'organizzazione per la CA aziendale) e, quando si riceve il file di risposta, copiare il nuovo certificato nel computer in modo che sia disponibile per l'importazione.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>Per importare il certificato per l'interfaccia interna

1.  Accedere all'Edge Server in cui è stata creata la richiesta di certificato come membro del gruppo Administrators locale.

2.  Nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.
    
    Dopo aver eseguito il passaggio 3 la prima volta, il pulsante viene modificato di **nuovo in esecuzione**, ma un segno di spunta verde (che indica il completamento dell'attività) non viene visualizzato finché non sono stati richiesti, installati e assegnati tutti i certificati.

3.  Nella pagina **attività certificato disponibili** fare clic su **Importa un certificato da a. File di P7b, pfx o CER**.

4.  Nella pagina **Importa certificato** Digitare il percorso completo e il nome file del certificato richiesto e ricevuto per l'interfaccia interna di questo Edge Server (oppure fare clic su **Sfoglia** per individuare e selezionare il file).

5.  Se si importano certificati per altri membri del pool un certificato contenente una chiave privata, selezionare il **file di certificato contiene la casella di controllo chiave privata di certificato** e specificare la password.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Per esportare il certificato con la chiave privata per Edge Server in un pool

1.  Accedere come membro del gruppo Administrators allo stesso Edge Server in cui è stato importato il certificato.

2.  Fare clic sul pulsante **Start**, scegliere **Esegui**e digitare **MMC**.

3.  Nella console MMC fare clic su **file**, fare clic su **Aggiungi/Rimuovi snap-in**.

4.  Nella pagina Aggiungi o Rimuovi snap-in fare clic su **certificati**, fare clic su **Aggiungi**.

5.  Nella finestra di dialogo snap-in certificati selezionare **account computer**. Fare clic su **Avanti**. In Seleziona computer selezionare **computer locale: (il computer in cui è in uso la console)**. Fare clic su **fine**. Fare clic su **OK** per completare la configurazione della console MMC.

6.  Fare doppio clic su **certificati (computer locale)** per espandere gli archivi di certificati. Fare doppio clic su **personale**, quindi fare doppio clic su **certificati**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se non ci sono certificati nell'archivio personale certificati per il computer locale, non esiste alcuna chiave privata associata al certificato importato. Esaminare la procedura di richiesta e importazione. Se il problema persiste, contattare l'amministratore o il provider dell'autorità di certificazione.

    
    </div>

7.  Nell'archivio personale certificati per il computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando. Fare clic su **tutte le attività**, fare clic su **Esporta**.

8.  Nell'esportazione guidata certificati fare clic su **Avanti**. Selezionare **Sì, esportare la chiave privata**. Fare clic su **Avanti**.
    
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
    
    Fare clic su **Avanti** per continuare.

10. Se si vuole assegnare una password per proteggere la chiave privata, digitare una password per la chiave privata. Immettere di nuovo la password per confermare. Fare clic su **Avanti**.

11. Digitare un percorso e un nome di file per il certificato esportato, usando un'estensione di file PFX. Il percorso deve essere accessibile a tutti gli altri Edge Server nel pool o disponibile per il trasporto tramite supporti rimovibili, ad esempio un'unità flash USB. Fare clic su **Avanti**.

12. Esaminare il riepilogo nella finestra di dialogo completamento dell'esportazione guidata certificati. Fare clic su **fine**.

13. Fare clic su **OK** nella finestra di dialogo Esporta riuscita.

14. Importare il file di certificato esportato negli altri Edge Server seguendo la procedura descritta in [configurare i certificati per l'interfaccia esterna di Edge per le procedure di Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>Per assegnare il certificato interno agli Edge Server

1.  In ogni server perimetrale, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di **nuovo**clic su Esegui.

2.  Nella pagina **attività certificato disponibili** fare clic su **assegna un certificato esistente**.

3.  Nella pagina **assegnazione certificato** selezionare **bordo interno** nell'elenco.

4.  Nella pagina **archivio certificati** selezionare il certificato importato per il bordo interno (nella procedura precedente).

5.  Nella pagina **Riepilogo assegnazione certificati** verificare le impostazioni e quindi fare clic su **Avanti** per assegnare i certificati.

6.  Nella pagina Completamento procedura guidata fare clic su **fine**.

7.  Dopo aver usato questa procedura per assegnare il certificato del bordo interno, aprire lo snap-in certificato in ogni server, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati**e quindi verificare nel riquadro dei dettagli l'elenco del certificato perimetrale interno.

8.  Se la distribuzione include più Edge Server, ripetere questa procedura per ogni server perimetrale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

