---
title: "Lync Server 2013: configurazione dei certificati per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d78aff761f1df9140bfc491e94ba98e1a0814f25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Configurazione dei certificati per l'individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-12_

I certificati per il pool di server Director, per il pool Front end e per il proxy inverso richiedono ulteriori voci del nome alternativo del soggetto per il supporto delle connessioni sicure con i client Lync.

<div>


> [!NOTE]  
> È possibile utilizzare il cmdlet <STRONG>Get-CsCertificate</STRONG> per visualizzare le informazioni sui certificati attualmente assegnati. Tuttavia, la visualizzazione predefinita tronca le proprietà del certificato e non Visualizza tutti i valori della proprietà SubjectAlternativeNames. È possibile utilizzare i cmdlet <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate e <STRONG>Set-CsCertificate</STRONG> per visualizzare alcune informazioni e per richiedere e assegnare i certificati. Tuttavia, non è il metodo migliore da utilizzare se non si è sicuri delle proprietà dei nomi alternativi del soggetto (SAN) nel certificato corrente. Per visualizzare il certificato e tutti i membri della proprietà, è consigliabile utilizzare lo snap-in certificati di <EM>Microsoft Management Console (MMC)</EM> o utilizzare la distribuzione guidata di Lync Server. Nella distribuzione guidata di Lync Server, è possibile utilizzare la configurazione guidata certificati per visualizzare le proprietà del certificato. Le procedure per la visualizzazione, la richiesta e l'assegnazione di un certificato tramite Lync Server Management Shell e <EM>Microsoft Management Console (MMC)</EM> sono descritte nelle procedure seguenti. Per utilizzare la distribuzione guidata di Lync Server, vedere informazioni dettagliate in questo articolo se è stato distribuito il pool di Director o Director facoltativo: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurare i certificati per il server Director in Lync 2013</A>. Per il front end server o il pool Front End, vedere i dettagli qui: <A href="lync-server-2013-configure-certificates-for-servers.md">configurare i certificati per i server in Lync server 2013</A>.<BR>I passaggi iniziali di questa procedura sono i passaggi di preparazione, per orientare il ruolo che i certificati correnti risuonano. Per impostazione predefinita, i certificati non avranno un lyncdiscover. &lt;SipDomain&gt; o LyncdiscoverInternal. &lt;la voce del&gt; nome di dominio interno, a meno che non siano stati precedentemente installati servizi per dispositivi mobili o che i certificati siano stati preparati in anticipo. In questa procedura viene utilizzato il nome di dominio SIP ' contoso.com ' e il nome di dominio interno ' contoso.net ' di esempio.<BR>La configurazione predefinita dei certificati per Lync Server 2013 e Lync Server 2010 prevede l'utilizzo di un singolo certificato (denominato ' default ') con l'impostazione predefinita per tutti gli scopi, ad eccezione dei servizi Web, WebServicesExternal e WebServicesInternal. Una configurazione facoltativa consiste nell'utilizzare certificati distinti per ogni scopo. I certificati possono essere gestiti utilizzando i cmdlet di Lync Server Management Shell e Windows PowerShell oppure utilizzando la procedura guidata certificate nella distribuzione guidata di Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Per aggiornare i certificati con i nuovi nomi alternativi del soggetto mediante Lync Server Management Shell

1.  Accedere al computer utilizzando un account che disponga dei diritti e delle autorizzazioni di amministratore locale.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Individuare quali certificati sono stati assegnati al server e per quale tipo di utilizzo. Per assegnare il certificato aggiornato, è necessario utilizzare queste informazioni nel passaggio successivo. Nella riga di comando digitare il comando seguente:
    
        Get-CsCertificate

4.  Esaminare l'output del passaggio precedente per verificare se un singolo certificato è assegnato a più utilizzi o se è stato assegnato un certificato diverso per ogni utilizzo. Esaminare il parametro Use per scoprire come viene utilizzato un certificato. Confrontare il parametro identificazione personale per i certificati visualizzati per vedere se lo stesso certificato dispone di più utilizzi.

5.  Aggiornare il certificato. Nella riga di comando digitare il comando seguente:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Ad esempio, se il cmdlet **Get-CsCertificate** ha visualizzato un certificato con l'utilizzo di default, un altro con un utilizzo di WebServicesInternal e un altro con un utilizzo di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando digitare quanto segue:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Se per ogni utilizzo viene assegnato un certificato separato (il valore di identificazione personale è diverso per ogni certificato), è importante non eseguire il cmdlet **Set-CsCertificate** con più tipi. In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo. Ad esempio:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Per visualizzare il certificato, fare clic sul pulsante **Start**, scegliere **Esegui...**. Digitare MMC per aprire Microsoft Management Console.

7.  Scegliere **file**dal menu MMC, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati. Fare clic su **Aggiungi**. Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.

8.  Se il certificato è presente nel computer in cui si trova, selezionare **computer locale**. Se il certificato si trova in un altro computer, selezionare **un altro computer**, digitare il nome di dominio completo del computer oppure fare clic su **Sfoglia** in **immettere il nome dell'oggetto da selezionare**, digitare il nome del computer. Fare clic su **Controlla nomi**. Quando il nome del computer viene risolto, verrà sottolineato. Fare clic su **OK**, quindi su **fine**. Fare clic su **OK** per eseguire il commit della selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il certificato non viene visualizzato nella console, verificare che l'utente o il servizio non sia stato selezionato. È necessario selezionare il computer oppure non sarà possibile individuare il certificato probper.

    
    </div>

9.  Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**. Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.

10. Nella visualizzazione **certificato** selezionare **Dettagli**. Da qui, è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e vengono visualizzati il nome del soggetto assegnato e le proprietà associate.

11. Per visualizzare i nomi alternativi del soggetto assegnati, selezionare **nome alternativo soggetto**. Vengono visualizzati tutti i nomi alternativi del soggetto assegnati. Per impostazione predefinita, i nomi alternativi del soggetto trovati nella proprietà sono di tipo **DNS Name** . Verranno visualizzati i membri seguenti (tutti i nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):
    
      - Nome del pool per il pool o nome del server singolo se non si tratta di un pool
    
      - Nome del server a cui è assegnato il certificato
    
      - Simple URL Records, in genere Meet e dialin
    
      - Servizi Web interni e nomi esterni dei servizi Web (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e le selezioni dei servizi Web in corso.
    
      - Se è già stato assegnato, il lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.
    
    L'ultimo elemento è quello che più ti interessa: se è presente una voce di SAN Lyncdiscover e lyncdiscoverinternal.
    
    Dopo aver apportato queste informazioni, è possibile chiudere la visualizzazione certificati e MMC.

12. Se si tratta di un servizio di individuazione automatica, ovvero lyncdiscover. \>nome\> di dominio e lyncdiscoverinternal. \<nome\> di dominio (a seconda se si tratta di un certificato esterno o interno) il nome alternativo del soggetto è mancante e si utilizza un singolo certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:
    
      - Al prompt dei comandi della riga di comando di Lync Server Management Shell digitare quanto segue:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain. Al contrario, è necessario utilizzare il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Ad esempio:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Per assegnare il certificato, digitare quanto segue:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.

13. Per un nome alternativo del soggetto di individuazione automatica mancante quando si utilizzano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:
    
      - Al prompt dei comandi della riga di comando di Lync Server Management Shell digitare quanto segue:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain. Al contrario, è necessario utilizzare il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario utilizzare un prefisso appropriato per il nome FQDN del dominio SIP. Ad esempio:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Per un nome alternativo del soggetto di individuazione automatica esterno mancante, nella riga di comando digitare quanto segue:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain. Al contrario, è necessario utilizzare il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario utilizzare un prefisso appropriato per il nome FQDN del dominio SIP. Ad esempio:
        
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

