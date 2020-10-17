---
title: 'Lync Server 2013: configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server'
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
ms.openlocfilehash: 790798835694fcd76a4501c4b94e6ca59f220524
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521043"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-26_

Se la messaggistica unificata di Exchange è stata distribuita, come descritto in [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione e si desidera fornire le funzionalità di messaggistica unificata di Exchange agli utenti di VoIP aziendale nell'organizzazione, è possibile utilizzare le procedure seguenti per configurare il certificato sul server che esegue la messaggistica unificata di Exchange.

<div>


> [!IMPORTANT]  
> Per i certificati interni, entrambi i server che eseguono Lync Server 2013 e i server che eseguono Microsoft Exchange devono disporre di certificati autorità radice attendibili che sono mutuamente attendibili. L'autorità di certificazione (CA) può essere la stessa o un'autorità di certificazione diversa, purché i server dispongano del certificato radice dell'autorità di certificazione registrata nell'archivio certificati dell'autorità radice attendibile.



</div>

Il server di Exchange deve essere configurato con un certificato server per la connessione a Lync Server 2013:

1.  Scaricare il certificato CA per Exchange Server.

2.  Installare il certificato CA per Exchange Server.

3.  Verificare che la CA sia inclusa nell'elenco delle CA radice attendibili di Exchange Server.

4.  Creare una richiesta di certificato per Exchange Server e installare il certificato.

5.  Assegnare il certificato per Exchange Server.

<div>

## <a name="to-download-the-ca-certificate"></a>Per scaricare il certificato CA

1.  Nel server che esegue la messaggistica unificata di Exchange, fare clic sul pulsante **Start**, scegliere **esegui**, digitare **http:// \<name of your Issuing CA Server\> /certsrv**e quindi fare clic su **OK**.

2.  In **Selezionare un'attività** fare clic su **Scarica un certificato CA, la catena di certificati o un CRL**.

3.  In **Scarica un certificato CA, una catena di certificati o un CRL selezionare il** **metodo di codifica su base 64**e quindi fare clic su **Scarica certificato CA**.
    
    <div>
    

    > [!NOTE]  
    > È inoltre possibile specificare la codifica DER (Distinguished Encoding Rules) in questo passaggio. Se si seleziona la codifica DER, il tipo di file nel prossimo passaggio e nel passaggio 10 di <STRONG>Per installare il certificato CA</STRONG> è .p7b anziché .cer.

    
    </div>

4.  Nella finestra di dialogo **Download file** fare clic su **Salva** e quindi salvare il file nel disco rigido del server. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio precedente.

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Per installare il certificato CA

1.  Nel server che esegue la messaggistica unificata di Exchange, aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella **Apri** e quindi facendo clic su **OK**.

2.  Scegliere **Aggiungi/Rimuovi snap-in** dal menu **File** e quindi fare clic su **Aggiungi**.

3.  Nella casella **Aggiungi snap-in autonomo** fare clic su **Certificati** e quindi su **Aggiungi**.

4.  Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.

5.  Nella finestra di dialogo **Seleziona computer** verificare che sia selezionata la casella di controllo computer **locale (il computer su cui è in esecuzione questa console)** e quindi fare clic su **fine**.

6.  Fare clic su **Chiudi** e quindi su **OK**.

7.  Nell'albero della console espandere **Certificati (computer locale)**, espandere **Autorità di certificazione radice attendibili** e quindi fare clic su **Certificati**.

8.  Fare clic con il pulsante destro del mouse su **Certificati**, scegliere **Tutte le attività** e quindi **Importa**.

9.  Fare clic su **Avanti**.

10. Fare clic su **Sfoglia** per individuare il file e quindi fare clic su **Avanti**. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio 3 di **Per scaricare il certificato CA**.

11. Fare clic su **Mettere tutti i certificati nel seguente archivio**.

12. Fare clic su **Sfoglia** e quindi selezionare **Autorità di certificazione radice attendibili**.

13. Fare clic su **Avanti** per verificare le impostazioni e quindi fare clic su **Fine**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Per verificare che la CA sia inclusa nell'elenco delle CA radice attendibili

1.  Nel server che esegue la messaggistica unificata di Exchange, in MMC espandere **certificati (computer locale)**, espandere **autorità di certificazione radice attendibili**e quindi fare clic su **certificati**.

2.  Nel riquadro dei dettagli verificare che la CA sia inclusa nell'elenco delle CA attendibili.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Per configurare la messaggistica unificata di Exchange Server 2013 con Lync Server

1.  Per informazioni dettagliate, vedere la sezione relativa alla messaggistica unificata di Exchange 2013 con Lync Server nella documentazione di Exchange Server all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Per creare una richiesta di certificato e installare il certificato in Exchange Server 2007 (SP1)

1.  Nel server che esegue la messaggistica unificata di Exchange, fare clic sul pulsante **Start**, scegliere **esegui**, digitare **http:// \<**name of your Issuing CA Server**\> /certsrv**e quindi fare clic su **OK**.

2.  In **Selezionare un'attività** fare clic su **Richiedi un certificato**.

3.  In **Richiedi un certificato** fare clic su **Richiesta avanzata di certificati**.

4.  In **Richiesta avanzata certificati** fare clic su **Creare e inviare una richiesta a questa CA**.

5.  In **Richiesta avanzata di certificati** selezionare **Server Web** o un altro modello di certificato server configurato per l'autenticazione server.

6.  In **informazioni di identificazione per modello**non in linea, nella casella **nome** digitare il nome di dominio completo (FQDN) del server Exchange.
    
    <div>
    

    > [!NOTE]  
    > È necessario immettere l'FQDN di Exchange Server per garantire il funzionamento delle comunicazioni.

    
    </div>

7.  In **Opzioni chiave** selezionare la casella di controllo **Archivia certificato nell'archivio certificati del computer locale**.

8.  Fare clic sul pulsante **Invia** nella parte inferiore della pagina Web.

9.  Nella finestra di dialogo visualizzata in cui viene richiesto di confermare l'operazione, fare clic su **Sì**.

10. Nella pagina Certificato emesso fare clic su **Installa questo certificato** in **Certificato emesso**.

11. Nella finestra di dialogo visualizzata in cui viene richiesto di confermare l'operazione, fare clic su **Sì**.

12. Verificare che venga visualizzato il messaggio indicante il completamento dell'installazione del nuovo certificato.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Per creare un certificato in Exchange Server 2010

1.  Accedere al server che esegue la messaggistica unificata di Exchange con diritti utente adeguati. Per informazioni dettagliate, vedere "autorizzazioni di accesso client" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .

2.  Per creare il certificato, fare riferimento alle procedure seguenti:
    
    1.  "Creare un nuovo certificato di Exchange" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importazione di un certificato di Exchange" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Per l'opzione <STRONG>Nome soggetto</STRONG> del certificato, è necessario immettere l'FQDN di Exchange Server per garantire il funzionamento delle comunicazioni.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Per assegnare il certificato in Exchange Server 2007 (SP1)

1.  Nel server che esegue la messaggistica unificata di Exchange, aprire MMC.

2.  Nell'albero della console espandere **Personale** e quindi fare clic su **Certificati**.

3.  Nel riquadro dei dettagli verificare che il certificato personale sia visualizzato.

4.  Fare doppio clic sul certificato per leggere i dettagli e verificare che sia valido.
    
    <div>
    

    > [!NOTE]  
    > Prima che il certificato venga visualizzato come valido potrebbero essere necessari alcuni minuti.

    
    </div>

5.  Riavviare il servizio di messaggistica unificata di Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > Il certificato corretto viene automaticamente recuperato dal server che esegue la messaggistica unificata di Exchange Server 2007 SP1.

    
    </div>

6.  Aprire il Visualizzatore eventi e cercare l'ID evento 1112, che specifica il certificato recuperato dal server che esegue la messaggistica unificata di Exchange Server 2007 SP1.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Per assegnare il certificato in Exchange Server 2010

1.  Accedere al server che esegue la messaggistica unificata di Exchange con diritti utente adeguati. Per informazioni dettagliate, vedere "autorizzazioni di accesso client" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .

2.  Per la procedura per assegnare il certificato, vedere la sezione "assegnare servizi a un certificato" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

