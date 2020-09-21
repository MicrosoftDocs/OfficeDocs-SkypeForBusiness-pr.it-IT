---
title: Telefoni per Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Questo articolo illustra l'elenco dei telefoni certificati per Microsoft teams e le funzionalità supportate nei telefoni certificati per Microsoft teams.
ms.openlocfilehash: cd38586b67f728febb4a43d3f018875b378cffd8
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962847"
---
# <a name="phones-for-microsoft-teams"></a>Telefoni per Microsoft Teams

Microsoft teams supporta un portafoglio di telefoni da tavolo per gli utenti che necessitano di un'esperienza telefonica tradizionale. Questo articolo offre una panoramica completa dei telefoni di teams e può aiutare a pianificare, distribuire e gestire telefoni Microsoft teams come parte della soluzione del sistema telefonico Microsoft. 

Per offrire un'esperienza di Microsoft teams affidabile e di alta qualità sui telefoni, stiamo collaborando attivamente con Yealink, Crestron, Lenovo, Polycom e AudioCodes per sviluppare e certificare un ampio portafoglio di telefoni da tavolo e dispositivi audio per la sala riunioni. Per ottenere le informazioni più recenti e aggiornate sui dispositivi team, accedere a [Teams Marketplace](https://office.com/teamsdevices).

Per gestire i telefoni, è necessario essere un amministratore globale, un amministratore del servizio teams o un amministratore del dispositivo teams. Per altre informazioni sui ruoli di amministratore, vedere [usare i ruoli di amministratore di Microsoft teams per gestire i team](../using-admin-roles.md).

## <a name="features-supported-by-teams-phones"></a>Funzionalità supportate dai telefoni di Teams
I telefoni con certificazione Teams hanno una vasta gamma di funzionalità per aiutare gli utenti a svolgere il proprio lavoro e aiutarti a gestire il loro uso. Ecco un riepilogo delle funzionalità disponibili nei telefoni con certificazione teams:

- **Autenticazione** I telefoni usano l'autenticazione moderna per semplificare l'accesso e migliorare la sicurezza. Gli utenti possono accedere immettendo il proprio nome utente e la password sul telefono oppure effettuando l'accesso da un altro dispositivo, ad esempio PC/smartphone.
- **Chiamata veloce e cronologia chiamate** Gli utenti hanno accesso rapido ai contatti, alla cronologia delle chiamate e alla segreteria telefonica. Possono gestire facilmente i contatti e le voci di chiamata veloce direttamente dal telefono.
- **Riunioni e chiamate** Gli utenti possono visualizzare le loro pianificazioni e partecipare facilmente alle riunioni usando il One-Touch join dei team.
- **Gruppi di chiamate** Gli agenti telefonici che partecipano a gruppi di chiamate possono gestire facilmente la disponibilità e accettare o rifiutare le chiamate in arrivo dalla coda di chiamata.
- **Delega utente** Gli assistenti esecutivi e gli amministratori possono gestire i telefoni dei loro dirigenti-intercettare le chiamate in arrivo; effettuare chiamate per conto dell'Executive; subentrano le chiamate effettuate dall'esecutivo in attesa; e controlla se l'Executive è su una chiamata, in attesa e così via.
- **Scrivania a caldo** Gli utenti possono ottenere i contatti, le riunioni e altre preferenze, semplicemente accedendo a un telefono. Al termine, è possibile disconnettersi e tenere il telefono pronto per l'utente successivo.
- **Video** I telefoni con supporto video consentono agli utenti di partecipare alle chiamate e alle videoconferenze, proprio come nel computer in cui si trovavano. Gli utenti possono mantenersi intimità usando l'otturatore della fotocamera del telefono e l'opzione di silenziamento del microfono quando disponibile.
- **Migliorare insieme** I telefoni possono bloccare e sbloccare in modo integrato quando si è connessi al PC Windows che gestisce un client desktop a squadre di 64 bit.
- **Accessibilità** I telefoni hanno diverse funzionalità di accessibilità, ad esempio testo a contrasto elevato, per semplificare l'uso di tutti gli utenti.
- **Supporto E911 dinamico e avanzato** Gli utenti con accesso che chiamano 911 vedranno la propria posizione sul telefono. 
    > [!IMPORTANT]
    > Se un telefono non è connesso o se non ha una connessione Internet, non è possibile inserire le chiamate di 911. In questo caso, nel telefono viene visualizzata una notifica.

Oltre alle caratteristiche descritte sopra, è possibile controllare quali funzionalità sono disponibili a seconda del tipo di licenza e dei criteri del telefono assegnati all'utente che effettua l'accesso al telefono. Ad esempio, gli utenti che accedono a un telefono con gli account personali possono accedere all'intera gamma di funzionalità: chiamate, riunioni, segreteria telefonica e così via. Gli account assegnati a una licenza telefonica per l'area comune che accedono a un telefono possono avere accesso solo a un numero limitato di funzionalità; la cronologia delle chiamate e le pianificazioni delle riunioni potrebbero non essere mantenute, ad esempio per proteggere la privacy degli utenti.

## <a name="required-licenses"></a>Licenze necessarie

Le licenze di Microsoft teams possono essere acquistate come parte degli [abbonamenti a microsoft 365 e Office 365](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description). Per altre informazioni sulle licenze necessarie per l'uso di Microsoft teams sui telefoni, vedere [licenze di sistema telefonico](https://products.office.com/microsoft-teams/voice-calling)disponibili.

Per altre informazioni su come ottenere teams, vedere [come si accede a Microsoft teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-via-intune"></a>Distribuire i telefoni tramite Intune

### <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è una caratteristica di Azure Active Directory che consente di verificare che i dispositivi che accedono alle risorse di Office 365 siano gestiti correttamente e siano sicuri.  Se si applicano criteri di accesso condizionale al servizio teams, i dispositivi Android (incluso un telefono di Teams) che i team di Access devono essere iscritti a Intune e le relative impostazioni devono essere conformi ai criteri.  Se il dispositivo non è registrato in Intune o se è registrato ma le sue impostazioni non sono conformi ai criteri, l'accesso condizionale impedirà a un utente di accedere o usare l'app Teams nel dispositivo.

In genere, i criteri di conformità definiti in Intune vengono assegnati a gruppi di utenti.  Questo significa che se assegni un criterio di conformità Android a user@contoso.com, tale criterio verrà applicato ugualmente allo smartphone Android e a qualsiasi dispositivo team basato su Android in cui user@contoso.com.

Se si usa l'accesso condizionale, che richiede la registrazione di Intune per essere applicata, nell'organizzazione sono disponibili un paio di cose che è necessario configurare per consentire una registrazione di Intune riuscita:

- **Licenza Intune** L'utente che accede al telefono Microsoft Teams deve essere concesso in licenza per Intune.  Finché i telefoni Microsoft teams sono connessi a un account utente con una licenza valida di Intune, il telefono verrà registrato automaticamente in Microsoft Intune come parte del processo di accesso.
- **Configurare Intune** È necessario disporre di un tenant di Intune configurato in modo appropriato per la registrazione di amministratore di dispositivi Android.

### <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurare Intune per la registrazione di Team dispositivi basati su Android

I dispositivi basati su Android di teams sono gestiti da in Intune tramite la gestione di Android Device Administrator (DA). Prima di poter registrare i dispositivi in Intune, è possibile eseguire alcuni passaggi di base.  Se si stanno già gestendo i dispositivi con Intune oggi, è probabile che siano già stati eseguiti tutti questi elementi.  In caso contrario, ecco cosa fare:

1. Impostare l'autorità di Intune MDM (Mobile Device Management).  Se non si è mai usato Intune prima, è necessario impostare l'autorità MDM prima di poter registrare i dispositivi. Per altre informazioni, vedere [impostare l'autorità di gestione di dispositivi mobili](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Si tratta di un passaggio di una sola volta che deve essere eseguito dopo la creazione di un nuovo tenant di Intune.
2. Abilitare la registrazione di amministratore di dispositivi Android. Il dispositivo teams basato su Android viene gestito come dispositivi di amministrazione dei dispositivi con Intune.  La registrazione dell'amministratore del dispositivo è disinserita per impostazione predefinita per i tenant appena creati.  Per altre informazioni, Vedi [registrazione di amministratore di dispositivi Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Assegnare licenze agli utenti. Agli utenti dei dispositivi team che si iscrive a Intune deve essere assegnata una licenza valida di Intune. Per altre informazioni, vedere [assegnare licenze agli utenti in modo che possano registrare i dispositivi in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Assegnare criteri di conformità di amministratore del dispositivo.  Creare un criterio di conformità di amministratore di dispositivi Android e assegnarlo al gruppo di Azure Active Directory che contiene gli utenti che effettueranno l'accesso ai dispositivi teams. Per altre informazioni, vedere [usare i criteri di conformità per impostare regole per i dispositivi gestiti con Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="manage-your-phones"></a>Gestire i telefoni

Un amministratore del tenant può gestire e conservare tutti i loro dispositivi di teams aggiornati tramite l'interfaccia di amministrazione di teams. Per altre informazioni, vedere [gestire i dispositivi in Microsoft teams](https://docs.microsoft.com/microsoftteams/devices/device-management). 

## <a name="see-also"></a>Vedere anche

[Marketplace Teams](https://office.com/teamsdevices)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)
