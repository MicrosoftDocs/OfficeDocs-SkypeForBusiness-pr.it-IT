---
title: Elenco di controllo di accesso guest di Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Usare questo elenco di controllo per configurare l'accesso guest in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3354f7b503b2f1ea91c050a751b5d7d9ab0537a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962534"
---
<a name="microsoft-teams-guest-access-checklist"></a>Elenco di controllo di accesso guest di Microsoft Teams
==========================================

Usare questo elenco di controllo per attivare e configurare l'accesso guest in Microsoft teams. È necessario essere un amministratore globale o un amministratore di teams per apportare queste modifiche.

> [!IMPORTANT]
> Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto. 

Guardare questo breve video (5:31 minuti) per vedere come attivare l'accesso guest in tutto Microsoft 365, inclusi i team.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>Passaggio 1: attivare l'accesso Guest a livello di organizzazione Teams

Per attivare l'accesso guest, accedere all'interfaccia di **amministrazione di Microsoft teams**. 

1. Nell'interfaccia di amministrazione di teams selezionare**l'accesso Guest** **delle impostazioni** > a livello di organizzazione.
2. Impostare l'opzione **Consenti accesso guest in Microsoft teams** **su**attivato.

    ![Screenshot mostra un esempio di attivazione di impostazioni team](media/guest-access-checklist-set-up-guests-image1.png)

3. Nella stessa pagina attivare o disattivare le impostazioni di **chiamata**, **riunione**e **messaggistica** per gli utenti.
4. Fai clic su **Salva**.

> [!TIP]
> Se si usano le impostazioni predefinite in Azure Active Directory, SharePoint Online e Office 365 groups, è possibile che sia stata eseguita la configurazione dell'accesso guest. In questo caso, è possibile ignorare il resto della procedura. In caso di dubbi o se si usano impostazioni personalizzate per i gruppi AAD, SharePoint Online o Office 365, procedere con il resto della procedura descritta in questo elenco di controllo.


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>Passaggio 2: configurare le impostazioni di Azure AD business-to-business

1. Accedere a [Azure Portal](https://portal.azure.com) come amministratore del tenant.
2. Selezionare**** > **le impostazioni utente**di **Azure Active Directory** > Users.
3. In **utenti esterni**selezionare **Gestisci impostazioni di collaborazione esterna**.
   > [!NOTE]
   > Le **impostazioni di collaborazione esterna** sono disponibili anche nella pagina **relazioni organizzative** . In Azure Active Directory, in **Gestisci**, passa a > **Impostazioni** **relazioni organizzative**.
4. Nella pagina **impostazioni di collaborazione esterna** scegliere i criteri che si desidera abilitare.

    - Le **autorizzazioni degli utenti Guest sono limitate**: questo criterio determina le autorizzazioni per gli ospiti nella directory. Selezionare **Sì** per bloccare gli ospiti da determinate attività di directory, come l'enumerazione di utenti, gruppi o altre risorse di directory. Selezionare **No** per offrire agli ospiti lo stesso accesso ai dati della directory come utenti regolari nella directory.
     - Gli **amministratori e gli utenti del ruolo dell'invitato Guest possono invitare**: per consentire agli amministratori e agli utenti del ruolo "Guest invite" di invitare gli ospiti, impostare questo criterio su **Sì**.
     - **I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare gli ospiti, impostare questo criterio su **Sì**.

         > [!NOTE]
         > Se si impostano **membri può invitare** a **No** e quindi abilitare l'accesso guest nei gruppi di Office 365 e Microsoft teams, gli amministratori possono controllare gli inviti Guest nella directory. Dopo che gli ospiti si trovano nella directory, possono essere aggiunti ai team da membri non amministratori che sono proprietari del team. Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).
         > [!IMPORTANT]
         > Per il pieno funzionamento dell'accesso guest in Teams, è necessario impostare **I membri possono invitare** su **Sì**.   
     - **Gli ospiti possono invitare**: per consentire agli ospiti di invitare altri ospiti, impostare questo criterio su **Sì**.
         > [!IMPORTANT]
         > Al momento Teams non supporta il ruolo mittente dell'invito, pertanto se si imposta **I guest possono invitare** su **Sì**, gli utenti guest non possono invitare altri guest in Teams.
     - **Abilitare la password unica per gli utenti (anteprima)**: per altre informazioni sulla funzionalità di codice per la sola volta, vedere autenticazione di un codice di accesso unico per la [posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
     - **Limitazioni della collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a specifici domini, vedere [consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
        > [!NOTE]
        > Per le limitazioni della collaborazione, vedere [abilitare la collaborazione esterna B2B e gestire chi può invitare gli ospiti](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
 
    Per altre informazioni su come controllare chi può invitare guest, consultare [Delegare gli inviti per Collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).


## <a name="step-3-configure-office-365-groups"></a>Passaggio 3: configurare i gruppi di Office 365

1. Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > **Servizi & i componenti**aggiuntivi e quindi selezionare **gruppi di Office 365**.

     ![La schermata mostra i gruppi di Office 365](media/guest-access-checklist-office365.png)
2. Verificare che la casella di controllo **consente ai membri del gruppo all'esterno del contenuto dell'organizzazione di Access Group** sia selezionata. Se questa impostazione non è selezionata, gli utenti non saranno in grado di accedere a qualsiasi contenuto di gruppo.
3. Verificare che la casella **di controllo Let Group owners Add people outside the Organization to** groups sia selezionata. Se questa impostazione non è selezionata, i proprietari del team non saranno in grado di aggiungere nuovi Guest. Questa impostazione deve essere almeno attiva per supportare l'accesso guest.

Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [gestire l'accesso guest nei gruppi di office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controllare l'accesso guest nei gruppi di Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="step-4-configure-sharing-in-office-365"></a>Passaggio 4: configurare la condivisione in Office 365 

Assicurarsi che gli utenti possano aggiungere Guest. Ecco come:

1. Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > di**sicurezza & privacy**.

     ![Screenshot mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. In **condivisione**selezionare **modifica**.

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Impostare **consentire agli utenti di aggiungere nuovi Guest a questa organizzazione** e quindi fare clic **su** **Salva**.

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > Questa impostazione è equivalente ai **membri che possono invitare** l'impostazione in **Impostazioni** > utente**utenti esterni** in Azure ad.  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Passaggio 5: verificare l'impostazione di condivisione in SharePoint

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. In **centri di amministrazione**selezionare **SharePoint**.
3. Nella nuova interfaccia di amministrazione di SharePoint, in **siti**, selezionare **siti attivi**.

    ![Siti attivi nell'interfaccia di amministrazione di SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. Selezionare il sito e quindi fare clic su **condivisione**.
4. Verificare che l'opzione sia impostata su **tutti gli utenti** o **gli ospiti nuovi o esistenti**.
 
     ![Screenshot mostra un esempio di attivazione di impostazioni di SharePoint Online](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>Passaggio 6: configurare le autorizzazioni per gli utenti Guest

Nell'applicazione teams, a livello di team specifico, configura le autorizzazioni guest che controllano se gli utenti possono creare, aggiornare o eliminare canali. Gli amministratori dei team e i proprietari del team possono configurare queste impostazioni.

![Screenshot mostra un esempio di attivazione di impostazioni del team/canale](media/guest-access-checklist-TeamsSettings2.png)

Per ulteriori informazioni sull'accesso guest, vedere [accesso guest in teams](guest-access.md) e [attivare o disattivare l'accesso Guest a Microsoft teams](set-up-guests.md).


## <a name="troubleshooting"></a>Risoluzione dei problemi

In caso di problemi con l'impostazione dell'accesso guest o l'aggiunta di ospiti in teams, usare queste risorse per aiutarti:

[Risolvere i problemi relativi all'accesso guest in Microsoft Teams](troubleshoot-guest-access.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



