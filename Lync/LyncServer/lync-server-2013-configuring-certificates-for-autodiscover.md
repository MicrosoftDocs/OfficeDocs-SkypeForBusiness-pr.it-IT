---
title: "Lync Server 2013: configurazione dei certificati per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Configurazione dei certificati per l'individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-12_

I certificati per il pool di Director, il pool Front-end e il proxy inverso richiedono ulteriori voci di nomi alternativi per supportare connessioni sicure con i client Lync.

<div>


> [!NOTE]  
> Puoi usare il cmdlet <STRONG>Get-CsCertificate</STRONG> per visualizzare le informazioni sui certificati attualmente assegnati. La visualizzazione predefinita, tuttavia, tronca le proprietà del certificato e non Visualizza tutti i valori nella proprietà SubjectAlternativeNames. È possibile usare i cmdlet <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate e <STRONG>Set-CsCertificate</STRONG> per visualizzare alcune informazioni e per richiedere e assegnare certificati. Tuttavia, non è il metodo migliore da usare se non si è certi delle proprietà dei nomi alternativi oggetto (SAN) del certificato corrente. Per visualizzare il certificato e tutti i membri della proprietà, è consigliabile usare lo snap-in certificati di <EM>Microsoft Management Console (MMC)</EM> o usare la distribuzione guidata di Lync Server. Nella distribuzione guidata di Lync Server è possibile usare la procedura guidata certificato per visualizzare le proprietà del certificato. Le procedure per la visualizzazione, la richiesta e l'assegnazione di un certificato tramite Lync Server Management Shell e <EM>Microsoft Management Console (MMC)</EM> sono descritte in dettaglio nelle procedure seguenti. Per usare la distribuzione guidata di Lync Server, vedere i dettagli qui se è stato distribuito il pool di Director o Director facoltativi: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurare i certificati per il Director in Lync server 2013</A>. Per il server front-end o il pool Front-End, vedere i dettagli qui: <A href="lync-server-2013-configure-certificates-for-servers.md">configurare i certificati per i server in Lync Server 2013</A>.<BR>I passaggi iniziali di questa procedura sono i passaggi di preparazione per orientare l'utente sul ruolo riprodotto dai certificati correnti. Per impostazione predefinita, i certificati non avranno un lyncdiscover. &lt;SipDomain&gt; o LyncdiscoverInternal. &lt;inserimento di un&gt; nome di dominio interno a meno che non siano stati installati in precedenza i servizi di mobilità o non siano stati preparati preventivamente i certificati. Questa procedura usa il nome di dominio SIP di esempio "contoso.com" e il nome di dominio interno di esempio "contoso.net".<BR>La configurazione predefinita dei certificati per Lync Server 2013 e Lync Server 2010 consiste nell'usare un singolo certificato (denominato "default") con l'impostazione predefinita per tutti gli scopi, ad eccezione dei servizi Web, WebServicesExternal e WebServicesInternal. Una configurazione facoltativa prevede l'uso di certificati distinti per ogni scopo. I certificati possono essere gestiti usando i cmdlet di Lync Server Management Shell e Windows PowerShell oppure usando la creazione guidata certificati nella distribuzione guidata di Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Per aggiornare i certificati con i nuovi nomi alternativi del soggetto tramite Lync Server Management Shell

1.  Accedere al computer usando un account che disponga dei diritti e delle autorizzazioni di amministratore locale.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Individuare i certificati assegnati al server e per il tipo di utilizzo. Queste informazioni sono necessarie nel passaggio successivo per assegnare il certificato aggiornato. Nella riga di comando digitare:
    
        Get-CsCertificate

4.  Esaminare l'output del passaggio precedente per verificare se è stato assegnato un singolo certificato per più usi o se è stato assegnato un certificato diverso per ogni utilizzo. Esaminare il parametro Use per scoprire in che modo viene usato un certificato. Confrontare il parametro identificazione personale per i certificati visualizzati per verificare se lo stesso certificato ha più usi.

5.  Aggiornare il certificato. Nella riga di comando digitare:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Ad esempio, se il cmdlet **Get-CsCertificate** Visualizza un certificato con l'uso di default, un altro con l'uso di WebServicesInternal e un altro con l'uso di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando digitare:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Se per ogni uso viene assegnato un certificato distinto (il valore di identificazione personale è diverso per ogni certificato), è importante non eseguire il cmdlet **Set-CsCertificate** con più tipi. In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo. Ad esempio:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Per visualizzare il certificato, fare clic sul pulsante **Start**, scegliere **Esegui...**. Digitare MMC per aprire Microsoft Management Console.

7.  Nel menu MMC selezionare **file**, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati. Fare clic su **Aggiungi**. Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.

8.  Se il certificato si trova in questo computer, selezionare **computer locale**. Se il certificato si trova in un altro computer, selezionare **un altro computer**, digitare il nome di dominio completo del computer o fare clic su **Sfoglia** in immettere il nome dell' **oggetto da selezionare**, digitare il nome del computer. Fare clic su **Controlla nomi**. Quando il nome del computer viene risolto, sarà sottolineato. Fare clic su **OK**e quindi su **fine**. Fare clic su **OK** per confermare la selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il certificato non viene visualizzato nella console, verificare che non sia stato selezionato un utente o un servizio. È necessario selezionare computer oppure non sarà possibile individuare il certificato probper.

    
    </div>

9.  Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**. Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.

10. Nella visualizzazione **certificato** selezionare **Dettagli**. Da qui è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e il nome del soggetto assegnato e le proprietà associate verranno visualizzate.

11. Per visualizzare i nomi alternativi oggetto assegnati, selezionare **nome alternativo soggetto**. Vengono visualizzati tutti i nomi alternativi soggetti assegnati. I nomi alternativi oggetto trovati nella proprietà sono di tipo **DNS Name** per impostazione predefinita. Dovrebbero essere visualizzati i membri seguenti (che dovrebbero essere tutti nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):
    
      - Nome del pool per il pool o nome del server singolo se non si tratta di un pool
    
      - Nome del server a cui è assegnato il certificato
    
      - Record URL semplici, in genere incontra e componi
    
      - Servizi Web Internal e Web Services External names (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologia e alle selezioni di servizi Web sovrascritte.
    
      - Se è già stata assegnata, Lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.
    
    L'ultimo elemento è quello che più ti interessa: se c'è una voce di SAN Lyncdiscover e lyncdiscoverinternal.
    
    Dopo aver ottenuto queste informazioni, è possibile chiudere la visualizzazione certificato e la console MMC.

12. Se un servizio di individuazione automatica, ovvero lyncdiscover. \>nome\> di dominio e lyncdiscoverinternal. \<nome\> di dominio (in base a se si tratta di un certificato esterno o interno) il nome alternativo dell'oggetto non è presente e si usa un unico certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:
    
      - Al prompt della riga di comando di Lync Server Management Shell digitare:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain. Devi invece usare il parametro DomainName. Quando si usa il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Ad esempio:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Per assegnare il certificato, digitare quanto segue:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.

13. Per i nomi alternativi degli argomenti di individuazione automatica degli elementi interni mancanti quando si usano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:
    
      - Al prompt della riga di comando di Lync Server Management Shell digitare:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain. Devi invece usare il parametro DomainName. Quando si usa il parametro DomainName, è necessario usare un prefisso appropriato per l'FQDN del dominio SIP. Ad esempio:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Per un nome alternativo dell'oggetto individuazione automatica esterno mancante, nella riga di comando digitare:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain. Devi invece usare il parametro DomainName. Quando si usa il parametro DomainName, è necessario usare un prefisso appropriato per l'FQDN del dominio SIP. Ad esempio:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Per assegnare i singoli tipi di certificato, digitare quanto segue:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Dove "identificazione personale" è l'identificazione digitale visualizzata per i singoli certificati appena emessi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

