---
title: Distribuire client scaricabili Web in Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: "Riepilogo: distribuire l'app Skype for Business Web App e le riunioni Skype usate con Skype for business."
ms.openlocfilehash: 8f2449fde2f270834bda50602fe163829f3b725f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234394"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Distribuire client scaricabili Web in Skype for Business Server

**Riepilogo:** Distribuire l'app Skype for business 2015 Web App e le riunioni Skype usate con Skype for Business Server.

Skype for Business Web App è un client Web Internet Information Services (IIS) installato nel server che esegue Skype for Business Server e per impostazione predefinita viene distribuito su richiesta per soddisfare gli utenti che non hanno già il client Skype for business. Questi utenti della riunione sono più spesso che non si connettono all'esterno della rete. Ogni volta che un utente fa clic su un URL di riunione ma non è installato il client Skype for business, l'utente viene presentato con l'opzione di partecipare alla riunione usando l'ultima versione di Skype for Business Web App, l'app riunioni Skype o Skype for business per Mac.

Le funzionalità vocali, video e di condivisione in Skype for Business Web App richiedono un controllo ActiveX Microsoft usato come plug-in dal browser dell'utente. È possibile installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, che avviene la prima volta che usano Skype for Business Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.

> [!NOTE]
> Nelle distribuzioni di Skype for Business Server Edge Server è necessario un proxy inverso HTTPS nella rete perimetrale per l'accesso client di Skype for Business Web App. Devi anche pubblicare URL semplici. Per informazioni dettagliate, vedere [configurare i server proxy inversi](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) e i [requisiti DNS per gli URL semplici in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Abilitare l'autenticazione a più fattori per Skype for Business Web App
<a name="MFA"> </a>

Skype for Business Web App, app riunioni Skype e Skype for business per Mac supportano l'autenticazione a più fattori. Oltre al nome utente e alla password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti che partecipano da reti esterne quando accedono a riunioni Skype for business. Puoi abilitare l'autenticazione a più fattori distribuendo il server federativo di Active Directory Federation Service (ADFS) e abilitando l'autenticazione passiva in Skype for Business Server. Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare a riunioni Skype for business vengono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene la sfida di nome utente e password insieme a qualsiasi altro metodo di autenticazione configurati.

> [!IMPORTANT]
> Di seguito sono riportate considerazioni importanti se si prevede di configurare ADFS per l'autenticazione a più fattori:

- L'autenticazione ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione si trovano nella stessa organizzazione o sono entrambi provenienti da un'organizzazione federata ADFS. L'autenticazione ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non lo supporta.

- Se si usano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie in bilanciamento del carico in modo che tutte le richieste provenienti dai client dell'app web Skype for business o delle riunioni vengano gestite dallo stesso server front-end.

- Quando si stabilisce un trust tra i partecipanti tra Skype for Business Server e i server ADFS, assegnare un token di durata sufficiente per la durata massima delle riunioni di Skype for business. In genere, una durata del token di 240 minuti è sufficiente.

- Questa configurazione non si applica ai client di Lync mobile.

### <a name="configure-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori

1. Installare un ruolo del server federativo ADFS. Per informazioni dettagliate, vedere la [Guida alla distribuzione di Active Directory Federation Services 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Creare certificati per ADFS. Per altre informazioni, vedere la sezione ["certificati del server federativo"](https://go.microsoft.com/fwlink/p/?LinkId=285376) del piano per e distribuire ADFS per l'uso con l'argomento Single Sign-on.

3. Dall'interfaccia della riga di comando di Windows PowerShell eseguire il comando seguente:

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Creare una partnership eseguendo il comando seguente:

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Impostare le regole del componente seguenti:

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Disabilitare BranchCache
<a name="MFA"> </a>

La caratteristica BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con i componenti Web di Skype for Business Web App. Per evitare problemi per gli utenti di Skype for Business Web App, verificare che BranchCache non sia abilitato.

Per informazioni dettagliate sulla disabilitazione di BranchCache, vedere la [Guida alla distribuzione di BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Verifica della distribuzione di Skype for Business Web App
<a name="MFA"> </a>

Puoi usare il cmdlet test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza usando l'API Web Unified Communications (UCWA). Per informazioni dettagliate su questo cmdlet, vedere [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) nella documentazione di Skype for Business Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Risoluzione dei problemi di installazione del plug-in in Windows Server 2008 R2
<a name="MFA"> </a>

Se l'installazione del plug-in non riesce in un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del registro di sistema DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificare l'impostazione di sicurezza in Internet Explorer

1. Aprire Internet Explorer.

2. Fare clic su **strumenti**, su **Opzioni Internet**e quindi su **Avanzate**.

3. Scorrere verso il basso fino alla sezione **sicurezza** .

4. Deselezionare non **salvare pagine crittografate su disco**e quindi fare clic su **OK**.

    > [!NOTE]
    > Se selezionata, questa impostazione causa anche un errore quando si prova a scaricare un allegato da Skype for Business Web App.

5. Partecipare di più alla riunione. Il plug-in dovrebbe essere scaricato senza errori.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificare l'impostazione del registro di sistema DisableMSI

1. Fare clic sul pulsante **Start**e quindi su **Esegui**.

2. Per accedere all'editor del registro di sistema, digitare **Regedit**.

3. Passare a HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modificare o aggiungere la chiave del registro di sistema DisableMSI di tipo REG_DWORD e impostarla su 0.

5. Partecipare di più alla riunione.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Abilitare l'app riunioni Skype per sostituire Skype for Business Web App (facoltativo, solo Skype for Business Server 2015)
<a name="SMA_Enable"> </a>

Questa procedura è facoltativa e si applica a Skype for Business Server 2015 CU5 e versioni successive. Se non la usi, gli utenti esterni continueranno a partecipare a riunioni usando Skype for Business Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Abilitare l'app riunioni semplificate per riunioni ed eventi Skype

1. Quando si Abilita l'accesso alla rete di distribuzione di contenuti (CDN), gli utenti avranno la possibilità di connettersi a CDN online e ottenere l'app riunioni Skype (in Windows) e Skype for business per Mac (su Mac) e utilizzeranno l'esperienza di partecipazione alla riunione semplificata.

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Consenti la telemetria di registrazione lato client dalla pagina Web di riunione o l'app riunioni Skype da inviare ai server Microsoft (il comando viene impostato su false).

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Le informazioni inviate a Microsoft sono in stretta conformità con le [procedure di raccolta dei dati di Skype for business](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Imposta il timeout prima di rientrare nell'esperienza di Skype for business web app ospitata localmente se la rete CDN non è disponibile. Il valore predefinito è 6 secondi. Se questo valore è impostato su 0, non ci sarà alcun timeout.

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Vedere anche
<a name="SMA_Enable"> </a>

[Pianificare i client delle riunioni (app Web e riunioni)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurare la pagina di partecipazione alla riunione in Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Informativa sulla privacy dei Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Condizioni di licenza e documentazione](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
