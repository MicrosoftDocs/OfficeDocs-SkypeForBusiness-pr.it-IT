---
title: 'Lync Server 2013: configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-26_

Se è stata distribuita la messaggistica unificata di Exchange, come descritto in [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione e si desidera specificare le caratteristiche di messaggistica unificata di Exchange per gli utenti di VoIP aziendale nell'organizzazione, è possibile usare le procedure seguenti per configurare il certificato nel server che usa la messaggistica unificata di Exchange.

<div>


> [!IMPORTANT]  
> Per i certificati interni, sia i server che esegue Lync Server 2013 che i server che esegue Microsoft Exchange devono avere certificati di autorità radice attendibili che sono mutuamente attendibili. L'autorità di certificazione (CA) può essere uguale o un'autorità di certificazione diversa, purché i server dispongano del certificato radice dell'autorità di certificazione registrato nell'archivio certificati dell'autorità radice attendibile.



</div>

Il server Exchange deve essere configurato con un certificato server per la connessione a Lync Server 2013:

1.  Scaricare il certificato CA per il server Exchange.

2.  Installare il certificato CA per il server Exchange.

3.  Verificare che la CA si trovi nell'elenco delle autorità di certificazione radice attendibili del server Exchange.

4.  Creare una richiesta di certificato per il server Exchange e installare il certificato.

5.  Assegnare il certificato per il server Exchange.

<div>

## <a name="to-download-the-ca-certificate"></a>Per scaricare il certificato CA

1.  Nel server che esegue la messaggistica unificata di Exchange fare clic sul pulsante **Start**, scegliere **esegui**, digitare **http://\<nome\>del server della CA emittente/certsrv**e quindi fare clic su **OK**.

2.  In **selezionare un'attività**fare clic su **Scarica un certificato CA, una catena di certificati o un CRL**.

3.  In **scaricare un certificato CA, una catena di certificati o un CRL**selezionare **metodo di codifica per base 64**e quindi fare clic su **Scarica certificato CA**.
    
    <div>
    

    > [!NOTE]  
    > È anche possibile specificare la codifica DER (Distinguished Encoding Rules) in questo passaggio. Se si seleziona la codifica DER, il tipo di file nel passaggio successivo di questa procedura e nel passaggio 10 di <STRONG>per installare il certificato della CA</STRONG> è. p7b anziché. cer.

    
    </div>

4.  Nella finestra di dialogo **Download file** fare clic su **Salva**e quindi salvare il file nel disco rigido nel server. In base alla codifica selezionata nel passaggio precedente, il file includerà un file con estensione cer o. p7b.

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Per installare il certificato CA

1.  Nel server che esegue la messaggistica unificata di Exchange aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella **Apri** e quindi facendo clic su **OK**.

2.  Nel menu **file** fare clic su **Aggiungi/Rimuovi snap-in**e quindi fare clic su **Aggiungi**.

3.  Nella casella **Add standalone snap-** in fare clic su **certificati**e quindi fare clic su **Aggiungi**.

4.  Nella finestra di dialogo di **snap-in certificato** fare clic su **account computer**e quindi su **Avanti**.

5.  Nella finestra di dialogo **Seleziona computer** verificare che la casella di controllo computer **locale: (il computer in cui è in uso questa console)** sia selezionata e quindi fare clic su **fine**.

6.  Fare clic su **Chiudi**e quindi su **OK**.

7.  Nell'albero della console espandere **certificati (computer locale)**, espandere **autorità di certificazione radice attendibili**e quindi fare clic su **certificati**.

8.  Fare clic con il pulsante destro del mouse su **certificati**, scegliere **tutte le attività**e fare clic su **Importa**.

9.  Fare clic su **Avanti**.

10. Fare clic su **Sfoglia** per individuare il file e quindi fare clic su **Avanti**. Il file includerà un'estensione cer o p7b, a seconda della codifica selezionata nel passaggio 3 di **per scaricare il certificato della CA**.

11. Fare clic su **Inserisci tutti i certificati nello Store seguente**.

12. Fare clic su **Sfoglia**e quindi selezionare **autorità di certificazione radice attendibili**.

13. Fare clic su **Avanti** per verificare le impostazioni e quindi fare clic su **fine**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Per verificare che la CA si trovi nell'elenco delle autorità di certificazione radice attendibili

1.  Nel server che gestisce la messaggistica unificata di Exchange, in MMC Espandi **certificati (computer locale)**, Espandi **autorità di certificazione radice attendibili**e quindi fai clic su **certificati**.

2.  Nel riquadro dei dettagli verificare che la CA sia nell'elenco delle CA attendibili.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Per configurare la messaggistica unificata di Exchange Server 2013 con Lync Server

1.  Per informazioni dettagliate, vedere "integrare la messaggistica unificata di Exchange 2013 con Lync Server" nella [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)documentazione di Exchange Server.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Per creare una richiesta di certificato e installare il certificato in Exchange Server 2007 (SP1)

1.  Nel server che esegue la messaggistica unificata di Exchange fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **\<http://** nome del server**\>** della CA emittente/certsrv e quindi fare clic su **OK**.

2.  In **Seleziona un'attività**fare clic su **Richiedi un certificato**.

3.  In **Richiedi un certificato**fare clic su **richiesta di certificato avanzata**.

4.  In **richiesta di certificato avanzato**fare clic su **Crea e inviare una richiesta alla CA**.

5.  In **richiesta di certificato avanzato**selezionare **server Web** o un altro modello di certificato server configurato per l'autenticazione del server.

6.  In **informazioni di identificazione per il modello offline**Digitare il nome di dominio completo (FQDN) del server Exchange nella casella **nome** .
    
    <div>
    

    > [!NOTE]  
    > È necessario immettere il nome di dominio completo del server Exchange per le comunicazioni per il lavoro.

    
    </div>

7.  In **Opzioni chiave**fare clic sulla casella di controllo Archivia **certificato nell'archivio certificati del computer locale** .

8.  Fare clic sul pulsante **Invia** nella parte inferiore della pagina Web.

9.  Nella finestra di dialogo che apre la richiesta di conferma fare clic su **Sì**.

10. Nella pagina certificato rilasciato, in **certificato emesso**, fare clic su **installa questo certificato**.

11. Nella finestra di dialogo che apre la richiesta di conferma fare clic su **Sì**.

12. Verificare che venga visualizzato il messaggio "il nuovo certificato è stato installato correttamente".

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Per creare un certificato in Exchange Server 2010

1.  Accedere al server che gestisce la messaggistica unificata di Exchange con i diritti utente appropriati. Per informazioni dettagliate, vedere "autorizzazioni di [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)accesso client".

2.  Per creare il certificato, vedere le procedure seguenti:
    
    1.  "Creare un nuovo certificato di Exchange" in[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importare un certificato di Exchange" in[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Per il <STRONG>nome del soggetto</STRONG>del certificato, è necessario immettere l'FQDN del server Exchange per le comunicazioni per il lavoro.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Per assegnare il certificato in Exchange Server 2007 (SP1)

1.  Nel server che gestisce la messaggistica unificata di Exchange aprire MMC.

2.  Nell'albero della console espandere **Personal** e quindi fare clic su **certificati**.

3.  Nel riquadro dei dettagli verificare che venga visualizzato il certificato personale.

4.  Fare doppio clic sul certificato per leggere i dettagli e verificare che sia valido.
    
    <div>
    

    > [!NOTE]  
    > Potrebbe essere necessario attendere alcuni minuti prima che il certificato venga visualizzato come valido.

    
    </div>

5.  Riavviare il servizio di messaggistica unificata di Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > Il server che gestisce la messaggistica unificata di Exchange Server 2007 SP1 recupera automaticamente il certificato corretto.

    
    </div>

6.  Aprire il Visualizzatore eventi e cercare l'ID evento 1112, che specifica quale certificato è stato recuperato dal server che ha eseguito la messaggistica unificata di Exchange Server 2007 SP1.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Per assegnare il certificato in Exchange Server 2010

1.  Accedere al server che gestisce la messaggistica unificata di Exchange con i diritti utente appropriati. Per informazioni dettagliate, vedere "autorizzazioni di [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)accesso client".

2.  Per la procedura per l'assegnazione del certificato, vedere "assegnare servizi a un certificato" [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).

</div>

</div>

<span> </span>

</div>

</div>

</div>

