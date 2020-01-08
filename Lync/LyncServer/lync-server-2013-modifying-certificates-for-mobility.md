---
title: 'Lync Server 2013: Modifica dei certificati per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bccb901f241089a21fd7428e28b005f46e157300
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modifica dei certificati per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-20_

Per supportare connessioni sicure tra l'ambiente Lync e i client mobili, i certificati SSL (Secure Socket Layer) per il pool di Director, il pool Front end e il proxy inverso devono essere aggiornati con un altro nome alternativo soggetto ( SAN). Per altre informazioni sui requisiti di certificato per la mobilità, vedere la sezione requisiti dei certificati nei [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), ma in pratica è necessario ottenere nuovi certificati dall'autorità di certificazione con le altre voci di San incluse e quindi aggiungere questi certificati usando i passaggi di questo articolo.

Naturalmente, prima di iniziare, in genere è consigliabile conoscere i nomi alternativi del soggetto che i certificati hanno già. Se non si è sicuri di cosa è già stato configurato, è possibile scoprirlo in molti modi. Mentre l'opzione è disponibile per eseguire il comando **Get-CsCertificate** e altri comandi di PowerShell per visualizzare queste informazioni, (che percorriamo di seguito) per impostazione predefinita, i dati verranno troncati, quindi potrebbe non essere possibile visualizzare tutte le proprietà necessarie. Per ottenere una buona occhiata al certificato e a tutte le sue proprietà, è possibile passare a Microsoft Management Console (MMC) e caricare lo snap-in certificati (che si può anche seguire) oppure è sufficiente archiviare la distribuzione guidata di Lync Server.

Come indicato in precedenza, la procedura seguente consente di eseguire l'aggiornamento dei certificati tramite Lync Server Management Shell e MMC. Se si è interessati all'uso della procedura guidata certificati nella distribuzione guidata di Lync Server, è possibile selezionare la casella di controllo [Configura i certificati per il Director in Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) per il pool di Director o Director, se ne è stato configurato uno (non è possibile). Per il server front-end o per il pool Front-End, è consigliabile vedere [configurare i certificati per i server in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md).

Un'ultima cosa da ricordare è che potresti avere un singolo certificato predefinito nell'ambiente Lync Server 2013 oppure puoi avere certificati distinti per impostazione predefinita (che è tutto tranne i servizi Web), WebServicesExternal e WebServicesInternal. Qualunque sia la configurazione, questi passaggi dovrebbero essere utili.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Per aggiornare i certificati con i nuovi nomi alternativi del soggetto tramite Lync Server Management Shell

1.  È necessario accedere al server Lync Server 2013 usando un account che disponga dei diritti e delle autorizzazioni di amministratore locale. Inoltre, se si sta usando la richiesta di PowerShell **-CsCertificate** nei passaggi 12 e oltre, l'account deve avere diritti per l'autorità di certificazione (CA) specificata.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per poter assegnare un certificato aggiornato, è necessario verificare quali certificati sono stati assegnati al server e per quale tipo di utilizzo. Nella riga di comando digitare:
    
        Get-CsCertificate

4.  Esaminare l'output del passaggio precedente per verificare se un singolo certificato è stato assegnato per più usi o se è stato assegnato un certificato diverso per ogni utilizzo. Cerca nel parametro Use per scoprire in che modo viene usato un certificato. Confrontare il parametro identificazione personale per i certificati visualizzati per verificare se lo stesso certificato ha più usi. Tieni d'occhio il parametro identificazione personale.

5.  Aggiornare il certificato. Nella riga di comando digitare:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Ad esempio, se il cmdlet **Get-CsCertificate** Visualizza un certificato con l'uso di default, un altro con l'uso di WebServicesInternal e un altro con l'uso di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando devi digitare:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Se per ogni uso viene assegnato un certificato distinto (in modo che il valore di identificazione personale selezionato in precedenza sia diverso per ogni certificato), è fondamentale **non** eseguire il cmdlet **Set-CsCertificate** con più tipi, come nell'esempio precedente. In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo. Ad esempio:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Per visualizzare il certificato (o i certificati), fare clic sul pulsante **Start**, scegliere **Esegui...**. Digitare MMC per aprire Microsoft Management Console.

7.  Nel menu MMC selezionare **file**, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati. Fare clic su **Aggiungi**. Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.

8.  Se si tratta del server in cui si trova il certificato, selezionare **computer locale**. Se il certificato si trova in un altro computer, è necessario selezionare **un altro computer**, quindi è possibile digitare il nome di dominio completo del computer oppure fare clic su **Sfoglia** in **immettere il nome dell'oggetto da selezionare**e digitare il nome del computer. Fare clic su **Controlla nomi**. Quando il nome del computer viene risolto, sarà sottolineato. Fare clic su **OK**e quindi su **fine**. Fare clic su **OK** per confermare la selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.

9.  Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**. Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.

10. Nella visualizzazione **certificato** selezionare **Dettagli**. Da qui è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e il nome del soggetto assegnato e le proprietà associate verranno visualizzate.

11. Per visualizzare i nomi alternativi oggetto assegnati, selezionare **nome alternativo soggetto**. Vengono visualizzati tutti i nomi alternativi assegnati al soggetto. I nomi alternativi oggetto trovati qui sono di tipo **DNS Name** per impostazione predefinita. Dovrebbero essere visualizzati i membri seguenti (che dovrebbero essere tutti nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):
    
      - Nome del pool per il pool o nome del server singolo se non si tratta di un pool
    
      - Nome del server a cui è assegnato il certificato
    
      - Record URL semplici, in genere incontra e componi
    
      - Servizi Web Internal e Web Services External names (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologia e alle selezioni di servizi Web sovrascritte.
    
      - Se è già stata assegnata, Lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.
    
    L'ultimo elemento è quello che ti interessa di più: se c'è una voce di SAN Lyncdiscover e lyncdiscoverinternal.
    
    Ripetere questi passaggi se si hanno più certificati da controllare. Dopo aver ottenuto queste informazioni, è possibile chiudere la visualizzazione certificato e la console MMC.

12. Se non è presente un nome alternativo dell'oggetto del servizio di individuazione automatica e si usa un singolo certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:
    
      - Al prompt della riga di comando di Lync Server Management Shell digitare:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain. Devi invece usare il parametro DomainName. Quando si usa il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Ad esempio:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Per assegnare il certificato, digitare quanto segue:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.

13. Per una SAN automatica interna mancante quando si usano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:
    
      - Al prompt della riga di comando di Lync Server Management Shell digitare:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain. Devi invece usare il parametro DomainName. Quando usi il parametro DomainName, devi usare un prefisso appropriato per l'FQDN del dominio SIP. Ad esempio:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Per un nome alternativo dell'oggetto individuazione automatica esterno mancante, nella riga di comando digitare:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain. Devi invece usare il parametro DomainName. Quando usi il parametro DomainName, devi usare un prefisso appropriato per l'FQDN del dominio SIP. Ad esempio:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Per assegnare i singoli tipi di certificato, digitare quanto segue:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Dove "identificazione personale" è l'identificazione digitale visualizzata per i singoli certificati appena emessi.
    
    <div>
    

    > [!NOTE]  
    > Solo per notare che i passaggi 12 e 13 devono essere eseguiti solo se l'account che li esegue può accedere all'autorità di certificazione con le autorizzazioni appropriate. Se non si riesce ad accedere con un account che contiene tali autorizzazioni o se si usa un'autorità di certificazione pubblica o remota per i certificati, è necessario richiederli tramite la distribuzione guidata di Lync Server, che è stata toccata nella parte superiore della articolo.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

