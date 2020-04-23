---
title: Configurare la connettività ibrida | Distribuire Skype for Business Server 2019 Connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per l'implementazione della connettività ibrida tra Skype for Business Server e Skype for business online.
ms.openlocfilehash: 0c4b2f716e906e30dd45b2750cfe5487868ce6df
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780095"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurare la connettività ibrida tra Skype for Business Server e Office 365

**Riepilogo:** Leggere questo argomento per informazioni su come configurare la connettività ibrida tra Skype for Business Server e teams o Skype for business online.  La connettività ibrida consente di spostare gli utenti locali in team o in Skype for business online e consente agli utenti di usufruire dei servizi cloud.
  
Prima di eseguire la procedura descritta in questo argomento, è consigliabile leggere [pianificare la connettività ibrida tra Skype for Business Server e Office 365](plan-hybrid-connectivity.md).
  
Nella tabella seguente sono elencate le attività necessarie per configurare la connettività ibrida di Skype for business e vengono forniti collegamenti agli articoli associati per ulteriori informazioni.
  
|Passaggio|Descrizione|
|:-----|:-----|
|Creare un account tenant per Office 365   <br/> |Informazioni su Office 365 in [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Per assicurarsi che l'ambiente sia pronto per Office 365, vedere i [requisiti di sistema](https://products.office.com/office-system-requirements).  <br/> Per informazioni dettagliate sulla configurazione di Office 365, vedere [Guida introduttiva a office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Aggiungere il proprio dominio all'organizzazione di Office 365 e verificare la proprietà  <br/> | È necessario aggiungere il proprio dominio all'organizzazione di Office 365, quindi seguire la procedura per convalidare il dominio con Office 365. In questo modo si conferma che si è il proprietario del dominio. <br/> Per aggiungere il dominio alla propria organizzazione di Office 365, attenersi alla procedura descritta in [aggiungere un dominio a office 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurare la sincronizzazione di Active Directory  <br/> |La sincronizzazione di Active Directory mantiene continuamente sincronizzata la propria Active Directory locale con Office 365. In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo.  <br/> <br> **Importante:** È necessario sincronizzare gli account di Active Directory per tutti gli utenti di Skype for business nell'organizzazione tra le distribuzioni locali e online, anche se gli utenti non vengono spostati in un team o in Skype for business online. Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e quelli online nell'organizzazione potrebbe non funzionare come previsto. Per ulteriori informazioni, vedere [Configure Azure ad Connect for Hybrid environments](configure-azure-ad-connect.md).         |
| Configurare Skype for Business ibrido | Questa procedura prevede tre passaggi di base: <br><br> 1. configurare l'ambiente locale per la Federazione con Office 365. <br> 2. configurare l'ambiente locale in modo che consideri attendibile Office 365 e che sia abilitato lo spazio degli indirizzi SIP condiviso con Office 365.<br> 3. abilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione di Office 365. <br><br> Inoltre, se si dispone di Exchange locale, è consigliabile configurare OAuth tra gli ambienti Exchange locali e Skype for Business Online. <br> <br>Per ulteriori informazioni, vedere [Configure Skype for business Hybrid](configure-federation-with-skype-for-business-online.md).
|Spostare gli utenti pilota  <br/> |Dopo aver completato la procedura per preparare e configurare l'ambiente per i team o per Skype for business online, è possibile avviare lo spostamento degli utenti pilota nell'organizzazione di Office 365 online. Per ulteriori informazioni, vedere [spostare gli utenti da locale a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md) e [spostare gli utenti da locale a teams](move-users-from-on-premises-to-Teams.md).  <br/> |