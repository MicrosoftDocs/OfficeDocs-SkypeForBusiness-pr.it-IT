---
title: 'Lync Server 2013: modifica dei certificati per i dispositivi mobili'
description: 'Lync Server 2013: modifica dei certificati per i dispositivi mobili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555852"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modifica dei certificati per i dispositivi mobili in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-20_

Per supportare connessioni sicure tra l'ambiente Lync e i client mobili, i certificati SSL (Secure Socket Layer) per il pool di server Director, il pool Front end e il proxy inverso devono essere aggiornati con alcune voci aggiuntive del nome alternativo soggetto (SAN). Se è necessario estrarre ulteriori informazioni sui requisiti dei certificati per i dispositivi mobili, vedere la sezione requisiti dei certificati in [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), ma in pratica è necessario ottenere nuovi certificati dall'autorità di certificazione con le voci di San aggiuntive incluse e quindi aggiungere tali certificati utilizzando i passaggi di questo articolo.

Naturalmente, prima di iniziare, è consigliabile sapere quali nomi alternativi del soggetto sono già presenti nei certificati. Se non si è sicuri di cosa è già stato configurato, è possibile scoprirlo in molti modi. Mentre l'opzione è disponibile per l'esecuzione dei comandi **Get-CsCertificate** e di altri PowerShell per visualizzare queste informazioni, (che è possibile esaminare in basso) per impostazione predefinita, i dati verranno troncati, pertanto potrebbe non essere possibile visualizzare tutte le proprietà necessarie. Per ottenere un buon aspetto del certificato e di tutte le relative proprietà, è possibile accedere a Microsoft Management Console (MMC) e caricare lo snap-in certificati (che è anche possibile esaminare in basso) oppure è sufficiente archiviare la distribuzione guidata di Lync Server.

Come indicato in questo esempio, la procedura seguente consente di eseguire l'aggiornamento dei certificati mediante Lync Server Management Shell e MMC. Se si è interessati all'utilizzo della procedura guidata di certificazione nella distribuzione guidata di Lync Server, è possibile controllare la [configurazione dei certificati per il Director in Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) out per il Director o il pool di Director, se ne è stata configurata una (potrebbe non essere possibile). Per il front end server o il pool Front End, è necessario vedere [Configure Certificates for Servers in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md).

Un'ultima cosa da tenere in considerazione consiste nel fatto che è possibile disporre di un singolo certificato predefinito nell'ambiente Lync Server 2013 oppure che si disponga di certificati distinti per il valore predefinito (ovvero tutto tranne che per i servizi Web), WebServicesExternal e WebServicesInternal. Qualunque sia la configurazione, questi passaggi dovrebbero risultare utili.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Per aggiornare i certificati con i nuovi nomi alternativi del soggetto mediante Lync Server Management Shell

1.  È necessario eseguire l'accesso al server Lync Server 2013 utilizzando un account che disponga dei diritti e delle autorizzazioni di amministratore locale. Inoltre, se si esegue la richiesta di PowerShell **-CsCertificate** nei passaggi 12 e oltre, l'account deve disporre dei diritti per l'autorità di certificazione (CA) specificata.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Prima di poter assegnare un certificato aggiornato, è necessario scoprire quali certificati sono stati assegnati al server e per quale tipo di utilizzo. Nella riga di comando digitare il comando seguente:
    
        Get-CsCertificate

4.  Esaminare l'output del passaggio precedente per verificare se è stato assegnato un singolo certificato per più utilizzi o se è stato assegnato un certificato diverso per ogni utilizzo. Esaminare il parametro Use per individuare il modo in cui viene utilizzato un certificato. Confrontare il parametro identificazione personale per i certificati visualizzati per vedere se lo stesso certificato dispone di più utilizzi. Tenere d'occhio il parametro identificazione personale.

5.  Aggiornare il certificato. Nella riga di comando digitare il comando seguente:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Ad esempio, se il cmdlet **Get-CsCertificate** ha visualizzato un certificato con l'utilizzo di default, un altro con un utilizzo di WebServicesInternal e un altro con un utilizzo di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando digitare quanto segue:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Se per ogni utilizzo viene assegnato un certificato distinto, in modo che il valore di identificazione personale controllato in alto sia diverso per ogni certificato, è importante che **non** venga eseguito il cmdlet **Set-CsCertificate** con più tipi, come nell'esempio precedente. In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo. Ad esempio:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Per visualizzare il certificato (o i certificati), fare clic sul pulsante **Start**, scegliere **Esegui...**. Digitare MMC per aprire Microsoft Management Console.

7.  Scegliere **file**dal menu MMC, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati. Fare clic su **Aggiungi**. Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.

8.  Se si tratta del server in cui si trova il certificato, selezionare **computer locale**. Se il certificato è posizionato in un altro computer, è necessario selezionare **un altro computer**, quindi è possibile digitare il nome di dominio completo del computer oppure fare clic su **Sfoglia** in **immettere il nome dell'oggetto da selezionare**e digitare il nome del computer. Fare clic su **Controlla nomi**. Quando il nome del computer viene risolto, verrà sottolineato. Fare clic su **OK**, quindi su **fine**. Fare clic su **OK** per eseguire il commit della selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.

9.  Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**. Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.

10. Nella visualizzazione **certificato** selezionare **Dettagli**. Da qui, è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e vengono visualizzati il nome del soggetto assegnato e le proprietà associate.

11. Per visualizzare i nomi alternativi del soggetto assegnati, selezionare **nome alternativo soggetto**. Vengono visualizzati tutti i nomi alternativi del soggetto assegnati. Per impostazione predefinita, i nomi alternativi del soggetto trovati qui sono di tipo **DNS Name** . Verranno visualizzati i membri seguenti (tutti i nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):
    
      - Nome del pool per il pool o il nome del server singolo se non si tratta di un pool
    
      - Nome del server a cui è assegnato il certificato
    
      - Simple URL Records, in genere Meet e dialin
    
      - Servizi Web interni e nomi esterni dei servizi Web (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e le selezioni dei servizi Web in corso.
    
      - Se è già stato assegnato, il lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> record.
    
    L'ultimo elemento è quello che più ti interessa: se c'è una voce di Lyncdiscover e lyncdiscoverinternal SAN.
    
    Ripetere questi passaggi se si dispone di più certificati da controllare. Dopo aver apportato queste informazioni, è possibile chiudere la visualizzazione certificati e MMC.

12. Se non è presente un nome alternativo del soggetto del servizio di individuazione automatica e si utilizza un singolo certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:
    
      - Al prompt dei comandi della riga di comando di Lync Server Management Shell digitare quanto segue:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain. Al contrario, è necessario utilizzare il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Ad esempio:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Per assegnare il certificato, digitare quanto segue:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.

13. Per una rete SAN di individuazione automatica mancante quando si utilizzano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:
    
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
    
    <div>
    

    > [!NOTE]  
    > Solo per tenere presente che i passaggi 12 e 13 devono essere eseguiti solo se l'account che esegue tali operazioni ha accesso all'autorità di certificazione con le autorizzazioni appropriate. Se non si è in grado di eseguire l'accesso con un account che dispone di tali autorizzazioni o se si utilizza un'autorità di certificazione pubblica o remota per i certificati, è necessario richiederli tramite la distribuzione guidata di Lync Server, che è stata toccata nella parte superiore dell'articolo.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

