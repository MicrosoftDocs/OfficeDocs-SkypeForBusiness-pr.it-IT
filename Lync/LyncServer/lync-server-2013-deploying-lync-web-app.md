---
title: 'Lync Server 2013: distribuzione di Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7415be2210e6c791434ced8af8f309b49603e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Distribuzione di Lync Web App in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-18_

Lync Web App è un client Web Internet Information Services (IIS) che viene installato con Lync Server 2013 ed è abilitato per impostazione predefinita. Non sono necessarie altre procedure per abilitare Lync Web App sul server o distribuire il client Web agli utenti. Ogni volta che un utente fa clic su un URL di riunione ma non è installato il client Lync 2013, l'utente viene presentato con l'opzione di partecipare alla riunione usando la versione più recente di Lync Web App.

Le funzionalità vocali, video e di condivisione in Lync Web App richiedono un controllo ActiveX Microsoft. È possibile installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, ovvero la prima volta che usano Lync Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.

<div class=" ">


> [!NOTE]  
> Nelle distribuzioni di Lync Server 2013 Edge Server è necessario un proxy inverso HTTPS nella rete perimetrale per l'accesso client Lync Web App. Devi anche pubblicare URL semplici. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configurazione di server proxy inversa per Lync server 2013</A> e <A href="lync-server-2013-planning-for-simple-urls.md">pianificazione di URL semplici in Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Attivazione dell'autenticazione a più fattori per Lync Web App

La versione Lync Server 2013 di Lync Web App supporta l'autenticazione a più fattori. Oltre al nome utente e alla password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti che partecipano da reti esterne quando accedono a riunioni Lync. È possibile abilitare l'autenticazione a più fattori distribuendo il server federativo di Active Directory Federation Service (ADFS) e abilitando l'autenticazione passiva in Lync Server 2013. Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare a riunioni Lync vengono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene la sfida di nome utente e password, oltre a eventuali altri metodi di autenticazione configurati .

<div class=" ">


> [!IMPORTANT]  
> Di seguito sono riportate considerazioni importanti se si prevede di configurare ADFS per l'autenticazione a più fattori: 
> <UL>
> <LI>
> <P>L'autenticazione ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione si trovano nella stessa organizzazione o sono entrambi provenienti da un'organizzazione federata ADFS. L'autenticazione ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non lo supporta.</P>
> <LI>
> <P>Se si usano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie in bilanciamento del carico in modo che tutte le richieste del client Lync Web App vengano gestite dallo stesso server front-end.</P>
> <LI>
> <P>Quando si stabilisce un trust tra i server Lync e i server ADFS, assegnare una durata abbastanza lunga per la durata massima delle riunioni di Lync. In genere, una durata del token di 240 minuti è sufficiente.</P>
> <LI>
> <P>Questa configurazione non si applica ai client di Lync mobile.</P></LI></UL>



</div>

**Per configurare l'autenticazione a più fattori**

1.  Installare un ruolo del server federativo ADFS. Per informazioni dettagliate, vedere la guida alla distribuzione di Active Directory Federation Services 2,0 all'indirizzo<http://go.microsoft.com/fwlink/p/?linkid=267511>

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
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>Configurazione di BranchCache

La caratteristica BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con i componenti Web di Lync Web App. Per evitare problemi per gli utenti di Lync Web App, verificare che BranchCache non sia abilitato.

Per informazioni dettagliate sulla disabilitazione di BranchCache, vedere la guida alla distribuzione di BranchCache, disponibile in formato Word nell'area download Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) in e in formato HTML nella raccolta tecnica di Windows Server 2008 R2 [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Verifica della distribuzione di Lync Web App

Puoi usare il cmdlet test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza usando l'API Web Unified Communications (UCWA). Per informazioni dettagliate su questo cmdlet, vedere [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Risoluzione dei problemi di installazione del plug-in in Windows Server 2008 R2

Se l'installazione del plug-in non riesce in un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del registro di sistema DisableMSI.

**Per modificare l'impostazione di sicurezza in Internet Explorer**

1.  Aprire Internet Explorer.

2.  Fare clic su **strumenti**, su **Opzioni Internet**e quindi su **Avanzate**.

3.  Scorrere verso il basso fino alla sezione **sicurezza** .

4.  Deselezionare non **salvare pagine crittografate su disco**e quindi fare clic su **OK**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Se selezionata, questa impostazione causa anche un errore quando si prova a scaricare un allegato da Lync Web App.

    
    </div>

5.  Partecipare di più alla riunione. Il plug-in dovrebbe essere scaricato senza errori.

**Per modificare l'impostazione del registro di sistema DisableMSI**

1.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

2.  Per accedere all'editor del registro di sistema, digitare **Regedit**.

3.  Passare alla pagina\_relativa\_ai\\criteri\\\\del software\\locale\\HKEY Microsoft Windows Installer.

4.  Modificare o aggiungere la chiave del registro di sistema DisableMSI\_di tipo reg DWORD e impostarla su 0.

5.  Partecipare di più alla riunione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Piattaforme supportate di Lync Web App per Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

