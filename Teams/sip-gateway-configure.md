---
title: Configurare il gateway SIP
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
description: Informazioni su come configurare il gateway SIP.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1af44c5e3962f89346cae166bf40efa6a8622338
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2022
ms.locfileid: "62065182"
---
# <a name="configure-sip-gateway"></a>Configurare il gateway SIP

Questo articolo spiega come configurare il gateway SIP in modo che l'organizzazione possa usare dispositivi SIP compatibili con Microsoft Teams. Per informazioni su cosa può fare il gateway SIP per l'organizzazione e su quali componenti hardware, software e licenze è necessario all'organizzazione, vedere [Pianificare il gateway SIP.](sip-gateway-plan.md)

Prima di configurare il gateway SIP, eseguire le operazioni seguenti:

- **Reimpostare i dispositivi SIP alle impostazioni predefinite del produttore.** L'utente o gli utenti dell'organizzazione devono reimpostare le impostazioni predefinite predefinite di ogni dispositivo SIP usato con il gateway SIP. Per informazioni su come farlo, vedere le istruzioni del produttore.

- **Aprire il firewall per Microsoft 365 e Teams.** Aprire il firewall della rete per Microsoft 365 e Teams traffico, come descritto in URL e intervalli di indirizzi IP Office 365 [indirizzi IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- **Assicurarsi che i dispositivi SIP non siano dietro un proxy.** Assicurarsi che il traffico http/s bypassi qualsiasi proxy http/s aziendale.

- **Aprire la porta UDP.** Aprire la porta UDP nell'intervallo da 49152 a 53247 per gli intervalli IP da 52.112.0.0/14 a 52.120.0.0/14.

- **Aprire la porta TCP.** Aprire la porta TCP 5061 per gli intervalli IP da 52.112.0.0/14 a 52.120.0.0/14.

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



Le sezioni seguenti descrivono le operazioni che è necessario eseguire come amministratore per configurare il gateway SIP.

- [Verificare che gateway SIP sia disponibile per l'organizzazione](#verify-that-sip-gateway-is-available-for-your-organization).

- [Abilitare il gateway SIP per gli utenti dell'organizzazione.](#enable-sip-gateway-for-the-users-in-your-organization)

- [Impostare l'URL del server di provisioning del gateway SIP](#set-the-sip-gateway-provisioning-server-url).

Questo articolo descrive anche come:

- [Registrare i dispositivi SIP singolarmente o in batch per comodità.](#provision-and-enroll-sip-devices-as-common-area-phones)  


- [Visualizzare e monitorare i dispositivi SIP.](#view-and-monitor-sip-devices)

- [Abilitare il supporto per un'interfaccia utente in più lingue.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Verificare che gateway SIP sia disponibile per l'organizzazione

1. Accedere all'interfaccia [Teams di amministrazione.](https://admin-teams.microsoft.com/)

2. A sinistra, seleziona Teams **dispositivi e** verifica se la scheda **Dispositivi SIP** è visibile. In caso contrario, il servizio Gateway SIP è abilitato per l'organizzazione.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Abilitare il gateway SIP per gli utenti dell'organizzazione

È possibile abilitare il gateway SIP per l'organizzazione in due modi: usando l'interfaccia di amministrazione di Teams o un cmdlet di PowerShell.

### <a name="by-using-teams-admin-center"></a>Usando l'Teams di amministrazione

Per abilitare il gateway SIP nell'interfaccia Teams di amministrazione, seguire questa procedura:

1. Passare [all'interfaccia Teams di amministrazione](https://admin.teams.microsoft.com/)

2. A sinistra, in **Voce,** selezionare **Criteri di chiamata.**

3. A destra in **Gestisci** criteri selezionare il criterio di chiamata appropriato assegnato agli utenti o, se necessario, creare un nuovo criterio di chiamata e assegnarlo agli utenti necessari.

4. Selezionare **Gestisci criteri,** selezionare un criterio e quindi scegliere **Modifica.**

5. Attivare l'impostazione per i **dispositivi SIP che possono essere usati per le chiamate** e quindi selezionare **Salva.**


### <a name="by-using-powershell"></a>Usando PowerShell

È anche possibile abilitare il gateway SIP usando il cmdlet [Set-CsTeamsCallingPolicy di](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) PowerShell. Per abilitare gli utenti per i dispositivi SIP, selezionare un criterio e impostare `-AllowSIPDevicesCalling` l'attributo su `True` . Il valore predefinito è , quindi gli utenti non potranno usare i dispositivi SIP a `False` meno che non vengano abilitati.


> [!NOTE]
> - La propagazione dei criteri può richiedere fino a 24 ore.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Impostare l'URL del server di provisioning del gateway SIP

È possibile impostare l'URL del server di provisioning del gateway SIP nel server DHCP (Dynamic Host Configuration Protocol). Gli utenti che lavorano in remoto devono configurarlo manualmente.

### <a name="using-dhcp"></a>Uso di DHCP

Per ogni dispositivo SIP, impostare uno degli URL del server di provisioning del gateway SIP seguenti: 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- Americhe: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Aggiungere dispositivi SIP all'organizzazione Teams configurando l'URL del server di provisioning del gateway SIP precedente nel server DHCP. Per altre informazioni sul server DHCP, vedere [Distribuire e gestire IL SERVER DHCP.](/learn/modules/deploy-manage-dynamic-host-configuration-protocol) È anche possibile usare l'opzione DHCP 42 per specificare il server NTP (Network Time Protocol) e l'opzione DHCP 2 per specificare l'offset dall'ora UTC (Coordinated Universal Time) in secondi. I dispositivi dell'organizzazione verranno instradati al server di provisioning del gateway SIP. I telefoni SIP di cui è stato eseguito il provisioning verranno visualizzati il logo Teams e un pulsante soft per l'accesso.

Verificare che i dispositivi SIP siano nella versione minima supportata del firmware per l'onboarding. Durante l'onboarding, gateway SIP inserisce l'interfaccia utente di configurazione e autenticazione predefinita nel dispositivo. Per informazioni sulla versione del firmware necessaria per i dispositivi SIP, vedere [Pianificare il gateway SIP.](sip-gateway-plan.md)

### <a name="manually"></a>Manualmente

Gli utenti che lavorano in remoto devono configurare manualmente l'URL del server di provisioning nel dispositivo SIP usando la procedura seguente:

1. Apri **Impostazioni** sul dispositivo e ottieni l'indirizzo IP del dispositivo.

2. Aprire una finestra del browser, immettere l'indirizzo IP del dispositivo, accedere (se necessario) e configurare l'URL del server di provisioning nell'utilità Web del dispositivo.

3. In **Impostazioni** impostazioni avanzate **nell'utilità** Web immettere l'URL del server di provisioning mostrato sopra.

> [!NOTE]
> - Solo i dispositivi SIP compatibili possono essere collegati al gateway SIP. 
> - I telefoni IP Cisco devono essere lampeggiati sul firmware multipiattaforma prima di poter essere a bordo. Per informazioni su come fare, vedere [Guida alla conversione del firmware Cisco.](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)
> - Per i telefoni Yealink, usare l'opzione 66.
> - Per i telefoni Cisco, Poly e AudioCode, usare l'opzione 160. 
> - Per i dispositivi Cisco, aggiungere **/$PSN.xml** all'URL del server di provisioning.


## <a name="configure-conditional-access"></a>Configurare l'accesso condizionale

L'accesso condizionale è una Azure Active Directory (Azure AD) che consente di garantire che i dispositivi che accedono alle risorse Microsoft 365 risorse siano gestiti e protetti correttamente. Il gateway SIP autentica i dispositivi SIP con Azure AD, quindi se l'organizzazione usa l'accesso condizionale per i dispositivi nella rete aziendale, dovrebbe escludere gli indirizzi IP seguenti:

- America del Nord:
    - Stati Uniti orientali: 52.170.38.140
    - Stati Uniti occidentali: 40.112.144.212
-   Area EMEA:
    - Ue settentrionale: 40.112.71.149
    - Ue occidentale: 40.113.112.67
-   Area APAC:
    - Australia Orientale: 20.92.120.71
    - Australia Sudest: 13.73.115.90

Per altre informazioni, vedere [Intervalli di indirizzi IP.](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Eseguire il provisioning e registrare i dispositivi SIP come telefoni dell'area comune
> [!NOTE]
> Un dispositivo SIP deve essere onboarded al gateway SIP prima di poterlo registrare.

Per semplificare le attività, è possibile registrare i dispositivi SIP nell Teams di amministrazione, uno alla volta o in batch. Ecco come:

1. Accedere all'interfaccia [**Teams di amministrazione.**](https://admin.teams.microsoft.com)

2. Selezionare **Teams dispositivi**  >  **SIP**.

3. Nell'angolo in alto a destra selezionare **Azioni**  >  **provisioning dispositivi** e seguire una di queste istruzioni:

  - **Per eseguire il provisioning di un dispositivo:**

     a. In **In attesa di attivazione** selezionare **Aggiungi**.

     b. Nel riquadro **Aggiungi indirizzi MAC** immettere l'indirizzo **MAC** e **la** posizione del dispositivo e quindi selezionare **Applica**.
     
     c. In **In attesa di attivazione** selezionare il dispositivo appena aggiunto e quindi selezionare Genera codice di **verifica.**
     
     d. Nel riquadro **Provisioning dispositivi,** in **Codice di verifica,** prendere nota del codice di verifica per il dispositivo SIP.

   - **Per eseguire il provisioning di molti dispositivi:**

     a. In **In attesa dell'attivazione,** a destra, **selezionare** Esporta (l'icona Microsoft Excel).
     
     b. Nel riquadro **Provisioning dei dispositivi,** in Upload più indirizzi **MAC,** selezionare **scarica un modello.**
     
     c. Salvare **Template_Provisioning.csv** nel computer e compilare i campi **ID MAC** e **Posizione.**
    
     d. Nel riquadro **Provisioning dispositivi** selezionare Upload più **indirizzi MAC.** 

     e. A destra del riquadro Upload **indirizzi MAC** selezionare Seleziona **un file** e quindi selezionare il **file** Template_Provisioning.csvche contiene i dati.

     f. Nel riquadro **Provisioning dei dispositivi,** **in** In attesa  di attivazione, selezionare un dispositivo e quindi selezionare Genera codice di verifica per generare un codice di verifica una sola volta per ogni dispositivo di cui è stato eseguito il provisioning. Prendere nota del codice di verifica per ogni dispositivo SIP.

4. Nel dispositivo SIP comporre il codice della funzionalità di registrazione seguito dal codice di verifica. Nel dispositivo SIP comporre il codice di funzionalità di registrazione 55* (usato dal Gateway SIP per la convalida del codice di verifica una sola volta), seguito dal codice di verifica generato nell'interfaccia di amministrazione di Teams per questo \* particolare dispositivo. Ad esempio, se il codice di verifica è 123456, comporre \* 55 123456 \* per registrare il dispositivo.

5.  Nel riquadro **Provisioning dei dispositivi,** in In **attesa di accesso,** selezionare **Disconnesso**.

6. Nella finestra **di dialogo Accedi a un utente** copiare o prendere nota del codice di associazione del dispositivo SIP.

7. Passare a e in Immetti codice immettere il codice di associazione del dispositivo [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) SIP e quindi selezionare **Avanti.** 

8. Nel campo **E-mail** o  telefono della pagina Di accesso Microsoft immettere l'indirizzo di posta elettronica per il dispositivo SIP e quindi selezionare **Avanti.**

9. Nella pagina **Password** immettere la password per l'indirizzo di posta elettronica per il dispositivo SIP e quindi selezionare **Accedi**.

10. Nella pagina **Stai provando ad accedere a Teams gateway** di dispositivi SIP, seleziona **Continua**.

## <a name="how-to-sign-in-and-sign-out"></a>Come accedere e disconnettersi

Per i dispositivi personali degli utenti è supportato solo l'accesso locale. Per disconnettere un dispositivo dall'interfaccia di amministrazione, seguire questa procedura:

1. Accedere all'interfaccia [**Teams di amministrazione.**](https://admin.teams.microsoft.com)

2. Selezionare **Teams dispositivi**  >  **SIP**.

3. A destra selezionare un dispositivo SIP e quindi **scegliere Disconnenneti**.


### <a name="user-pairing-and-sign-in"></a>Associazione degli utenti e accesso

Per associare un dispositivo SIP dopo l'autenticazione dell'utente con le credenziali aziendali, un utente deve:

1. Premere **Accedi nel telefono** SIP per visualizzare l'URL di autenticazione e il codice di associazione. Il codice di associazione è sensibile al tempo. Se scade, l'utente deve **premere** Indietro sul telefono e avviare di nuovo il processo di accesso.

2. Passare all'URL di autenticazione nel browser desktop o mobile dell'utente e usare le credenziali aziendali per accedere.

3. Immettere il codice di associazione visualizzato nel telefono SIP nell'app di autenticazione Web per associare il telefono SIP all'account dell'utente. Con un accesso riuscito, che potrebbe richiedere del tempo, il telefono SIP visualizza il numero di telefono e il nome utente, se il dispositivo lo supporta.

> [!NOTE]
> La posizione del dispositivo visualizzata nell'app Azure Active Directory di autenticazione Web è il data center del gateway SIP a cui è connesso il dispositivo. I telefoni SIP nell'ambito non sono compatibili con OAuth, quindi gateway SIP autentica l'utente tramite l'app di autenticazione Web e quindi abbina il dispositivo alle credenziali dell'utente. Altre informazioni qui: Microsoft Identity Platform flusso di concessione dell'autorizzazione per i dispositivi [OAuth 2.0.](/azure/active-directory/develop/v2-oauth2-device-code)

### <a name="sign-out"></a>Disconnessione

Per disconnettersi, un utente del dispositivo può:

- Premere **Esci nel** dispositivo SIP e seguire la procedura descritta nel dispositivo. 

Per disconnettere un dispositivo nell'interfaccia Teams di amministrazione:

1. Accedere all'interfaccia [**Teams di amministrazione.**](https://admin.teams.microsoft.com)

2. Selezionare **Teams dispositivi**  >  **SIP**.

3. A destra, nel riquadro **Dispositivi SIP,** selezionare il dispositivo.

4. Nel riquadro Dettagli **del dispositivo** selezionare la scheda Dettagli e in alto a destra nel menu Azioni selezionare  **Disconnetta**.  


## <a name="view-and-monitor-sip-devices"></a>Visualizzare e monitorare i dispositivi SIP

È possibile visualizzare e monitorare l'inventario dei dispositivi SIP nell'Teams di amministrazione dopo che gli utenti dei dispositivi hanno fatto l'accesso almeno una volta. Ecco come:

1. Accedere all'interfaccia [Teams di amministrazione.](https://admin.teams.microsoft.com/)

2. Selezionare **Teams dispositivi**  >  **SIP**. Tutti i dispositivi SIP connessi sono elencati a destra.

## <a name="restart-a-sip-device"></a>Riavviare un dispositivo SIP

1. Accedere all'interfaccia [Teams di amministrazione.](https://admin.teams.microsoft.com)

2. Selezionare **Teams dispositivi**  >  **SIP**. 

3. A destra selezionare il dispositivo SIP da riavviare e quindi scegliere **Riavvia**.

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Modifiche ai criteri di sincronizzazione nei dispositivi SIP per applicare i criteri

I dettagli utente e i criteri verranno recuperati nei dispositivi SIP all'accesso degli utenti. Eventuali modifiche ai criteri successivamente apportate agli utenti connessi verranno sincronizzate con il dispositivo entro un'ora. La registrazione dei dispositivi deve essere aggiornata periodicamente con il gateway SIP. I telefoni SIP dipendono dal reindirizzamento delle chiamate, quindi l'amministratore deve impostare `AllowCallRedirect` l'attributo in `Set-CsTeamsCallingPolicy` su `Enabled` .


## <a name="set-a-sip-devices-ui-language"></a>Impostare la lingua dell'interfaccia utente di un dispositivo SIP

Un dispositivo SIP può in genere visualizzare informazioni in molte lingue. L'impostazione della lingua dell'interfaccia utente influisce sulla relativa interfaccia, inclusi i tasti softkey e i messaggi di sistema di accesso/disconnessione. L'impostazione della lingua dell'interfaccia utente viene eseguita nel server di provisioning, usando il server DHCP o manualmente aggiungendo una stringa di codice nell'URL, come illustrato negli esempi seguenti.

Come impostare il tedesco per telefoni Polycom, AudioCodes e Yealink:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Come impostare il giapponese per i telefoni Cisco:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Lingue supportate

|Nome della lingua|Codice lingua]
|-------------|-------------|
|Inglese (impostazione predefinita)|it       |
|Spagnolo      |es           |
|Giapponese     |ja           |
|Tedesco       |de           |
|Francese       |fr           |
|Portoghese   |pt           |

> [!Note]
> - Il giapponese non è supportato da Yealink e parzialmente supportato da Polycom VVX.
> - L'impostazione predefinita del sistema è l'inglese se la lingua selezionata non è supportata dall'endpoint SIP.
> - Se il **parametro lang_xx** non è impostato tramite l'URL di provisioning, viene usato l'inglese come lingua predefinita.
> - Se **l'opzione** Accedi per effettuare una chiamata di emergenza non viene tradotta in altre lingue, verrà presentata una versione abbreviata solo in inglese in **Premere Accedi** sui modelli di telefono IP seguenti a causa di limitazioni di dimensioni dello schermo:
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - L'etichetta softkey della segreteria telefonica è hardcoded con **testo vm** in tutte le lingue per Poly VVX a causa di una limitazione della lunghezza delle stringhe.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPv6

Il gateway SIP supporta solo IPv4. Microsoft Teams servizio e client supportano sia IPv4 che IPv6. Se si vogliono controllare le comunicazioni con Microsoft Teams, usare gli intervalli di indirizzi IP negli URL Microsoft 365 e negli intervalli [di indirizzi IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

## <a name="emergency-calling"></a>Chiamate di emergenza

Il gateway SIP supporta solo indirizzi di emergenza statici, detti anche registrati. Attualmente, gli indirizzi registrati non sono supportati per gli scenari di routing diretto. Per altre informazioni sulle chiamate di emergenza, vedere [Pianificare e gestire le chiamate di emergenza.](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

## <a name="report-problems-to-microsoft"></a>Segnalare problemi a Microsoft

Per segnalare problemi, contattare il [supporto tecnico Microsoft.](https://support.microsoft.com)
