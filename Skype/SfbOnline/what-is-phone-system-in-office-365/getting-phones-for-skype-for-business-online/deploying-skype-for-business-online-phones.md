---
title: Distribuzione dei telefoni per Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Informazioni sui passaggi di distribuzione per ottenere il firmware corretto, aggiornarlo se necessario, assegnare licenze e configurare le impostazioni per i telefoni Skype for business online
ms.openlocfilehash: f4f1a36e5a2e98c4566a81b41bc6e6c281ac9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113149"
---
# <a name="deploying-skype-for-business-online-phones"></a>Distribuzione dei telefoni per Skype for Business Online

[] Questa guida ti aiuta nella distribuzione dei telefoni IP per Skype for Business Online.
  
In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Fasi della distribuzione di telefoni IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Fase 1 - Scarica le guide per l'amministratore e i manuali del telefono del produttore

Prima di iniziare, è una buona idea quella di scaricare le guide per l'amministratore e i manuali d'uso del telefono del produttore.
  
- Per i telefoni Polycom, vedere la [raccolta di documentazione di Poly](https://documents.polycom.com/category/voice).
    
- Per i telefoni Yealink, vedi la [soluzione Yealink Skype for Business HD SIP Phones](http://www.yealink.com/products_top_2.html).
    
- Per i telefoni AudioCodes, consulta la [Guida alla gestione del provisioning Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Fase 2 - Assicurati di stare acquistando o migrando un telefono IP e firmware supportati da Skype for Business.

A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Fase 3 - Verifica che sia installato il firmware giusto e aggiorna il firmware, se necessario

Check the firmware version on your phones. For:
  
- **Telefoni VVX Polycom**, vai a **Impostazioni** > **Stato** > **Piattaforma** > **Applicazione** > **Principale**.
    
- i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.
    
- **Telefoni AudioCodes**, vai a **Menu** > **Stato dispositivo** > **Versione firmware** dalla schermata di avvio.
    
    > [!NOTE]
    > For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals. 
  
- I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.
    
### <a name="step-4---device-update-considerations"></a>Fase 4 - Considerazioni sull'aggiornamento del dispositivo

> [!NOTE]
> Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1). 
  
Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.
  
![Screenshot che mostra la distribuzione di telefoni](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.
  
![Screenshot che mostra le opzioni di aggiornamento e posticipazione.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Per un telefono Polycom, è possibile aggiornare il firmware del telefono selezionando **SwUpdate**.
  
![Screenshot che mostra l'opzione SwUpdate](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Puoi anche scegliere di gestire gli aggiornamenti del firmware utilizzando un sistema di provisioning partner. Per la gestione del sistema di provisioning partner, compresa la personalizzazione avanzata del telefono, consulta le guide per l'amministratore del produttore.
  
> [!CAUTION]
> Assicurati di avere un'unica autorità di aggiornamento dispositivi (aggiornamento del dispositivo in banda o server di provisioning di terze parti) per evitare loop di aggiornamento. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Passaggio 5-impostazioni del telefono per la configurazione e l'infrastruttura

Puoi impostare le opzioni e i criteri del telefono più comunemente utilizzati che utilizzano i cmdlet di Windows PowerShell per la gestione in banda di Skype for Business. Consulta [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) per i dettagli di questi parametri e impostazioni.
  
Per la pianificazione dell'infrastruttura di rete, Vedi [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Passaggio 6-preparazione per l'accesso degli utenti

To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Per altre informazioni sui piani di chiamata, è possibile leggere i [piani di telefono e chiamate](/microsoftteams/calling-plan-landing-page)
  
- Le **opzioni di accesso** disponibili per gli utenti online son le seguenti.
    
  - Gli utenti con **Polycom VVX 5xx/6xx** Phones vedranno:
    
     ![Screenshot che mostra l'accesso ai telefoni Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Gli utenti con **YEALINK T48G/T46G** Phones vedranno:
    
     ![Screenshot che mostra l'accesso ai telefoni Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Per informazioni dettagliate sulle opzioni di accesso supportate dal produttore, vedere [ottenere telefoni per Skype for business online](getting-phones-for-skype-for-business-online.md).
    
- **ID utente** Utilizzando la tastiera del telefono o la tastiera a schermo (se disponibile), gli utenti possono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come <em>amosm@contoso.com</em>  per il nome utente.
    
     ![Screenshot che mostra la schermata di accesso](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'autenticazione PIN non è supportata per Skype for Business online per i telefoni IP LPE e Partner. 
  
- **Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.
    
  > [!NOTE]
  > Gli utenti devono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come  <em>amosm@contoso.com</em>  per il nome utente.
  
     ![Screenshot che mostra la schermata di accesso](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.
    
  - Gli utenti con **Polycom VVX 5xx/6xx** Phones vedranno:
    
     ![Screenshot che mostra le istruzioni di Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Gli utenti con **YEALINK T48G/T46G** Phones vedranno:
    
     ![Screenshot che mostra le istruzioni di Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.
    
  - Gli utenti con **Polycom VVX 5xx/6xx** Phones vedranno:
    
     ![Screenshot che mostra il codice Polycom scaduto](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Gli utenti con **YEALINK T48G/T46G** Phones vedranno:
    
     ![Screenshot che mostra il codice Yealink scaduto](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Utilizzando un browser, accedi all'indirizzo visualizzato sul telefono e inserisci il tuo nome utente Skype for Business.
    
     ![Screenshot che mostra la verifica della posta elettronica](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Immetti il codice mostrato sul telefono.
    
     ![Screenshot che mostra l'immissione di codice nella schermata di accesso](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verificare che il sito visualizzi "[nome produttore telefono] **telefono certificato Skype for business**", quindi fare clic su **continua**.
    
     ![Screenshot che mostra la verifica del nome](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Fai clic sulle credenziali dell'utente o fai clic su **Usa un altro account**:
    
     ![Screenshot che mostra le opzioni delle credenziali](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando viene visualizzata la pagina seguente, è sicuro chiudere il browser.
    
     ![Screenshot che mostra il messaggio di conferma](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > I telefoni LPE per Skype for Business online supportano l'accesso solo attraverso tethering USB. 
  
- **Distribuzioni supportate** La tabella seguente mostra i tipi di autenticazione supportati per i modelli di distribuzione attualmente supportati tra cui integrazione Exchange, autenticazione moderna con autenticazione a più fattori (MFA) e Skype for Business online e locale.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Metodo di accesso telefono** <br/> |**Accesso di Skype for business** <br/> |**Accesso Exchange con autorizzazione moderna e MFA disattivate** <br/> |**Accesso Exchange con autorizzazione moderna e MFA attivate** <br/> |
|Online  <br/> |Online  <br/> |Accesso Web  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Online  <br/> |Online  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Accesso Web  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Autenticazione PIN  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |
|Locale  <br/> |Online/locale  <br/> |Accesso via PC (BTOE)  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |
   
- **Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.
    
    È possibile disabilitare il blocco telefonico per l'organizzazione (che è abilitato per impostazione predefinita), cambiare il timeout di inattività e scegliere se gli utenti possono effettuare telefonate mentre sono bloccati o non usano le impostazioni di inbando. Per altre informazioni su queste impostazioni, vedere [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) .
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:
  
- Accedere al proprio telefono IP usando l'app desktop Skype for business (usando un PC)
    
- Sincronizza telefono con blocco PC
    
- Fare clic per chiamare
    
BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.
  
 **Per distribuire BToE agli utenti**
  
1. Collegare il PC al telefono utilizzando la porta del PC.
    
     ![Schermata che mostra la connessione a un PC](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Scaricare e installare il software BToE più recente dal sito Web del produttore dai collegamenti seguenti. Per migliorare l'esperienza utente, è possibile distribuire e installare il software BToE usando una soluzione di distribuzione dell'amministratore, ad esempio Microsoft endpoint Configuration Manager. Per informazioni sull'uso di Configuration Manager, vedere [pacchetti e programmi in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).
    
   - [Sito di download del software Polycom BToE](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Download software BToE Yealink](http://www.yealink.com/products_list_10.html)
    
   - [Download software BToE AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).
    
> [!NOTE]
> BToE non è attualmente supportato su piattaforme Mac e VDI. 
  
## <a name="related-topics"></a>Argomenti correlati
[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
