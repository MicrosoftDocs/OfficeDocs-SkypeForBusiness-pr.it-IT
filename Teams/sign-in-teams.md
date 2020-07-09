---
title: Accedere a Teams con l'autenticazione moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Informazioni sul funzionamento dell'autenticazione moderna, su come cambiare account e come risolvere i problemi relativi all'autenticazione moderna. Include il metodo per indicare a Teams di ignorare il precompilamento del nome dell'utente (UPN) al momento dell'accesso.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb5b21be6b45aab617c0bcb48fbcbb2d404a816
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085442"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Accedere a Microsoft Teams con l'autenticazione moderna
==========================

Microsoft consiglia alle organizzazioni di usare le versioni recenti di Windows 10 con configurazione di aggiunta a dominio ibrido o aggiunta ad Azure AD. Questo assicura che gli account degli utenti vengano inseriti in Gestione account Web di Windows, il che a sua volta abilita l'accesso Single Sign-On a Teams e ad altre applicazioni Microsoft. Ne risultano un miglioramento dell'esperienza utente, grazie all'accesso automatico, e un livello di sicurezza superiore.

Microsoft Teams usa l'autenticazione moderna per mantenere l'esperienza di accesso più semplice e sicura. Per scoprire in che modo gli utenti accedono a Teams, leggere [Accedere a Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Funzionamento dell'autenticazione moderna

L'autenticazione moderna è un processo che informa Teams che gli utenti hanno già immesso le loro credenziali, come l'indirizzo di posta elettronica aziendale e la password, e che non è necessario immetterle di nuovo per avviare l'app. L'esperienza varia in base a un paio di fattori, ad esempio se gli utenti lavorano in Windows o in Mac. Inoltre, varia a seconda che l'organizzazione abbia abilitato l'autenticazione a un fattore o l'autenticazione a più fattori. L'autenticazione a più fattori implica in genere la verifica delle credenziali tramite un telefono, l'inserimento di un codice univoco, l'immissione di un PIN o la presentazione di un'identificazione personale. Ecco una panoramica di ogni scenario di autenticazione moderna.

### <a name="windows-users"></a>Utenti di Windows

- Se gli utenti hanno già eseguito l'accesso a Windows o ad altre app di Office tramite il loro account aziendale o dell'istituto di istruzione, all'avvio di Teams vengono portati direttamente all'app. Non è necessario immettere le credenziali.

- Microsoft consiglia di usare Windows 10 versione 1903 o successiva per ottenere un'esperienza di Single Sign-On ottimale.

- Se gli utenti non hanno eseguito l'accesso al proprio account Microsoft aziendale o dell'istituto di istruzione, all'avvio di Teams viene loro chiesto di fornire l'autenticazione a uno o a più fattori (SFA o MFA), in base alla scelta dell'organizzazione.

- Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio, all'avvio di Teams potrebbero dover eseguire un ulteriore passaggio di autenticazione, a seconda che l'organizzazione abbia scelto di richiedere l'autenticazione MFA o che il computer in uso richieda già l'autenticazione MFA per accedere. Se il computer in uso richiede già l'autenticazione MFA per accedere, aprendo Teams l'app viene avviata automaticamente.

- Nel caso dei PC aggiunti a dominio, quando il Single Sign-On non è possibile, Teams potrebbe precompilare il nome dell'entità utente (UPN) nella propria schermata di accesso. In alcuni casi questo non è desiderabile, soprattutto se l'organizzazione usa UPN diversi in locale e in Azure Active Directory. Per disattivare il prepopolamento dell'UPN si può usare la chiave del Registro di sistema di Windows seguente:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > La precompilazione del nome utente per i nomi che terminano in ".local" o ".corp" è disattivata per impostazione predefinita, non è necessario impostare una chiave del Registro di sistema allo scopo.


### <a name="mac-users"></a>Utenti Mac

In MacOS, Teams richiederà agli utenti di immettere il nome utente e le credenziali e potrebbe richiedere l'autenticazione a più fattori, in base alle impostazioni dell'organizzazione. Una volta immesse le credenziali, gli utenti non dovranno fornirle di nuovo. Da quel momento in poi, Teams si avvierà automaticamente ogni volta che lavorano con lo stesso computer.

## <a name="teams-for-ios-and-android-users"></a>Teams per gli utenti di iOS e Android

Dopo l'accesso, gli utenti dei dispositivi mobili visualizzano un elenco di tutti gli account di Microsoft 365 attualmente connessi o che sono stati connessi al dispositivo in precedenza. Possono toccare uno qualsiasi degli account per eseguire l'accesso. Per l'accesso ai dispositivi mobili sono possibili due scenari:
    
1. Se l'account selezionato è attualmente connesso ad altre app di Office 365 o Microsoft 365, l'utente viene indirizzato direttamente a Teams. Non è necessario immettere le credenziali.
    
2. Se l'utente non ha effettuato l'accesso al proprio account di Microsoft 365 in nessun'altra posizione, verrà chiesto di effettuare un'autenticazione a uno o più fattori (SFA o MFA), a seconda di come l'organizzazione ha configurato i criteri di accesso per i dispositivi mobili.

> [!NOTE]
> Per consentire agli utenti di provare l'esperienza di accesso descritta in questa sezione, sui dispositivi deve essere installata la versione 2.0.13 (Build 2020061704) o successiva di Teams per iOS, oppure la versione 1416/1.0.0.2020061702 o successiva di Teams per Android.


### <a name="adding-multiple-accounts-to-teams"></a>Aggiungere account multipli in Teams

Teams per iOS e Android supporta l'aggiunta di più account da un singolo dispositivo. Le immagini seguenti mostrano il modo in cui gli utenti possono aggiungere più account in Teams.
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Aggiunta di più account in Teams":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a>Usare Enterprise Mobility Management per controllare quali account possono accedere a Teams

Teams per iOS e Android offre agli amministratori IT la possibilità di inviare le configurazioni account agli account di Microsoft 365. Questa funzionalità può essere usata con qualsiasi provider di Gestione dei dispositivi mobili (MDM) che usa il canale di  [Configurazione gestita delle app](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html)  per iOS o il canale  [Android Enterprise](https://developer.android.com/work/managed-configurations)  per Android.

Per gli utenti registrati in Microsoft Intune, è possibile distribuire le impostazioni di configurazione degli account usando Intune nel Portale di Azure.

Dopo la configurazione dell'account nel provider MDM e dopo che l'utente ha eseguito la registrazione del dispositivo, Teams per iOS e Android mostrerà solo gli account autorizzati nella pagina di accesso. L'utente può toccare uno qualsiasi degli account autorizzati in tale pagina per eseguire l'accesso.

Impostare i parametri di configurazione seguenti nel portale di Azure Intune per i dispositivi gestiti.


|Piattaforma |Chiave  |Valore  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Abilitato**: l'unico account autorizzato è l'account utente gestito definito dalla chiave IntuneMAMUPN.<br> **Disabilitato:** (o qualsiasi valore senza distinzione tra maiuscole e minuscole che corrisponde a **Abilitato**): qualsiasi account è abilitato.        |
|iOS     |   **IntuneMAMUPN**      |   UPN dell'account autorizzato ad accedere a Teams.<br> Per i dispositivi registrati in Intune, è possibile usare il token {{userprincipalname}} per rappresentare l'account utente registrato.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    I soli account autorizzati sono gli account utente gestiti definiti da questa chiave.<br> Uno o più punti e virgola (;) - UPN delimitati.<br> Per i dispositivi registrati in Intune, è possibile usare il token {{userprincipalname}} per rappresentare l'account utente registrato.

Dopo la configurazione dell'account, Teams limiterà la possibilità di eseguire l'accesso, in modo che possano accedere solo agli account autorizzati nei dispositivi registrati.

Per creare un criterio di configurazione dell'app per i dispositivi iOS/iPadOS gestiti, vedere [Aggiungere i criteri di configurazione delle app per dispositivi gestiti iOS/iPadOS](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).

Per creare un criterio di configurazione dell'app per i dispositivi Android gestiti, vedere  [Aggiungere i criteri di configurazione delle app per dispositivi gestiti Android](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).


## <a name="switching-accounts-after-completing-modern-authentication"></a>Cambiare account dopo aver completato l'autenticazione moderna

Se gli utenti stanno lavorando su un computer aggiunto a un dominio, ad esempio se il tenant ha abilitato Kerberos, non possono cambiare account utente dopo aver completato l'autenticazione moderna. Se gli utenti non stanno lavorando su un computer aggiunto a un dominio, possono cambiare account.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Disconnessione da Teams dopo aver completato l'autenticazione moderna

Per disconnettersi da Teams, gli utenti possono fare clic sull'immagine del profilo nella parte superiore dell'app e quindi selezionare **Disconnetti**. Possono anche fare clic con il pulsante destro del mouse sull'icona dell'app nella barra delle applicazioni e scegliere **Disconnetti**. Dopo la disconnessione da Teams, per avviare l'app è necessario immettere di nuovo le credenziali.

### <a name="signing-out-of-teams-for-ios-and-android"></a>Disconnessione da Teams dei dispositivi iOS e Android

Gli utenti di dispositivi mobili possono disconnettersi da Teams passando al menu, scegliendo **Altro** e poi **Disconnetti**. Una volta disconnessi, dovranno reimmettere le credenziali per avviare l'app la volta successiva.

> [!NOTE]
> Teams per Android usa Single Sign-on (SSO) per facilitare l'esperienza di accesso. Gli utenti devono disconnettersi da **Tutte** le app Microsoft, oltre a Teams, per completare l'uscita dalla piattaforma Android.

## <a name="urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP

Teams richiede la connettività a Internet. Per informazioni sugli endpoint che devono essere raggiungibili per i clienti che usano Teams nei piani di Office 365, nel cloud per enti pubblici e in altri cloud, vedere [URL e intervalli di indirizzi IP per Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> Attualmente Teams richiede l'accesso sulla porta TCP 443 al servizio Google ssl.gstatic.com (<https://ssl.gstatic.com)> per tutti gli utenti. Questo avviene anche se non si usa Gstatic. Teams rimuoverà il requisito presto (all'inizio del 2020) e questo articolo verrà aggiornato di conseguenza.

## <a name="troubleshooting-modern-authentication"></a>Risoluzione dei problemi relativi all'autenticazione moderna

L'autenticazione moderna è disponibile per tutte le organizzazioni che usano Teams, quindi se gli utenti non riescono a completare il processo potrebbe esserci un problema con il dominio o con l'account Microsoft aziendale o dell'istituto di istruzione dell'organizzazione.

Per altre informazioni, vedere [Perché non riesco ad accedere a Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)


## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)