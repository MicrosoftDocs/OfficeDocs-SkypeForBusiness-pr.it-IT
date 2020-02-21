---
title: "Lync Server 2013: verificare o configurare l'autenticazione e la certificazione nelle directory virtuali di IIS"
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
ms.openlocfilehash: ca51a3c597be40c679a7b131f87775876a63811d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali di IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-05-25_

Utilizzare la procedura seguente per configurare il certificato nelle directory virtuali di Internet Information Services (IIS) o verificare che il certificato sia configurato correttamente. Eseguire la procedura seguente in ogni server che esegue IIS nel pool interno di Lync Server e nei server del pool Director o Director opzionali.

<div>


> [!NOTE]  
> La procedura seguente consente di definire una procedura per richiedere un certificato combinato utilizzato per tutti gli scopi Lync Server, il sito Web interno e il sito Web esterno in IIS. Lync Server 2010 ha introdotto un set di cmdlet di Windows&nbsp;PowerShell di Lync Server Management Shell per lo scopo esplicito di gestire la richiesta di certificato, l'importazione e l'assegnazione. La procedura parte dal presupposto che ci sia un'Autorità di certificazione (CA) distribuita internamente in grado di elaborare la richiesta. Se si utilizzano certificati pubblici per gli scopi di Lync Server o la CA richiede una richiesta offline, vedere la sintassi dettagliata in questo argomento per informazioni sul parametro – output. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Per configurare l'autenticazione e i certificati nelle directory virtuali di IIS

1.  Per eseguire correttamente le operazioni seguenti, è necessario essere connessi al computer (front end server o Director) in cui sono installati i servizi Web e essere un amministratore locale. È necessario disporre delle autorizzazioni di **lettura** e **iscrizione** per l'Autorità di certificazione a cui verranno richiesti i certificati, se l'autorità di certificazione è quella dell'organizzazione. Non sono necessarie autorizzazioni per l'Autorità di certificazione se si intende configurare e inviare una richiesta di certificato offline.

2.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Gestione Internet Information Services (IIS)**.

3.  In **Gestione Internet Information Services (IIS)** selezionare **NomeServer**. In **Visualizzazione funzionalità** selezionare **Certificati server**, fare clic con il pulsante destro del mouse e scegliere **Apri funzionalità**.
    
    <div>
    

    > [!TIP]  
    > Eventuali certificati assegnati al server appariranno nella visualizzazione delle funzionalità dei certificati server. Se un certificato corrisponde ai requisiti del sito Web esterno in IIS, è possibile riutilizzarlo. Per visualizzare un certificato, fare clic con il pulsante destro del mouse su di esso e scegliere <STRONG>Visualizza</STRONG>

    
    </div>

4.  Nel server front-end o nel Director che si desidera richiedere il certificato, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

5.  In Lync Server Management Shell, digitare quanto segue:
    
        Get-CsCertificate
    
    L'output è dato da un elenco dei certificati attualmente presenti nel server nell'archivio certificati personali del computer. Si noti che nel caso di un certificato combinato, in cui i servizi Web interni ed esterni predefiniti utilizzano lo stesso certificato, il valore della proprietà Use sarà Default, WebServicesInternal e WebServicesExternal. Inoltre, la proprietà Thumbprint sarà uguale per ogni tipo di Use. Di seguito viene mostrato un output di esempio per Get-CsCertificate.
    
    ![Get-CsCertificate info sullo stato SCERT corrente](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info sullo stato SCERT corrente")

6.  In Lync Server Management Shell, digitare quanto segue:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Dove il comando completo sarà simile all'esempio seguente:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Per impostazione predefinita, Request-CsCertificate inserirà nel nome soggetto il nome del server o del pool e nelle voci del nome soggetto alternativo gli FQDN del server, del pool, degli URL semplici e dei servizi Web interni ed esterni facendo riferimento al documento relativo alla topologia presente nella distribuzione. Se si specifica il parametro –Verbose nel caso di un valore mancante, l'utente verrà informato che i valori calcolati ed effettivi dei nomi alternativi sono diversi, ma non di quali siano i valori mancanti. All'utente viene fornito il valore intero calcolato cui fa riferimento il cmdlet. Utilizzare la stringa dei nomi alternativi calcolati nell'output per richiedere un nuovo certificato che includa tutti i valori.

    
    </div>
    
    ![Output dalla richiesta CERT tramite Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output dalla richiesta CERT tramite Request-CsCertifica")

7.  In Lync Server Management Shell, digitare quanto segue:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Dove il comando completo sarà simile all'esempio seguente:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    L'output del cmdlet Set-CsCertificate mostrerà che lo stesso certificato (con identificazione digitale) viene assegnato per l'utilizzo di Default, WebServicesExternal e WebServicesInternal.
    
    ![Output da Set-CsCertificate in IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output da Set-CsCertificate in IIS WebExt")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Per verificare o configurare l'autenticazione e i certificati nelle directory virtuali di IIS

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Gestione Internet Information Services (IIS)**.

2.  In **Gestione Internet Information Services (IIS)** espandere **nomeserver**e quindi espandere **siti**.

3.  Fare clic con il pulsante destro del mouse su **Lync Server External Web Site** e quindi scegliere **Modifica binding**.

4.  Verificare che https sia associato alla porta 4443 e quindi fare clic su **https**.

5.  Selezionare la voce HTTPS, fare clic su **modifica**e quindi verificare che Lync Server WebServicesExternalCertificate sia associato a questo protocollo. Confrontare l'identificazione digitale fornita dal cmdlet Set-CsCertificate per essere certi che il certificato previsto sia correttamente associato con binding HTTPS.

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

