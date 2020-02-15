---
title: Distribuire i client scaricabili Web in Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: "Riepilogo: distribuire l'app Skype for Business Web App e le riunioni Skype utilizzate con Skype for business."
ms.openlocfilehash: 7f6bebbc9950a7eb5da202c3b818b1288c811f17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029047"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Distribuire i client scaricabili Web in Skype for Business Server

**Riepilogo:** Distribuire l'app Skype for business 2015 Web App e le riunioni Skype utilizzate con Skype for Business Server.

Skype for Business Web App è un client Web di Internet Information Services (IIS) installato nel server che esegue Skype for Business Server e, per impostazione predefinita, viene distribuito su richiesta per soddisfare gli utenti che non dispongono già del client Skype for business. Questi utenti di riunioni sono più spesso di quanto non si connettono dall'esterno della rete. Ogni volta che un utente fa clic su un URL di riunione ma non è installato il client Skype for business, l'utente viene presentato con la possibilità di partecipare alla riunione usando la versione più recente di Skype for Business Web App, Skype Meetings app o Skype for business per Mac.

Le funzionalità vocali, video e di condivisione in Skype for Business Web App richiedono un controllo ActiveX Microsoft utilizzato come plug-in dal browser dell'utente. È possibile installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, ovvero la prima volta che utilizzano Skype for Business Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.

> [!NOTE]
> Nelle distribuzioni di Skype for Business Server Edge Server, è necessario un proxy inverso HTTPS nella rete perimetrale per l'accesso client Skype for Business Web App. È inoltre necessario pubblicare gli URL semplici. Per informazioni dettagliate, vedere [configurare i server proxy inversi](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) e i [requisiti DNS per gli URL semplici in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Abilitare l'autenticazione a più fattori per Skype for Business Web App
<a name="MFA"> </a>

Skype for Business Web App, Skype Meetings app e Skype for business per Mac supportano l'autenticazione a più fattori. Oltre a nome utente e password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti che si congiungono da reti esterne quando eseguono l'accesso alle riunioni di Skype for business. È possibile abilitare l'autenticazione a più fattori distribuendo il server federativo di Active Directory Federation Services (ADFS) e l'abilitazione dell'autenticazione passiva in Skype for Business Server. Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare alle riunioni di Skype for business sono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene il nome utente e la sfida per la password insieme a tutti i metodi di autenticazione aggiuntivi che sono stati sono state configurate.

> [!IMPORTANT]
> Se si intende configurare ADFS per l'autenticazione a più fattori, è importante considerare quanto segue:

- L'autenticazione di ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione sono entrambi presenti nella stessa organizzazione o sono entrambi provenienti da un'organizzazione federata ADFS. L'autenticazione ad ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non lo supporta.

- Se si utilizzano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie sui bilanciamento del carico in modo che tutte le richieste provenienti dai client app Skype for Business Web App o meeting siano gestite dallo stesso front end server.

- Quando si stabilisce una relazione di trust relying party tra i server di Skype for Business Server e AD FS, assegnare una durata del token sufficiente a coprire la durata massima delle riunioni di Skype for business. 240 minuti in genere sono una durata sufficiente per i token.

- Questa configurazione non è valida per i client mobili di Lync.

### <a name="configure-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori

1. Installare un ruolo del server federativo ADFS. Per informazioni dettagliate, vedere la [Guida alla distribuzione di Active Directory Federation Services 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Creare certificati per ADFS. Per ulteriori informazioni, vedere la sezione relativa ai [certificati del server federativo](https://go.microsoft.com/fwlink/p/?LinkId=285376) del piano per e deploy ad FS per l'utilizzo con l'argomento Single Sign-on.

3. Dall'interfaccia della riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Stabilire una relazione eseguendo il comando seguente:

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Impostare le regole di relying party seguenti:

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Disabilitare BranchCache
<a name="MFA"> </a>

La funzionalità BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con i componenti Web di Skype for Business Web App. Per evitare problemi per gli utenti di Skype for Business Web App, verificare che BranchCache non sia abilitato.

Per informazioni dettagliate sulla disabilitazione di BranchCache, vedere la [Guida alla distribuzione di BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verifica della distribuzione di Skype for Business Web App
<a name="MFA"> </a>

È possibile utilizzare il cmdlet Test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza tramite UCWA (Unified Communications Web API). Per informazioni dettagliate su questo cmdlet, vedere [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) nella documentazione di Skype for Business Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Risoluzione dei problemi relativi all'installazione del plug-in in Windows Server 2008 R2
<a name="MFA"> </a>

Se l'installazione del plug-in ha esito negativo su un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del registro di sistema DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificare l'impostazione di sicurezza in Internet Explorer

1. Aprire Internet Explorer.

2. Fare clic su **Strumenti**, su **Opzioni Internet** e quindi su **Avanzate**.

3. Scorrere verso il basso fino alla sezione **Sicurezza**.

4. Deselezionare **Non salvare pagine crittografate su disco** e quindi fare clic su **OK**.

    > [!NOTE]
    > Se questa opzione è selezionata, questa impostazione provocherà anche un errore durante il tentativo di download di un allegato da Skype for Business Web App.

5. Tornare a partecipare alla riunione. Il download del plug-in dovrebbe avere luogo senza errori.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificare l'impostazione del registro di sistema DisableMSI

1. Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2. Per accedere all'editor del Registro di sistema, digitare **regedit**.

3. Passare a HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modificare o aggiungere la chiave DisableMSI di tipo REG_DWORD del Registro di sistema e impostarla su 0.

5. Tornare a partecipare alla riunione.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Abilitazione dell'app per le riunioni Skype per sostituire Skype for Business Web App (facoltativo, solo Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Questa procedura è facoltativa e si applica a Skype for Business Server 2015 CU5 e versioni successive. Se non lo si utilizza, gli utenti esterni continueranno a partecipare alle riunioni utilizzando Skype for Business Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Abilitazione dell'app riunioni semplificate di join e Skype meeting

1. Quando si Abilita l'accesso alla rete di distribuzione del contenuto (CDN), gli utenti avranno la possibilità di connettersi a CDN online e di ricevere le app per riunioni Skype (su Windows) e Skype for business per Mac (su Mac) e utilizzeranno l'esperienza di partecipazione alla riunione semplificata.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Consenti la telemetria di registrazione laterale client dalla pagina Web di partecipazione alle riunioni o l'app Skype Meetings da inviare ai server Microsoft (il comando predefinito è false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Le informazioni inviate a Microsoft sono rigorosamente conformi alle [procedure di raccolta dei dati di Skype for business](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Impostare il timeout prima di ricadere nell'esperienza di Skype for Business Web App localmente ospitata se la rete CDN non è disponibile. Il valore predefinito è 6 secondi. Se questo valore è impostato su 0, non vi sarà alcun timeout.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Con MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, il valore predefinito è impostato su false. Questo causa un problema per il quale il client Skype for business per Mac non è in grado di partecipare alle riunioni dei partner non federati come Guest, anche se l'amministratore di Skype for business ha impostato MeetingUxUseCdn su true. Affinché ciò funzioni, Skype for Business Server 2015 deve disporre dell'aggiornamento cumulativo 7, 6.0.9319.534 o versione successiva. Vedere [Enable Skype Meetings app to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Vedere anche
<a name="SMA_Enable"> </a>

[Pianificare i client di riunioni (app per le riunioni e le app Web)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurare la pagina di partecipazione alle riunioni in Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Informativa sulla privacy di Microsoft Online Services](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Termini e documentazione sulle licenze](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
