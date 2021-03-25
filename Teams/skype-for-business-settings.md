---
title: Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams
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
description: Scopri come gestire le impostazioni per le funzionalità di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117004"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

L'interfaccia di amministrazione di Microsoft Teams consente di gestire le funzionalità di Skype for Business per gli utenti Skype for Business dell'organizzazione. Puoi gestire le impostazioni [per la tua](#manage-skype-for-business-settings-for-your-organization) organizzazione [](#manage-skype-for-business-settings-for-individual-users) nella pagina Skype **for Business** e le impostazioni per i singoli utenti nella scheda Skype **for Business** delle pagine dei dettagli degli utenti.

Verrà visualizzata la pagina **Skype for Business** solo se la modalità di coesistenza per l'organizzazione non è impostata solo su **Teams.** Allo stesso modo, vedrai la scheda **Skype for Business** per un utente solo se la modalità di coesistenza dell'utente non è solo **Teams.** Per altre informazioni sulle modalità di coesistenza, vedere Informazioni sulla coesistenza e [l'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Teams e Skype for Business e [Impostare le impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> Le impostazioni di Skype for Business si trovavano in **precedenza** nel portale legacy nell'interfaccia di amministrazione di Microsoft Teams. Con il ritiro del portale legacy, abbiamo eseguito la migrazione delle impostazioni in queste nuove posizioni nell'interfaccia di amministrazione di Teams per la gestione di Skype for Business.

Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams, è necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) dell'amministratore globale o dell'amministratore di Skype for Business.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gestire le impostazioni di Skype for Business per l'organizzazione

Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Impostazioni** a livello di  >  **organizzazione Skype for Business.** Da qui puoi configurare e gestire Skype Meeting Broadcast, la privacy della presenza e le notifiche dei dispositivi mobili per tutti gli utenti Skype for Business della tua organizzazione.

### <a name="skype-meeting-broadcast"></a>Skype Meeting Broadcast

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Usa le impostazioni seguenti per gestire [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) nella tua organizzazione.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot delle impostazioni di Skype Meeting Broadcast nell'interfaccia di amministrazione":::

- **Skype Meeting Broadcasts:** attiva questa opzione per abilitare Skype Meeting Broadcast per la tua organizzazione. Dopo aver abilitato questa funzionalità, è necessario [configurare la rete per Skype Meeting Broadcast.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Vedere funzionalità di anteprima:** attivare questa opzione per ottenere l'accesso anticipato alle nuove funzionalità.
- **Gli organizzatori possono pianificare riunioni** anonime: attivare questa opzione se si vuole consentire agli organizzatori di creare eventi di trasmissione che consentano a chiunque all'esterno dell'organizzazione di partecipare senza dover accedere. 
- **Registra riunioni Skype Meeting Broadcast:** attiva questa opzione per consentire a organizzatori e relatori di registrare le riunioni.  
- **URL supporto helpdesk** per i partecipanti: immettere l'URL di supporto dell'organizzazione che i partecipanti alla riunione possono usare se hanno bisogno di assistenza durante una riunione.

### <a name="presence-and-mobile-notifications"></a>Notifiche di presenza e dispositivi mobili

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Usare le impostazioni seguenti per gestire la privacy della presenza di Skype for Business e le notifiche per dispositivi mobili nell'organizzazione.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot delle impostazioni di presenza nell'interfaccia di amministrazione":::

#### <a name="presence"></a>Icone di presenza

Per impostazione predefinita, gli utenti skype for business dell'organizzazione possono vedere lo stato presenza (ad esempio Disponibile, Occupato o Non al computer) di altri utenti di Skype for Business. Scegli una delle opzioni seguenti per impostare chi può vedere la presenza degli utenti Skype for Business.

- **Visualizzare automaticamente** le informazioni sulla presenza: qualsiasi utente Skype for Business  dell'organizzazione che non è stato aggiunto all'elenco Esterno o Bloccato dell'utente può vedere la presenza dell'utente. 
- **Visualizzare le** informazioni sulla presenza solo ai contatti di un utente: qualsiasi utente Skype for  Business  nell'elenco Contatti dell'utente che non viene aggiunto all'elenco Esterno o Bloccato può vedere la presenza dell'utente. Gli utenti possono ignorare questa impostazione in Skype for Business andando in **Strumenti**  >  **impostazioni**  >  **Opzioni**.

#### <a name="mobile-notifications"></a>Notifiche per dispositivi mobili

È possibile specificare se gli utenti di Skype for Business per dispositivi mobili riceveno avvisi relativi ai messaggi istantanei in arrivo e persi, ai messaggi della segreteria telefonica e alle chiamate perse tramite un servizio di notifica push. A seconda dei dispositivi mobili usati nell'organizzazione, è possibile usare il servizio di notifica **Push Microsoft,** il servizio di notifica **Push Apple** o entrambi.

Tenere presente quanto segue:

- Se dissegni le notifiche push, gli utenti riceveranno tutti gli avvisi al successivo avvio di Skype for Business sul dispositivo mobile.
- Per impostazione predefinita, le notifiche push sono attivate. I singoli utenti possono disattivarli in Skype for Business sul dispositivo mobile.
- Quando si disattivano le notifiche push, gli utenti non possono riattivarle. 

> [!IMPORTANT]
> Microsoft usa altre società per fornire notifiche per dispositivi mobili Skype for Business in tempo reale per gli utenti di Windows Phone, iPhone e iPad. Vedere questa [Informativa sulla privacy.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gestire le impostazioni di Skype for Business per singoli utenti

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Per gestire le impostazioni di Skype for Business per i singoli utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Utenti,** fare clic sul nome visualizzato dell'utente per aprire la pagina dei dettagli utente e quindi selezionare la scheda Impostazioni **di Skype for Business.** Da qui è possibile configurare le impostazioni di accesso esterno e riunione per l'utente.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot della scheda Skype for Business nella pagina dei dettagli dell'utente":::

### <a name="external-access-settings"></a>Impostazioni di accesso esterno

È possibile consentire o bloccare in modo selettivo se un utente può comunicare con persone esterne all'organizzazione.

- **Utenti esterni di Skype for Business:** attiva questa opzione per consentire all'utente di comunicare con utenti Skype for Business in domini federati.
- **Utenti Skype esterni:** attiva questa opzione per consentire all'utente di comunicare con gli utenti Skype. 

### <a name="meeting-settings"></a>Impostazioni riunione

È possibile configurare le impostazioni della riunione seguenti per l'utente.

- **Audio & Video:** scegliere una delle impostazioni audio e video seguenti:

    - **Nessuno:** l'utente non può usare audio o video.
    - **Solo audio:** l'utente può usare l'audio ma non il video.
    - **Audio e video:** l'utente può usare audio e video.
    - **Audio e video (HD): l'utente** può usare audio e video ad alta definizione.
    
- **Registrare conversazioni & riunioni:** attivare questa opzione per consentire all'utente di registrare conversazioni e riunioni.
- **Conformità:** attivare questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente.