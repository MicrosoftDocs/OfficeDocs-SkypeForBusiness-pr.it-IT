---
title: Configurare l'autenticazione a due fattori in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: "Riepilogo: configurare l'autenticazione a due fattori in Skype for Business Server."
ms.openlocfilehash: 91a8929b89a584b116f1c7ec9313daa2fe679fd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189689"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurare l'autenticazione a due fattori in Skype for Business Server

**Riepilogo:** Configurare l'autenticazione a due fattori in Skype for Business Server.

Nelle sezioni seguenti vengono illustrati i passaggi necessari per configurare l'autenticazione a due fattori per la distribuzione. Per altre informazioni sull'autenticazione a due fattori, vedere [abilitare l'autenticazione a più fattori di Office 365 per gli amministratori online-Grid User post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurare un'autorità di certificazione radice aziendale per supportare l'autenticazione tramite smart card

La procedura seguente descrive come configurare una CA radice aziendale per supportare l'autenticazione tramite smart card:

Per informazioni su come installare una CA radice aziendale, vedere [installare un'autorità di certificazione radice aziendale](https://go.microsoft.com/fwlink/p/?LinkID=313364).

1. Accedere al computer della CA aziendale usando un account di amministratore di dominio.

2. Avviare System Manager e verificare che sia installato il ruolo di registrazione Web Authority Certificate.

3. Nel menu **strumenti di amministrazione** aprire la console di gestione **autorità di certificazione** .

4. Nel riquadro di spostamento espandere **autorità di certificazione**.

5. Fare clic con il pulsante destro del mouse sui **modelli di certificato**, scegliere **nuovo**e quindi **modello certificato da emettere**.

6. Selezionare **agente di registrazione**, **utente smartcard**e accesso tramite **smartcard**.

7. Fare clic su **OK**.

8. Fare clic con il pulsante destro sul **modello di certificato**.

9. Selezionare **Gestisci**.

10. Aprire le proprietà del modello utente smartcard.

11. Fare clic sulla scheda **sicurezza** .

12. Modificare le autorizzazioni nel modo seguente:

    - Aggiungere singoli account di annunci utente con autorizzazioni di lettura/registrazione (Consenti) oppure

    - Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure

    - Aggiungere il gruppo Domain Users con le autorizzazioni di lettura/registrazione (Consenti)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurare Windows 8 per smart card virtuali

Un fattore da tenere in considerazione quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo di implementazione. Windows 8 offre una serie di nuove funzionalità di sicurezza e una delle nuove caratteristiche più interessanti è il supporto per le smart card virtuali.

Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza apportare ulteriori investimenti nell'hardware. Per altre informazioni, vedere [uso di smart card virtuali con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Per configurare Windows 8 per smart card virtuali

1. Accedere al computer con Windows 8 usando le credenziali di un utente abilitato per Skype for business.

2. Nella schermata Start di Windows 8 Posizionare il cursore nell'angolo in basso a destra dello schermo.

3. Selezionare l'opzione di **ricerca** e quindi Cerca in forCommand prompt.

4. Fare clic con il pulsante destro del mouse sul **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

5. Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando seguente:

  ```
  Tpm.msc
  ```

6. Nella console di gestione TPM verificare che la versione specifica del TPM sia di almeno 1,2

    > [!NOTE]
    > Se viene visualizzata una finestra di dialogo che indica che non è possibile trovare un modulo TPM (compatible Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS di sistema.

7. Chiudere la console di gestione TPM

8. Dal prompt dei comandi creare una nuova smart card virtuale usando il comando seguente:

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Per specificare un valore PIN personalizzato durante la creazione della smart card virtuale, usare invece il prompt di/pin.

9. Dal prompt dei comandi aprire la console di gestione computer eseguendo il comando seguente:

  ```
  CompMgmt.msc
  ```

10. Nella console di gestione computer selezionare **Gestione dispositivi**.

11. Espandi **lettori di smart card**.

12. Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrare gli utenti per l'autenticazione tramite smart card

Sono in genere disponibili due metodi per l'iscrizione degli utenti per l'autenticazione tramite smart card. Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card usando la registrazione Web, mentre il metodo più complesso prevede l'uso di un agente di registrazione. Questo argomento riguarda l'autoregistrazione per i certificati smartcard.

Per altre informazioni sull'iscrizione per conto degli utenti come agente di registrazione, vedere [registrare i certificati per conto di altri utenti](https://go.microsoft.com/fwlink/p/?LinkID=313367).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Per registrare gli utenti per l'autenticazione tramite smart card

1. Accedere alla workstation Windows 8 usando le credenziali di un utente abilitato per Skype for business.

2. Avviare Internet Explorer.

3. Passare alla pagina di **registrazione Web Authority Certificate** (ad esempio https://MyCA.contoso.com/certsrv).

    > [!NOTE]
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare il sito Web in modalità compatibilità.

4. Nella pagina di **benvenuto** selezionare **Richiedi un certificato**.

5. Selezionare quindi **Advanced request**.

6. Selezionare **Crea e invia una richiesta a questa CA**.

7. Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:

  - Le **Opzioni principali** confermano le impostazioni seguenti:

    - Selezionare il pulsante di opzione **Crea nuovo set di tasti**

    - Per **CSP**selezionare **provider di crittografia Smart Card Microsoft base**

    - Per l' **utilizzo delle chiavi**, selezionare **Exchange** (questa è l'unica opzione disponibile).

    - Per le **dimensioni della chiave**, immettere 2048

    - Verificare che il **nome del contenitore di tasti automatico** sia selezionato

    - Abbandonare le altre caselle deselezionate.

  - In **Opzioni aggiuntive** confermare i valori seguenti:

    - Per il **formato di richiesta** selezionare **CMC**.

    - Per l' **algoritmo hash** selezionare **SHA1**.

    - Per **nome** descrittivo enterSmardcard certificato.

8. Se si usa un lettore di smartcard fisico, inserire la smart card nel dispositivo.

9. Fare clic su **Invia** per inviare la richiesta di certificato.

10. Quando richiesto, immettere il PIN usato per creare la smart card virtuale.

    > [!NOTE]
    > Il valore PIN della smart card virtuale predefinito è "12345678".

11. Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.

    > [!NOTE]
    >  Se la richiesta di certificato non riesce con l'errore "questo Web browser non supporta la generazione di richieste di certificato," Esistono tre modi possibili per risolvere il problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurare Active Directory Federation Services (AD FS 2,0)

La sezione seguente descrive come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori. Per informazioni su come installare ADFS 2,0, vedere [istruzioni dettagliate su adfs 2,0 e come eseguire una guida](https://go.microsoft.com/fwlink/p/?LinkId=313374).

> [!NOTE]
> Quando si installa ADFS 2,0, non usare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services. Scaricare e installare invece il [pacchetto-RTW di Active Directory Federation Services 2,0](https://go.microsoft.com/fwlink/p/?LinkId=313375).

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Per configurare ADFS per l'autenticazione a due fattori

1. Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.

2. Avviare Windows PowerShell.

3. Nella riga di comando di Windows PowerShell eseguire il comando seguente:

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Stabilire una partnership con ogni server che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome del server specifico della distribuzione:

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Nel menu strumenti di amministrazione avviare la console di gestione di ADFS 2,0.

6. Espandere i**trust** **tra le relazioni** > di trust.

7. Verificare che sia stato creato un nuovo trust per il server Skype for business.

8. Creare e assegnare una regola di autorizzazione del rilascio per l'attendibilità del componente tramite Windows PowerShell eseguendo i comandi seguenti:

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente usando Windows PowerShell eseguendo i comandi seguenti:

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Nella console di gestione di ADFS 2,0 fare clic con il pulsante destro del mouse sull'attendibilità del componente e scegliere **modifica regole attestazione**.

11. Selezionare la scheda **regole di autorizzazione del rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.

12. Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurazione di ADFS 2,0 per supportare l'autenticazione del client

Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire AD FS 2,0 di supportare l'autenticazione tramite smart card:

- Autenticazione basata su moduli (FBA)

- Autenticazione del client di sicurezza dei livelli di trasporto

Usando l'autenticazione basata su moduli, puoi sviluppare una pagina Web che consente agli utenti di autenticarsi usando il loro nome utente/password o usando la loro smart card e il PIN. Questo argomento illustra come implementare l'autenticazione del client di sicurezza dei livelli di trasporto con ADFS 2,0. Per altre informazioni sui tipi di autenticazione di ADFS 2,0, vedere ADFS [2,0: come modificare il tipo di autenticazione locale](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Per configurare ADFS 2,0 per supportare l'autenticazione del client

1. Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.

2. Avviare Esplora risorse.

3. Passare a C:\Inetpub\Adfs\Ls

4. Creare una copia di backup del file Web. config esistente.

5. Aprire il file Web. config esistente tramite il blocco note.

6. Nella barra dei menu selezionare **modifica** e quindi **trova**.

7. Cercare \<localAuthenticationTypes\>.

    Tieni presente che sono presenti quattro tipi di autenticazione, uno per riga.

8. Posizionare la linea contenente il tipo di autenticazione TLSClient nella parte superiore dell'elenco nella sezione.

9. Salvare e chiudere il file Web. config.

10. Avviare un prompt dei comandi con privilegi elevati.

11. Riavviare IIS eseguendo il comando seguente:

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurazione dell'autenticazione passiva di Skype for Business Server

La sezione seguente descrive come configurare Skype for Business Server per supportare l'autenticazione passiva. Una volta abilitati, gli utenti abilitati per l'autenticazione a due fattori saranno tenuti a usare una smart card fisica o virtuale e un PIN valido per accedere con il client Skype for business.

> [!NOTE]
> È consigliabile che i clienti consentano l'autenticazione passiva per il registrar e i servizi Web a livello di servizio. Se l'autenticazione passiva è abilitata per i servizi di registrazione e Web a livello globale, probabilmente si verificheranno errori di autenticazione a livello di organizzazione per gli utenti che non hanno eseguito l'accesso con il client desktop supportato.

### <a name="web-service-configuration"></a>Configurazione del servizio Web

I passaggi seguenti descrivono come creare una configurazione di servizio Web personalizzata per direttori, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Per creare una configurazione di un servizio Web personalizzato

1. Accedere al server front end di Skype for Business Server usando un account di amministratore di Skype for business.

2. Avviare Skype for Business Server Management Shell.

3. Dalla riga di comando di Skype for Business Server Management Shell creare una nuova configurazione di servizio Web per ogni Director, pool Enterprise e server Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > Il valore per l'FQDN di WsFedPassiveMetadataUri è il nome del servizio federativo del server ADFS 2,0. Il valore nome servizio federativo può essere trovato nella console di gestione di ADFS 2,0 facendo clic con il pulsante destro del mouse su **servizio** dal riquadro di spostamento e quindi selezionando **modifica proprietà servizio federativo**.

4. Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando seguente:

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferibile per l'autenticazione webticket. Per tutti i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disabilitati in servizi web Skype for business eseguendo il cmdlet seguente:

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verificare che tutti gli altri tipi di autenticazione siano stati correttamente disabilitati eseguendo il cmdlet seguente:

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configurazione proxy

Quando l'autenticazione dei certificati è disabilitata per i servizi web Skype for business, il client Skype for business userà un tipo di autenticazione meno consigliato, ad esempio Kerberos o NTLM, per eseguire l'autenticazione nel servizio registrar. L'autenticazione del certificato è ancora necessaria per consentire al client di recuperare un ticket, ma Kerberos e NTLM devono essere disabilitati per il servizio registrar.

I passaggi seguenti descrivono come creare una configurazione proxy personalizzata per i pool di Edge, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Per creare una configurazione proxy personalizzata

1. Dalla riga di comando di Skype for Business Server Management Shell creare una nuova configurazione proxy per ogni server Edge di Skype for Business Server, pool Enterprise e Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo le operazioni seguenti comandi

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Verificare che tutti gli altri tipi di autenticazione proxy siano stati correttamente disabilitati eseguendo il comando seguente:

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione a due fattori in Skype for Business Server](two-factor-authentication.md)

[Usare l'autenticazione a due fattori con client Skype for business e Skype for Business Server](use-two-factor.md)
