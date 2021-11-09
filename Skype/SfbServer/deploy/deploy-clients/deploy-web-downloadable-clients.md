---
title: Distribuire client scaricabili Web in Skype for Business Server
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: "Riepilogo: distribuire l'app Skype for Business Web App e Skype riunioni usata con Skype for Business."
ms.openlocfilehash: abb0a24d234043d793b09a538cbff23d0d549ac0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842498"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Distribuire client scaricabili Web in Skype for Business Server

**Riepilogo:** Distribuisci l Skype for Business App Web 2015 e l Skype App riunioni usata con Skype for Business Server.

Skype for Business Web App è un client Web Internet Information Services (IIS) installato nel server che esegue Skype for Business Server e per impostazione predefinita viene distribuito su richiesta agli utenti che non dispongono già del client Skype for Business. Questi utenti di riunioni si connettono più spesso che non si connettono dall'esterno della rete. Ogni volta che un utente fa clic sull'URL di una riunione ma non ha installato il client Skype for Business, all'utente viene presentata l'opzione per partecipare alla riunione utilizzando la versione più recente di Skype for Business Web App, Skype Meetings App o Skype for Business per Mac.

Le funzionalità vocali, video e di condivisione in Skype for Business Web App richiedono un controllo microsoft ActiveX utilizzato come plug-in dal browser dell'utente. È possibile installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, cosa che avviene la prima volta che usano Skype for Business Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.

> [!NOTE]
> Nelle Skype for Business Server server perimetrali è necessario un proxy inverso HTTPS nella rete perimetrale per Skype for Business Web App accesso client. È inoltre necessario pubblicare gli URL semplici. Per informazioni dettagliate, [vedere Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and DNS requirements for simple [URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Abilitare l'autenticazione a più fattori per Skype for Business Web App
<a name="MFA"> </a>

Skype for Business Web App, Skype'app Riunioni e Skype for Business per Mac supportano l'autenticazione a più fattori. Oltre al nome utente e alla password, è possibile richiedere metodi di autenticazione aggiuntivi, ad esempio smart card o PIN, per autenticare gli utenti che si uniscono da reti esterne quando aseguono Skype for Business riunioni. È possibile abilitare l'autenticazione a più fattori distribuendo il server federativo Active Directory Federation Service (AD FS) e abilitando l'autenticazione passiva in Skype for Business Server. Dopo la configurazione di ADFS, agli utenti esterni che tentano di partecipare alle riunioni di Skype for Business viene presentata una pagina Web di autenticazione Skype for Business più fattori di AD FS che contiene il nome utente e la password di verifica insieme a eventuali metodi di autenticazione aggiuntivi configurati.

> [!IMPORTANT]
> Se si intende configurare ADFS per l'autenticazione a più fattori, è importante considerare quanto segue:

- L'autenticazione ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione sono entrambi nella stessa organizzazione o sono entrambi di un'organizzazione federata AD FS. L'autenticazione ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non la supporta.

- Se si utilizzano servizi di bilanciamento del carico hardware, abilitare la persistenza dei cookie nei servizi di bilanciamento del carico in modo che tutte le richieste provenienti dai client dell'app Skype for Business Web App o riunioni siano gestite dallo stesso Front End Server.

- Quando si stabilisce un trust della relying party tra i server Skype for Business Server e AD FS, assegnare una durata token sufficientemente lunga per la durata massima delle riunioni Skype for Business riunioni. 240 minuti in genere sono una durata sufficiente per i token.

- Questa configurazione non si applica ai client mobili Lync.

### <a name="configure-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori

1. Installare un ruolo del server federativo ADFS. Per informazioni dettagliate, vedere la [Guida alla distribuzione di Active Directory Federation Services 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. Creare certificati per ADFS. Per ulteriori informazioni, vedere [la sezione "Certificati server](/previous-versions/azure/azure-services/jj205462(v=azure.100)) federativi" dell'argomento Pianificare e distribuire ADFS per l'utilizzo con Single Sign-on.

3. Dall'Windows PowerShell della riga di comando, eseguire il comando seguente:

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

La funzionalità BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con Skype for Business Web App Web. Per evitare problemi per Skype for Business Web App utenti, assicurati che BranchCache non sia abilitato.

Per informazioni dettagliate sulla disabilitazione di BranchCache, vedere [la Guida alla distribuzione di BranchCache.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verifica della Skype for Business Web App distribuzione
<a name="MFA"> </a>

È possibile utilizzare il cmdlet Test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza tramite UCWA (Unified Communications Web API). Per informazioni dettagliate su questo cmdlet, vedere [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) nella documentazione Skype for Business Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Risoluzione dei problemi relativi all'installazione di plug-in Windows Server 2008 R2
<a name="MFA"> </a>

Se l'installazione del plug-in non riesce in un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del Registro di sistema DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificare l'impostazione di sicurezza in Internet Explorer

1. Aprire Internet Explorer.

2. Fare clic su **Strumenti**, su **Opzioni Internet** e quindi su **Avanzate**.

3. Scorrere verso il basso fino alla sezione **Sicurezza**.

4. Deselezionare **Non salvare pagine crittografate su disco** e quindi fare clic su **OK**.

    > [!NOTE]
    > Se selezionata, questa impostazione causerà un errore anche quando si tenta di scaricare un allegato da Skype for Business Web App.

5. Tornare a partecipare alla riunione. Il download del plug-in dovrebbe avere luogo senza errori.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificare l'impostazione DisableMSI Registry

1. Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2. Per accedere all'editor del Registro di sistema, digitare **regedit**.

3. Passare a HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modificare o aggiungere la chiave DisableMSI di tipo REG_DWORD del Registro di sistema e impostarla su 0.

5. Tornare a partecipare alla riunione.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Abilita Skype'app Riunioni per sostituire Skype for Business Web App (facoltativo, Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Questa procedura è facoltativa e si applica Skype for Business Server 2015 CU5 e versioni successive. Se non viene utilizzato, gli utenti esterni continueranno a partecipare alle riunioni Skype for Business Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Abilitare la partecipazione semplificata alle riunioni e Skype'app Riunioni

1. Quando abiliti l'accesso al rete per la distribuzione di contenuti (rete CDN), gli utenti potranno connettersi a rete CDN online e ottenere l'app riunioni Skype (su Windows) e Skype for Business per Mac (su Mac) e verrà utilizzata l'esperienza semplificata di partecipazione alle riunioni.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Consenti l'invio ai server Microsoft della telemetria della registrazione sul lato client dalla pagina Web di partecipazione alla riunione o dall'app riunioni di Skype (il comando è impostato su false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Le informazioni inviate a Microsoft sono conformi alle procedure Skype for Business [raccolta dei dati.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Imposta il timeout prima del fall back sull'esperienza di Skype for Business Web App locale se rete CDN non è disponibile. Il valore predefinito è 6 secondi. Se questo valore è impostato su 0, non vi sarà alcun timeout.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Con MeetingUxUseCdn nell'Skype for Business Server 2015 cumulativo 5, il valore predefinito è impostato su False. Ciò causa un problema per cui Skype for Business per Mac client non è in grado di partecipare alle riunioni dei partner non federati come guest, anche se l'amministratore di Skype for Business ha impostato MeetingUxUseCdn su True. Per il funzionamento, Skype for Business Server 2015 deve disporre dell'aggiornamento cumulativo 7, 6.0.9319.534 o versione successiva. Vedere [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015.](https://support.microsoft.com/kb/4132312)


## <a name="see-also"></a>Vedere anche
<a name="SMA_Enable"> </a>

[Pianificare i client riunioni (App Web e app Riunioni)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurare la pagina di partecipazione alla riunione in Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Informativa sulla privacy di Microsoft Online Services](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Condizioni di licenza e documentazione](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)