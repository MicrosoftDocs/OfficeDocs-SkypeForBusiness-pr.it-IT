---
title: Elenco di controllo di accesso guest di Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Usare questo elenco di controllo per configurare l'accesso guest in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8418c9386c635d1fc1662ee6df80dfae21908bd0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244440"
---
<a name="teams-guest-access-checklist"></a>Elenco di controllo di accesso Guest Teams
==========================================

Usare questo elenco di controllo per abilitare e configurare la caratteristica di accesso guest in Microsoft teams in base alle preferenze dell'organizzazione.

> [!NOTE] 
> Per le limitazioni della collaborazione [, vedere Abilitare la collaborazione esterna B2B e gestire chi può invitare Guest](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="understand-the-limitations-for-guests"></a>Informazioni sulle limitazioni per gli utenti

L'esperienza Guest ha limitazioni per progettazione. Assicurarsi di comprendere l'esperienza Guest in modo che non si tenti di risolvere un problema. Ecco, ad esempio, un elenco di alcune delle funzionalità che non sono disponibili per un guest in Microsoft teams:

- OneDrive for business
- Ricerca utenti esterni a teams
- Calendario, riunioni pianificate o dettagli riunione
- PSTN
- Organigramma
- Creare o modificare un team
- Cercare un team
- Caricare file in una chat utente
- Gli utenti possono continuare a cercare e trovare un utente (al di fuori del proprio team) se conoscono l'ID della posta elettronica completa. Per evitare questo problema, gli amministratori possono usare modelli come la [ricerca di directory con ambito](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) che hanno la possibilità di limitare gli ospiti al proprio GAL virtuale.

Per altri dettagli, vedere [l'esperienza Guest](guest-experience.md) e l' [accesso guest nei gruppi di Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

### <a name="guest-access-vs-external-access-federation"></a>Accesso guest e accesso esterno (Federazione)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> Attualmente Microsoft teams non supporta il ruolo di invitato Guest. Almeno l'opzione "i membri possono invitare" deve essere impostata su "Sì" per consentire l'accesso Guest al lavoro in Microsoft teams. Se si imposta "i membri possono invitare" a "No" e quindi abilitare l'accesso guest nei gruppi di Office 365 e Microsoft teams, gli amministratori possono controllare gli inviti Guest nella directory. Dopo che gli ospiti si trovano nella directory, possono essere aggiunti ai team da membri non amministratori che sono proprietari del team.

## <a name="if-your-guests-are-seeing-license-errors"></a>Se i clienti vedono gli errori di licenza

L'accesso guest in Microsoft teams USA Azure Active Directory (Azure AD) business to business (B2B) e il relativo modello di licenza. Se si verificano errori di licenza, leggere le istruzioni per la gestione delle licenze [B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) per comprendere i requisiti di licenza dell'organizzazione in modo che gli utenti siano in grado di invitare gli ospiti alla propria organizzazione.

Alcuni aspetti da ricordare:

- Gli ospiti sono utenti esterni all'organizzazione. I dipendenti, gli appaltatori onsite, gli agenti onsite e così via non possono essere aggiunti come Guest. Lo stesso vale per gli affiliati.
- Le licenze Guest vengono conteggiate con l'organizzazione invitante. Considerate questa operazione quando si calcola il numero di licenze necessarie.
- Le licenze vengono conteggiate in base all'organizzazione se gli ospiti invitati provengono da un altro tenant di Office 365 o usano gli indirizzi di posta elettronica personali.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Passaggio 1: configurare le impostazioni in Azure AD business-to-business

1. Accedere a [Azure Portal](https://portal.azure.com) come amministratore del tenant.
2. Selezionare**** > **le impostazioni utente**di **Azure Active Directory** > Users.
3. In **utenti esterni**selezionare **Gestisci impostazioni di collaborazione esterna**.
   > [!NOTE]
   > Le **impostazioni di collaborazione esterna** sono disponibili anche nella pagina **relazioni organizzative** . In Azure Active Directory, in **Gestisci**, passa a**Impostazioni** **relazioni** > organizzative.
4. Nella pagina **impostazioni di collaborazione esterna** scegliere i criteri che si desidera abilitare.

  - Le **autorizzazioni degli utenti Guest sono limitate**: questo criterio determina le autorizzazioni per gli ospiti nella directory. Selezionare **Sì** per bloccare gli ospiti da determinate attività di directory, come l'enumerazione di utenti, gruppi o altre risorse di directory. Selezionare **No** per offrire agli ospiti lo stesso accesso ai dati della directory come utenti regolari nella directory.
   - Gli **amministratori e gli utenti del ruolo dell'invitato Guest possono invitare**: per consentire agli amministratori e agli utenti del ruolo "Guest invite" di invitare gli ospiti, impostare questo criterio su **Sì**.
   - **I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare gli ospiti, impostare questo criterio su **Sì**.
   
       > [!NOTE]
       > Se si impostano **membri può invitare** a **No** e quindi abilitare l'accesso guest nei gruppi di Office 365 e Microsoft teams, gli amministratori possono controllare gli inviti Guest nella directory. Dopo che gli ospiti si trovano nella directory, possono essere aggiunti ai team da membri non amministratori che sono proprietari del team. Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).
   
   - **Gli ospiti possono invitare**: per consentire agli ospiti di invitare altri ospiti, impostare questo criterio su **Sì**.
   - **Abilitare la password unica per gli utenti (anteprima)**: per altre informazioni sulla funzionalità di codice per la sola volta, vedere autenticazione di un codice di accesso unico per la [posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
   - **Limitazioni della collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a specifici domini, vedere [consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="-step-2-configure-office-365-groups"></a>□ Passaggio 2: configurare i gruppi di Office 365

1. Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > **Servizi &** > gruppi di componenti aggiuntivi di**Office 365**.
2. Assicurarsi che **i membri del gruppo al di fuori del contenuto del gruppo di Access dell'organizzazione** siano impostati **su**attivato. Se questa impostazione è disattivata, gli utenti non saranno in grado di accedere a qualsiasi contenuto di gruppo.
3. Assicurarsi che **i proprietari del gruppo aggiungano persone all'esterno dell'organizzazione a gruppi** sia impostato **su**attivato. Se questa impostazione è disattivata, i proprietari del team non saranno in grado di aggiungere nuovi Guest. Questa impostazione deve essere almeno attiva per supportare l'accesso guest.

     ![La schermata mostra i gruppi di Office 365](media/guest-access-checklist-office365.png)

Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [gestire l'accesso guest nei gruppi di office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controllare l'accesso guest nei gruppi di Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Passaggio 3: abilitare l'accesso Guest a livello di tenant

È necessario attivare l'accesso guest per Microsoft teams sotto l'interfaccia di **amministrazione di Microsoft teams**. 

1. Nell'interfaccia di amministrazione di teams selezionare**l'accesso Guest** **delle impostazioni** > a livello di organizzazione.
2. Impostare l'opzione **Consenti accesso guest in Microsoft** teams **su**attivato.

    ![Screenshot mostra un esempio di attivazione di impostazioni team](media/guest-access-checklist-set-up-guests-image1.png)

3. Nella stessa pagina Configurare le altre impostazioni Guest necessarie.
4. Fai clic su **Salva**.

Per istruzioni dettagliate, vedere [attivare o disattivare l'accesso Guest a Microsoft teams](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Passaggio 4: configurare la condivisione in Office 365 

Assicurarsi che gli utenti possano aggiungere Guest. Ecco come:

1. Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > di**sicurezza & privacy**.

     ![Screenshot mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. In **condivisione**selezionare **modifica**.

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Impostare **consentire agli utenti di aggiungere nuovi Guest a questa organizzazione** e quindi fare clic **su** **Salva**.

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Questa impostazione è equivalente ai **membri che possono invitare** l'impostazione in **Impostazioni** > utente**utenti esterni** in Azure ad.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Passaggio 5: verificare l'impostazione di condivisione in SharePoint

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Fare clic su interfaccia di **Amministrazione**e quindi selezionare **SharePoint**.
3. Nell'interfaccia di amministrazione di SharePoint selezionare **condivisione**.
4. Verificare che l'opzione **non consentire la condivisione all'esterno** dell'organizzazione *non* sia selezionata.
 
     ![La schermata mostra un esempio di attivazione di impostazioni online di SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Passaggio 6: abilitare impostazioni specifiche per i canali 

Nell'applicazione teams, a livello di team specifico, configura le autorizzazioni guest in modo che gli utenti possano creare, aggiornare ed eliminare canali. Oltre agli amministratori, i proprietari del team possono configurare questa impostazione.

![Screenshot mostra un esempio di attivazione di impostazioni del team/canale](media/guest-access-checklist-TeamsSettings2.png)

Per altre informazioni, inclusi i video di How-to, vedere [accesso guest in Microsoft teams](guest-access.md).


## <a name="troubleshooting"></a>Risoluzione dei problemi

In caso di problemi con l'aggiunta di Guest in Microsoft teams, vedere la [Guida alla risoluzione dei problemi relativi a Access](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


