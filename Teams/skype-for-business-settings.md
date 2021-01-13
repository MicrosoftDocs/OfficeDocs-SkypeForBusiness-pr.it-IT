---
title: Gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire le impostazioni per le funzionalità di Skype for business nell'interfaccia di amministrazione di Microsoft teams.
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834216"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Come amministratore, l'interfaccia di amministrazione di Microsoft teams è la posizione in cui Gestisci le funzionalità di Skype for business per gli utenti di Skype for business nell'organizzazione. È possibile gestire le [impostazioni per l'organizzazione](#manage-skype-for-business-settings-for-your-organization) nella pagina **Skype for business** e le impostazioni [per singoli utenti](#manage-skype-for-business-settings-for-individual-users) nella scheda **Skype for business** delle pagine dei dettagli utente.

Verrà visualizzata solo la pagina **Skype for business** se la modalità di coesistenza per l'organizzazione non è impostata **solo su teams**. Analogamente, viene visualizzata solo la scheda **Skype for business** per un utente se la modalità di coesistenza dell'utente non è **solo teams**. Per altre informazioni sulle modalità di coesistenza, vedere informazioni sui [team e sulla coesistenza e interoperabilità di Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e [impostare le impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Le impostazioni di Skype for business erano in precedenza nel **portale legacy** nell'interfaccia di amministrazione di Microsoft teams. Con la pensione del portale legacy, abbiamo migrato le impostazioni a queste nuove posizioni nell'interfaccia di amministrazione di teams per la gestione di Skype for business.

Per gestire le funzionalità di Skype for business nell'interfaccia di amministrazione di Microsoft teams, è necessario avere il [ruolo di amministratore di Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) per l'amministratore globale o per l'amministratore di Skype for business.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gestire le impostazioni di Skype for business per l'organizzazione

Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **impostazioni a livello di organizzazione**  >  **Skype for business**. Da qui puoi configurare e gestire le notifiche di Skype meeting broadcast, Presence privacy e device mobile per tutti gli utenti di Skype for business nell'organizzazione.

### <a name="skype-meeting-broadcast"></a>Skype Meeting Broadcast

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Usare le impostazioni seguenti per gestire [Skype meeting broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) nell'organizzazione.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot delle impostazioni di Skype meeting broadcast nell'interfaccia di amministrazione":::

- **Skype meeting broadcasts**: attivare questa opzione per abilitare Skype meeting broadcast per l'organizzazione. Dopo aver abilitato questa funzionalità, è necessario [configurare la rete per Skype meeting broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Vedere funzionalità di anteprima**: attivare questa opzione per ottenere l'accesso anticipato alle nuove funzionalità.
- Gli **organizzatori possono programmare riunioni anonime**: attivare questa opzione se si vuole consentire agli organizzatori di creare eventi broadcast che consentano a tutti gli utenti esterni all'organizzazione di partecipare senza dover eseguire l'accesso. 
- **Registrare riunioni Skype meeting broadcast**: attivare questa opzione per consentire agli organizzatori e ai relatori di registrare riunioni.  
- **URL del supporto dell'helpdesk per i partecipanti**: immettere l'URL del supporto dell'organizzazione che i partecipanti alla riunione possono usare se hanno bisogno di assistenza durante una riunione.

### <a name="presence-and-mobile-notifications"></a>Notifiche di presenza e per dispositivi mobili

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Usare le impostazioni seguenti per gestire le notifiche di privacy e dispositivi mobili di Skype for business nella propria organizzazione.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot delle impostazioni di presenza nell'interfaccia di amministrazione":::

#### <a name="presence"></a>Icone di presenza

Per impostazione predefinita, gli utenti di Skype for business nell'organizzazione possono vedere lo stato presenza, ad esempio disponibile, occupato o assente, di altri utenti di Skype for business. Scegli una delle opzioni seguenti per impostare chi può vedere la presenza degli utenti di Skype for business.

- **Visualizza automaticamente le informazioni sulla presenza**: qualsiasi utente di Skype for business nell'organizzazione che non è stato aggiunto all'elenco **esterno** o **bloccato** dell'utente può vedere la presenza dell'utente.
- **Visualizzare le informazioni sulla presenza solo ai contatti di un utente**: qualsiasi utente Skype for business nell'elenco contatti dell'utente che non è stato aggiunto all'elenco **esterno** o **bloccato** può vedere la presenza dell'utente. Gli utenti possono eseguire l'override di questa impostazione in Skype for business accedendo alle  >  **Opzioni degli strumenti** impostazioni  >  .

#### <a name="mobile-notifications"></a>Notifiche per dispositivi mobili

Puoi impostare se gli utenti di Skype for business mobile ricevono avvisi sui messaggi istantanei in arrivo e in uscita, i messaggi della segreteria telefonica e le chiamate perse tramite un servizio di notifica push. A seconda dei dispositivi mobili usati nell'organizzazione, è possibile usare il servizio di **notifica push Microsoft**, il **servizio notifica push Apple** o entrambi.

Tieni presente quanto segue:

- Se si disattivano le notifiche push, gli utenti riceveranno tutti gli avvisi al successivo avvio di Skype for business nel dispositivo mobile.
- Per impostazione predefinita, le notifiche push sono attivate. I singoli utenti possono disattivarli in Skype for business nel dispositivo mobile.
- Quando si disattivano le notifiche push, gli utenti non possono riattivarli. 

> [!IMPORTANT]
> Microsoft usa altre società per comunicare in tempo reale le notifiche per dispositivi mobili Skype for business per gli utenti di Windows Phone, iPhone e iPad. Vedere la presente [informativa sulla privacy](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gestire le impostazioni di Skype for business per singoli utenti

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Per gestire le impostazioni di Skype for business per singoli utenti, nella barra di spostamento sinistra dell'interfaccia di amministrazione di teams, passa a **utenti**, fai clic sul nome visualizzato dell'utente per aprire la pagina dei dettagli utente e quindi seleziona la scheda **impostazioni di Skype for business** . Da qui è possibile configurare le impostazioni di accesso esterno e riunione per l'utente.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot della scheda Skype for business nella pagina dei dettagli utente":::

### <a name="external-access-settings"></a>Impostazioni di accesso esterno

È possibile consentire o bloccare selettivamente se un utente può comunicare con persone esterne all'organizzazione.

- **Utenti Skype for business esterni**: attivare questa opzione se si vuole consentire all'utente di comunicare con utenti Skype for business in domini federati.
- **Utenti Skype esterni**: attivare questa opzione se si vuole consentire all'utente di comunicare con utenti Skype. 

### <a name="meeting-settings"></a>Impostazioni riunione

È possibile configurare le impostazioni delle riunioni seguenti per l'utente.

- **Audio & video**: scegliere una delle impostazioni audio e video seguenti:

    - **Nessuno**: l'utente non può usare l'audio o il video.
    - **Solo audio**: l'utente può usare l'audio ma non il video.
    - **Audio e video**: l'utente può usare l'audio e il video.
    - **Audio e video (HD)**: l'utente può usare l'audio e il video ad alta definizione.
    
- **Registrare conversazioni & riunioni**: attivare questa opzione per consentire all'utente di registrare conversazioni e riunioni.
- **Conformità**: attivare questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente. 
