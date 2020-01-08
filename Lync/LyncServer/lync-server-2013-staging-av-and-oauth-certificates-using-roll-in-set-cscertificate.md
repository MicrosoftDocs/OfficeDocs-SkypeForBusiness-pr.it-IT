---
title: Gestione di certificati AV e OAuth con-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4acdf759181dee3df872c7803ec595c63fb07016
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Gestione di certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-13_

Le comunicazioni audio/video (A/V) sono un componente chiave di Microsoft Lync Server 2013. Le caratteristiche come la condivisione delle applicazioni e le conferenze audio e video si basano sui certificati assegnati al servizio a/V Edge, in particolare il servizio di autenticazione A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Questa nuova funzionalità è progettata per l'utilizzo per il servizio A/V Edge e per il certificato <EM>OAuthTokenIssuer</EM> . È possibile effettuare il provisioning di altri tipi di certificato insieme al servizio A/V Edge e al tipo di certificato OAuth, ma non beneficiano del comportamento di coesistenza che verrà eseguito dal certificato del servizio A/V Edge.</P>
> <LI>
> <P>I cmdlet di PowerShell di Lync Server Management Shell usati per gestire i certificati di Microsoft Lync Server 2013 si riferiscono al certificato del servizio A/V Edge come tipo di certificato <EM>AudioVideoAuthentication</EM> e al certificato OAuthServer come tipo <EM>OAuthTokenIssuer</EM>. Per il resto di questo argomento e per identificare in modo univoco i certificati, questi verranno definiti dallo stesso tipo di identificatore, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</P></LI></OL>



</div>

Il servizio di autenticazione A/V è responsabile per il rilascio di token usati dai client e da altri utenti A/V. I token vengono generati dagli attributi del certificato e quando il certificato scade, la perdita di connessione e il requisito di ricongiungersi con un nuovo token generato dal nuovo certificato si tradurrà. Una nuova funzionalità di Lync Server 2013 allevierà questo problema: la possibilità di organizzare un nuovo certificato prima della scadenza e consentendo a entrambi i certificati di continuare a funzionare per un periodo di tempo. Questa funzionalità Usa la funzionalità aggiornata nel cmdlet Set-CsCertificate di Lync Server Management Shell. Il nuovo parametro-roll, con il parametro esistente-EffectiveDate, inserisce il nuovo certificato AudioVideoAuthentication nell'archivio certificati. Il certificato AudioVideoAuthentication precedente rimarrà ancora valido per i token emessi da convalidare. A partire dall'immissione del nuovo certificato AudioVideoAuthentication, si verificherà la serie di eventi seguente:

<div>


> [!TIP]
> Usando i cmdlet di Lync Server Management Shell per la gestione dei certificati è possibile richiedere certificati distinti e distinti per ogni scopo nell'Edge Server. L'uso della creazione guidata certificati nella distribuzione guidata di Lync Server consente di creare certificati, ma in genere è il tipo <STRONG>predefinito</STRONG> per cui tutte le coppie usano tutti i certificati per il server perimetrale su un singolo certificato. La procedura consigliata se si vuole usare la caratteristica del certificato rotante consiste nel disaccoppiare il certificato AudioVideoAuthentication dagli altri scopi del certificato. È possibile eseguire il provisioning e la fase di un certificato del tipo predefinito, ma solo la parte AudioVideoAuthentication del certificato combinato trarrà vantaggio dalla gestione temporanea. Un utente coinvolto (ad esempio) una conversazione di messaggistica istantanea quando il certificato scade deve disconnettersi e accedere nuovamente per usare il nuovo certificato associato al servizio Access Edge. Si verificherà un comportamento simile per un utente coinvolto in una conferenza Web tramite il servizio Web Conferencing Edge. Il certificato OAuthTokenIssuer è un tipo specifico condiviso in tutti i server. Si crea e si gestisce il certificato in un'unica posizione e il certificato viene archiviato in Central Management store per tutti gli altri server.



</div>

È necessario ulteriore dettaglio per comprendere appieno le opzioni e i requisiti quando si usa il cmdlet Set-CsCertificate e usarlo per eseguire la fase dei certificati prima della scadenza del certificato corrente. Il parametro-Roll è importante, ma in sostanza un unico scopo. Se lo definisci come parametro, stai dicendo a Set-CsCertificate che ti verranno fornite informazioni sul certificato che sarà influenzato da: tipo (ad esempio AudioVideoAuthentication e OAuthTokenIssuer), quando il certificato diventa efficacia definita da-EffectiveDate.

**-Roll:** Il parametro-Roll è obbligatorio e contiene le dipendenze che devono essere fornite insieme. Parametri obbligatori per definire completamente quali certificati saranno interessati e come verranno applicati:

**-EffectiveDate:** Il parametro: EffectiveDate definisce quando il nuovo certificato diventerà coattivo con il certificato corrente. La – EffectiveDate può essere vicina all'ora di scadenza del certificato corrente o può essere di un periodo di tempo più lungo. Un valore minimo consigliato: EffectiveDate per il certificato AudioVideoAuthentication sarebbe di 8 ore, ovvero la durata del token predefinita per i token del servizio Edge AV emessi con il certificato AudioVideoAuthentication.

Quando si verificano i certificati di OAuthTokenIssuer, esistono requisiti diversi per il tempo di anticipo prima che il certificato diventi effettivo. Il tempo minimo che deve avere il certificato OAuthTokenIssuer per il tempo di consegna è 24 ore prima della data di scadenza del certificato corrente. Il tempo di esecuzione esteso per la coesistenza è dovuto ad altri ruoli del server che dipendono dal certificato OAuthTokenIssuer (ad esempio, server Exchange) che ha un tempo di conservazione più lungo per l'autenticazione e la chiave di crittografia create da un certificato materiali.

**-Identificazione personale:** L'identificazione personale è un attributo del certificato univoco per tale certificato. Il parametro – identificazione personale viene usato per identificare il certificato che verrà influenzato dalle azioni del cmdlet Set-CsCertificate.

**-Digitare:** Il parametro-Type può accettare un singolo tipo di utilizzo del certificato o un elenco separato da virgole dei tipi di utilizzo del certificato. I tipi di certificato sono quelli che identificano il cmdlet e al server lo scopo del certificato. Ad esempio, digitare AudioVideoAuthentication per l'uso da parte del servizio A/V Edge e del servizio di autenticazione AV. Se si decide di eseguire la fase e il provisioning di certificati di un tipo diverso contemporaneamente, è necessario considerare il tempo di anticipo effettivo minimo richiesto per i certificati. Ad esempio, è necessario organizzare i certificati di tipo AudioVideoAuthentication e OAuthTokenIssuer. Il minimo: EffectiveDate deve essere il maggiore dei due certificati, in questo caso OAuthTokenIssuer, che ha un tempo di anticipo minimo di 24 ore. Se non si vuole eseguire la fase di esecuzione del certificato AudioVideoAuthentication con un tempo di anticipo di 24 ore, eseguire la fase separatamente con un EffectiveDate più per le proprie esigenze.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato A/V Edge service con i parametri-roll e-EffectiveDate

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Richiedere un rinnovo o un nuovo certificato AudioVideoAuthentication con la chiave privata esportabile per il certificato esistente nel servizio A/V Edge.

3.  Importare il nuovo certificato AudioVideoAuthentication nel server perimetrale e in tutti gli altri Edge Server nel pool (se è stato distribuito un pool).

4.  Configurare il certificato importato con il cmdlet Set-CsCertificate e usare il parametro – roll con il parametro – EffectiveDate. La data effettiva deve essere definita come scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno durata del token (per impostazione predefinita otto ore). In questo modo, il certificato deve essere impostato su attivo ed è la stringa \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 AM".
    
    <div>
    

    > [!IMPORTANT]
    > Per un pool di Edge, è necessario disporre di tutti i certificati AudioVideoAuthentication distribuiti e provisionati in base alla data e all'ora definiti dal parametro – EffectiveDate del primo certificato distribuito per evitare possibili interruzioni di comunicazioni a/V a causa del vecchio certificato che scade prima che tutti i client e i token di consumo siano stati rinnovati con il nuovo certificato.

    
    </div>
    
    Comando Set-CsCertificate con il parametro – roll e – EffectiveTime:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Comando Set-CsCertificate di esempio:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate deve essere formattato in base alle impostazioni dell'area geografica e della lingua del server. Nell'esempio vengono usate le impostazioni della lingua e dell'area inglese degli Stati Uniti

    
    </div>

Per comprendere ulteriormente il processo che Set-CsCertificate,-roll e-EffectiveDate USA per creare un nuovo certificato per il rilascio di nuovi token AudioVideoAuthentication mentre si usa ancora un certificato esistente per convalidare AudioVideoAuthentication in uso per i consumatori, una sequenza temporale visiva rappresenta un mezzo efficace per comprendere il processo.

Nell'esempio seguente l'amministratore determina che il certificato del servizio A/V Edge è scaduto a 2:00:00 PM su 07/22/2012. Richiede e riceve un nuovo certificato e lo importa in ogni Edge Server nel suo pool. Alle 2 di 07/22/2012, inizia a eseguire Get-CsCertificate con-roll,-identificazione personale uguale alla stringa di identificazione personale del nuovo certificato e-EffectiveTime impostato su 07/22/2012 6:00:00 AM. Esegue questo comando in ogni server perimetrale.

![Uso dei parametri roll e EffectiveDate.] (images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Uso dei parametri roll e EffectiveDate.")

Quando viene raggiunto il tempo effettivo (7/22/2012 6:00:00 AM), tutti i nuovi token vengono emessi dal nuovo certificato. Quando si convalidano i token, i token verranno prima convalidati in base al nuovo certificato. Se la convalida non riesce, viene provato il vecchio certificato. Il processo per provare il nuovo e il ritorno al vecchio certificato continuerà fino all'ora di scadenza del vecchio certificato. Dopo la scadenza del certificato precedente (7/22/2012 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato. Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro – Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato OAuthTokenIssuer con i parametri-roll e-EffectiveDate

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Richiedere un rinnovo o un nuovo certificato OAuthTokenIssuer con la chiave privata esportabile per il certificato esistente nel servizio A/V Edge.

3.  Importare il nuovo certificato OAuthTokenIssuer in un server front-end nel pool (se è stato distribuito un pool). Il certificato OAuthTokenIssuer viene replicato globalmente e deve essere aggiornato e rinnovato solo in qualsiasi server della distribuzione. Il server front-end viene usato come esempio.

4.  Configurare il certificato importato con il cmdlet Set-CsCertificate e usare il parametro – roll con il parametro – EffectiveDate. La data effettiva deve essere definita come il periodo di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno un minimo di 24 ore.
    
    Comando Set-CsCertificate con il parametro – roll e – EffectiveTime:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Comando Set-CsCertificate di esempio:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate deve essere formattato in base alle impostazioni dell'area geografica e della lingua del server. Nell'esempio vengono usate le impostazioni della lingua e dell'area inglese degli Stati Uniti

    
    </div>

Quando viene raggiunto il tempo effettivo (7/21/2012 1:00:00 AM), tutti i nuovi token vengono emessi dal nuovo certificato. Quando si convalidano i token, i token verranno prima convalidati in base al nuovo certificato. Se la convalida non riesce, viene provato il vecchio certificato. Il processo per provare il nuovo e il ritorno al vecchio certificato continuerà fino all'ora di scadenza del vecchio certificato. Dopo la scadenza del certificato precedente (7/22/2012 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato. Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro – Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificare i certificati dei server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configurare i certificati perimetrali per Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

