---
title: Configurare la licenza Telefono area comune
ms.author: czawideh
author: cazawideh
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
description: "Informazioni su come configurare i telefoni dell'area comune per lobby, aree di ricezione e sale riunioni "
ms.openlocfilehash: 313a17d1829c8f3584ec5fb7f37e5f1ec49231d0
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456939"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Distribuire telefoni ad area comune per Microsoft Teams

Un telefono dell'area comune è in genere posizionato in un'area come una sala d'attesa o un'altra area che è disponibile a molte persone per effettuare una chiamata; ad esempio un'area di ricezione, una sala d'attesa o un telefono per conferenze. I telefoni dell'area comune sono connessi con account collegati a una licenza di area Telefono comune.

Questo articolo fornisce una panoramica su come distribuire e configurare i telefoni Teams telefoni come telefoni di area comune per gli spazi condivisi. Per un'esperienza più completa nelle sale riunioni, inclusa l'audioconferenza, è consigliabile acquistare la licenza Sala riunioni con un dispositivo della sala riunioni.

## <a name="overview"></a>Panoramica

La licenza common area Telefono supporta: 


| &nbsp;  |  Telefono di area comune  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema telefonico |    &#x2714; |
|Audioconferenza |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilità in tutto il mondo |       &#x2718; &sup2;  |
|Disponibilità del canale |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Area comune I telefoni possono partecipare a conferenze audio tramite il numero di accesso fornito dall'organizzatore della riunione

&sup2; Non disponibile nei cloud sovrani  

>[!NOTE]
> Gli account per i telefoni di area comune creati in Skype for Business Server non possono essere migrati a Microsoft Teams. Seguire i passaggi di questo articolo per ricreare gli account per Teams e, se necessario, eseguire la migrazione della connettività PTSN.

## <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze

Prima di tutto, è necessario acquistare una licenza di Common Area Telefono (CAP) e assicurarsi di avere un telefono certificato. Per cercare e altre informazioni sui telefoni certificati, vai a Microsoft Teams [dispositivi](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. Nel interfaccia di amministrazione di Microsoft 365, passare a **BillingPurchase** >  services. 

2. Se la **sezione Visualizza per categoria** non è già visualizzata, passare a Acquista **da Microsoft** e selezionare **Visualizza prodotti**. Quindi selezionare **Collaborazione e comunicazione**.  

3. Nell'elenco dei prodotti trovare **Area comune** Telefono e selezionare **Dettagli**.

4. Immetti il numero di licenze necessarie e seleziona **Acquista**.

>[!NOTE]
>Se si usa Intune nell'ambiente e si hanno regole di accesso condizionale che richiedono la conformità dei dispositivi, è necessario assegnare una licenza di Azure Active Directory Premium Piano 1 e Intune all'account del dispositivo per il telefono dell'area comune.
>
>I telefoni delle aree comuni possono essere influenzati dalle regole di accesso condizionale e da altre configurazioni di identità, come l'autenticazione a più fattori. Per [altre informazioni, vedere Procedure consigliate di autenticazione Teams dispositivi Android](devices/authentication-best-practices-for-android-devices.md).

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Passaggio 2 - Creare un nuovo account utente e assegnare licenze

### <a name="using-the-microsoft-365-admin-center"></a>Uso del interfaccia di amministrazione di Microsoft 365

Se si distribuiscono più telefoni di area comuni contemporaneamente, vedere come creare account e assegnare licenze [con PowerShell](#using-powershell).

Se si sta distribuendo un dispositivo:

1. Nella finestra interfaccia di amministrazione di Microsoft 365 passare a **UtentiAttiviAggiungere** >  >  **un utente**.

2. Immettere un nome utente come "Principale" per il nome e "Ricezione" per il secondo nome.

3. Immettere un nome visualizzato se non lo rigenera automaticamente, ad esempio "Ricezione principale".

4. Immettere un nome utente come "MainReception" o "Mainlobby".

5. Impostare manualmente la password per il telefono dell'area comune per impedirla. A questo scopo, deselezionare **Crea automaticamente una password** e richiedere all'utente di **cambiare la password al primo accesso**.  

    >[!Important]
    > È consigliabile impostare manualmente una password per i telefoni dell'area comune per evitare problemi di accesso per gli utenti finali.

6. Selezionare la posizione di utilizzo del dispositivo e assegnare l'area Telefono licenza all'account. Se sono necessarie altre licenze, ad esempio Piani per chiamate, assegnarle.

>[!NOTE]
> Non è necessario aggiungere una licenza Sistema telefonico licenza. È inclusa con la licenza per il Telefono di area comune.
>
>Se non si usa l'Telefono Microsoft System Direct Routing o Connessione con operatore, è possibile aggiungere licenze per i Piani di chiamata. Per altre informazioni sulle licenze, vedere Microsoft Teams [licenze per i componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell quando si vogliono creare e assegnare licenze per più account utente contemporaneamente. Per [altre informazioni, vedere Creare Microsoft 365](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) account utente con PowerShell e [Assegnare Microsoft 365 licenze agli account utente con PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide).

## <a name="step-3---set-policies-for-common-area-phones"></a>Passaggio 3 - Impostare i criteri per i telefoni dell'area comune

Usare i criteri per controllare quali funzionalità sono disponibili per gli utenti nei telefoni dell'area comune.

>[!NOTE]
>Dopo aver assegnato un criterio, disconnettersi dal telefono e accedere di nuovo. L'applicazione di un'assegnazione dei criteri può richiedere fino a un'ora.

### <a name="ip-phone-policies"></a>Criteri per i telefoni IP

I telefoni connessi con account a cui è stata assegnata una licenza Telefono area comune visualizzano l'esperienza utente dell'area comune.

Se si vuole ignorare l'interfaccia predefinita di un telefono, è consigliabile creare un criterio [telefono IP](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps). Ad esempio, se un telefono di area comune viene usato in un'area pubblica, impostare un criterio telefono IP per limitare la ricerca nella Rubrica globale dell'organizzazione e bloccare l'hot desking. Per [altre informazioni, vedere Teams'interfaccia utente dei dispositivi Android](devices/Teams-Android-devices-user-interface.md).

### <a name="calling-policies"></a>Criteri di chiamata

Usare i criteri di chiamata per abilitare le chiamate private, l'inoltro di chiamata o l'squillo simultaneo sui telefoni della zona comune. Vedere [Chiamate e inoltro di chiamata in Teams](teams-calling-policy.md) per altre informazioni.

Per impostazione predefinita, il parcheggio di chiamata non è abilitato per i telefoni dell'area comune. È necessario creare un criterio per abilitarlo. Per [altre informazioni, vedere Parcheggio di chiamata Microsoft Teams](call-park-and-retrieve.md) per altre informazioni.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Passaggio 4 - Acquisire e assegnare numeri di telefono

Vedere [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md) per informazioni su come acquisire e assegnare numeri di telefono in base all'opzione di connettività PSTN.

## <a name="step-5---sign-in"></a>Passaggio 5 - Accedere

Dopo aver creato e configurato un account utente, è possibile accedere a un telefono. A seconda del numero di telefoni che si sta distribuendo, sono disponibili tre opzioni di accesso:

- [Accesso locale](#local-sign-in)
- [Accedere da un altro dispositivo](#sign-in-from-another-device)
- [Accedere con l'interfaccia Teams di amministrazione](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Accesso locale

Per accedere localmente con un nome utente e una password: 

1. Attivare il telefono dell'area comune

2. Seleziona **Accedi in questo dispositivo**

3. Seguire le istruzioni di accesso nel dispositivo. Una volta effettuato l'accesso, il telefono visualizza l'esperienza utente del telefono dell'area comune.

> [!NOTE]
> Se si usa un criterio di configurazione personalizzato che sblocca l'app per le chiamate, la tastiera del telefono non viene visualizzata nell'area Telefono. Per altre informazioni sui criteri Teams di configurazione delle app, vedere [Gestire i criteri di configurazione delle app in Microsoft Teams](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>Accedere da un altro dispositivo

È anche possibile accedere a un telefono dell'area comune da un altro dispositivo usando un codice. Quando accedi in questo modo, immetti il nome utente e la password su un altro dispositivo, invece che sul telefono stesso.

1. Prima di tutto, nel telefono dell'area comune cercare il codice visualizzato nella schermata di accesso.

2. In un altro dispositivo passare a https://www.microsoft.com/devicelogin.

3. Immettere il codice e seguire le istruzioni per completare l'accesso.

### <a name="sign-in-using-the-teams-admin-center"></a>Accedere con l'interfaccia Teams di amministrazione

Gli amministratori possono eseguire il provisioning e accedere in remoto ai telefoni dell'area comune dall'Teams di amministrazione. Si tratta del metodo di accesso più efficiente quando si distribuisce un numero elevato di telefoni contemporaneamente. Per [altre informazioni, vedere Provisioning remoto e accesso Teams dispositivi Android](devices/remote-provision-remote-login.md).

## <a name="next-steps"></a>Passaggi successivi

Dopo aver configurato e effettuato l'accesso ai telefoni dell'area comune per l'organizzazione, è possibile gestirli nell'interfaccia di amministrazione Teams rete. Vedi [Microsoft Teams: Gestire i tuoi dispositivi](devices/device-management.md) per saperne di più.

## <a name="related-topics"></a>Argomenti correlati

- [Aggiornare Microsoft Teams dispositivi in remoto](devices/remote-update.md)
- [Gestire i Microsoft Teams dei dispositivi](devices/manage-device-tags.md)
- [Microsoft Teams dell'integrità dei dispositivi](alerts/device-health-status.md)
