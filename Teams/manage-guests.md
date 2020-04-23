---
title: Gestire l'accesso guest in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come creare i primi team e i nuovi canali, a bordo dei primi adottanti, monitorare l'uso e il feedback e ottenere risorse per pianificare l'implementazione a livello di organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 544dcb4ffd424512797d3791e2eda6b22439c084
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777841"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gestire l'accesso guest in Microsoft Teams
======================================

> [!IMPORTANT]
> Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive. 

**Guest** è un tipo di utente in Microsoft teams incluso in tutti gli abbonamenti a Microsoft 365 business standard, Office 365 Enterprise, Microsoft 365 Business Basic e Office 365 Education. Non sono necessarie altre licenze di Office 365. Leggi altre informazioni sulla [gestione delle licenze di accesso Guest](#guest-access-licensing-limits) di seguito.

L'accesso Guest teams è un'impostazione a livello di tenant ed è disattivata per impostazione predefinita. Per informazioni dettagliate su come attivare l'accesso guest, vedere [attivare o disattivare l'accesso Guest ai team](set-up-guests.md)oppure usare l'elenco di [controllo di accesso Guest](guest-access-checklist.md) per passare alla configurazione.

Dopo che l'accesso Guest è attivato, è possibile configurare le impostazioni per gli utenti che usano i controlli descritti in [gestire le impostazioni dei team per l'organizzazione](enable-features-office-365.md) e [gestire i team durante la transizione al nuovo centro di amministrazione di Microsoft teams](manage-teams-skypeforbusiness-admin-center.md).     
    
Gli amministratori IT possono aggiungere ospiti a livello di tenant, impostare e gestire i criteri e le autorizzazioni degli utenti guest e tirare i report sulle attività degli utenti guest. Questi controlli sono disponibili nell'interfaccia di amministrazione di teams. I contenuti e le attività degli utenti Guest rientrano nella stessa protezione di conformità e controllo del resto di Office 365.

I proprietari del team possono invitare nuovi ospiti e aggiungere utenti Guest Directory esistenti ai loro team nell'interfaccia di amministrazione di teams. Identificare gli utenti guest nella **pagina teams** > **Manage teams** e impostare le funzionalità relative ai canali per gli ospiti nella pagina di**accesso Guest** **delle impostazioni** > a livello di organizzazione. Le impostazioni includono consentire agli utenti di creare, aggiornare ed eliminare canali, come illustrato nella figura seguente.

![Impostazioni delle autorizzazioni guest in teams](media/manage-guest-access-image1.png)
  
È possibile usare il portale di Azure Active Directory (Azure AD) per gestire gli utenti e l'accesso alle risorse di Office 365 e teams. L'accesso Guest teams consente di usare le funzionalità di collaborazione di Azure AD business-to-business (B2B) come infrastruttura sottostante per archiviare le informazioni sui principi di sicurezza, ad esempio le proprietà delle identità, le appartenenze e le impostazioni di autenticazione a più fattori. Per altre informazioni su Azure AD B2B, vedere [cos'è la collaborazione tra Azure ad B2B](https://go.microsoft.com/fwlink/p/?linkid=853011) e le [domande frequenti su Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020)per la collaborazione B2B.

> [!NOTE]
> Microsoft teams sempre onora le impostazioni esterne di Azure ad per consentire o impedire l'aggiunta di utenti Guest al tenant. Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).


## <a name="guest-access-licensing-limits"></a>Limiti delle licenze di accesso Guest

Teams non impone un numero limite di utenti guest che è possibile aggiungere. Tuttavia, il numero totale di utenti guest che possono essere aggiunti al tenant dipende dal limite imposto dalla licenza di Azure AD, che in genere è di 5 guest per ogni utente con licenza. Per altre informazioni, vedere [Licenze di collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

A causa di queste limitazioni della licenza (e per mantenere aggiornato il tenant), è consigliabile rivedere periodicamente l'accesso guest per identificare gli utenti che non hanno più bisogno di accedere. Puoi usare Azure AD per creare una revisione di Access per i membri del gruppo o gli utenti assegnati a un'applicazione. La creazione di recensioni di Access periodiche consente di risparmiare tempo. Se è necessario rivedere abitualmente gli utenti che hanno accesso a un'applicazione o sono membri di un gruppo, è possibile definire la frequenza di tali revisioni. 

È possibile eseguire una revisione dell'accesso guest, chiedere agli ospiti di rivedere la propria appartenenza o chiedere a un proprietario dell'applicazione o a un decisore aziendale di eseguire la revisione di Access. Usare il portale di Azure per eseguire le recensioni di accesso guest. Per altre informazioni, vedere [gestire l'accesso guest con le recensioni di Access di Azure ad](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Prerequisiti per le recensioni di Access di Azure AD

Le recensioni di Access sono disponibili con l'edizione Premium P2 di Azure AD, inclusa in Microsoft Enterprise Mobility + Security, E5. Per altre informazioni, Vedi [edizioni di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis). Ogni utente che interagisce con questa funzionalità creando una recensione, compilando una recensione o confermando l'accesso, deve avere una licenza.



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>Tempo di ritardo per l'effetto delle impostazioni di accesso Guest

Per le impostazioni di accesso guest in Azure Active Directory, sono necessarie 2-24 ore affinché le modifiche abbiano effetto su Microsoft 365 o Office 365. Se un utente vede il messaggio "Contatta l'amministratore" quando prova ad aggiungere un Guest al proprio team, è probabile che la caratteristica Guest non sia stata attivata o che le impostazioni non siano ancora valide. Per informazioni sui problemi di configurazione dell'accesso guest, leggere [risolvere i problemi di accesso guest in teams](troubleshoot-guest-access.md).

  
## <a name="external-access-federation-vs-guest-access"></a>Accesso esterno (federazione) e accesso guest

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Altre informazioni

Per informazioni sull'uso di PowerShell per gestire l'accesso guest, vedere [usare PowerShell per controllare l'accesso Guest a un team](guest-access-powershell.md).


