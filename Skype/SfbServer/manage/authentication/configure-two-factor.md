---
title: Configurare l'autenticazione a due fattori in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: "Riepilogo: configurare l'autenticazione a due fattori in Skype for Business Server."
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814416"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurare l'autenticazione a due fattori in Skype for Business Server

**Riepilogo:** Configurare l'autenticazione a due fattori in Skype for Business Server.

Nelle sezioni seguenti vengono descritti i passaggi necessari per configurare l'autenticazione a due fattori per la distribuzione. Per ulteriori informazioni sull'autenticazione a due fattori, vedere [Abilitazione di Office 365 multi-factor authentication for online Administrators-Grid User post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurare un'autorità di certificazione radice dell'organizzazione per il supporto dell'autenticazione con smart card

Nella procedura seguente viene descritto come configurare una CA radice dell'organizzazione per il supporto dell'autenticazione con smart card:

Per informazioni su come installare una CA radice dell'organizzazione, vedere [Install a Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).

1. Accedere al computer della CA dell'organizzazione utilizzando un account di amministratore di dominio.

2. Avviare System Manager e verificare che sia installato il ruolo di registrazione Web dell'autorità di certificazione.

3. Dal menu **strumenti di amministrazione** , aprire la console di gestione **autorità di certificazione** .

4. Nel riquadro di spostamento espandere **autorità di certificazione**.

5. Fare clic con il pulsante destro del mouse su **modelli di certificato**, selezionare **nuovo** e quindi selezionare **modello di certificato da emettere**.

6. Selezionare **l'agente di registrazione, l'** **utente smartcard** e l' **accesso smartcard**.

7. Fare clic su **OK**.

8. Fare clic con il pulsante destro su **modelli di certificato**.

9. Selezionare **Gestisci**.

10. Aprire le proprietà del modello utente smartcard.

11. Fare clic sulla scheda **sicurezza** .

12. Modificare le autorizzazioni come indicato di seguito:

    - Aggiungere singoli account di Active Directory con autorizzazioni di lettura/registrazione (Consenti) oppure

    - Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure

    - Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (Consenti)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurare Windows 8 per smart card virtuali

Uno dei fattori da considerare quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo dell'implementazione. Windows 8 fornisce una serie di nuove funzionalità di sicurezza e una delle nuove funzionalità più interessanti è il supporto per le smart card virtuali.

Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza effettuare ulteriori investimenti nell'hardware. Per ulteriori informazioni, vedere [using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Per configurare Windows 8 per smart card virtuali

1. Eseguire l'accesso al computer con Windows 8 utilizzando le credenziali di un utente abilitato per Skype for business.

2. Nella schermata Start di Windows 8, spostare il cursore nell'angolo in basso a destra dello schermo.

3. Selezionare l'opzione di **ricerca** e quindi prompt di ricerca forCommand.

4. Fare clic con il pulsante destro del mouse su **prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

5. Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando riportato di seguito:

  ```console
  Tpm.msc
  ```

6. Dalla console di gestione TPM, verificare che la versione specifica TPM sia almeno 1,2

    > [!NOTE]
    > Se viene visualizzata una finestra di dialogo in cui viene indicato che non è possibile trovare un modulo TPM (Trusted Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS del sistema.

7. Chiudere la console di gestione TPM

8. Al prompt dei comandi creare una nuova smart card virtuale utilizzando il comando seguente:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Per fornire un valore PIN personalizzato quando si crea la smart card virtuale, utilizzare invece il prompt di/pin.

9. Al prompt dei comandi, aprire la console di gestione computer eseguendo il comando riportato di seguito:

  ```console
  CompMgmt.msc
  ```

10. Nella console Gestione computer selezionare **Gestione dispositivi**.

11. Espandere **lettori di smart card**.

12. Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrare gli utenti per l'autenticazione con smart card

Sono in genere disponibili due metodi per la registrazione di utenti per l'autenticazione con smart card. Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card tramite la registrazione Web, mentre il metodo più complesso implica l'utilizzo di un agente di registrazione. Questo argomento è dedicato alla registrazione automatica dei certificati smartcard.

Per ulteriori informazioni sull'iscrizione per conto degli utenti come agente di registrazione, vedere [registrazione per i certificati per conto di altri utenti](https://go.microsoft.com/fwlink/p/?LinkID=313367).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Per registrare gli utenti per l'autenticazione con smart card

1. Accedere alla workstation Windows 8 utilizzando le credenziali di un utente abilitato per Skype for business.

2. Avviare Internet Explorer.

3. Passare alla pagina **registrazione Web Authority Certificate** (ad https://MyCA.contoso.com/certsrv) esempio,.

    > [!NOTE]
    > Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.

4. Nella pagina **iniziale** , selezionare **Richiedi un certificato**.

5. Successivamente, selezionare **richiesta avanzata**.

6. Selezionare **Crea e invia una richiesta a questa CA**.

7. Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:

  - Le **Opzioni principali** confermano le impostazioni seguenti:

    - Selezionare il pulsante di opzione **Crea nuovo set di tasti**

    - Per **CSP**, selezionare **Microsoft Base Smart Card Crypto Provider**

    - Per l' **utilizzo della chiave**, selezionare **Exchange** (è l'unica opzione disponibile).

    - Per le **dimensioni della chiave**, immettere 2048

    - Confermare che il **nome del contenitore di chiavi automatico** sia selezionato

    - Lasciare deselezionate le altre caselle.

  - In **Opzioni aggiuntive** confermare i valori seguenti:

    - Per il **formato di richiesta** selezionare **CMC**.

    - Per l' **algoritmo hash** selezionare **SHA1**.

    - Per il certificato enterSmardcard **nome descrittivo** .

8. Se si utilizza un lettore di smartcard fisico, inserire la smart card nel dispositivo.

9. Fare clic su **Invia** per inviare la richiesta di certificato.

10. Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.

    > [!NOTE]
    > Il valore del PIN della smart card virtuale predefinito è' 12345678'.

11. Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.

    > [!NOTE]
    >  Se la richiesta di certificato ha esito negativo con l'errore "questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi possibili per risolvere il problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurazione di Active Directory Federation Services (AD FS 2,0)

Nella sezione seguente viene descritto come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori. Per informazioni su come installare ADFS 2,0, vedere [ad fs 2,0 Step-by-Step e guide](https://go.microsoft.com/fwlink/p/?LinkId=313374).

> [!NOTE]
> Quando si installa AD FS 2,0, non utilizzare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services. Scaricare e installare invece il [pacchetto di RTW di Active Directory Federation Services 2,0](https://go.microsoft.com/fwlink/p/?LinkId=313375).

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Per configurare AD FS per l'autenticazione a due fattori

1. Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.

2. Avviare Windows PowerShell.

3. Dalla riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Stabilire una partnership con ogni server che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome del server specifico della distribuzione:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Dal menu strumenti di amministrazione, avviare la console di gestione di AD FS 2,0.

6. Espandi **relazioni di trust**  >  **relying party trust**.

7. Verificare che sia stata creata una nuova relazione di trust per il server Skype for business.

8. Creare e assegnare una regola di autorizzazione di rilascio per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Dalla console di gestione AD FS 2,0, fare clic con il pulsante destro del mouse sul trust relying party e selezionare **modifica regole attestazione**.

11. Selezionare la scheda **regole di autorizzazione rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.

12. Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurazione di AD FS 2,0 per il supporto dell'autenticazione client

Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire ad FS 2,0 di supportare l'autenticazione tramite smart card:

- Autenticazione basata su form (moduli)

- Autenticazione del client di sicurezza layer di trasporto

Se si utilizza l'autenticazione basata su moduli, è possibile sviluppare una pagina Web che consenta agli utenti di autenticarsi usando il proprio nome utente/password o utilizzando la smart card e il PIN. Questo argomento è dedicato all'implementazione dell'autenticazione del client per la sicurezza del layer di trasporto con AD FS 2,0. Per ulteriori informazioni sui tipi di autenticazione AD FS 2,0, vedere [ad fs 2,0: come modificare il tipo di autenticazione locale](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Per configurare ad FS 2,0 per il supporto dell'autenticazione client

1. Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.

2. Avviare Esplora risorse.

3. Passare a C:\Inetpub\Adfs\Ls

4. Creare una copia di backup del file di web.config esistente.

5. Aprire il file web.config esistente utilizzando il blocco note.

6. Dalla barra dei menu, selezionare **modifica** , quindi selezionare **trova**.

7. Cerca \<localAuthenticationTypes\> .

    Tenere presente che sono presenti quattro tipi di autenticazione, uno per riga.

8. Spostare la riga contenente il tipo di autenticazione di TLSClient nella parte superiore dell'elenco della sezione.

9. Salvare e chiudere il file web.config.

10. Avviare un prompt dei comandi con privilegi elevati.

11. Riavviare IIS eseguendo il comando riportato di seguito:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurazione dell'autenticazione passiva di Skype for Business Server

Nella sezione seguente viene descritto come configurare Skype for Business Server per supportare l'autenticazione passiva. Una volta abilitata, gli utenti abilitati per l'autenticazione a due fattori dovranno utilizzare una smart card fisica o virtuale e un PIN valido per accedere utilizzando il client Skype for business.

> [!NOTE]
> È consigliabile che i clienti consentano l'autenticazione passiva per i servizi di registrazione e Web a livello di servizio. Se l'autenticazione passiva è abilitata per i servizi di registrazione e Web a livello globale, è probabile che si verifichino errori di autenticazione a livello dell'organizzazione per gli utenti che non accedono con il client desktop supportato.

### <a name="web-service-configuration"></a>Configurazione del servizio Web

Nella procedura seguente viene descritto come creare una configurazione del servizio Web personalizzata per i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Per creare una configurazione del servizio Web personalizzato

1. Accedere al server front end di Skype for Business Server utilizzando un account di amministratore di Skype for business.

2. Avviare la shell di gestione di Skype for Business Server.

3. Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione del servizio Web per ogni Director, pool Enterprise e server Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > Il valore dell'FQDN di WsFedPassiveMetadataUri è il nome del servizio federativo del server AD FS 2,0. Il valore nome servizio federativo può essere trovato nella console di gestione AD FS 2,0 facendo clic con il pulsante destro del mouse su **servizio** dal riquadro di spostamento e quindi selezionando **modifica proprietà servizio federativo**.

4. Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando riportato di seguito:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferibile per l'autenticazione webticket. Per tutti i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disattivati nei servizi Web di Skype for business eseguendo il cmdlet seguente:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verificare che tutti gli altri tipi di autenticazione siano stati disabilitati eseguendo il cmdlet seguente:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configurazione del proxy

Quando l'autenticazione dei certificati è disattivata per i servizi Web di Skype for business, il client Skype for business utilizzerà un tipo di autenticazione meno preferito, ad esempio Kerberos o NTLM, per autenticare il servizio di registrazione. L'autenticazione dei certificati è ancora necessaria per consentire al client di recuperare un ticket, tuttavia Kerberos e NTLM devono essere disattivati per il servizio di registrazione.

Nella procedura seguente viene descritto come creare una configurazione proxy personalizzata per i pool di server perimetrali, i pool Enterprise e gli Standard Edition che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Per creare una configurazione proxy personalizzata

1. Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione proxy per ogni server Edge di Skype for Business Server, pool Enterprise e Standard Edition che verranno abilitati per l'autenticazione passiva tramite l'esecuzione dei seguenti comandi:

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Verificare che tutti gli altri tipi di autenticazione proxy siano stati disabilitati eseguendo il comando riportato di seguito:

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione a due fattori in Skype for Business Server](two-factor-authentication.md)

[Utilizzare l'autenticazione a due fattori con il client Skype for business e Skype for Business Server](use-two-factor.md)
