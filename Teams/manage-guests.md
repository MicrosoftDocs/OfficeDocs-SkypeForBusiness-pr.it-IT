---
title: Gestire l'accesso guest in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Gli amministratori IT possono aggiungere ospiti a livello di tenant, impostare e gestire i criteri e le autorizzazioni degli utenti guest, determinare gli utenti che possono invitare gli ospiti e tirare i report sulle attività degli utenti guest.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7db3d42a8d4ae44364ee56f6c7f31ce501a34137
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37573169"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gestire l'accesso guest in Microsoft Teams
======================================

**Guest** è un tipo di utente/licenza in Microsoft teams incluso in tutti gli abbonamenti a Office 365 Business Premium, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Office 365. L'accesso Guest teams è un'impostazione a livello di tenant ed è disattivata per impostazione predefinita. Per informazioni dettagliate su come abilitare l'accesso guest, vedere [attivare o disattivare l'accesso Guest a Microsoft teams](set-up-guests.md).

Dopo aver attivato il tipo di utente/licenza **Guest** , è possibile configurare le impostazioni per gli utenti tramite i controlli descritti in [gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md) e [gestire i team durante la transizione ai nuovi Microsoft Teams ](manage-teams-skypeforbusiness-admin-center.md)interfaccia di amministrazione.     
    
Gli amministratori IT possono aggiungere ospiti a livello di tenant, impostare e gestire i criteri e le autorizzazioni degli utenti guest e tirare i report sulle attività degli utenti guest. Questi controlli sono disponibili nell'interfaccia di amministrazione di Microsoft teams. I contenuti e le attività degli utenti Guest sono sotto la stessa protezione di conformità e controllo del resto di Office 365.

I proprietari del team possono invitare nuovi ospiti e aggiungere utenti Guest Directory esistenti ai loro team. I proprietari del team possono identificare gli utenti guest tramite **Teams** > **Manage teams**e impostare le funzionalità relative ai canali per gli ospiti tramite**l'accesso Guest**per **le impostazioni** > a livello di organizzazione, incluso consentire agli ospiti di creare, aggiornare e eliminare i canali, come illustrato nella figura seguente.

![Impostazioni delle autorizzazioni guest in teams](media/manage-guest-access-image1.png)
  
È possibile usare il portale di Azure Active Directory (Azure AD) per gestire gli utenti e l'accesso alle risorse di Office 365 e teams. L'accesso Guest teams consente di usare le funzionalità di collaborazione di Azure AD business-to-business (B2B) come infrastruttura sottostante per archiviare le informazioni sui principi di sicurezza, ad esempio le proprietà delle identità, le appartenenze e le impostazioni di autenticazione a più fattori. Per altre informazioni su Azure AD B2B, vedere [cos'è la collaborazione tra Azure ad B2B](https://go.microsoft.com/fwlink/p/?linkid=853011) e le [domande frequenti su Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020)per la collaborazione B2B.

> [!NOTE]
> Microsoft teams sempre onora le impostazioni esterne di Azure ad per consentire o impedire l'aggiunta di utenti Guest al tenant. Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>Accesso guest e accesso esterno (Federazione)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>Rivedere periodicamente l'accesso Guest

In teams è possibile aggiungere 5 Guest per ogni utente con licenza. A causa di questa limitazione o perché si vuole mantenere aggiornato il tenant, è consigliabile rivedere periodicamente l'accesso guest per identificare gli utenti che non hanno più bisogno di accedere. Puoi usare Azure AD per creare una revisione di Access per i membri del gruppo o gli utenti assegnati a un'applicazione. La creazione di recensioni di Access periodiche consente di risparmiare tempo. Se è necessario rivedere abitualmente gli utenti che hanno accesso a un'applicazione o sono membri di un gruppo, è possibile definire la frequenza di tali revisioni. 

È possibile eseguire una revisione dell'accesso guest, chiedere agli ospiti di rivedere la propria appartenenza o chiedere a un proprietario dell'applicazione o a un decisore aziendale di eseguire la revisione di Access. Si usa il portale di Azure per eseguire le recensioni di accesso guest. Per altre informazioni, vedere [gestire l'accesso guest con le recensioni di Access di Azure ad](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites"></a>Prerequisiti

Le recensioni di Access sono disponibili con l'edizione Premium P2 di Azure AD, inclusa in Microsoft Enterprise Mobility + Security, E5. Per altre informazioni, Vedi [edizioni di Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis). Ogni utente che interagisce con questa funzionalità creando una recensione, compilando una recensione o confermando l'accesso, deve avere una licenza.

Teams non limita il numero di Guest che è possibile aggiungere. Il numero totale di utenti che possono essere aggiunti al tenant è tuttavia basato su ciò che consente la licenza di AAD. Per altre informazioni, Vedi [licenze di collaborazione B2B di Azure ad](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="guest-access-latencies"></a>Latenze di accesso Guest

Le impostazioni Guest sono impostate in Azure AD. Le modifiche possono essere effettive nell'organizzazione di Office 365 in 2 ore e 24 ore. Se un utente vede il messaggio "Contatta l'amministratore" quando prova ad aggiungere un Guest al proprio team, è probabile che la caratteristica Guest non sia stata abilitata o che le impostazioni non siano ancora valide.

## <a name="more-information"></a>Ulteriori informazioni

Per informazioni sull'uso di PowerShell per gestire l'accesso guest, vedere [usare PowerShell per controllare l'accesso Guest a un team](guest-access-powershell.md).


