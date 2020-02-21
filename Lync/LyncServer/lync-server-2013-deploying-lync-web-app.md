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
ms.openlocfilehash: 8babb6bf37e3dd75f2051dd08f0b2ebf3a4f093b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Distribuzione di Lync Web App in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-18_

Lync Web App è un client Web di Internet Information Services (IIS) che viene installato con Lync Server 2013 ed è abilitato per impostazione predefinita. Non è necessario eseguire ulteriori passaggi per abilitare Lync Web App nel server o distribuire il client Web agli utenti. Ogni volta che un utente fa clic su un URL di riunione ma non è installato il client Lync 2013, all'utente viene presentata la possibilità di partecipare alla riunione utilizzando la versione più recente di Lync Web App.

Le funzionalità vocali, video e di condivisione in Lync Web App richiedono un controllo ActiveX Microsoft. È possibile installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, ovvero la prima volta che si utilizza Lync Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.

<div class=" ">


> [!NOTE]  
> Nelle distribuzioni di Lync Server 2013 Edge Server, è necessario un proxy inverso HTTPS nella rete perimetrale per l'accesso client di Lync Web App. È inoltre necessario pubblicare gli URL semplici. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync server 2013</A> e <A href="lync-server-2013-planning-for-simple-urls.md">Planning for Simple URLs in Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Abilitazione dell'autenticazione a più fattori per Lync Web App

La versione Lync Server 2013 di Lync Web App supporta l'autenticazione a più fattori. Oltre a nome utente e password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti che si congiungono da reti esterne quando eseguono l'accesso alle riunioni di Lync. È possibile abilitare l'autenticazione a più fattori mediante la distribuzione del server federativo di Active Directory Federation Services (ADFS) e l'abilitazione dell'autenticazione passiva in Lync Server 2013. Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare alle riunioni di Lync sono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene il nome utente e la sfida per la password insieme a tutti i metodi di autenticazione aggiuntivi che sono stati configurati. .

<div class=" ">


> [!IMPORTANT]  
> Se si intende configurare ADFS per l'autenticazione a più fattori, è importante considerare quanto segue: 
> <UL>
> <LI>
> <P>L'autenticazione di ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione sono entrambi presenti nella stessa organizzazione o sono entrambi provenienti da un'organizzazione federata ADFS. L'autenticazione ad ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non lo supporta.</P>
> <LI>
> <P>Se si utilizzano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie sui bilanciamento del carico in modo che tutte le richieste provenienti dal client Lync Web App siano gestite dallo stesso front end server.</P>
> <LI>
> <P>Quando si stabilisce una relazione di trust relying party tra Lync Server e i server AD FS, assegnare una durata del token sufficiente a coprire la lunghezza massima delle riunioni di Lync. 240 minuti in genere sono una durata sufficiente per i token.</P>
> <LI>
> <P>Questa configurazione non è valida per i client mobili di Lync.</P></LI></UL>



</div>

**Per configurare l'autenticazione a più fattori**

1.  Installare un ruolo del server federativo ADFS. Per informazioni dettagliate, vedere la guida alla distribuzione di Active Directory Federation Services 2,0 all'indirizzo<https://go.microsoft.com/fwlink/p/?linkid=267511>

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

La funzionalità BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con i componenti Web di Lync Web App. Per evitare problemi per gli utenti di Lync Web App, verificare che BranchCache non sia abilitato.

Per informazioni dettagliate sulla disabilitazione di BranchCache, vedere la guida alla distribuzione di BranchCache, disponibile in formato Word nell'area download Microsoft [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) all'interno e in formato HTML nella raccolta tecnica di Windows Server 2008 [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789)R2 all'indirizzo.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Verifica della distribuzione di Lync Web App

È possibile utilizzare il cmdlet Test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza tramite UCWA (Unified Communications Web API). Per informazioni dettagliate su questo cmdlet, vedere [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Risoluzione dei problemi relativi all'installazione del plug-in in Windows Server 2008 R2

Se l'installazione del plug-in ha esito negativo su un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del registro di sistema DisableMSI.

**Per modificare l'impostazione di sicurezza in Internet Explorer**

1.  Aprire Internet Explorer.

2.  Fare clic su **Strumenti**, su **Opzioni Internet** e quindi su **Avanzate**.

3.  Scorrere verso il basso fino alla sezione **Sicurezza**.

4.  Deselezionare **Non salvare pagine crittografate su disco** e quindi fare clic su **OK**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Se si seleziona questa opzione, si verificherà un errore anche quando si tenta di scaricare un allegato da Lync Web App.

    
    </div>

5.  Tornare a partecipare alla riunione. Il download del plug-in dovrebbe avere luogo senza errori.

**Per modificare l'impostazione DisableMSI del Registro di sistema**

1.  Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2.  Per accedere all'editor del Registro di sistema, digitare **regedit**.

3.  Accedere a criteri\_\\software\_\\del\\computer locale di\\HKEY\\Microsoft Windows Installer.

4.  Modificare o aggiungere la chiave del registro di sistema DisableMSI\_di tipo reg DWORD e impostarla su 0.

5.  Tornare a partecipare alla riunione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Web App piattaforme supportate per Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

