---
title: Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire le impostazioni per le funzionalità di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: 06c5cc4a199a7b29f2db97159850583d6927fc13
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563704"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

L'interfaccia di amministrazione di Microsoft Teams consente agli amministratori di gestire le funzionalità di Skype for Business per Skype for Business utenti dell'organizzazione. È possibile gestire le impostazioni [per l'organizzazione](#manage-skype-for-business-settings-for-your-organization) nella pagina **Skype for Business** e le impostazioni [per singoli utenti](#manage-skype-for-business-settings-for-individual-users) nella scheda **Skype for Business** delle pagine dettagli utente.

La pagina **Skype for Business** viene visualizzata solo se la modalità di coesistenza per l'organizzazione non è impostata **su Solo Teams**. Analogamente, vedrai la scheda **Skype for Business** per un utente solo se la modalità di coesistenza dell'utente non è **solo teams**. Per altre informazioni sulle modalità di coesistenza, vedere [Informazioni su Teams e Skype for Business coesistenza e interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e [Impostare le impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Skype for Business impostazioni erano in precedenza nel **portale legacy** nell'interfaccia di amministrazione di Microsoft Teams. Con il ritiro del portale legacy, abbiamo trasferito le impostazioni in queste nuove posizioni nell'interfaccia di amministrazione di Teams per la gestione Skype for Business.

Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams, è necessario avere il [ruolo di amministratore di Azure AD](/azure/active-directory/roles/permissions-reference) di amministratore globale o amministratore di Skype for Business.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gestire le impostazioni di Skype for Business per l'organizzazione

Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Impostazioni  > **a livello di organizzazione** Skype for Business. Da qui è possibile configurare e gestire Riunione Skype broadcast, la privacy della presenza e le notifiche dei dispositivi mobili per tutti gli utenti Skype for Business dell'organizzazione.

### <a name="skype-meeting-broadcast"></a>Skype Meeting Broadcast

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Usa le impostazioni seguenti per gestire [Riunione Skype Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) nella tua organizzazione.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot delle impostazioni di Riunione Skype Broadcast nell'interfaccia di amministrazione.":::

- **Riunione Skype Broadcast**: attiva questa opzione per abilitare Riunione Skype Broadcast per la tua organizzazione. Dopo aver abilitato questa funzionalità, devi [configurare la rete per Riunione Skype Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Vedere le funzionalità di anteprima**: attivare questa opzione per accedere in anteprima alle nuove funzionalità.
- **Gli organizzatori possono pianificare riunioni anonime**: attiva questa opzione se vuoi consentire agli organizzatori di creare eventi di trasmissione che consentano a chiunque all'esterno dell'organizzazione di partecipare senza dover eseguire l'accesso. 
- **Registrare Riunione Skype riunioni in broadcast**: attiva questa opzione per consentire agli organizzatori e ai relatori di registrare le riunioni.  
- **URL di supporto helpdesk per i partecipanti**: immettere l'URL di supporto dell'organizzazione che i partecipanti alla riunione possono usare se hanno bisogno di aiuto durante una riunione.

### <a name="presence-and-mobile-notifications"></a>Notifiche di presenza e dispositivi mobili

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Usare le impostazioni seguenti per gestire Skype for Business la privacy della presenza e le notifiche per dispositivi mobili nell'organizzazione.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot delle impostazioni di presenza nell'interfaccia di amministrazione.":::

#### <a name="presence"></a>Icone di presenza

Per impostazione predefinita, Skype for Business utenti dell'organizzazione possono visualizzare lo stato presenza di altri utenti Skype for Business, ad esempio Disponibile, Occupato o Non al computer. Scegliere una delle opzioni seguenti per impostare chi può visualizzare la presenza degli utenti Skype for Business.

- **Visualizzare automaticamente le informazioni sulla presenza**: qualsiasi Skype for Business utente dell'organizzazione che non è stato aggiunto all'elenco **di utenti esterni** o **bloccati** può vedere la presenza dell'utente.
- **Visualizzare le informazioni sulla presenza solo ai contatti di un utente**: qualsiasi utente Skype for Business'elenco Contatti dell'utente che non è stato aggiunto all'elenco **Esterno** o **Bloccato** può vedere la presenza di quell'utente. Gli utenti possono ignorare questa impostazione in Skype for Business passando a **Opzioni** **strumenti** >  **impostazioni** > .

#### <a name="mobile-notifications"></a>Notifiche per dispositivi mobili

È possibile specificare se gli utenti di Skype for Business dispositivi mobili ricevono avvisi sui messaggi istantanei in arrivo e persi, i messaggi vocali e le chiamate perse tramite un servizio di notifica push. A seconda dei dispositivi mobili usati nell'organizzazione, è possibile usare il **servizio di notifica Push Microsoft**, il **servizio di notifica Push Apple** o entrambi.

Tenere presente quanto segue:

- Se disattivi le notifiche push, gli utenti riceveranno tutti gli avvisi al successivo avvio Skype for Business sul dispositivo mobile.
- Per impostazione predefinita, le notifiche push sono attivate. I singoli utenti possono disattivarli in Skype for Business nel dispositivo mobile.
- Quando disattivi le notifiche push, gli utenti non possono riattivarle. 

> [!IMPORTANT]
> Microsoft utilizza altre aziende per fornire notifiche in tempo reale Skype for Business per dispositivi mobili per gli utenti di Windows Phone, iPhone e iPad. Vedere la presente [Informativa sulla privacy](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gestire le impostazioni di Skype for Business per singoli utenti

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Per gestire le impostazioni di Skype for Business per singoli utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Utenti**, fare clic sul nome visualizzato dell'utente per aprire la pagina dei dettagli dell'utente e quindi selezionare la scheda **Skype for Business impostazioni**. Da qui è possibile configurare le impostazioni di accesso esterno e riunione per l'utente.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot della scheda Skype for Business nella pagina dei dettagli dell'utente.":::

### <a name="external-access-settings"></a>Impostazioni di accesso esterno

È possibile consentire o bloccare in modo selettivo se un utente può comunicare con persone esterne all'organizzazione.

- **Utenti Skype for Business esterni**: attivare questa opzione se si vuole consentire all'utente di comunicare con Skype for Business utenti nei domini federati.
- **Utenti Skype esterni**: attiva questa opzione se vuoi consentire all'utente di comunicare con gli utenti Skype. 

### <a name="meeting-settings"></a>Impostazioni riunione

È possibile configurare le seguenti impostazioni della riunione per l'utente.

- **Audio & Video**: Scegliere una delle impostazioni audio e video seguenti:

    - **Nessuno**: l'utente non può usare audio o video.
    - **Solo audio**: l'utente può usare l'audio ma non il video.
    - **Audio e video**: l'utente può usare audio e video.
    - **Audio e video (HD)**: l'utente può usare audio e video ad alta definizione.
    
- **Registrare conversazioni & riunioni**: attivare questa opzione per consentire all'utente di registrare conversazioni e riunioni.
- **Conformità**: attivare questa opzione se è richiesto per legge la conservazione delle informazioni archiviate elettronicamente.