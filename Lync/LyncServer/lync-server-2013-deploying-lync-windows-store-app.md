---
title: "Lync Server 2013: distribuzione dell'app Lync Windows Store"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de478ddf104f36fc208f2773c26c772b2cc0addd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Distribuzione di Lync Windows Store app in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-03_

Prima di rendere disponibile l'app Windows Store di Lync per gli utenti, verificare che la distribuzione soddisfi i [requisiti delle app di Windows Store per Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Per informazioni dettagliate sulla configurazione di Lync Server 2013 per il supporto delle app di Windows Store di Lync, vedere l'articolo del Blog di NextHop "individuazione automatica di Lync Server e [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966)l'app Lync Windows Store" all'indirizzo. Dopo che l'ambiente server è stato configurato correttamente, è possibile indirizzare gli utenti a scaricare l'app Lync da Windows Store eseguendo una ricerca per "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Abilitazione dell'autenticazione a più fattori per l'app Windows Store di Lync

Aggiornamenti cumulativi per Lync Server 2013: giugno 2013 aggiunge il supporto per l'autenticazione a più fattori per i client delle app di Windows Store di Lync. Oltre a nome utente e password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti esterni quando eseguono l'accesso alle riunioni di Lync. Per abilitare l'autenticazione a più fattori, è necessario distribuire il server federativo di Active Directory Federation Services (ADFS) e abilitare l'autenticazione passiva in Lync Server 2013. Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare alle riunioni di Lync sono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene il nome utente e la sfida per la password insieme a tutti i metodi di autenticazione aggiuntivi che sono stati configurati. .

<div class=" ">


> [!IMPORTANT]  
> Di seguito sono riportate considerazioni importanti se si prevede di configurare ad FS per l'autenticazione a più fattori per l'app Windows Store di Lync: 
> <UL>
> <LI>
> <P>Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: il numero di giugno 2013 è necessario almeno. I client desktop Lync 2013 non richiedono aggiornamenti cumulativi per Lync Server 2013: giugno 2013, pertanto potrebbe sembrare che l'autenticazione passiva funzioni perché i client di Lync 2013 sono in grado di eseguire l'autenticazione. Tuttavia, il processo di autenticazione per i client app di Windows Store di Lync non verrà completato e non verrà visualizzato alcun messaggio di errore o notifica.</P>
> <LI>
> <P>Il server deve essere configurato in modo che l'autenticazione passiva sia l'unico tipo di autenticazione offerto.</P>
> <LI>
> <P>Se si utilizzano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie sui bilanciamento del carico in modo che tutte le richieste provenienti dal client app Lync Windows Store siano gestite dallo stesso front end server.</P>
> <LI>
> <P>Quando si stabilisce una relazione di trust relying party tra Lync Server e i server AD FS, assegnare una durata del token sufficiente a coprire la lunghezza massima delle riunioni di Lync. 240 minuti in genere sono una durata sufficiente per i token.</P></LI></UL>



</div>

**Per configurare l'autenticazione a più fattori**

1.  Installare un ruolo del server federativo ADFS. Per informazioni dettagliate, vedere la guida alla distribuzione di Active Directory Federation <https://go.microsoft.com/fwlink/p/?linkid=267511>Services 2,0 all'indirizzo.

2.  Creare certificati per ADFS. Per ulteriori informazioni, vedere la sezione relativa ai certificati del server federativo del piano per la distribuzione di ADFS per l'utilizzo con l'argomento Single Sign- [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)on all'indirizzo.

3.  Dall'interfaccia della riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Stabilire una relazione eseguendo il comando seguente:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  Impostare le regole di relying party seguenti:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Problemi noti che possono impedire l'accesso

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>La data e l'ora non vengono impostate con precisione sul dispositivo che esegue Lync Windows Store app

L'impostazione relativa all'ora del dispositivo deve essere sincronizzata con l'impostazione relativa all'ora sul server. Questo è particolarmente importante per i dispositivi come Microsoft Surface e altri dispositivi che eseguono Windows RT che non sono aggiunti a un dominio. Per impostare automaticamente l'ora su questi dispositivi da un server di tempo, eseguire il comando seguente da un prompt dei comandi con privilegi elevati nel dispositivo:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>L'app Lync Windows Store non è in grado di accedere al server o ai servizi Lync

L'app Lync Windows Store potrebbe non essere in grado di accedere a Lync Server o ai servizi tramite schede di rete, ad esempio i modem USB 4G LTE, che non sono registrati con Windows 8 come dispositivi fisici. L'app Lync Windows Store può avere questo problema anche quando le app e i browser desktop sono in grado di accedere ad altri server e siti Web.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>L'app Lync Windows Store non è in grado di accedere con Lync Server 2010 e il server perimetrale di Office Communications Server 2007 R2

Se la topologia è costituita da Lync Server 2010 con Office Communications Server 2007 R2 Edge Server, sarà necessario eseguire la versione aggiornata di generatore di topologie disponibile nell'aggiornamento cumulativo per Lync Server 2010: luglio 2013. Le versioni precedenti del generatore di topologie non creano il mapping necessario a Office Communications Server 2007 Edge Server, quindi i client app di Lync Windows Store non sono in grado di eseguire l'accesso. Sono necessari i passaggi seguenti:

1.  Installare l'aggiornamento cumulativo per Lync Server 2010: luglio 2013 nei pool Lync Server 2010 e nei direttori di Lync Server 2010.

2.  Aggiornare la configurazione di individuazione automatica di Lync per indicare che il punto di ingresso SIP esterno è l'indirizzo del server perimetrale eseguendo le operazioni seguenti:
    
    1.  Aprire Lync Server Management Shell.
    
    2.  Eseguire il comando riportato di seguito:
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>L'app Lync Windows Store non è in grado di accedere a causa di un errore di convalida del nome del certificato

È possibile che si verifichi un problema di accesso per gli utenti di Office 365 che non eseguono la versione più recente dell'app Lync Windows Store. Questo problema si verifica in genere quando si utilizzano più domini (ad esempio, quando l'URI SIP è **usera@domainZ.com** ma il server perimetrale è **SIP.domainX.com**). Per risolvere il problema, è necessario che gli utenti installino la versione più recente dell'app Lync Windows Store, che richiede anche Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Utilizzare i registri delle app di Windows Store di Lync per risolvere i problemi

È possibile utilizzare i registri generati nel dispositivo per risolvere i problemi. I registri sono archiviati nella cartella seguente:

% LocalAppData%\\Packages\\Microsoft.\_LyncMX\\8wekyb3d8bbwe\\traccia LocalState

Prima di ottenere i log da un utente, verificare che la registrazione sia attivata e quindi chiedere all'utente di salvare i registri in modo che tutte le informazioni archiviate in memoria vengano salvate anche nei file nel disco rigido.

**Per abilitare la registrazione**

1.  Aprire l'app Lync Windows Store nel dispositivo.

2.  Scorrere rapidamente dal lato destro dello schermo. Se si utilizza un mouse, puntare l'angolo in alto a destra dello schermo e quindi spostare il puntatore del mouse verso il basso sullo schermo.

3.  Selezionare **Impostazioni**, fare clic su **Opzioni**e quindi impostare i **registri diagnostici** **su**attivato.

4.  Se i **log diagnostici** erano spenti in precedenza, è necessario riavviare Lync. Per riavviare Lync, effettuare una delle seguenti operazioni:
    
      - Riavviare il dispositivo.
    
      - Terminare l'attività Lync e avviare di nuovo l'applicazione. Per terminare l'attività, aprire Gestione attività di Windows, selezionare **Lync**e quindi toccare **Termina attività**. Se Lync non è elencato, toccare **altre informazioni** e cercare Lync in **processi in background**.

**Per salvare i registri**

1.  Aprire l'app Lync Windows Store nel dispositivo.

2.  Provare a eseguire l'accesso.

3.  Scorrere rapidamente dal lato destro dello schermo. Se si utilizza un mouse, puntare l'angolo in alto a destra dello schermo e quindi spostare il puntatore del mouse verso il basso sullo schermo.

4.  Selezionare **Impostazioni**, quindi fare clic **su**, quindi selezionare **Salva registri**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

