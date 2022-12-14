---
title: Configurare i telefoni dell'area comune per Microsoft Teams
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
- admindeeplinkMAC
- admindeeplinkTEAMS
description: Scopri come configurare telefoni per aree comuni per lobby, aree di ricevimento e sale riunioni.
ms.openlocfilehash: 06005f853ac125478ae1fd99dba2d022c5eb0100
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392156"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Configurare telefoni ad area comune per Microsoft Teams

Un telefono dell'area comune viene in genere posizionato in un'area come una sala d'attesa o un'altra area disponibile a molte persone per effettuare una chiamata: un'area di ricezione, una sala di attesa o un telefono per conferenze. I telefoni dell'area comune hanno eseguito l'accesso con account collegati a una licenza **dispositivi condivisi di Microsoft Teams** .

Questo articolo fornisce una panoramica su come distribuire e configurare i dispositivi telefonici di Teams come telefoni ad area comune per gli spazi condivisi. Per un'esperienza più completa con le sale riunioni, incluse le audioconferenze, è consigliabile acquistare una licenza dedicata **per Teams Rooms** con un dispositivo Teams Rooms. Per altre informazioni su Teams Rooms, vedere [Microsoft Teams Rooms](rooms/index.md).

> [!NOTE]
> Gli account per gli oggetti dei telefoni ad area comune creati in Skype for Business Server non possono essere migrati a Microsoft Teams. Seguire i passaggi di questo articolo per ricreare questi account per Teams e, se necessario, eseguire la migrazione della connettività PSTN (Public Switched Telephone Network).

## <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze

Prima di tutto, è necessario acquistare una licenza **per Dispositivi condivisi di Teams** e assicurarsi di avere un telefono certificato. Per cercare e scoprire di più sui telefoni certificati, vai a [Dispositivi Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. Nel [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) passare a **Servizi di acquisto** **fatturazione** > .

2. Se la sezione **Visualizza per categoria** non è già visualizzata, vai a **Acquista da Microsoft** e seleziona **Visualizza prodotti**. Selezionare quindi **Collaborazione e comunicazione**.  

3. Nell'elenco dei prodotti trovare **Dispositivi condivisi di Microsoft Teams** e selezionare **Dettagli**.

4. Immettere il numero di licenze necessarie e selezionare **Acquista**.

> [!NOTE]
> Se si usa Intune nell'ambiente e si hanno regole di accesso condizionale che richiedono la conformità del dispositivo, è necessario assegnare una licenza **di Azure Active Directory Premium Piano 1** e **Intune** all'account del dispositivo per il telefono dell'area comune.
>
> I telefoni ad area comune possono essere interessati da regole di accesso condizionale e da altre configurazioni di identità, come l'autenticazione a più fattori. Per altre informazioni, vedere [Procedure consigliate per l'autenticazione per i dispositivi Teams Android](devices/authentication-best-practices-for-android-devices.md) .

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Passaggio 2 - Creare un nuovo account utente e assegnare licenze

### <a name="using-the-microsoft-365-admin-center"></a>Uso della interfaccia di amministrazione di Microsoft 365

Se stai distribuendo più telefoni area comuni contemporaneamente, scopri come creare account e assegnare licenze [con PowerShell](#using-powershell).

Se stai distribuendo un dispositivo:

1. Nella [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) passare a **Utenti** >  > **attivi****Aggiungere un utente**.

2. Immettere un nome utente come `Main` il nome e `Reception` il secondo nome.

3. Immetti un nome visualizzato se non ne genera automaticamente uno come `Main Reception`.

4. Immetti un nome utente come `MainReception` o `Mainlobby`.

5. Impostare manualmente la password per il telefono dell'area comune. Per impostare la password, deselezionare **Crea automaticamente una password** e **chiedere all'utente di cambiarla al primo accesso**.  

    > [!IMPORTANT]
    > È consigliabile impostare manualmente una password per i telefoni ad area comune per evitare problemi di accesso per gli utenti finali.

6. Selezionare la posizione di utilizzo del dispositivo e assegnare la licenza **Dispositivi condivisi di Teams** all'account. Se sono necessarie altre licenze, ad esempio i Piani per chiamate, assegnale.

> [!NOTE]
> Non è necessario aggiungere una licenza con le funzionalità Sistema telefonico. È incluso nella licenza **Dispositivi condivisi di Teams** .
>
> Se non usi Microsoft Phone System con Direct Routing o Operator Connect, puoi aggiungere le licenze **piani** per chiamate. Per altre informazioni sulle licenze, vedere Licenze per i [componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell quando si vogliono creare e assegnare licenze per più account utente contemporaneamente. Per altre informazioni, vedere [Creare account utente di Microsoft 365 con PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) e [Assegnare licenze di Microsoft 365 agli account utente con PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>Passaggio 3 - Impostare i criteri per i telefoni dell'area comune

Usare i criteri per controllare quali funzionalità sono disponibili per gli utenti nei telefoni dell'area comune.

### <a name="ip-phone-policies"></a>Criteri per i telefoni IP

I criteri per il telefono IP di Teams possono essere modificati solo se l'account che accede al telefono è concesso in licenza con una licenza diversa da **dispositivi condivisi di Teams** .  Se è concessa in licenza con un abbonamento Microsoft 365 E3 o E5 o con un abbonamento Office 365 Enterprise E1, E3 o E5, è possibile modificare i criteri relativi al telefono IP.  Se usi una licenza **di Teams Rooms** nell'account telefonico dell'area comune, ti consentirà solo di usare la `MeetingRoomSignIn` modalità. `MeetingRoomSignIn` non è disponibile nella maggior parte dei telefoni ad area comuni. Per altre informazioni sulle sostituzioni supportate per l'interfaccia del telefono, vedere [Impostare l'interfaccia utente dei dispositivi Android di Microsoft Teams](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection).

Usando i criteri del telefono IP di Teams, impostare il [parametro SignInMode](/powershell/module/skype/new-csteamsipphonepolicy#parameters) per abilitare `CommonAreaPhoneSignIn` l'esperienza telefonica nell'area comune sul dispositivo telefonico di Teams.

Per configurare altri parametri, è consigliabile creare criteri [per i telefoni IP](/powershell/module/skype/new-csteamsipphonepolicy). Ad esempio, se si usa un telefono ad area comune in un'area pubblica, impostare criteri per i telefoni IP per limitare la ricerca nella Rubrica globale dell'organizzazione e bloccare l'hot desking. Per altre informazioni, vedere [Impostare l'interfaccia utente dei dispositivi Android di Teams](/microsoftteams/devices/Teams-Android-devices-user-interface).

### <a name="calling-policies"></a>Criteri di chiamata

Usare i criteri di chiamata per abilitare le chiamate private, usando l'inoltro di chiamata o lo squillo simultaneo sui telefoni dell'area comune. Per altre informazioni, vedi [Chiamate e inoltro di chiamata in Teams](teams-calling-policy.md).

Per impostazione predefinita, il parcheggio di chiamata non è abilitato per i telefoni dell'area comune. È necessario creare un criterio per abilitarlo. Per altre informazioni, vedere [Parcheggio di chiamata e recupero in Microsoft Teams](call-park-and-retrieve.md).

> [!NOTE]
> Dopo aver assegnato un criterio, disconnettiti dal telefono ed esegui di nuovo l'accesso. L'applicazione di un'assegnazione dei criteri può richiedere fino a un'ora.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Passaggio 4 - Acquisire e assegnare numeri di telefono

Per informazioni su come acquisire e assegnare numeri di telefono in base all'opzione di connettività PSTN, vedere [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md) .

## <a name="step-5---sign-in"></a>Passaggio 5 - Accedere

Dopo aver creato e configurato un account utente, puoi accedere a un telefono. A seconda del numero di telefoni da distribuire, sono disponibili tre opzioni di accesso:

- [Accesso locale](#local-sign-in).
- [Accedi da un altro dispositivo](#sign-in-from-another-device).
- [Accedere con l'interfaccia di amministrazione di Teams](#sign-in-using-the-teams-admin-center).

### <a name="local-sign-in"></a>Accesso locale

Per accedere localmente con un nome utente e una password:

1. Attiva il telefono dell'area comune.
2. Seleziona **Accedi su questo dispositivo**.
3. Segui le istruzioni per l'accesso nel dispositivo. Una volta effettuato l'accesso, nel telefono verrà visualizzata l'esperienza utente del telefono dell'area comune.

> [!NOTE]
> Se usi criteri di configurazione personalizzati per rimuovere l'app chiamante, la tastiera del telefono non viene visualizzata nel telefono dell'area comune. Per altre informazioni sui criteri di configurazione di Teams, vedere [Gestire i criteri di configurazione delle app in Microsoft Teams](teams-app-setup-policies.md).

### <a name="sign-in-from-another-device"></a>Accedere da un altro dispositivo

Puoi anche accedere a un telefono dell'area comune da un altro dispositivo usando un codice. Quando accedi in questo modo, immetti il nome utente e la password su un altro dispositivo, invece che sul telefono stesso.

1. Nel telefono dell'area comune, trova il codice visualizzato nella schermata di accesso.
2. In un altro dispositivo vai a [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin).
3. Immetti il codice e segui le istruzioni per completare l'accesso.

### <a name="sign-in-using-the-teams-admin-center"></a>Accedere con l'interfaccia di amministrazione di Teams

Gli amministratori possono eseguire il provisioning remoto e accedere ai telefoni dell'area comune [dall'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). Questo metodo è il metodo di accesso più efficiente quando si distribuisce un numero elevato di telefoni contemporaneamente. Per altre informazioni, vedere [Provisioning remoto e accesso per dispositivi Teams Android](devices/remote-provision-remote-login.md) .

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>Passaggio 6 - Configurare chiamate avanzate nei telefoni dell'area comune (facoltativo)

Per impostazione predefinita, l'esperienza di chiamata di base verrà visualizzata nella schermata iniziale del telefono dell'area comune, ma puoi attivare un'esperienza di chiamata avanzata.

Le seguenti funzionalità di chiamata avanzate sono disponibili per i modelli di dispositivi telefonici Teams supportati con una licenza **Dispositivi condivisi di Teams** e gli ultimi aggiornamenti di Teams (versione minima: 1449/1.0.94.2022061702):

- [Chiama il parcheggio e recupera](call-park-and-retrieve.md).
- [Segreteria telefonica basata sul cloud tramite Exchange Online Piano 2](set-up-phone-system-voicemail.md).
  - Per disabilitare la segreteria telefonica basata sul cloud, vedere [Impostazioni dell'utente della segreteria telefonica con PowerShell](/powershell/module/skype/set-csonlinevoicemailusersettings).
- [Code di chiamata](create-a-phone-system-call-queue.md).
- [Operatori automatici](create-a-phone-system-auto-attendant.md).
- [Ritiro chiamata di gruppo](call-sharing-and-group-call-pickup.md).
- [Regole di inoltro](teams-calling-policy.md).

Per usare queste funzionalità di chiamata avanzate nei modelli di dispositivi telefonici di Teams supportati, è possibile attivare l'interruttore **Chiamate avanzate** [nell'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) o nel dispositivo telefonico teams connesso all'account Dispositivi condivisi di Teams.

L'attivazione delle funzionalità di chiamata avanzate richiede l'acquisto di modelli hardware in grado di supportare tutte le funzionalità richieste.

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Attivare Chiamate avanzate nell'interfaccia di amministrazione di Teams

1. Accedere [all'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/dashboard) con un account amministratore di Microsoft 365.
1. Dal menu a sinistra, passa ai **dispositivi** >  Teams **Telefoni** > e seleziona la scheda **Profili di configurazione**.
1. Nell'elenco seleziona il profilo di configurazione assegnato al telefono dell'area comune.
1. Nella sezione **Impostazioni chiamate** , trova l'interruttore **Chiamate avanzate** .
1. Attiva l'interruttore.
1. Nella parte inferiore della pagina selezionare il pulsante **Salva** .

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Attivare chiamate avanzate da un dispositivo telefonico di Teams

1. Dopo aver eseguito l'accesso al dispositivo telefonico di Teams, passare a **Impostazioni** > **dispositivo** >  **Amministrazione solo** > **Chiamate**.
1. Trova l'interruttore **Chiamate avanzate** e attivalo.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver configurato e eseguito l'accesso ai telefoni dell'area comune per l'organizzazione, è possibile gestirli nell'interfaccia di amministrazione di Teams. Per altre informazioni [, vedere Microsoft Teams: Gestione dei dispositivi](devices/device-management.md) .

## <a name="related-articles"></a>Articoli correlati

- [Aggiornare i dispositivi Microsoft Teams in remoto](devices/remote-update.md).
- [Gestire i tag dei dispositivi di Microsoft Teams](devices/manage-device-tags.md).
- [Monitoraggio dell'integrità dei dispositivi di Microsoft Teams](alerts/device-health-status.md).
