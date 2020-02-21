---
title: Gestione temporanea dei certificati AV e OAuth tramite-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee572bbf115d1e83476194b0e5c92859886da42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-13_

Le comunicazioni audio/video (A/V) sono un componente chiave di Microsoft Lync Server 2013. Funzionalità quali la condivisione di applicazioni e le conferenze audio e video si basano sui certificati assegnati al servizio A/V Edge, in particolare il servizio di autenticazione A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Questa nuova funzionalità è progettata per funzionare con il servizio A/V Edge e il certificato <EM>OAuthTokenIssuer</EM> . È possibile eseguire il provisioning di altri tipi di certificato insieme al servizio A/V Edge e al tipo di certificato OAuth, ma non beneficiare del comportamento di coesistenza del certificato del servizio A/V Edge.</P>
> <LI>
> <P>I cmdlet di PowerShell di Lync Server Management Shell utilizzati per gestire i certificati di Microsoft Lync Server 2013 si riferiscono al certificato del servizio A/V Edge come tipo di certificato <EM>AudioVideoAuthentication</EM> e il certificato OAuthServer come tipo <EM>OAuthTokenIssuer</EM>. Per il resto di questo argomento e per identificare in modo univoco i certificati, verranno riferiti dallo stesso tipo di identificatore, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</P></LI></OL>



</div>

Il servizio di autenticazione A/V è responsabile dell'emissione di token utilizzati dai client e da altri utenti A/V. I token vengono generati dagli attributi del certificato e, quando il certificato scade, la perdita di connessione e il requisito di riunirsi con un nuovo token generato dal nuovo certificato risultano. Una nuova funzionalità di Lync Server 2013 consente di alleviare questo problema: la possibilità di eseguire un nuovo certificato prima della scadenza e di consentire a entrambi i certificati di continuare a funzionare per un determinato periodo di tempo. Questa funzionalità utilizza la funzionalità aggiornata nel cmdlet Set-CsCertificate di Lync Server Management Shell. Il nuovo parametro-roll, con il parametro existing-EffectiveDate, inserirà il nuovo certificato AudioVideoAuthentication nell'archivio certificati. Il certificato AudioVideoAuthentication meno recente continuerà a essere convalidato per i token emessi. A partire dalla messa in posizione del nuovo certificato AudioVideoAuthentication, si verificherà la seguente serie di eventi:

<div>


> [!TIP]
> Utilizzando i cmdlet di Lync Server Management Shell per la gestione dei certificati, è possibile richiedere certificati separati e distinti per ogni scopo nel server perimetrale. L'utilizzo della configurazione guidata certificati nella distribuzione guidata di Lync Server consente di creare certificati, ma in genere è il tipo <STRONG>predefinito</STRONG> per il quale tutti i certificati vengono utilizzati per il server perimetrale su un singolo certificato. Se si intende utilizzare la funzionalità di certificati in sequenza, la procedura consigliata consiste nel disassociare il certificato AudioVideoAuthentication dagli scopi degli altri certificati. È possibile effettuare il provisioning e gestire temporaneamente un certificato di tipo predefinito, ma solo la parte AudioVideoAuthentication del certificato combinato sfrutterà i vantaggi della gestione temporanea. Un utente coinvolto (ad esempio) una conversazione di messaggistica istantanea quando il certificato scade avrà bisogno di disconnettersi e accedere nuovamente per utilizzare il nuovo certificato associato al servizio Access Edge. Si verificherà un comportamento analogo per un utente coinvolto in una conferenza Web tramite il servizio Web Conferencing Edge. Il certificato OAuthTokenIssuer è un tipo specifico condiviso in tutti i server. È possibile creare e gestire il certificato in un'unica posizione e il certificato viene archiviato nell'archivio di gestione centrale per tutti gli altri server.



</div>

Per comprendere appieno le opzioni e i requisiti relativi all'uso del cmdlet Set-CsCertificate e alla gestione temporanea di certificati tramite tale cmdlet prima della scadenza del certificato corrente, sono necessarie altre informazioni. Il parametro –Roll è importante, ma ha essenzialmente un solo scopo. Se lo si definisce come parametro, si sta dicendo a Set-CsCertificate che verranno fornite informazioni sul certificato che sarà influenzato da – tipo (ad esempio AudioVideoAuthentication e OAuthTokenIssuer), quando il certificato diventerà effetto definito da – EffectiveDate.

**-Roll:** Il parametro – Roll è obbligatorio e dispone di dipendenze che devono essere fornite insieme. Parametri obbligatori per definire completamente quali certificati saranno interessati e come saranno applicati:

**-EffectiveDate:** Il parametro – EffectiveDate definisce quando il nuovo certificato diventerà coattivo con il certificato corrente. Il parametro –EffectiveDate può essere vicino all'ora di scadenza del certificato corrente oppure corrispondere a un periodo di tempo più lungo. Un valore minimo consigliato per –EffectiveDate per il certificato AudioVideoAuthentication è di 8 ore, ovvero la durata predefinita del token per i token del servizio A/V Edge emessi utilizzando il certificato AudioVideoAuthentication.

Quando si gestiscono temporaneamente certificati OAuthTokenIssuer, esistono diversi requisiti per il tempo di anticipo prima che il certificato diventi effettivo. Il tempo di anticipo minimo per il certificato OAuthTokenIssuer è di 24 ore prima dell'ora di scadenza del certificato corrente. Il tempo di anticipo prolungato per la coesistenza è dovuto ad altri ruoli del server dipendenti dal certificato OAuthTokenIssuer (ad esempio Exchange Server) che ha un periodo di memorizzazione più lungo per i materiali di autenticazione e chiave di crittografia creati dal certificato.

**-Identificazione personale:** L'identificazione personale è un attributo del certificato univoco per il certificato. Il parametro –Thumbprint è utilizzato per identificare il certificato che sarà interessato dalle azioni del cmdlet Set-CsCertificate.

**-Digitare:** Il parametro – Type può accettare un singolo tipo di utilizzo del certificato o un elenco separato da virgole di tipi di utilizzo dei certificati. I tipi di certificati identificato lo scopo del certificato per il cmdlet e il server. Ad esempio, digitare AudioVideoAuthentication è per l'utilizzo da parte del servizio A/V Edge e del servizio di autenticazione AV. Se si decide di gestire temporaneamente ed effettuare il provisioning di certificati di un tipo diverso contemporaneamente, è necessario considerare il più lungo tempo di anticipo effettivo minimo richiesto per i certificati. Ad esempio, è necessario gestire temporaneamente i certificati di tipo AudioVideoAuthentication e OAuthTokenIssuer. Il valore minimo di –EffectiveDate deve essere il maggiore dei due certificati, in questo caso OAuthTokenIssuer, che ha un tempo di anticipo di almeno 24 ore. Se non si desidera gestire temporaneamente il certificato AudioVideoAuthentication con un tempo di anticipo di 24 ore, gestirlo separatamente con un valore di EffectiveDate più adeguato ai requisiti specifici.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato del servizio A/V Edge con i parametri-roll e-EffectiveDate

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Richiedere un rinnovo o un nuovo certificato AudioVideoAuthentication con una chiave privata esportabile per il certificato esistente nel servizio A/V Edge.

3.  Importare il nuovo certificato di AudioVideoAuthentication nel server perimetrale e in tutti gli altri server perimetrali del pool (se è stato distribuito un pool).

4.  Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro –Roll con il parametro –EffectiveDate. La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno la durata del token (otto ore per impostazione predefinita). In questo modo viene indicato che il certificato deve essere impostato su attivo ed è la stringa \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 AM".
    
    <div>
    

    > [!IMPORTANT]
    > Per un pool di server perimetrali, è necessario disporre di tutti i certificati di AudioVideoAuthentication distribuiti e provisionati in base alla data e all'ora definite dal parametro – EffectiveDate del primo certificato distribuito per evitare possibili interruzioni di comunicazioni a/V a causa del certificato meno recente che scade prima che tutti i client e i token consumer siano stati rinnovati utilizzando il nuovo certificato.

    
    </div>
    
    Comando Set-CsCertificate con i parametri –Roll e –EffectiveTime:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Esempio di comando Set-CsCertificate:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > È necessario formattare il parametro EffectiveDate secondo le impostazioni di lingua e paese del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti).

    
    </div>

Per capire meglio il processo utilizzato da Set-CsCertificate, -Roll e –EffectiveDate per gestire temporaneamente un nuovo certificato per l'emissione di nuovi token AudioVideoAuthentication pur continuando a utilizzare un certificato esistente per convalidare token AudioVideoAuthentication utilizzati dai consumer, è utile servirsi di una sequenza temporale visiva.

Nell'esempio seguente l'amministratore determina che il certificato del servizio A/V Edge deve scadere alle 2:00:00 PM del 07/22/2012. Richiede e riceve un nuovo certificato e lo importa in ogni server perimetrale del pool. Alle 2.00 del 22/07/2012 inizia a eseguire Get-CsCertificate con –Roll, -Thumbprint equivalente alla stringa di identificatore digitale del nuovo certificato e –EffectiveTime impostato su 22/07/2012 6.00. Esegue questo comando in ogni server perimetrale.

![Utilizzo dei parametri roll e EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Utilizzo dei parametri roll e EffectiveDate.")

All'ora effettiva (6.00 del 22/7/2012), tutti i nuovi token vengono emessi dal nuovo certificato. Alla convalida, i token verranno prima convalidati rispetto al nuovo certificato e, in caso di esito negativo, verrà effettuato un tentativo con il vecchio certificato. Questo processo che prevede prima l'uso del nuovo certificato e del vecchio certificato come fallback viene ripetuto fino alla scadenza del vecchio certificato. Una volta scaduto il vecchio certificato (22/7/2012 alle 14.00), i token verranno convalidati solo mediante il nuovo certificato. Il vecchio certificato potrà essere rimosso senza problemi utilizzando il cmdlet Remove-CsCertificate con il parametro –Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato OAuthTokenIssuer con parametri –Roll e -EffectiveDate

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Richiedere un rinnovo o un nuovo certificato OAuthTokenIssuer con una chiave privata esportabile per il certificato esistente nel servizio A/V Edge.

3.  Importare il nuovo certificato di OAuthTokenIssuer in un front end server nel pool (se è stato distribuito un pool). Il certificato OAuthTokenIssuer viene replicato globalmente e deve solo essere aggiornato e rinnovato in ogni server nella distribuzione. Il front end server viene utilizzato come esempio.

4.  Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro –Roll con il parametro –EffectiveDate. La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno un minimo di 24 ore.
    
    Comando Set-CsCertificate con i parametri –Roll e –EffectiveTime:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Esempio di comando Set-CsCertificate:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > È necessario formattare il parametro EffectiveDate secondo le impostazioni di lingua e paese del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti).

    
    </div>

All'ora effettiva (1.00.00 del 21/07/2012), tutti i nuovi token vengono emessi dal nuovo certificato. Alla convalida, i token verranno prima convalidati rispetto al nuovo certificato e, in caso di esito negativo, verrà effettuato un tentativo con il vecchio certificato. Questo processo che prevede prima l'uso del nuovo certificato e del vecchio certificato come fallback viene ripetuto fino alla scadenza del vecchio certificato. Una volta scaduto il vecchio certificato (22/7/2012 alle 14.00), i token verranno convalidati solo mediante il nuovo certificato. Il vecchio certificato potrà essere rimosso senza problemi utilizzando il cmdlet Remove-CsCertificate con il parametro –Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificare i certificati dei server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configurare i certificati perimetrali per Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

