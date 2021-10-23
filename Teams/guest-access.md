---
title: Accesso guest in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: L'accesso guest in Microsoft Teams consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali.
ms.openlocfilehash: 80c1fcb9012efbc1809b1d1d4252c9801d148ba9
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537087"
---
# <a name="guest-access-in-microsoft-teams"></a>Accesso guest in Microsoft Teams

Tramite l’accesso guest, è possibile consentire l'accesso a team, documenti nei canali, risorse, chat e applicazioni alle persone esterne all’organizzazione, pur mantenendo il totale controllo dei dati aziendali. Vedere [Configurare la collaborazione sicura con Microsoft 365 e Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams). L'accesso guest in Teams è un'impostazione a livello di organizzazione ed è attivato per impostazione predefinita. È possibile controllare l'accesso guest ai singoli team usando le [etichette di riservatezza](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Se si vuole semplicemente trovare, chiamare, chattare e configurare riunioni con persone di altre organizzazioni, usare l’[accesso esterno](manage-external-access.md).

Un guest è una persona che non è né un dipendente, né uno studente, né un membro dell'organizzazione e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione. Ad esempio, gli utenti guest possono includere partner, fornitori o consulenti. Chiunque non faccia parte dell'organizzazione può essere aggiunto come guest in Teams. Questo significa che chiunque abbia un account aziendale, ossia un account Azure Active Directory, o un account di posta elettronica personale, con Outlook.com, Gmail.com o altri, può partecipare come guest in Teams, con accesso ai team e ai canali.

Gli utenti guest in Teams sono coperti dalla stessa protezione di conformità e controllo del resto di Microsoft 365 e possono essere gestiti all'interno di Azure AD. L'accesso guest è soggetto ai limiti di servizio di Azure AD e Microsoft 365 o Office 365.

L'esperienza guest presenta limitazioni di progettazione. Per un elenco completo delle operazioni che un utente guest può eseguire o meno in Teams, vedere [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Gli utenti guest sono inclusi nelle impostazioni a livello di organizzazione di Teams per la modalità di aggiornamento della coesistenza. Questa impostazione non può essere modificata.

Per configurare l'accesso guest, vedere [Collaborare con gli utenti guest in un team](/microsoft-365/solutions/collaborate-as-team). 

Per confrontare l'accesso esterno (federazione) con l'accesso guest e decidere quale usare, leggere [Comunicare con utenti di altre organizzazioni in Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurare l’accesso per gli utenti guest

L'accesso guest in Teams richiede la configurazione di altre impostazioni in Microsoft 365, tra cui le impostazioni in Azure AD, i Gruppi di Microsoft 365 e SharePoint. Quando si è pronti a invitare utenti guest a Teams, leggere una delle opzioni seguenti:

- Per configurare l'accesso degli utenti guest per l’uso generale di Teams, vedere [Collaborare con gli utenti guest in un team](/microsoft-365/solutions/collaborate-as-team).
- Per collaborare con un'organizzazione partner che usa Azure Active Directory e consentire agli utenti guest di iscriversi autonomamente per l'accesso a Teams, vedere [Creare una Extranet B2B con utenti guest gestiti](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Se come amministratori si sperimentano problemi con l'accesso guest in Microsoft Teams, si può selezionare **Esegui test** in basso, per popolare la diagnostica di Accesso guest nell'interfaccia di Amministrazione Microsoft 365. Questi test verificheranno la configurazione e consiglieranno rapidamente i passaggi da intraprendere per abilitare l'accesso guest per il tenant.
>> [!div class="nextstepaction"]
>> [Esegui Test: accesso guest](https://aka.ms/TeamsGuestAccessDiagDMC)

### <a name="turning-guest-access-off"></a>Disattivazione dell’accesso guest

Se si disattiva l'accesso guest in Teams, gli utenti guest esistenti perdono l'accesso al proprio team. Tuttavia, non vengono rimossi dal team. Sono ancora visibili ai membri del team e possono essere @menzionati. Se si riattiva l'accesso guest di Teams, l'accesso verrà recuperato.

Se si ha intenzione di lasciare disattivato l'accesso guest, si consiglia di informare i proprietari dei team di rimuovere manualmente gli account guest dai team. Sebbene questi ospiti non avranno accesso, avere i loro account visibili nel team potrebbe creare confusione agli altri membri del team.

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Come diventare un membro di un team da utente guest

1. Il proprietario di un team o un amministratore di Microsoft 365 [aggiunge un utente guest al team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Il guest riceve un'e-mail di benvenuto dal proprietario del team, contenente informazioni sul team e sulle funzionalità disponibili in quanto nuovo membro.
3. Il guest accetta l'invito.
  Gli utenti guest che hanno un account aziendale o dell'Istituto di istruzione per Azure Active Directory possono accettare l'invito e autenticarsi direttamente. Agli altri utenti viene inviato un passcode monouso per convalidare la propria identità (obbligatoria l’[autenticazione con passcode monouso](/azure/active-directory/external-identities/one-time-passcode))
4. Dopo aver accettato l'invito, il guest può [partecipare a team e canali](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), ricevere e rispondere ai messaggi del canale, [accedere ai file nei canali](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), partecipare alle chat, partecipare alle riunioni, collaborare ai documenti e altro ancora. 

In Teams, i guest vengono identificati in modo chiaro. Il nome di un utente guest include l'etichetta **(Guest)** e il canale include un'icona che indica la presenza di utenti guest nel team. Per maggiori dettagli, vedere [Informazioni sull'esperienza guest](guest-experience.md).
  
I guest possono abbandonare il team in qualsiasi momento tramite Teams. Per i dettagli, vedere [Come abbandonare un team](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Abbandonare il team non implica la rimozione dell'account guest dalla directory dell'organizzazione. Questa operazione deve essere eseguita da un amministratore globale di Microsoft 365 o da un amministratore di Azure AD.

## <a name="licensing-for-guest-access"></a>Licenze per l'accesso guest

L'accesso guest può essere usato in tutti gli abbonamenti di Microsoft 365 Business Standard, Microsoft 365 Enterprise e Microsoft 365 Education. Non sono necessarie altre licenze di Microsoft 365. Il [modello di fatturazione per Azure AD per identità esterne](/azure/active-directory/b2b/licensing-guidance) si applica agli utenti guest in Microsoft 365. Solo le persone esterne all'organizzazione possono essere invitate come utenti guest.

## <a name="guest-access-reviews"></a>Verifiche di accesso per gli utenti guest

È possibile usare Azure AD per creare una verifica di accesso per i membri del gruppo o gli utenti assegnati a un'applicazione. La creazione di verifiche di accesso ricorrenti consente di risparmiare tempo. Se è necessario verificare abitualmente gli utenti che hanno accesso a un'applicazione, un team o sono membri di un gruppo, è possibile definire la frequenza di tali verifiche. 

È possibile eseguire la verifica dell'accesso guest, chiedere agli utenti guest di verificare l'appartenenza o rivolgersi al proprietario di un’applicazione o a un decisore aziendale per eseguire la verifica di accesso. Usare il portale di Azure per eseguire le verifiche di accesso degli utenti guest. Per altre informazioni, vedere [Gestire l'accesso guest con le verifiche di accesso di Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Argomenti correlati

[Collaborare con persone esterne all'organizzazione](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloccare gli utenti guest di un gruppo di Microsoft 365 specifico o di un team di Microsoft Teams](/microsoft-365/solutions/per-group-guest-access)

[Creare un ambiente di condivisione guest sicuro](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore](/microsoft-365/admin/contact-support-for-business-products)

[Configurare Teams con tre livelli di protezione](/microsoft-365/solutions/configure-teams-three-tiers-protection)
