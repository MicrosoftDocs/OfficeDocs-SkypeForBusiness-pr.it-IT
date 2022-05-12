---
title: Configurare gateway SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Informazioni su come configurare il Gateway SIP.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72fdabd1ba25254876bc3d4506c889d50cbc6613
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370889"
---
# <a name="configure-sip-gateway"></a>Configurare gateway SIP

Questo articolo spiega come configurare gateway SIP in modo che l'organizzazione possa usare dispositivi SIP compatibili con Microsoft Teams. Per informazioni su cosa può fare il Gateway SIP per l'organizzazione e su hardware, software e licenze di cui l'organizzazione ha bisogno, vedere [Pianificare il Gateway SIP](sip-gateway-plan.md).

Prima di configurare il Gateway SIP, eseguire le operazioni seguenti:

- **Ripristina le impostazioni predefinite dei dispositivi SIP.** L'utente o gli utenti dell'organizzazione devono ripristinare le impostazioni predefinite di fabbrica di ogni dispositivo SIP usato con Gateway SIP. Per scoprire come farlo, vedi le istruzioni del produttore.

- **Apri il firewall per Microsoft 365 e Teams.** Aprire il firewall della rete per Microsoft 365 e Teams traffico come descritto in [URL e intervalli di indirizzi IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges). Le regole del firewall sono necessarie solo per il traffico in uscita.

- **Verificare che i dispositivi SIP non siano dietro un proxy.** Assicurarsi che il traffico http/s bypassi qualsiasi proxy http/s aziendale.

- **Aprire la porta UDP.** Aprire la porta UDP nell'intervallo da 49152 a 53247 per gli intervalli IP 52.112.0.0/14 e 52.120.0.0/14.

- **Aprire la porta TCP.** Aprire la porta TCP 5061 per gli intervalli IP 52.112.0.0/14 e 52.120.0.0/14.

- **Aprire gli endpoint https seguenti (indirizzi IP e URL):**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net



Le sezioni seguenti descrivono le operazioni da eseguire come amministratore per configurare il Gateway SIP.

- [Verificare che gateway SIP sia disponibile per l'organizzazione](#verify-that-sip-gateway-is-available-for-your-organization).

- [Abilitare gateway SIP per gli utenti dell'organizzazione](#enable-sip-gateway-for-the-users-in-your-organization).

- [Impostare l'URL del server di provisioning del Gateway SIP](#set-the-sip-gateway-provisioning-server-url).

Questo articolo descrive anche come:

- [Registra i dispositivi SIP singolarmente o in batch per motivi di praticità](#provision-and-enroll-sip-devices-as-common-area-phones).  


- [Visualizza e monitora i dispositivi SIP.](#view-and-monitor-sip-devices)

- [Abilita il supporto per un'interfaccia utente multi-lingua.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Verificare che gateway SIP sia disponibile per l'organizzazione

1. Accedere [all'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/).

2. A sinistra seleziona **Teams dispositivi** e verifica se la scheda **Dispositivi SIP** è visibile. In caso affermativo, il servizio Gateway SIP è abilitato per l'organizzazione.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Abilitare gateway SIP per gli utenti dell'organizzazione

È possibile abilitare gateway SIP per l'organizzazione in due modi: usando l'interfaccia di amministrazione di Teams o un cmdlet di PowerShell.

### <a name="by-using-teams-admin-center"></a>Usando Teams'interfaccia di amministrazione

Per abilitare Gateway SIP nell'interfaccia di amministrazione di Teams, seguire questa procedura:

1. Passare [all'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/)

2. A sinistra, in **Voce**, seleziona **Criteri per le chiamate**.

3. A destra in **Gestisci criteri** seleziona il criterio di chiamata appropriato assegnato agli utenti o, se necessario, crea un nuovo criterio per le chiamate e assegnalo agli utenti necessari.

4. Selezionare **Gestisci criteri**, selezionare un criterio e **quindi modifica.**

5. Attiva l'impostazione per **i dispositivi SIP che possono essere usati per le chiamate**, quindi seleziona **Salva**.


### <a name="by-using-powershell"></a>Tramite PowerShell

È anche possibile abilitare gateway SIP utilizzando il cmdlet [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) di PowerShell. Per abilitare gli utenti per i dispositivi SIP, selezionare un criterio e impostare l'attributo `-AllowSIPDevicesCalling` su `True`. Il valore predefinito è `False`, quindi gli utenti non potranno usare i propri dispositivi SIP a meno che non vengano abilitati.

> [!NOTE]
> - La propagazione dei criteri può richiedere fino a 24 ore.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Impostare l'URL del server di provisioning del gateway SIP

È possibile impostare l'URL del server di provisioning del gateway SIP nel server DHCP (Dynamic Host Configuration Protocol). Gli utenti che lavorano in remoto devono configurarlo manualmente.

### <a name="using-dhcp"></a>Uso di DHCP

Per ogni dispositivo SIP, impostare uno degli URL del server di provisioning del Gateway SIP seguenti: 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- Americas: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Aggiungere dispositivi SIP all'organizzazione Teams configurando l'URL del server di provisioning del Gateway SIP indicato sopra nel server DHCP. Per altre informazioni sul server DHCP, vedi [Distribuire e gestire DHCP](/learn/modules/deploy-manage-dynamic-host-configuration-protocol). Inoltre, è possibile usare l'opzione DHCP 42 per specificare il server NTP (Network Time Protocol) e l'opzione DHCP 2 per specificare l'offset da UTC (Coordinated Universal Time) in pochi secondi. I dispositivi dell'organizzazione verranno instradati al server di provisioning del Gateway SIP. Se il provisioning dei telefoni SIP è stato completato correttamente, verranno visualizzati il logo Teams e un pulsante soft per l'accesso.

Verifica che i dispositivi SIP siano nella versione firmware minima supportata per l'onboarding. Durante l'onboarding, gateway SIP eseguirà il push dell'interfaccia utente di autenticazione e configurazione predefinita nel dispositivo. Per informazioni sulla versione del firmware necessaria per i dispositivi SIP, vedere [Pianificare il Gateway SIP](sip-gateway-plan.md).

### <a name="manually"></a>Manualmente

Gli utenti che lavorano in remoto devono configurare manualmente l'URL del server di provisioning nel dispositivo SIP utilizzando la procedura seguente:

1. Apri **Impostazioni** sul dispositivo e ottieni l'indirizzo IP del dispositivo.

2. Aprire una finestra del browser, immettere l'indirizzo IP del dispositivo, accedere (se necessario) e configurare l'URL del server di provisioning nell'utilità Web del dispositivo.

3. In **Impostazioni** o **Impostazioni avanzate** dell'utilità Web immetti l'URL del server di provisioning mostrato sopra.

> [!NOTE]
> - È possibile eseguire l'onboarding di solo dispositivi SIP compatibili nel Gateway SIP. 
> - I telefoni IP Cisco devono essere sottoposti a flashing sul firmware multipiattaforma prima di poter essere caricati. Per scoprire come, vedi [Guida alla conversione del firmware Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html).
> - Per i telefoni Yealink, usa l'opzione 66.
> - Per i telefoni Cisco, Poly e AudioCode, usa l'opzione 160. 
> - Per i dispositivi Cisco, aggiungere **/$PSN.xml** all'URL del server di provisioning.


## <a name="configure-conditional-access"></a>Configurare l'accesso condizionale

L'accesso condizionale è una funzionalità di Azure Active Directory (Azure AD) che consente di garantire che i dispositivi che accedono alle risorse Microsoft 365 siano gestiti e protetti correttamente. Gateway SIP autentica i dispositivi SIP con Azure AD, quindi se l'organizzazione usa l'accesso condizionale per i dispositivi della rete aziendale, deve escludere i seguenti indirizzi IP:

- America del Nord:
    - Stati Uniti orientali: 52.170.38.140
    - Stati Uniti occidentali: 40.112.144.212
-   Area EMEA:
    - Ue settentrionale: 40.112.71.149
    - Ue occidentale: 40.113.112.67
-   Area APAC:
    - Australia orientale: 20.92.120.71
    - Australia sud-orientale: 13.73.115.90

Per altre informazioni, vedere [Intervalli di indirizzi IP](/azure/active-directory/conditional-access/location-condition#ip-address-ranges).


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Provisioning e registrazione di dispositivi SIP come telefoni dell'area comune
> [!NOTE]
> Per poter essere registrato, è necessario eseguire l'onboarding di un dispositivo SIP in Gateway SIP.

Per semplificare le attività, è possibile registrare i dispositivi SIP nell'interfaccia di amministrazione di Teams uno alla volta o in batch. Ecco come:

1. Accedere [**all'interfaccia di amministrazione di Teams**](https://admin.teams.microsoft.com).

2. Seleziona **Teams** **dispositiviSIP** >  dispositivi.

3. In alto a destra seleziona **ActionsProvision**  >  devices e segui uno di questi passaggi:

  - **Per eseguire il provisioning di un dispositivo:**

     a. In **In attesa dell'attivazione** seleziona **Aggiungi**.

     b. Nel riquadro **Aggiungi indirizzi MAC** immetti **l'indirizzo MAC** e la **posizione** del dispositivo, quindi seleziona **Applica**.
     
     C. In **In attesa dell'attivazione** seleziona il dispositivo appena aggiunto e quindi seleziona **Genera codice di verifica**.
     
     D. Nel riquadro **Provisioning dei dispositivi** , in **Codice di verifica**, prendere nota del codice di verifica per il dispositivo SIP.

   - **Per eseguire il provisioning di molti dispositivi:**

     a. In **In attesa dell'attivazione**, a destra, seleziona **Esporta** (l'icona Microsoft Excel).
     
     b. Nel riquadro **Provisioning dei dispositivi**, in **Upload più indirizzi MAC**, selezionare **scarica un modello**.
     
     C. Salvare **Template_Provisioning.csv** nel computer e compilare i campi **ID MAC** e **Posizione** .
    
     D. Nel riquadro **Provisioning dei dispositivi** selezionare **Upload più indirizzi MAC**. 

     e. A destra del riquadro **Upload indirizzi MAC** selezionare **Seleziona un file** e quindi selezionare il file **Template_Provisioning.csv** che contiene i dati.

     F. Nel riquadro **Provisioning dei dispositivi** , in **In attesa dell'attivazione**, seleziona un dispositivo e quindi seleziona **Genera codice di verifica** per generare un codice di verifica una tantum per ogni dispositivo di cui è stato effettuato il provisioning. Prendere nota del codice di verifica per ogni dispositivo SIP.

4. Nel dispositivo SIP comporre il codice della funzionalità di registrazione seguito dal codice di verifica. Nel dispositivo SIP comporre il codice \*funzionalità di registrazione 55* (usato dal Gateway SIP per la convalida del codice di verifica una tantum), seguito dal codice di verifica generato nell'interfaccia di amministrazione di Teams per questo particolare dispositivo. Ad esempio, se il codice di verifica è 123456, comporre \*il numero 55\* 123456 per registrare il dispositivo.

5.  Nel riquadro **Provisioning dei dispositivi** , **in In attesa dell'accesso**, seleziona **Disconnetti**.

6. Nella finestra di dialogo **Accedi a un utente** copiare o prendere nota del codice di associazione del dispositivo SIP.

7. Vai a [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)e in **Immetti il codice** immetti il codice di associazione del dispositivo SIP, quindi seleziona **Avanti**.

8. Nella pagina Microsoft **Sign in** immettere l'indirizzo di posta elettronica del dispositivo SIP nel campo **E-mail o telefono** e quindi selezionare **Avanti**.

9. Nella pagina **Password** immettere la password per l'indirizzo di posta elettronica del dispositivo SIP e quindi selezionare **Accedi**.

10. Nella pagina **Stai tentando di accedere a Teams gateway di dispositivi SIP**, seleziona **Continua**.

## <a name="how-to-sign-in-and-sign-out"></a>Come accedere e disconnettersi

Solo l'accesso locale è supportato per i dispositivi personali degli utenti. Per disconnettersi da un dispositivo dall'interfaccia di amministrazione, procedere come segue:

1. Accedere [**all'interfaccia di amministrazione di Teams**](https://admin.teams.microsoft.com).

2. Seleziona **Teams** **dispositiviSIP** >  dispositivi.

3. A destra seleziona un dispositivo SIP e quindi **disconnetti**.


### <a name="user-pairing-and-sign-in"></a>Associazione e accesso dell'utente

Per associare un dispositivo SIP dopo l'autenticazione dell'utente con le credenziali aziendali, un utente deve:

1. Premi **Accedi nel** telefono SIP per visualizzare l'URL di autenticazione e il codice di associazione. Il codice di associazione fa distinzione tra data e ora. Se scade, l'utente deve premere **Indietro** sul telefono e avviare di nuovo la procedura di accesso.

2. Passare all'URL di autenticazione nel browser desktop o per dispositivi mobili dell'utente e usare le credenziali aziendali per accedere.

3. Immetti il codice di associazione visualizzato nel telefono SIP nell'app di autenticazione Web per associare il telefono SIP all'account dell'utente. In caso di accesso riuscito, che potrebbe richiedere del tempo, il telefono SIP visualizzerà il numero di telefono e il nome utente, se supportati dal dispositivo.

> [!NOTE]
> La posizione del dispositivo visualizzata nell'app di autenticazione Web Azure Active Directory è il data center Gateway SIP a cui è connesso il dispositivo. I telefoni SIP nell'ambito non supportano OAuth, quindi il Gateway SIP autentica l'utente tramite l'app di autenticazione Web e quindi associa il dispositivo alle credenziali dell'utente. Altre informazioni sono disponibili qui: [Microsoft Identity Platform e il flusso di concessione delle autorizzazioni per i dispositivi OAuth 2.0](/azure/active-directory/develop/v2-oauth2-device-code).

### <a name="sign-out"></a>Disconnessione

Per disconnettersi, un utente del dispositivo può:

- Premi **Disconnetti** nel dispositivo SIP e segui i passaggi descritti nel dispositivo. 

Per disconnettersi da un dispositivo nell'interfaccia di amministrazione di Teams:

1. Accedere [**all'interfaccia di amministrazione di Teams**](https://admin.teams.microsoft.com).

2. Seleziona **Teams** **dispositiviSIP** >  dispositivi.

3. A destra, nel riquadro **Dispositivi SIP** , selezionare il dispositivo.

4. Nel **riquadro Dettagli** del dispositivo seleziona la scheda **Dettagli** , quindi in alto a destra nel menu **Azioni** seleziona **Disconnetti**. 

## <a name="view-and-monitor-sip-devices"></a>Visualizzare e monitorare i dispositivi SIP

Puoi visualizzare e monitorare l'inventario dei dispositivi SIP nell'interfaccia di amministrazione di Teams dopo che gli utenti dei dispositivi hanno eseguito l'accesso almeno una volta. Ecco come:

1. Accedere [all'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/).

2. Seleziona **Teams** **dispositiviSIP** >  dispositivi. Tutti i dispositivi SIP connessi sono elencati a destra.

## <a name="restart-a-sip-device"></a>Riavviare un dispositivo SIP

1. Accedere [all'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com).

2. Seleziona **Teams** **dispositiviSIP** >  dispositivi. 

3. A destra seleziona il dispositivo SIP che vuoi riavviare e quindi **seleziona Riavvia**.


> [!NOTE]
> - La rimozione di un dispositivo SIP dal tenant non è attualmente disponibile nell'interfaccia di amministrazione di Teams. 
> - L'esecuzione del comando dipende dalla disponibilità del dispositivo e potrebbe non corrispondere allo stato di esecuzione visualizzato nell'interfaccia di amministrazione di Teams. Se si tenta di abilitare il gateway SIP in un dispositivo che non lo supporta, il comando non verrà eseguito.

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Modifiche dei criteri di sincronizzazione nei dispositivi SIP per applicare i criteri

I dettagli e i criteri utente verranno recuperati nei dispositivi SIP quando gli utenti accedono. Le eventuali modifiche apportate successivamente ai criteri per gli utenti connessi verranno sincronizzate con il dispositivo entro un'ora. La registrazione dei dispositivi deve essere aggiornata periodicamente con il Gateway SIP. I telefoni SIP dipendono da Call Redirect, quindi l'amministratore deve impostare l'attributo `AllowCallRedirect` in su `Set-CsTeamsCallingPolicy` `Enabled`.


## <a name="set-a-sip-devices-ui-language"></a>Impostare la lingua dell'interfaccia utente di un dispositivo SIP

Un dispositivo SIP in genere può visualizzare informazioni in molte lingue. L'impostazione della lingua dell'interfaccia utente influisce sull'interfaccia, inclusi i tasti di scelta rapida e i messaggi di sistema di accesso/disconnessione. L'impostazione della lingua dell'interfaccia utente viene eseguita nel server di provisioning, tramite server DHCP o manualmente aggiungendo una stringa di codice nell'URL, come illustrato negli esempi seguenti.

Come impostare il tedesco per i telefoni Polycom, AudioCodes e Yealink:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Come impostare il giapponese per i telefoni Cisco:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Lingue supportate

|Nome della lingua|Codice lingua]
|-------------|-------------|
|Inglese (impostazione predefinita)|En       |
|Spagnolo      |Es           |
|Giapponese     |Ja           |
|Tedesco       |De           |
|Francese       |Padre           |
|Portoghese   |Pt           |

> [!Note]
> - Il giapponese non è supportato da Yealink e parzialmente supportato da Polycom VVX.
> - L'impostazione predefinita del sistema è l'inglese se la lingua selezionata non è supportata dall'endpoint SIP.
> - Quando il parametro **lang_xx** non è impostato tramite l'URL di provisioning, viene usato l'inglese come lingua predefinita.
> - Se **l'opzione Accedi per effettuare una chiamata di emergenza** non viene tradotta in altre lingue, una versione abbreviata solo in inglese verrà presentata in **Press Sign In** sui seguenti modelli di telefono IP a causa di limitazioni delle dimensioni dello schermo:
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - L'etichetta con tasti di scelta rapida della segreteria telefonica è hardcoded con testo **della macchina virtuale** in tutte le lingue per Poly VVX a causa di un limite di lunghezza della stringa.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPv6

Gateway SIP supporta solo IPv4. Microsoft Teams servizio e client supportano sia IPv4 che IPv6. Per controllare le comunicazioni con Microsoft Teams, usare gli intervalli di indirizzi IP in [url e intervalli di indirizzi IP Microsoft 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="emergency-calling"></a>Chiamate di emergenza

Gateway SIP supporta solo indirizzi di emergenza statici, denominati anche registrati. Attualmente, gli indirizzi registrati non sono supportati per gli scenari di routing diretto. Per altre informazioni sulle chiamate di emergenza, vedi [Pianificare e gestire le chiamate di emergenza](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).

## <a name="report-problems-to-microsoft"></a>Segnalare problemi a Microsoft

Per segnalare problemi, contatta [supporto tecnico Microsoft](https://support.microsoft.com).
