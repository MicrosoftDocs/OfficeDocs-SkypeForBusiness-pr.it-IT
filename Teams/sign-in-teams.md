---
title: Accedere a Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: Informazioni sul funzionamento dell'autenticazione moderna, su come cambiare account e come risolvere i problemi relativi all'autenticazione moderna. Include il metodo per indicare a Teams di ignorare la precompilazione del nome dell'utente (UPN) al momento dell'accesso.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d58d9aaecd2c5d07922a96e0d5b0cb1ead4ba25b
ms.sourcegitcommit: 5df33e7fe912426e3e158b3be7334e05dc3803a5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53345702"
---
<a name="sign-in-to-microsoft-teams"></a>Accedere a Microsoft Teams
==========================

## <a name="windows-users"></a>Utenti di Windows

Microsoft consiglia alle organizzazioni di usare le versioni recenti di Windows 10 con configurazione di aggiunta a dominio ibrido o aggiunta ad Azure AD. Con le versioni recenti, gli account degli utenti vengono inseriti in Gestione account Web di Windows, il che a sua volta abilita l'accesso Single Sign-On a Teams e ad altre applicazioni Microsoft. Il Single Sign-On offre un'esperienza utente migliore, grazie all'accesso automatico, e un livello di sicurezza superiore.

Microsoft Teams usa l'autenticazione moderna per mantenere l'esperienza di accesso più semplice e sicura. Per scoprire in che modo gli utenti accedono a Teams, leggere [Accedere a Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

### <a name="how-modern-authentication-works"></a>Funzionamento dell'autenticazione moderna

L'autenticazione moderna è un processo che informa Teams che gli utenti hanno già immesso le loro credenziali, come l'indirizzo di posta elettronica aziendale e la password, e che non è necessario immetterle di nuovo per avviare l'app. L'esperienza varia in base a un paio di fattori, ad esempio se gli utenti lavorano in Windows o in Mac. Inoltre, varia anche a seconda che l’organizzazione abbia abilitato l'autenticazione a fattore singolo o l'autenticazione a più fattori. L'autenticazione a più fattori implica in genere la verifica delle credenziali tramite telefono, la creazione di un codice univoco, l'immissione di un PIN o la presentazione di un'identificazione personale. Ecco una panoramica di ogni scenario di autenticazione moderna.

L'autenticazione moderna è disponibile per tutte le organizzazioni che usano Teams. Se gli utenti non riescono a completare il processo, può essere presente un problema sottostante relativo alla configurazione di Azure AD dell'organizzazione. Per altre informazioni, vedere [Perché non riesco ad accedere a Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

- Se gli utenti hanno già eseguito l'accesso a Windows o ad altre app di Office tramite il loro account aziendale o dell'istituto di istruzione, all'avvio di Teams vengono portati direttamente all'app. Non è necessario immettere le credenziali.

- Microsoft consiglia di usare Windows 10 versione 1903 o successiva per ottenere un'esperienza di Single Sign-On ottimale.

- Se gli utenti non hanno eseguito l'accesso al proprio account Microsoft aziendale o dell'istituto di istruzione, all'avvio di Teams viene loro chiesto di fornire l'autenticazione a uno o a più fattori (SFA o MFA). Questo processo dipende dalla scelta dei requisiti per la procedura di accesso da parte dell'organizzazione.

- Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio, all'avvio di Teams potrebbero dover eseguire un ulteriore passaggio di autenticazione, a seconda che l'organizzazione abbia scelto di richiedere l'autenticazione MFA o che il computer in uso richieda già l'autenticazione MFA per accedere. Se il computer in uso richiede già l'autenticazione MFA per accedere, aprendo Teams l'app viene avviata automaticamente.

- Nel caso dei PC aggiunti a dominio, quando il Single Sign-On non è possibile, Teams potrebbe precompilare il nome dell'entità utente (UPN) nella propria schermata di accesso. In alcuni casi questo non è desiderabile, soprattutto se l'organizzazione usa UPN diversi in locale e in Azure Active Directory. Per disattivare il prepopolamento dell'UPN si può usare la chiave del Registro di sistema di Windows seguente:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > La precompilazione del nome utente per i nomi che terminano in ".local" o ".corp" è disattivata per impostazione predefinita, non è necessario impostare una chiave del Registro di sistema allo scopo.

### <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Disconnessione da Teams dopo aver completato l'autenticazione moderna

Per disconnettersi da Teams, gli utenti possono selezionare l'immagine del profilo nella parte superiore dell'app e quindi selezionare **Disconnetti**. Possono anche fare clic con il pulsante destro del mouse sull'icona dell'app nella barra delle applicazioni e scegliere **Disconnetti**. Dopo la disconnessione da Teams, per avviare l'app è necessario immettere di nuovo le credenziali.

### <a name="signing-in-to-another-account-on-a-domain-joined-computer"></a>Accesso a un altro account in un computer aggiunto a un dominio

Gli utenti su un computer aggiunto a un dominio potrebbero non riuscire ad accedere a Teams con un altro account nello stesso dominio di Active Directory.

## <a name="macos-users"></a>Utenti di macOS

In macOS, Teams richiederà agli utenti di immettere il nome utente e le credenziali e potrebbe richiedere l'autenticazione a più fattori, in base alle impostazioni dell'organizzazione. Una volta immesse le credenziali, gli utenti non dovranno fornirle di nuovo. Da quel momento in poi, Teams si avvierà automaticamente ogni volta che lavorano con lo stesso computer.

## <a name="teams-on-ios-and-android-users"></a>Utenti di Teams per iOS e Android

Dopo l'accesso, gli utenti dei dispositivi mobili visualizzano un elenco di tutti gli account di Microsoft 365 attualmente connessi o che sono stati connessi al dispositivo in precedenza. Possono toccare uno qualsiasi degli account per eseguire l'accesso. Per l'accesso ai dispositivi mobili sono possibili due scenari:

1. Se l'account selezionato è attualmente connesso ad altre app Office 365 o Microsoft 365, l'utente viene indirizzato direttamente a Teams, senza dover immettere le credenziali.

2. Se l'utente non ha effettuato l'accesso al proprio account di Microsoft 365 in nessun'altra posizione, verrà chiesto di effettuare un'autenticazione a uno o più fattori (SFA o MFA), a seconda di come l'organizzazione ha configurato i criteri di accesso per i dispositivi mobili.

> [!NOTE]
> Per consentire agli utenti di provare l'esperienza di accesso descritta in questa sezione, sui dispositivi deve essere installata la versione 2.0.13 (Build 2020061704) o successiva di Teams per iOS, oppure la versione 1416/1.0.0.2020061702 o successiva di Teams per Android.

## <a name="using-teams-with-multiple-accounts"></a>Uso di Teams con più account

Teams per iOS e Teams per Android supportano l'uso affiancato di più account aziendali o dell'istituto di istruzione e di più account personali. Le applicazioni Teams desktop supporteranno l'uso affiancato di un solo account aziendale/dell'istituto di istruzione e un solo account personale dal dicembre 2020. Il supporto per più account aziendali/dell'istituto di istruzione sarà disponibile in una data successiva.

Le immagini seguenti mostrano il modo in cui gli utenti possono aggiungere più account nelle applicazioni Teams per dispositivi mobili.

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Aggiunta di più account in Teams":::

## <a name="restrict-sign-in-to-teams"></a>Limitare l'accesso a Teams

L'organizzazione può voler limitare l'uso delle app approvate dall'azienda nei dispositivi gestiti, ad esempio per limitare la capacità degli studenti o dei dipendenti di accedere ai dati di altre organizzazioni oppure di usare app approvate dall'azienda per scenari personali. Queste restrizioni possono essere applicate impostando criteri per i dispositivi riconosciuti dalle applicazioni Teams.   

### <a name="how-to-restrict-sign-in-on-mobile-devices"></a>Come limitare l'accesso nei dispositivi mobili

Teams per iOS e Teams per Android offrono agli amministratori IT la possibilità di inviare le configurazioni account agli account di Microsoft 365. Questa funzionalità può essere usata con qualsiasi provider di gestione dispositivi mobili (MDM) che usi il canale di [Configurazione gestita delle app](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) per iOS o il canale [Android Enterprise](https://developer.android.com/work/managed-configurations) per Android.

Per gli utenti registrati in Microsoft Intune, è possibile distribuire le impostazioni di configurazione degli account usando Intune nel portale di Azure.

Dopo la configurazione dell'account nel provider MDM e dopo che l'utente ha eseguito la registrazione del dispositivo, Teams per iOS e Teams per Android mostreranno solo gli account autorizzati nella pagina di accesso di Teams. L'utente può toccare uno qualsiasi degli account autorizzati in tale pagina per eseguire l'accesso.

Impostare i parametri di configurazione seguenti nel portale di Azure Intune per i dispositivi gestiti.

|Piattaforma |Chiave  |Valore  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Abilitato**: l'unico account autorizzato è l'account utente gestito definito dalla chiave IntuneMAMUPN.<br> **Disabilitato:** (o qualsiasi valore senza distinzione tra maiuscole e minuscole che corrisponde a **Abilitato**): qualsiasi account è abilitato.        |
|iOS     |   **IntuneMAMUPN**      |   UPN dell'account autorizzato ad accedere a Teams.<br> Per i dispositivi registrati in Intune, è possibile usare il token {{userprincipalname}} per rappresentare l'account utente registrato.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    I soli account autorizzati sono gli account utente gestiti definiti da questa chiave.<br> Uno o più punti e virgola;]- UPN delimitati.<br> Per i dispositivi registrati in Intune, è possibile usare il token {{userprincipalname}} per rappresentare l'account utente registrato.

Dopo la configurazione dell'account, Teams limiterà la possibilità di eseguire l'accesso, in modo che possano accedere solo agli account autorizzati nei dispositivi registrati.

Per creare un criterio di configurazione dell'app per i dispositivi iOS/iPadOS gestiti, vedere [Aggiungere criteri di configurazione delle app per i dispositivi iOS/iPadOS gestiti](/mem/intune/apps/app-configuration-policies-use-ios).

Per creare un criterio di configurazione dell'app per i dispositivi Android gestiti, vedere [Aggiungere criteri di configurazione delle app per i dispositivi Android gestiti](/mem/intune/apps/app-configuration-policies-use-android).

### <a name="how-to-restrict-sign-in-on-desktop-devices"></a>Come limitare l'accesso nei dispositivi desktop
Le app Teams in Windows e macOS supportano ora l'uso di criteri per i dispositivi che limitano l'accesso all'organizzazione. I criteri possono essere impostati mediante le normali soluzioni di gestione dei dispositivi, ad esempio MDM o GPO (oggetto Criteri di gruppo). 

Quando in un dispositivo è configurato questo criterio, gli utenti possono accedere solo con account ospitati in un tenant di Azure AD incluso nell'elenco dei tenant consentiti definito nel criterio. Il criterio si applica a tutti gli accessi, inclusi il primo e gli altri account. Se l'organizzazione si estende su più tenant di Azure AD, è possibile includere più ID tenant nell'elenco dei consentiti. I collegamenti per l'aggiunta di un altro account potrebbero continuare a essere visibili nell'app Teams, ma non saranno utilizzabili.

> [!NOTE]
>1. Il criterio limita solo gli accessi, ma non la possibilità per gli utenti di essere invitati come guest in altri tenant di Azure AD o di passare ad altri tenant (in cui gli utenti sono stati invitati come guest).
>2. Il criterio richiede Teams per Windows versione 1.3.00.30866 o successiva e Teams per macOS versione 1.3.00.30882 (rilasciati a metà novembre 2020).

**Criteri per Windows** I file modello amministrativi (ADMX/ADML) sono disponibili dal [Centro download](https://www.microsoft.com/download/details.aspx?id=49030) (il nome descrittivo dell'impostazione criterio nel file modello amministrativo è "Limita l'accesso a Teams agli account in tenant specifici"). Inoltre, è possibile impostare manualmente le chiavi nel Registro di sistema di Windows:

- Nome valore: RestrictTeamsSignInToAccountsFromTenantList
- Tipo valore: stringa
- Dati valore: ID tenant o elenco separato da virgole di ID tenant
- Percorso: usare uno dei seguenti:

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

Esempio: SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID o SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 1,Tenant ID 2,Tenant ID 3

**Criteri per macOS** Per i dispositivi gestiti macOS, usare .plist per distribuire le restrizioni di accesso. Il profilo di configurazione è un file con estensione plist composto da voci identificate da una chiave (che indica il nome della preferenza), seguito da un valore che varia in base alla natura della preferenza. I valori possono essere semplici, ad esempio un valore numerico, o complessi, come un elenco annidato di preferenze.

- Dominio: com.microsoft.teams
- Chiave: RestrictTeamsSignInToAccountsFromTenantList
- Tipo di dati: stringa
- Commenti: immettere un elenco delimitato da virgole di ID tenant di Azure AD


## <a name="sign-out-on-mobile-devices"></a>Disconnessione su dispositivi mobili

Gli utenti di dispositivi mobili possono disconnettersi da Teams passando al menu, selezionando **Altro** e poi **Disconnetti**. Una volta disconnessi, dovranno reimmettere le credenziali per avviare l'app la volta successiva.

> [!NOTE]
> Teams per Android usa Single Sign-on (SSO) per facilitare l'esperienza di accesso. Gli utenti devono disconnettersi da **Tutte** le app Microsoft, oltre a Teams, per completare l'uscita dalla piattaforma Android.

### <a name="global-sign-in-and-sign-out"></a>Accesso e disconnessione globali

L'app Teams per Android ora supporta l'accesso e la disconnessione globali, in modo da fornire un'esperienza di accesso e disconnessione senza problemi per gli operatori sul campo. I dipendenti possono selezionare un dispositivo dal pool di dispositivi condivisi ed eseguire un singolo accesso per "renderlo loro" per tutta la durata del turno. Al termine del turno, potranno eseguire la disconnessione globale da tutti gli account nel dispositivo. Questa operazione consente di rimuovere tutte le informazioni personali e aziendali dal dispositivo, in modo che possa essere ripristinato nel pool di dispositivi. Per ottenere questa funzionalità, è necessario che il dispositivo sia in modalità condivisa. Per informazioni su come configurare un dispositivo condiviso, vedere [Come usare la modalità dispositivo condiviso in Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

L'esperienza di accesso sarà simile a quella standard di Teams, mentre la disconnessione sarà simile alle due immagini seguenti:

![il telefono cellulare con la dimostrazione della disconnessione](media/global-SignOut.png)  

## <a name="urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP

Teams richiede la connettività a Internet. Per informazioni sugli endpoint che devono essere raggiungibili per i clienti che usano Teams per i piani di Office 365, nel cloud per enti pubblici e in altri cloud, vedere [URL e intervalli di indirizzi IP per Office 365](/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> Attualmente Teams richiede l'accesso sulla porta TCP 443 al servizio Google ssl.gstatic.com per tutti gli utenti. Questo avviene anche se non si usa Gstatic. Teams rimuoverà il requisito presto (all'inizio del 2020) e questo articolo verrà aggiornato di conseguenza.

## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
