---
title: "Lync Server 2013: Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali IIS"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-05-25_

Usare la procedura seguente per configurare il certificato nelle directory virtuali di Internet Information Services (IIS) oppure verificare che il certificato sia configurato correttamente. Eseguire la procedura seguente in ogni server che esegue IIS nel pool di Lync Server interno e nei server di pool Director o Director facoltativi.

<div>


> [!NOTE]  
> La procedura seguente definisce una procedura per richiedere un certificato combinato usato per tutti gli scopi Lync Server, sito Web interno e sito Web esterno in IIS. Lync Server 2010 ha introdotto un set di cmdlet di Windows&nbsp;PowerShell per Lync Server Management Shell per l'esplicito scopo di gestire la richiesta di certificato, l'importazione e l'assegnazione. La procedura presuppone che sia presente un'autorità di certificazione (CA) distribuita internamente in grado di elaborare la richiesta. Se si usano certificati pubblici per scopi di Lync Server o la CA richiede una richiesta offline, vedere la sintassi dettagliata in questo argomento per informazioni sul parametro – output. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Per configurare l'autenticazione e i certificati nelle directory virtuali di IIS

1.  Per completare correttamente le operazioni seguenti, è necessario avere effettuato l'accesso al computer (front end server o Director) in cui sono installati i servizi Web e essere un amministratore locale. È necessario disporre delle autorizzazioni di **lettura** e **registrazione** per l'autorità di certificazione di cui si richiederanno i certificati, se l'autorità di certificazione è l'autorità di certificazione dell'organizzazione. Non è necessario disporre delle autorizzazioni per l'autorità di certificazione se si vuole configurare e inviare una richiesta di certificato offline.

2.  Fare clic sul pulsante **Start**, selezionare **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.

3.  In **Gestione Internet Information Services (IIS)** selezionare **nomeserver**. In **visualizzazione funzionalità**selezionare **certificati server**, fare clic con il pulsante destro del mouse e scegliere **Apri funzionalità**.
    
    <div>
    

    > [!TIP]  
    > Nella visualizzazione funzionalità certificati server, se sono stati assegnati certificati al server, verranno visualizzati qui. Se è presente un certificato che corrisponde ai requisiti per il sito Web esterno in IIS, è possibile riutilizzare tale certificato. Per visualizzare un certificato, fare clic con il pulsante destro del mouse sul certificato e scegliere <STRONG>Visualizza.</STRONG> ..

    
    </div>

4.  Nel server front-end o nel Director di cui si richiede il certificato, fare clic sul pulsante **Start**, selezionare **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

5.  In Lync Server Management Shell digitare quanto segue:
    
        Get-CsCertificate
    
    L'output è un elenco dei certificati attualmente presenti nel server nell'archivio certificati del computer personale. Tieni presente che nel certificato combinato (ovvero in cui i servizi Web predefiniti interni e Web Services esterni usano lo stesso certificato) vedrai che la proprietà Use verrà popolata con default, WebServicesInternal e WebServicesExternal. La proprietà identificazione personale sarà inoltre uguale per ogni tipo di utilizzo. In questo esempio viene illustrato un output di esempio di Get-CsCertificate:
    
    ![Informazioni Get-CsCertificate sullo stato del certificato corrente](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Informazioni Get-CsCertificate sullo stato del certificato corrente")

6.  In Lync Server Management Shell digitare quanto segue:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    In cui il comando completo verrà visualizzato come esempio seguente:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Per impostazione predefinita, Request-CsCertificate compilerà il nome del soggetto con il nome del server o del pool e compilerà le voci nel nome dell'oggetto alternativo con l'FQDN del server, il FQDN del pool, gli FQDN degli URL semplici e gli FQDN dei servizi Web interni ed esterni. A questo scopo, fai riferimento al documento della topologia nella distribuzione. Se è presente un valore mancante ed è stato specificato il parametro – Verbose, si riceverà una notifica che i valori calcolati e effettivi per i nomi alternativi sono diversi, ma non informa i valori mancanti. Fornisce l'intero valore calcolato a cui fa riferimento il cmdlet. Usare la stringa di nomi alternativi calcolati nell'output per richiedere nuovamente un nuovo certificato che includa tutti i valori.

    
    </div>
    
    ![Output della richiesta di certificato tramite Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output della richiesta di certificato tramite Request-CsCertifica")

7.  In Lync Server Management Shell digitare quanto segue:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    In cui il comando completo verrà visualizzato come esempio seguente:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    L'output del cmdlet Set-CsCertificate mostrerà che viene assegnato lo stesso certificato (identificato dall'identificazione personale del certificato) per l'utilizzo predefinito, WebServicesExternal e WebServicesInternal.
    
    ![Output di Set-CsCertificate su IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output di Set-CsCertificate su IIS WebExt")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Per verificare o configurare l'autenticazione e i certificati nelle directory virtuali di IIS

1.  Fare clic sul pulsante **Start**, selezionare **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.

2.  In **Gestione Internet Information Services (IIS)** espandere **nomeserver**e quindi espandere **siti**.

3.  Fare clic con il pulsante destro del mouse su **sito Web esterno di Lync Server**e quindi scegliere **Modifica binding**

4.  Verificare che HTTPS sia associato alla porta 4443 e quindi fare clic su **https**.

5.  Selezionare la voce HTTPS, fare clic su **modifica**e quindi verificare che Lync Server WebServicesExternalCertificate sia associato al protocollo. Confrontare l'identificazione personale del cmdlet Set-CsCertificate per assicurarsi che il certificato previsto sia associato correttamente al binding HTTPS.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

