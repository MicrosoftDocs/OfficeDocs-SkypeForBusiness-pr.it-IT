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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: "Riepilogo: configurare l'autenticazione a due fattori in Skype for Business Server."
ms.openlocfilehash: 447039a5dd137482c330325fcf479dade583f395
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014370"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurare l'autenticazione a due fattori in Skype for Business Server

**Riepilogo:** Configurare l'autenticazione a due fattori in Skype for Business Server.

Nelle sezioni seguenti vengono descritti i passaggi necessari per configurare l'autenticazione a due fattori per la distribuzione. Per ulteriori informazioni sull'autenticazione a due fattori, [vedere Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurare un'Enterprise radice per supportare l'autenticazione con smart card

La procedura seguente descrive come configurare una CA Enterprise radice per supportare l'autenticazione smart card:

Per informazioni su come installare una CA Enterprise radice, vedere [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).

1. Accedere al computer Enterprise CA utilizzando un account di amministratore di dominio.

2. Avviare Gestore di sistema e verificare che il ruolo Registrazione Web autorità di certificazione sia installato.

3. Dal menu **Strumenti di amministrazione,** aprire la console **di gestione Autorità** di certificazione.

4. Nel riquadro di spostamento espandere **Autorità di certificazione.**

5. Fai clic con il **pulsante destro del** mouse su Modelli di certificato, seleziona **Nuovo,** quindi **seleziona Modello di certificato da emettere.**

6. Selezionare **Agente di registrazione,** **Utente smart card** e Accesso **smart card.**

7. Fare clic su **OK**.

8. Fare clic con il pulsante destro **del mouse su Modelli di certificato**.

9. Selezionare **Gestisci**.

10. Aprire le proprietà del modello Utente smart card.

11. Fare clic sulla **scheda** Sicurezza.

12. Modificare le autorizzazioni come segue:

    - Aggiungere singoli account AD utente con autorizzazioni di lettura/registrazione (consenti) o

    - Aggiungere un gruppo di sicurezza contenente utenti di smart card con autorizzazioni di lettura/registrazione (consenti) oppure

    - Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (consenti)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurare Windows 8 per le smart card virtuali

Un fattore da considerare quando si distribuisce l'autenticazione a due fattori e la tecnologia smart card è il costo dell'implementazione. Windows 8 offre una serie di nuove funzionalità di sicurezza e una delle nuove funzionalità più interessanti è il supporto per le smart card virtuali.

Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1.2, le organizzazioni possono ora ottenere i vantaggi dell'accesso con smart card senza effettuare ulteriori investimenti nell'hardware. Per ulteriori informazioni, vedere [Utilizzo di smart card virtuali con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Per configurare Windows 8 per le smart card virtuali

1. Accedere al computer Windows 8 utilizzando le credenziali di un Skype for Business utente abilitato.

2. Nella schermata Windows 8 start, spostare il cursore nell'angolo in basso a destra dello schermo.

3. Selezionare **l'opzione** Cerca e quindi cercare Prompt dei comandi.

4. Fare clic con il **pulsante destro del mouse** su Prompt dei comandi e quindi scegliere Esegui come **amministratore.**

5. Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando seguente:

   ```console
   Tpm.msc
   ```

6. Dalla console di gestione TPM, verificare che la versione della specifica TPM sia almeno 1.2

    > [!NOTE]
    > Se viene visualizzata una finestra di dialogo che indica che non è possibile trovare un TPM (Compatible Trust Platform Module), verificare che il computer abbia un modulo TPM compatibile e che sia abilitato nel BIOS di sistema.

7. Chiudere la console di gestione TPM

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

10. Nella console Gestione computer seleziona **Gestione dispositivi**.

11. Espandere **Lettori di smart card**.

12. Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrare gli utenti per l'autenticazione con smart card

Esistono in genere due metodi per registrare gli utenti per l'autenticazione con smart card. Il metodo più semplice prevede la registrazione diretta degli utenti per l'autenticazione con smart card tramite registrazione Web, mentre il metodo più complesso prevede l'utilizzo di un agente di registrazione. In questo argomento viene illustrata l'autoregistrazione per i certificati smart card.

Per ulteriori informazioni sulla registrazione per conto degli utenti come agente di registrazione, vedere [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Per registrare gli utenti per l'autenticazione con smart card

1. Accedere alla workstation Windows 8 utilizzando le credenziali di un Skype for Business utente abilitato.

2. Avviare Internet Explorer.

3. Passare alla **pagina Registrazione Web Autorità** di certificazione ,ad esempio https://MyCA.contoso.com/certsrv) .

    > [!NOTE]
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.

4. Nella pagina **di** benvenuto selezionare **Richiedi un certificato.**

5. Quindi, selezionare **Richiesta avanzata.**

6. Selezionare **Crea e invia una richiesta a questa CA.**

7. Selezionare **Utente smart card** nella sezione Modello **di** certificato e completare la richiesta avanzata di certificato con i valori seguenti:

  - **Le opzioni chiave** confermano che le impostazioni seguenti:

    - Selezionare il **pulsante di opzione Crea nuovo set di** chiavi

    - Per **CSP,** selezionare **Microsoft Base Smart Card Crypto Provider**

    - Per **Uso chiave,** **selezionare Exchange** (questa è l'unica opzione disponibile).

    - Per **Dimensioni chiave** immettere 2048

    - Verificare che **il nome del contenitore di chiavi automatico** sia selezionato

    - Lasciare deselezionate le altre caselle.

  - In **Opzioni aggiuntive** confermare i valori seguenti:

    - Per **Formato richiesta** selezionare **CMC**.

    - Per **Algoritmo hash** selezionare **sha1**.

    - Per **Nome descrittivo** immettereSmardcard Certificate.

8. Se si utilizza un lettore di smart card fisico, inserire la smart card nel dispositivo.

9. Fare **clic su** Invia per inviare la richiesta di certificato.

10. Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.

    > [!NOTE]
    > Il valore predefinito del PIN della smart card virtuale è "12345678".

11. Dopo l'emissione del certificato, fare clic **su Installa questo certificato** per completare il processo di registrazione.

    > [!NOTE]
    >  Se la richiesta di certificato ha esito negativo con l'errore "Questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi possibili per risolvere il problema:
    >- Abilita Visualizzazione Compatibilità in Internet Explorer.
    >- Abilita l'opzione Attiva impostazioni Intranet in Internet Explorer.
    >- Seleziona l'impostazione Reimposta tutte le aree al livello predefinito nella scheda Sicurezza del menu Opzioni di Internet Explorer.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurare Active Directory Federation Services (AD FS 2.0)

Nella sezione seguente viene descritto come configurare Active Directory Federation Services (AD FS 2.0) per supportare l'autenticazione a più fattori. Per informazioni su come installare AD FS 2.0, vedere [Ad FS 2.0 Step-by-Step e How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).

> [!NOTE]
> Quando si installa AD FS 2.0, non utilizzare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services. In alternativa, scaricare e installare [Active Directory Federation Services.](/troubleshoot/windows-server/identity/availability-description-afds)

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Per configurare ADFS per l'autenticazione a due fattori

1. Accedere al computer AD FS 2.0 utilizzando un account di amministratore di dominio.

2. Avviare Windows PowerShell.

3. Dalla riga Windows PowerShell comando, eseguire il comando seguente:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Stabilire una partnership con ogni server che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome del server specifico per la distribuzione:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Dal menu Strumenti di amministrazione, avviare la console di gestione di AD FS 2.0.

6. Espandere **Relazioni di** trust  >  **Trusting Party Trusts**.

7. Verificare che sia stato creato un nuovo trust per l'Skype for Business Server.

8. Creare e assegnare una regola di autorizzazione rilascio per l'attendibilità del relying party Windows PowerShell utilizzando i comandi seguenti:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Creare e assegnare una regola di trasformazione rilascio per l'attendibilità del relying party usando Windows PowerShell eseguendo i comandi seguenti:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Dalla console di gestione di AD FS 2.0 fai clic con il pulsante destro del mouse sull'attendibilità del componente e seleziona **Modifica regole attestazione.**

11. Selezionare la **scheda Regole di autorizzazione rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.

12. Selezionare la **scheda Regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurazione di AD FS 2.0 per supportare l'autenticazione client

Esistono due possibili tipi di autenticazione che possono essere configurati per consentire ad AD FS 2.0 di supportare l'autenticazione tramite smart card:

- Autenticazione basata su form

- Autenticazione client Transport Layer Security

Utilizzando l'autenticazione basata su form, è possibile sviluppare una pagina Web che consenta agli utenti di eseguire l'autenticazione utilizzando il nome utente/password o la smart card e il PIN. In questo argomento viene illustrato come implementare l'autenticazione client di Transport Layer Security con AD FS 2.0. Per ulteriori informazioni sui tipi di autenticazione AD FS 2.0, vedere [AD FS 2.0: Come modificare il tipo di autenticazione locale.](https://go.microsoft.com/fwlink/p/?LinkId=313384)

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Per configurare AD FS 2.0 per supportare l'autenticazione client

1. Accedere al computer AD FS 2.0 utilizzando un account di amministratore di dominio.

2. Avvia Windows Explorer.

3. Passare a C:\inetpub\adfs\ls

4. Creare una copia di backup del file web.config esistente.

5. Apri il file web.config esistente usando Blocco note.

6. Nella barra dei menu selezionare **Modifica** e quindi **Trova**.

7. Cercare \<localAuthenticationTypes\> .

    Si noti che sono elencati quattro tipi di autenticazione, uno per riga.

8. Spostare la riga contenente il tipo di autenticazione TLSClient all'inizio dell'elenco nella sezione.

9. Salvare e chiudere il file web.config file.

10. Avviare un prompt dei comandi con privilegi elevati.

11. Riavviare IIS eseguendo il comando seguente:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurazione dell Skype for Business Server a autenticazione passiva

Nella sezione seguente viene descritto come configurare Skype for Business Server per supportare l'autenticazione passiva. Una volta abilitato, gli utenti abilitati per l'autenticazione a due fattori doranno utilizzare una smart card fisica o virtuale e un PIN valido per accedere utilizzando il client Skype for Business.

> [!NOTE]
> È consigliabile che i clienti abilitino l'autenticazione passiva per la funzione di registrazione e i servizi Web a livello di servizio. Se l'autenticazione passiva è abilitata per la funzione di registrazione e i servizi Web a livello globale, si verificano probabilmente errori di autenticazione a livello di organizzazione per gli utenti che non amberanno con il client desktop supportato.

### <a name="web-service-configuration"></a>Configurazione servizio Web

Nei passaggi seguenti viene descritto come creare una configurazione del servizio Web personalizzata per i server Director, Enterprise Pool e edizione Standard che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Per creare una configurazione del servizio Web personalizzata

1. Accedere al Skype for Business Server Front End Server utilizzando un account Skype for Business amministratore.

2. Avviare Skype for Business Server Management Shell.

3. Dalla riga di comando di Skype for Business Server Management Shell creare una nuova configurazione del servizio Web per ogni server Director, pool Enterprise e server edizione Standard che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > Il valore per il nome di dominio completo WsFedPassiveMetadataUri è il nome del servizio federativo del server AD FS 2.0. Il valore Nome servizio federativo è disponibile nella console di gestione di AD FS 2.0 facendo clic con il pulsante destro del mouse su **Servizio** nel riquadro di spostamento e quindi scegliendo Modifica proprietà **servizio federativo**.

4. Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando seguente:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferito per l'autenticazione webticket. Per tutti i server Director, pool Enterprise e server edizione Standard che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disabilitati nei servizi Web di Skype for Business eseguendo il cmdlet seguente:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verificare che tutti gli altri tipi di autenticazione siano stati disabilitati correttamente eseguendo il cmdlet seguente:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configurazione proxy

Quando l'autenticazione del certificato è disabilitata per i servizi Web di Skype for Business, il client Skype for Business utilizzerà un tipo di autenticazione meno preferito, ad esempio Kerberos o NTLM, per l'autenticazione nel servizio di registrazione. L'autenticazione del certificato è ancora necessaria per consentire al client di recuperare un webticket, tuttavia, Kerberos e NTLM devono essere disabilitati per il servizio di registrazione.

I passaggi seguenti descrivono come creare una configurazione proxy personalizzata per pool di server perimetrali, pool di Enterprise e server edizione Standard che verranno abilitati per l'autenticazione passiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Per creare una configurazione proxy personalizzata

1. Dalla riga di comando di Skype for Business Server Management Shell creare una nuova configurazione Skype for Business Server proxy per ogni pool di server perimetrali, pool di Enterprise e server edizione Standard che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente: comandi:

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

[Usare l'autenticazione a due fattori con Skype for Business client e Skype for Business Server](use-two-factor.md)
