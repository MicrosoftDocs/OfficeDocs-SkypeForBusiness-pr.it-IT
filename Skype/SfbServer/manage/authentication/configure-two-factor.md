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

Nelle sezioni seguenti vengono descritti i passaggi necessari per configurare l'autenticazione a due fattori per la distribuzione. Per ulteriori informazioni sull'autenticazione a due fattori, vedere Abilitazione dell'autenticazione a più fattori di [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)per gli amministratori online - Grid User Post.

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurare un'autorità di certificazione radice dell'organizzazione per supportare l'autenticazione con smart card

Nei passaggi seguenti viene descritto come configurare una CA radice dell'organizzazione per supportare l'autenticazione smart card:

Per informazioni su come installare una CA radice dell'organizzazione, vedere [Install an Enterprise Root Certification Authority.](https://go.microsoft.com/fwlink/p/?LinkID=313364)

1. Accedere al computer della CA globale (enterprise) utilizzando un account di amministratore di dominio.

2. Avviare System Manager e verificare che il ruolo Registrazione Web autorità di certificazione sia installato.

3. Dal menu **Strumenti di amministrazione** aprire la console gestione **Autorità** di certificazione.

4. Nel riquadro di spostamento espandere **Autorità di certificazione.**

5. Fare clic con il **pulsante destro del** mouse su Modelli di certificato, selezionare **Nuovo,** quindi **selezionare Modello di certificato da emettere.**

6. Selezionare **Agente di registrazione,** **Utente smart card** e Accesso **smart card.**

7. Fare clic su **OK**.

8. Fare clic con il pulsante **destro del mouse su Modelli di certificato.**

9. Selezionare **Gestisci.**

10. Aprire le proprietà del modello Utente smart card.

11. Fare clic sulla **scheda** Sicurezza.

12. Modificare le autorizzazioni nel modo seguente:

    - Aggiungere singoli account ACTIVE utente con autorizzazioni di lettura/registrazione (Consenti) oppure

    - Aggiungere un gruppo di sicurezza contenente utenti di smart card con autorizzazioni lettura/registrazione (Consenti) oppure

    - Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (consenti)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurare Windows 8 per le smart card virtuali

Un fattore da considerare quando si distribuisce l'autenticazione a due fattori e la tecnologia delle smart card è il costo dell'implementazione. Windows 8 offre una serie di nuove funzionalità di sicurezza e una delle nuove funzionalità più interessanti è il supporto per le smart card virtuali.

Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1.2, le organizzazioni possono ora ottenere i vantaggi dell'accesso con smart card senza effettuare ulteriori investimenti in hardware. Per altre informazioni, vedi [Uso delle smart card virtuali con Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Per configurare Windows 8 per le smart card virtuali

1. Accedi al computer Windows 8 usando le credenziali di un utente abilitato per Skype for Business.

2. Nella schermata Start di Windows 8, sposta il cursore nell'angolo inferiore destro dello schermo.

3. Selezionare **l'opzione** di ricerca e quindi cercare Prompt comandi.

4. Fai clic con il **pulsante destro del** mouse su Prompt dei comandi e quindi scegli Esegui come **amministratore.**

5. Apri la console di gestione TPM (Trusted Platform Module) eseguendo il comando seguente:

  ```console
  Tpm.msc
  ```

6. Dalla console di gestione del TPM, verificare che la versione della specifica TPM sia almeno 1.2

    > [!NOTE]
    > Se ricevi una finestra di dialogo che indica che non è possibile trovare un modulo TPM (Compatible Trust Platform Module), verifica che il computer abbia un modulo TPM compatibile e che sia abilitato nel BIOS di sistema.

7. Chiudere la console di gestione del TPM

8. Al prompt dei comandi creare una nuova smart card virtuale utilizzando il comando seguente:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Per fornire un valore PIN personalizzato durante la creazione della smart card virtuale, usa invece il prompt /pin.

9. Al prompt dei comandi aprire la console Gestione computer eseguendo il comando seguente:

  ```console
  CompMgmt.msc
  ```

10. Nella console Gestione computer selezionare **Gestione dispositivi.**

11. Espandere **Lettori di smart card.**

12. Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrare gli utenti per l'autenticazione con smart card

Esistono in genere due metodi per registrare gli utenti per l'autenticazione con smart card. Il metodo più semplice prevede la registrazione diretta degli utenti per l'autenticazione tramite smart card tramite registrazione Web, mentre il metodo più complesso prevede l'uso di un agente di registrazione. In questo argomento viene illustrata la registrazione automatica per i certificati smart card.

Per altre informazioni sulla registrazione per conto degli utenti come agente di registrazione, vedi Registrare i certificati [per conto di altri utenti.](https://go.microsoft.com/fwlink/p/?LinkID=313367)

### <a name="to-enroll-users-for-smart-card-authentication"></a>Per registrare gli utenti per l'autenticazione con smart card

1. Accedi alla workstation Windows 8 usando le credenziali di un utente abilitato per Skype for Business.

2. Avviare Internet Explorer.

3. Passare alla **pagina Registrazione Web autorità** di certificazione (ad https://MyCA.contoso.com/certsrv) esempio.

    > [!NOTE]
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.

4. Nella pagina **di benvenuto** selezionare Richiedi **un certificato.**

5. Successivamente, selezionare **Richiesta avanzata.**

6. Selezionare **Crea e invia una richiesta a questa CA.**

7. Selezionare **Smartcard User** nella sezione **Certificate Template** e completare la richiesta di certificato avanzata con i seguenti valori:

  - **Le opzioni chiave** confermano che le impostazioni seguenti:

    - Selezionare il **pulsante di opzione Crea nuovo set di** chiavi

    - Per **CSP,** selezionare **Microsoft Base Smart Card Crypto Provider**

    - Per **Utilizzo chiave,** selezionare **Exchange** (questa è l'unica opzione disponibile).

    - Per **Dimensioni chiave,** immettere 2048

    - Verificare che sia **selezionato Il nome del contenitore di** chiavi automatico

    - Lasciare deselezionate le altre caselle.

  - In **Opzioni aggiuntive** verificare i valori seguenti:

    - Per **Formato richiesta selezionare** **CMC.**

    - Per **Algoritmo hash** selezionare **sha1.**

    - For **Friendly Name** enterSmardcard Certificate.

8. Se si utilizza un lettore di smart card fisico, inserire la smart card nel dispositivo.

9. Fare **clic su** Invia per inviare la richiesta di certificato.

10. Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.

    > [!NOTE]
    > Il valore predefinito del PIN della smart card virtuale è "12345678".

11. Dopo l'emissione del certificato, fare clic **su Installa questo certificato** per completare il processo di registrazione.

    > [!NOTE]
    >  Se la richiesta di certificato non riesce con l'errore "Questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi per risolvere il problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurare Active Directory Federation Services (ADFS 2.0)

Nella sezione seguente viene descritto come configurare Active Directory Federation Services (ADFS 2.0) per supportare l'autenticazione a più fattori. Per informazioni su come installare ADFS 2.0, vedere le istruzioni dettagliate e le procedure di [ADFS 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=313374)

> [!NOTE]
> Quando si installa AD FS 2.0, non utilizzare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services. Scaricare e installare invece il pacchetto RTW di [Active Directory Federation Services 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=313375)

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Per configurare AD FS per l'autenticazione a due fattori

1. Accedere al computer AD FS 2.0 con un account di amministratore di dominio.

2. Avviare Windows PowerShell.

3. Dalla riga Windows PowerShell comando, eseguire il comando seguente:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Stabilire una relazione con ogni server che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome del server specifico per la distribuzione:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Dal menu Strumenti di amministrazione avvia la console di gestione di ADFS 2.0.

6. Espandere **Relazioni di**  >  **attendibilità Attendibilità componente**.

7. Verificare che sia stata creata una nuova relazione di trust per Skype for Business Server.

8. Creare e assegnare una regola di autorizzazione rilascio per il trust della relying party usando Windows PowerShell eseguendo i comandi seguenti:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Creare e assegnare una regola di trasformazione rilascio per l'attendibilità della relying party usando Windows PowerShell eseguendo i comandi seguenti:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Dalla console di gestione di AD FS 2.0 fai clic con il pulsante destro del mouse sull'attendibilità del componente e scegli **Modifica regole attestazione.**

11. Selezionare la **scheda Regole di autorizzazione rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.

12. Selezionare la **scheda Regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurazione di ADFS 2.0 per supportare l'autenticazione client

Esistono due possibili tipi di autenticazione che possono essere configurati per consentire ad ADFS 2.0 di supportare l'autenticazione tramite smart card:

- Autenticazione basata su moduli

- Autenticazione client Transport Layer Security

Utilizzando l'autenticazione basata su moduli, è possibile sviluppare una pagina Web che consenta agli utenti di eseguire l'autenticazione utilizzando il nome utente/password oppure la smart card e il PIN. In questo argomento viene illustrato come implementare l'autenticazione client transport layer security con ADFS 2.0. Per ulteriori informazioni sui tipi di autenticazione AD FS 2.0, vedere [AD FS 2.0: Come modificare il tipo di autenticazione locale.](https://go.microsoft.com/fwlink/p/?LinkId=313384)

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Per configurare ADFS 2.0 per supportare l'autenticazione client

1. Accedere al computer AD FS 2.0 con un account di amministratore di dominio.

2. Avvia Esplora risorse.

3. Passare a C:\inetpub\adfs\ls

4. Creare una copia di backup del file web.config esistente.

5. Aprire il file di web.config esistente utilizzando Blocco note.

6. Nella barra dei menu selezionare **Modifica** e quindi **Trova.**

7. Cercare \<localAuthenticationTypes\> .

    Si noti che sono elencati quattro tipi di autenticazione, uno per riga.

8. Spostare la riga contenente il tipo di autenticazione TLSClient all'inizio dell'elenco nella sezione.

9. Salvare e chiudere il web.config file.

10. Avviare un prompt dei comandi con privilegi elevati.

11. Riavviare IIS eseguendo il comando seguente:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurazione dell'autenticazione passiva di Skype for Business Server

Nella sezione seguente viene descritto come configurare Skype for Business Server per supportare l'autenticazione passiva. Una volta abilitata, gli utenti abilitati per l'autenticazione a due fattori doranno utilizzare una smart card fisica o virtuale e un PIN valido per accedere con il client Skype for Business.

> [!NOTE]
> È consigliabile che i clienti abilitino l'autenticazione passiva per la funzione di registrazione e i servizi Web a livello di servizio. Se l'autenticazione passiva è abilitata per la funzione di registrazione e i servizi Web a livello globale, si verificano probabilmente errori di autenticazione a livello di organizzazione per gli utenti che non eseeranno l'accesso con il client desktop supportato.

### <a name="web-service-configuration"></a>Configurazione servizio Web

Nei passaggi seguenti viene descritto come creare una configurazione di servizio Web personalizzata per i Director, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Per creare una configurazione di servizio Web personalizzata

1. Accedere al server Front End di Skype for Business Server con un account amministratore di Skype for Business.

2. Avviare Skype for Business Server Management Shell.

3. Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione del servizio Web per ogni server Director, Pool Enterprise e Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > Il valore per l'FQDN WsFedPassiveMetadataUri è il nome del servizio federativo del server ADFS 2.0. Il valore Nome servizio federativo è disponibile nella console di gestione di  ADFS 2.0 facendo clic con il pulsante destro del mouse su Servizio nel riquadro di spostamento e quindi scegliendo Modifica proprietà **servizio federativo.**

4. Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando seguente:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Per i client, l'autenticazione passiva è il metodo di autenticazione meno consigliato per l'autenticazione webticket. Per tutti i Director, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disabilitati nei servizi Web Skype for Business eseguendo il cmdlet seguente:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verificare che tutti gli altri tipi di autenticazione siano stati disabilitati correttamente eseguendo il cmdlet seguente:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configurazione proxy

Quando l'autenticazione del certificato è disabilitata per i servizi Web Skype for Business, il client Skype for Business utilizzerà un tipo di autenticazione meno preferito, ad esempio Kerberos o NTLM, per l'autenticazione nel servizio di registrazione. L'autenticazione del certificato è ancora necessaria per consentire al client di recuperare un webticket, tuttavia Kerberos e NTLM devono essere disabilitati per il servizio di registrazione.

Nei passaggi seguenti viene descritto come creare una configurazione proxy personalizzata per pool di server perimetrali, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Per creare una configurazione proxy personalizzata

1. Dalla riga di comando di Skype for Business Server Management Shell, creare una nuova configurazione proxy per ogni pool di server perimetrali, pool Enterprise e server Standard Edition di Skype for Business Server che verrà abilitato per l'autenticazione passiva eseguendo i comandi seguenti:

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Verificare che tutti gli altri tipi di autenticazione proxy siano stati disabilitati correttamente eseguendo il comando seguente:

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione a due fattori in Skype for Business Server](two-factor-authentication.md)

[Usare l'autenticazione a due fattori con il client Skype for Business e Skype for Business Server](use-two-factor.md)
