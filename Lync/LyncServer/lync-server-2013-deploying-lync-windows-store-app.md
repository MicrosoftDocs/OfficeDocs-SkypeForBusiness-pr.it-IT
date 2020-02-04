---
title: "Lync Server 2013: distribuzione dell'app Lync di Windows Store"
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
ms.openlocfilehash: 49fcea107a4613ca78661a21d492612f82d9775f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Distribuzione dell'app Lync di Windows Store in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-03_

Prima di rendere disponibile l'app Lync di Windows Store agli utenti, assicurati che la distribuzione soddisfi i [requisiti dell'app Lync di Windows Store per Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Per informazioni dettagliate sulla configurazione di Lync Server 2013 per il supporto dell'app Lync di Windows Store, vedere l'articolo su Blog di NextHop "individuazione automatica Lync Server e l'app [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Lync Windows Store". Dopo aver configurato correttamente l'ambiente server, è possibile indirizzare gli utenti a scaricare l'app Lync da Windows Store cercando "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Abilitare l'autenticazione a più fattori per l'app Lync di Windows Store

Aggiornamenti cumulativi per Lync Server 2013: giugno 2013 aggiunge il supporto per l'autenticazione a più fattori per i client delle app Lync di Windows Store. Oltre al nome utente e alla password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti esterni quando accedono alle riunioni Lync. Per abilitare l'autenticazione a più fattori, distribuire il server federativo di Active Directory Federation Service (ADFS) e abilitare l'autenticazione passiva in Lync Server 2013. Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare a riunioni Lync vengono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene la sfida di nome utente e password, oltre a eventuali altri metodi di autenticazione configurati .

<div class=" ">


> [!IMPORTANT]  
> Di seguito sono riportate considerazioni importanti se si prevede di configurare ADFS per l'autenticazione a più fattori per l'app Lync di Windows Store: 
> <UL>
> <LI>
> <P>Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013:2013 giugno è necessario almeno. I client desktop di Lync 2013 non richiedono aggiornamenti cumulativi per Lync Server 2013: giugno 2013, quindi potrebbe sembrare che l'autenticazione passiva funzioni perché i client di Lync 2013 possono eseguire l'autenticazione. Tuttavia, il processo di autenticazione per i client delle app Lync di Windows Store non verrà completato e non verrà visualizzata alcuna notifica o messaggio di errore.</P>
> <LI>
> <P>Il server deve essere configurato in modo che l'autenticazione passiva sia l'unico tipo di autenticazione disponibile.</P>
> <LI>
> <P>Se si usano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie in bilanciamento del carico in modo che tutte le richieste del client dell'app Lync di Windows Store vengano gestite dallo stesso server front-end.</P>
> <LI>
> <P>Quando si stabilisce un trust tra i server Lync e i server ADFS, assegnare una durata abbastanza lunga per la durata massima delle riunioni di Lync. In genere, una durata del token di 240 minuti è sufficiente.</P></LI></UL>



</div>

**Per configurare l'autenticazione a più fattori**

1.  Installare un ruolo del server federativo ADFS. Per informazioni dettagliate, vedere la guida alla distribuzione di <http://go.microsoft.com/fwlink/p/?linkid=267511>Active Directory Federation Services 2,0.

2.  Creare certificati per ADFS. Per altre informazioni, vedere la sezione "certificati del server federativo" del piano per e distribuire ADFS per l'uso con l'argomento Single Sign-on [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Dall'interfaccia della riga di comando di Windows PowerShell eseguire il comando seguente:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Creare una partnership eseguendo il comando seguente:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  Impostare le regole del componente seguenti:
    
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

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>La data e l'ora non sono impostate in modo accurato nel dispositivo che esegue Lync Windows Store app

L'impostazione dell'ora nel dispositivo deve essere sincronizzata con l'impostazione dell'ora nel server. Questo aspetto è particolarmente importante per i dispositivi come Microsoft Surface e altri dispositivi che usano Windows RT non collegati a un dominio. Per impostare automaticamente l'ora di questi dispositivi da un server temporale, eseguire il comando seguente da un prompt dei comandi con privilegi elevati nel dispositivo:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>L'app Lync di Windows Store non può accedere al server o ai servizi Lync

L'app Lync di Windows Store potrebbe non essere in grado di accedere a Lync Server o ai servizi tramite schede di rete, ad esempio i modem USB 4G LTE, che non si registrano in Windows 8 come dispositivi fisici. L'app Lync di Windows Store potrebbe avere questo problema anche quando le app e i browser desktop sono in grado di accedere ad altri server e siti Web.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>L'app Lync di Windows Store non riesce ad accedere con Lync Server 2010 e Office Communications Server 2007 R2 Edge Server

Se la topologia è costituita da Lync Server 2010 con Office Communications Server 2007 R2 Edge Server, sarà necessario eseguire la versione aggiornata di generatore di topologia disponibile nell'aggiornamento cumulativo per Lync Server 2010: luglio 2013. Le versioni precedenti di generatore di topologie non creano il mapping obbligatorio a Office Communications Server 2007 Edge Server, quindi i client delle app Lync di Windows Store non riescono ad accedere. I passaggi seguenti sono obbligatori:

1.  Installare l'aggiornamento cumulativo per Lync Server 2010: luglio 2013 nei pool di Lync Server 2010 e nei direttori di Lync Server 2010.

2.  Aggiornare la configurazione di individuazione automatica di Lync per indicare che il punto di ingresso SIP esterno è l'indirizzo del server perimetrale eseguendo le operazioni seguenti:
    
    1.  Aprire Lync Server Management Shell.
    
    2.  Eseguire il comando seguente:
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>L'app Lync di Windows Store non può accedere a causa di un errore di convalida dei nomi di certificato

Un problema di accesso può verificarsi per gli utenti di Office 365 che non hanno eseguito l'ultima versione dell'app Lync di Windows Store. Questo problema si verifica in genere quando si usano più domini, ad esempio quando l'URI SIP è **usera@domainZ.com** , ma il server perimetrale è **SIP.domainX.com**. Per risolvere il problema, gli utenti devono installare la versione più recente dell'app Lync di Windows Store, che richiede anche Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Usare i registri delle app Lync di Windows Store per risolvere i problemi

È possibile usare i registri generati nel dispositivo per la risoluzione dei problemi. I registri sono archiviati nella cartella seguente:

% LocalAppData%\\Packages\\Microsoft.\_LyncMX\\8wekyb3d8bbwe\\LocalState Tracing

Prima di ottenere i log da un utente, verificare che la registrazione sia attivata e quindi chiedere all'utente di salvare i registri in modo che tutte le informazioni archiviate in memoria vengano salvate anche nei file del disco rigido.

**Per attivare la registrazione**

1.  Aprire l'app Lync di Windows Store nel dispositivo.

2.  Scorrere rapidamente dal lato destro dello schermo. Se si usa un mouse, posizionare il puntatore sull'angolo in alto a destra dello schermo e quindi spostare il cursore del mouse sullo schermo.

3.  Selezionare **Impostazioni**, **Opzioni**e quindi imposta log di **diagnostica** **su**attivato.

4.  Se i **registri diagnostici** erano spenti in precedenza, è necessario riavviare Lync. Per riavviare Lync, eseguire una delle operazioni seguenti:
    
      - Riavviare il dispositivo.
    
      - Terminare l'attività di Lync e avviare di nuovo l'app. Per terminare l'attività, aprire Gestione attività di Windows, selezionare **Lync**e quindi toccare **Termina attività**. Se Lync non è elencato, toccare **altri dettagli** e cercare Lync in **processi in background**.

**Per salvare i registri**

1.  Aprire l'app Lync di Windows Store nel dispositivo.

2.  Provare a eseguire l'accesso.

3.  Scorrere rapidamente dal lato destro dello schermo. Se si usa un mouse, posizionare il puntatore sull'angolo in alto a destra dello schermo e quindi spostare il cursore del mouse sullo schermo.

4.  Selezionare **Impostazioni**, quindi selezionare **informazioni su**e quindi **Salva registri**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

